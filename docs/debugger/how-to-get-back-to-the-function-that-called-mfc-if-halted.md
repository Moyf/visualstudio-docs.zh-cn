---
title: 返回到在中断时调用了 MFC 的函数 | Microsoft Docs
description: 了解如何在 Visual Studio 调试器中执行停止时返回到调用了 MFC 的函数。
ms.custom: SEO-VS-2020, seodec18
ms.date: 11/04/2016
ms.topic: how-to
f1_keywords:
- vs.debug.mfc
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- functions [C++], debugging
- function calls, returning to calling function
- debugging [MFC], returning to calling function
- debugging [MFC], functions
- Break command
- programs, halting
- functions [debugger]
ms.assetid: d254a5a9-afbd-4923-9d7a-7422d824cabf
author: mikejo5000
ms.author: mikejo
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: a0b3849653161278dc0f6e9e06a1baca2e8b6e62
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2021
ms.locfileid: "99904250"
---
# <a name="how-to-get-back-to-the-function-that-called-mfc-if-halted"></a>如何：返回到在中断时调用了 MFC 的函数

> [!NOTE]
> 显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[重置设置](../ide/environment-settings.md#reset-settings)。

如果你使用了“调试”菜单上的“中断”命令来暂停程序，结果结束在 MFC 上，而且你可以确认问题在代码中，则可以使用“调用堆栈”窗口来向后定位到函数 。 有关详细信息，请参阅[如何：使用“调用堆栈”窗口](../debugger/how-to-use-the-call-stack-window.md)。

有时，代码可能在消息泵中中断。 在这种情况下，调用堆栈中没有用户代码。 若要避免此问题，可以使用断点（也许加上条件和命中次数）而非“中断”命令。 有关详细信息，请参阅 [Breakpoints and Tracepoints](/previous-versions/ktf38f66(v=vs.100))。

## <a name="navigate-to-the-function-from-which-mfc-was-called"></a>导航到从中调用了 MFC 的函数

- 使用“调用堆栈”窗口。

## <a name="see-also"></a>请参阅

- [调试本机代码常见问题解答](../debugger/debugging-native-code-faqs.md)
- [调试本机代码](../debugger/debugging-native-code.md)