---
title: IDebugPortSupplierEx2 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugPortSupplierEx2 interface
ms.assetid: dae0050a-a50a-4f35-bfbd-e538f537b20f
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
ms.openlocfilehash: a9a0958614c8df326c20ad8030bb798447a5e62a
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2021
ms.locfileid: "99840153"
---
# <a name="idebugportsupplierex2"></a>IDebugPortSupplierEx2
提供对端口提供程序的支持，以便选择核心服务器并与之进行交互。

## <a name="syntax"></a>语法

```
IDebugPortSupplierEx2 : IUnknown
```

## <a name="notes-for-implementers"></a>实施者注意事项
 自定义端口供应商实现此接口，以便可以选择要使用的核心服务器。

## <a name="methods"></a>方法
 下表显示了 **IDebugPortSupplierEx2** 的方法。

|方法|说明|
|------------|-----------------|
|[SetServer](../../../extensibility/debugger/reference/idebugportsupplierex2-setserver.md)|为端口供应商设置核心服务器。|

## <a name="requirements"></a>要求
 标头： Portpriv

 命名空间： VisualStudio

 程序集： Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>另请参阅
- [核心接口](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)
- [IDebugPortSupplier3](../../../extensibility/debugger/reference/idebugportsupplier3.md)
