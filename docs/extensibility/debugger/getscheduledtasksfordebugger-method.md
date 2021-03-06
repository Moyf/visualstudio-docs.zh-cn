---
title: GetScheduledTasksForDebugger 方法 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- GetScheduledTasksForDebugger method, TaskScheduler class [.NET Framework debug engines]
ms.assetid: 7c9b4cde-6e4a-4cef-929f-7d02b1da5762
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
ms.openlocfilehash: 318e535d86dcd51f9c9bbfcfae8e228c8d7c20b4
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2021
ms.locfileid: "99921352"
---
# <a name="getscheduledtasksfordebugger-method"></a>GetScheduledTasksForDebugger 方法
检索所有计划任务的数组。

 **命名空间：** <xref:System.Threading.Tasks?displayProperty=fullName>

 **Assembly：** mscorlib (*mscorlib.dll*) 

 由于无法从 .NET Framework 访问此内部成员，因此在公共中间语言 (CIL) 中提供了以下语法。

## <a name="syntax"></a>语法

```csharp
.method assembly hidebysig instance class System.Threading.Tasks.Task[] GetScheduledTasksForDebugger() cil managed
```

## <a name="return-value"></a>返回值
 所有计划任务的数组。 每个任务正在执行或已完成执行。

## <a name="remarks"></a>备注
 此方法不是线程安全的，不应同时与的其他实例一起使用 <xref:System.Threading.Tasks.TaskScheduler> 。 仅当调试器挂起了所有其他线程时，才从调试器调用此方法。

## <a name="see-also"></a>另请参阅
- [TaskScheduler 类](../../extensibility/debugger/taskscheduler-class-internal-members.md)
