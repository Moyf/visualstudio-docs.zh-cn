---
title: IDebugAlias2 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugAlias2 interface
ms.assetid: 5252dcbb-8bfe-4d8a-a8e5-b022b194df19
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
ms.openlocfilehash: 171e9da3b25aa33ad3921f4ec5f841429490be72
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2021
ms.locfileid: "99944610"
---
# <a name="idebugalias2"></a>IDebugAlias2
> [!IMPORTANT]
> 在 Visual Studio 2015 中，不推荐使用这种实现表达式计算器的方式。 有关实现 CLR 表达式计算器的信息，请参阅 [Clr 表达式计算器](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 和 [托管表达式计算器示例](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)。

 表示变量的数字别名，并使表达式计算器 (EE) 获取别名的应用程序域。

## <a name="syntax"></a>语法

```
IDebugAlias2 : IDebugAlias
```

## <a name="notes-for-implementers"></a>实施者注意事项
 此接口由托管调试引擎实现 (DE) 。

## <a name="methods"></a>方法
 除了 [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md) 接口上的方法，此接口还实现以下方法：

|方法|说明|
|------------|-----------------|
|[GetAppDomainId](../../../extensibility/debugger/reference/idebugalias2-getappdomainid.md)|检索应用程序域的标识符。|

## <a name="remarks"></a>备注
 别名是字符串形式的十进制数，后跟 # 字符，例如 1001 #。

## <a name="requirements"></a>要求
 标头： Ee。h

 命名空间： VisualStudio

 程序集： Microsoft.VisualStudio.Debugger.Interop.dll
