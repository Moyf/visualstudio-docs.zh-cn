---
title: 为代码提供自动化 |Microsoft Docs
description: 了解如何实现代码模型，这需要实现由您的内部数据结构确定的接口。
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- CodeModel object
ms.assetid: 21cb3e63-f25c-404b-bc1d-a32ad0fdd4d5
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
ms.openlocfilehash: 41dca5d7a3d2a95ae9b89feb73fb7655b8923eb6
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2021
ms.locfileid: "99837211"
---
# <a name="providing-automation-for-code"></a>提供适用于 Code 的自动化
不需要为代码创建自动化模型。 环境 SDK 并不提供用于执行此操作的示例。 若要深入了解代码模型，请参阅 <xref:EnvDTE.CodeModel> 对象。

 若要实现代码模型，必须实现由您的内部数据结构确定的任何接口。 对象必须派生自 `IDispatch` 类。

 您扩展的对象、 <xref:EnvDTE.CodeModel> 和可以 <xref:EnvDTE.FileCodeModel> 从对象获取，如下所 <xref:EnvDTE.Project> 示：

- <xref:EnvDTE.Project.CodeModel%2A>

- <xref:EnvDTE.ProjectItem.FileCodeModel%2A>

 您可以选择只在 `CodeModel` `FileCodeModel` 从和对象返回的对象中实现或接口 `Project` <xref:EnvDTE.ProjectItem> 。 提供此接口中适用于你的项目系统的任何功能。

 如果要添加标准和接口中不可用的功能（如方法或属性） `CodeModel` `FileCodeModel` ，请创建从标准继承的你自己的接口。 请确保将它与您的项目系统一起记录起来，以便最终用户能够找到它。 返回标准接口，但用户可以调用 `QueryInterface` 方法或强制转换为接口（如果已知存在）。

## <a name="see-also"></a>另请参阅
- [自动化模型概述](../../extensibility/internals/automation-model-overview.md)
