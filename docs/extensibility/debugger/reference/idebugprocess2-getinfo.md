---
title: IDebugProcess2：： GetInfo |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProcess2::GetInfo
helpviewer_keywords:
- IDebugProcess2::GetInfo
ms.assetid: 46021dce-bb97-46c3-b0cc-e5b3b68acc35
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: cf4b8d933729c95eaffa3a0caa44961bb5c87baa
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2021
ms.locfileid: "99894915"
---
# <a name="idebugprocess2getinfo"></a>IDebugProcess2::GetInfo
获取进程的说明。

## <a name="syntax"></a>语法

```cpp
HRESULT GetInfo(
   PROCESS_INFO_FIELDS  Fields,
   PROCESS_INFO*        pProcessInfo
);
```

```csharp
int GetInfo(
   enum_PROCESS_INFO_FIELDS  Fields,
   PROCESS_INFO[]            pProcessInfo
);
```

## <a name="parameters"></a>parameters
`Fields`\
中 [PROCESS_INFO_FIELDS](../../../extensibility/debugger/reference/process-info-fields.md) 枚举中的值的组合，用于指定 `pProcessInfo` 要填充参数的哪些字段。

`pProcessInfo`\
弄一个 [PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md) 结构，其中填充了进程的说明。

## <a name="return-value"></a>返回值
 如果成功， `S_OK` 则返回; 否则返回错误代码。

## <a name="see-also"></a>另请参阅
- [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)
- [PROCESS_INFO_FIELDS](../../../extensibility/debugger/reference/process-info-fields.md)
- [PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md)
