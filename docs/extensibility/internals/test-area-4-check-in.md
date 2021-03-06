---
title: 测试区域4：签入 |Microsoft Docs
description: 此源代码管理插件测试区域介绍了如何使用 "签入" 命令将更新的项发送到版本存储区。
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control [Visual Studio SDK], checking items in
- source control plug-ins, checking items in
ms.assetid: d0329fa8-7a8d-4d30-b67b-6f2a97b75a30
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
ms.openlocfilehash: ef2baf2158403e8243632bc7ab77e58ea311b67b
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2021
ms.locfileid: "99898106"
---
# <a name="test-area-4-check-in"></a>测试区域 4：签入
此源代码管理插件测试区域涉及到通过 " **签入** " 命令将更新的项发送到版本存储区。

## <a name="command-menu-access"></a>命令菜单访问
 以下 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 集成开发环境菜单路径用于测试用例。

##### <a name="check-in"></a>签入：
 **文件**、 **源代码管理** 和 **签入**。

 **文件**，请 **签入**。

 快捷菜单中的 " **签入**"。

## <a name="common-expected-behavior"></a>常见的预期行为

- 添加到源代码管理下的解决方案或项目中的项目和文件显示在 " **签入** " 对话框和 " **挂起签入** " 窗口中。

- 签入后，添加的项将显示在 "源代码管理" 中。

- 签入后，更新的项会正确地在存储中进行版本控制。

## <a name="test-cases"></a>测试用例
 下面是签入测试区域的特定测试用例。

### <a name="case-4a-modified-items"></a>案例 4a：修改项
 介绍如何使用 "签入" 操作更新已修改的源代码管理下的文件。

|操作|测试步骤|要验证的预期结果|
|------------|----------------|--------------------------------|
|修改已签出的文本文件，"仅签入文件 (**签入** " 对话框) |1. 使用文本文件创建一个新项目。<br />2. 将解决方案添加到源代码管理。<br />3. 查看并修改该文本文件。<br />4. 通过 "签入" 对话框签入 (**文件**、 **源代码管理**、 **签入**) 。|常见的预期行为。|
|修改已签出的文本文件，只签入文件 (**挂起的签入** 窗口) |1. 使用文本文件创建一个新项目。<br />2. 将解决方案添加到源代码管理。<br />3. 查看并修改该文本文件。<br />4. 通过 " **挂起签入** " 窗口签入。|常见的预期行为。|

### <a name="case-4b-adding-files"></a>案例 4b：添加文件
 将文件添加到项目或将项目添加到解决方案时，项目或解决方案还必须更改。 因此，还将签出父文件，必须签入才能完成添加。

|操作|测试步骤|要验证的预期结果|
|------------|----------------|--------------------------------|
|添加一个文本文件并签入所有内容 (**签入** "对话框) |1. 创建一个新项目。<br />2. 将解决方案添加到源代码管理。<br />3. 将文本文件添加到项目。<br />4. 如果出现提示，请接受项目的签出。<br />5. 在 **解决方案资源管理器** 中选择解决方案。<br />6. 在 " **签入** " 对话框中签入。|常见的预期行为。|
|添加一个文本文件并签入所有 (**挂起的签入** 窗口) |1. 创建一个新项目。<br />2. 将解决方案添加到源代码管理。<br />3. 将文本文件添加到项目。<br />4. 如果出现提示，请接受项目的签出。<br />5. 在 " **挂起签入** " 窗口中签入解决方案。|常见的预期行为|

### <a name="case-4c-adding-projects"></a>案例 4c：添加项目
 向解决方案中添加项目时，该解决方案还必须更改。 因此，解决方案文件也会被签出，必须签入才能完成添加。

|操作|测试步骤|要验证的预期结果|
|------------|----------------|--------------------------------|
| (" **签入** " 对话框中的 "源代码管理" 下将项目添加到空白解决方案中) |1. 创建空白解决方案。<br />2. 将解决方案添加到源代码管理。<br />3. 添加新项目。<br />4. 在出现提示时接受对解决方案的签出。<br />5. 从 " **签入** " 对话框签入。|常见的预期行为。|
|将项目添加到源代码管理下的空白解决方案 (**挂起的签入** 窗口) |1. 创建空白解决方案。<br />2. 将解决方案添加到源代码管理。<br />3. 添加新项目。<br />4. 在出现提示时接受对解决方案的签出。<br />5. 在 " **挂起签入** " 窗口中签入解决方案。|常见的预期行为。|

## <a name="see-also"></a>另请参阅
- [源代码管理插件的测试指南](../../extensibility/internals/test-guide-for-source-control-plug-ins.md)
