---
title: IDebugComPlusSymbolProvider::GetAttributedClassesForLanguage
titleSuffix: ''
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- GetAttributedClassesForLanguage
- IDebugComPlusSymbolProvider::GetAttributedClassesForLanguage
ms.assetid: e5b1b8b6-52a6-4ade-9a36-644abfa9f4b2
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: d2e9c5b6738d328c92393f2f7487b980de3e50cb
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2021
ms.locfileid: "99892926"
---
# <a name="idebugcomplussymbolprovidergetattributedclassesforlanguage"></a>IDebugComPlusSymbolProvider::GetAttributedClassesForLanguage
检索具有指定的特性（在指定的编程语言中实现）的类。

## <a name="syntax"></a>语法

```cpp
HRESULT GetAttributedClassesForLanguage (
    GUID               guidLanguage,
    LPOLESTR           pstrAttribute,
    IEnumDebugFields** ppEnum
);
```

```csharp
int GetAttributedClassesForLanguage (
    Guid                 guidLanguage,
    string               pstrAttribute,
    out IEnumDebugFields ppEnum
);
```

## <a name="parameters"></a>parameters
`guidLanguage`\
中语言的唯一标识符。

`pstrAttribute`\
中特性字符串。

`ppEnum`\
弄返回特性类的枚举。

## <a name="return-value"></a>返回值
如果成功， `S_OK` 则返回; 否则返回错误代码。

## <a name="example"></a>示例
下面的示例演示如何为公开 [IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md)接口的 **CDebugSymbolProvider** 对象实现此方法。

```cpp
HRESULT CDebugSymbolProvider::GetAttributedClassesForLanguage(
    GUID guidLanguage,
    __in_z LPOLESTR pstrAttribute,
    IEnumDebugFields** ppEnum
)
{
    HRESULT hr = S_OK;
    CFieldList listFields;
    CModIter ModIter;
    CModule* pModule; // the iterator owns the reference
    ULONG cClasses = 0;
    DWORD iTypeDef = 0;
    mdTypeDef* rgTypeDefs = NULL;
    IDebugField** rgFields = NULL;
    DWORD ctField = 0;
    CEnumDebugFields* pEnumFields = NULL;

    ASSERT(IsValidObjectPtr(this, CDebugSymbolProvider));
    ASSERT(IsValidWritePtr(ppEnum, IEnumDebugFields*));

    METHOD_ENTRY( CDebugSymbolProvider::GetAttributedClassesForLanguage );

    IfFalseGo( ppEnum, E_INVALIDARG );
    *ppEnum = NULL;

    // For Each Module - call EnumFields
    IfFailGo( GetModuleIter(&ModIter) );

    // Find the Max number of classes
    while (ModIter.GetNext(&pModule))
    {
        CComPtr<IMetaDataImport> pMetaData;
        HCORENUM hEnum = 0;
        ULONG cTypeDefs;
        ULONG cEnum;

        pModule->GetMetaData( &pMetaData );

        IfFailGo( pMetaData->EnumTypeDefs( &hEnum,
                                           NULL,
                                           0,
                                           &cTypeDefs ) );
        IfFailGo( pMetaData->CountEnum( hEnum, &cEnum ) );
        cClasses += cEnum;
    }

    IfNullGo( rgTypeDefs = new mdTypeDef[cClasses], E_OUTOFMEMORY );
    IfNullGo( rgFields = new IDebugField * [cClasses], E_OUTOFMEMORY );

    ModIter.Reset();

    // Create the classes
    while (ModIter.GetNext(&pModule))
    {
        CComPtr<IMetaDataImport> pMetaData;
        HCORENUM hEnum = 0;
        ULONG cTypeDefs;
        ULONG cEnum;
        const void* pUnused;
        ULONG cbUnused;

        pModule->GetMetaData( &pMetaData );

        IfFailGo( pMetaData->EnumTypeDefs( &hEnum,
                                           NULL,
                                           0,
                                           &cTypeDefs ) );
        IfFailGo( pMetaData->CountEnum( hEnum, &cEnum ) );
        IfFailGo( pMetaData->EnumTypeDefs( &hEnum,
                                           rgTypeDefs,
                                           cEnum,
                                           &cTypeDefs ) );

        pMetaData->CloseEnum(hEnum);
        hEnum = NULL;

        for ( iTypeDef = 0; iTypeDef < cTypeDefs; iTypeDef++)
        {

            if (pMetaData->GetCustomAttributeByName( rgTypeDefs[iTypeDef],
                    pstrAttribute,
                    &pUnused,
                    &cbUnused ) == S_OK)
            {
                // Only return classes implemeted in the correct language

                if (pModule->ClassImplementedInLanguage( rgTypeDefs[iTypeDef],
                        guidLanguage) )
                {
                    if (CreateClassType( pModule->GetID(),
                                         rgTypeDefs[iTypeDef],
                                         rgFields + ctField) == S_OK)
                    {
                        ctField++;
                    }
                    else
                    {
                        ASSERT(!"Failed to Create Attributed Class");
                    }
                }
            }
        }
    }

    IfNullGo( pEnumFields = new CEnumDebugFields, E_OUTOFMEMORY );
    IfFailGo( pEnumFields->Initialize(rgFields, ctField) );
    IfFailGo( pEnumFields->QueryInterface( __uuidof(IEnumDebugFields),
                                           (void**) ppEnum ) );

Error:

    METHOD_EXIT( CDebugSymbolProvider::GetAttributedClassesForLanguage, hr );

    DELETERG( rgTypeDefs );

    for ( iTypeDef = 0; iTypeDef < ctField; iTypeDef++)
    {
        RELEASE( rgFields[iTypeDef] );
    }

    DELETERG( rgFields );
    RELEASE( pEnumFields );

    return hr;
}
```

## <a name="see-also"></a>另请参阅
- [IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md)
