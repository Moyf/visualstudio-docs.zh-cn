---
title: IPropertyProxyEESide |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IPropertyProxyEESide
helpviewer_keywords:
- IPropertyProxyEESide interface
ms.assetid: cf227cf8-39d9-4758-8f7e-a697aebb1926
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
ms.openlocfilehash: f0331365716c8399c1b2a565fc8046482df5d80f
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2021
ms.locfileid: "99938897"
---
# <a name="ipropertyproxyeeside"></a>IPropertyProxyEESide
此接口提供在关联的对象上查看数据的方法。 此接口是对类型可视化工具的支持的一部分。

## <a name="syntax"></a>语法

```
IPropertyProxyEESide : IUnknown
```

## <a name="notes-for-implementers"></a>实施者注意事项
 表达式计算器实现此接口以支持类型可视化工具。

## <a name="notes-for-callers"></a>调用方说明
 调用 [GetPropertyProxy](../../../extensibility/debugger/reference/ipropertyproxyprovider-getpropertyproxy.md) 以获取此接口。 在[IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)接口上调用[QueryInterface](/cpp/atl/queryinterface)以获取[IPropertyProxyProvider](../../../extensibility/debugger/reference/ipropertyproxyprovider.md)接口。

## <a name="methods-in-vtable-order"></a>Vtable 顺序的方法
 此接口实现以下方法：

|方法|说明|
|------------|-----------------|
|[InitSourceDataProvider](../../../extensibility/debugger/reference/ipropertyproxyeeside-initsourcedataprovider.md)|初始化数据源提供程序，以便可以访问该对象的数据。|
|[GetManagedViewerCreationData](../../../extensibility/debugger/reference/ipropertyproxyeeside-getmanagedviewercreationdata.md)|检索有关对象的程序集的信息。|
|[GetInitialData](../../../extensibility/debugger/reference/ipropertyproxyeeside-getinitialdata.md)|获取对象的初始数据。|
|[CreateReplacementObject](../../../extensibility/debugger/reference/ipropertyproxyeeside-createreplacementobject.md)|创建现有数据存储的副本。|
|[InPlaceUpdateObject](../../../extensibility/debugger/reference/ipropertyproxyeeside-inplaceupdateobject.md)|创建对现有数据存储区的引用。|
|[ResolveAssemblyRef](../../../extensibility/debugger/reference/ipropertyproxyeeside-resolveassemblyref.md)|在包含此对象的程序集的上下文中检索有关特定程序集的信息。|

## <a name="remarks"></a>备注
 类型可视化工具使用此接口来访问与此接口所属的对象相关联的值。 通过 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) 接口访问数据，该接口提供数据的只读视图。

## <a name="requirements"></a>要求
 标头： msdbg

 命名空间： VisualStudio

 程序集： Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>另请参阅
- [核心接口](../../../extensibility/debugger/reference/core-interfaces.md)
- [类型可视化工具和自定义查看器](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md)
- [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)
- [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)
