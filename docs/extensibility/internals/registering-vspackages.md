---
title: 正在注册 Vspackage |Microsoft Docs
description: .Pkgdef 文件包含其他将被添加到系统注册表中的信息。 了解 Visual Studio 如何使用 .pkgdef 文件描述/查找 VSPackage。
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- managed VSPackages, registering
- registration, managed VSPackages
ms.assetid: 79b9424e-7e9b-4fc8-9b9f-00212674573c
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
ms.openlocfilehash: 111debccd1623901790c83e743469327ffdd667e
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2021
ms.locfileid: "99905837"
---
# <a name="registering-vspackages"></a>注册 VSPackage
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 依赖 .pkgdef 文件来描述和查找 VSPackage。 .Pkgdef 文件包含其他将被添加到系统注册表中的注册信息。 托管 Vspackage 通过向源代码添加特性，然后在生成的程序集上运行 [CreatePkgDef 实用工具](../../extensibility/internals/createpkgdef-utility.md) 来注册 .pkgdef 文件。

## <a name="in-this-section"></a>本节内容
- [指定 VS Shell 的 VSPackage 文件位置](../../extensibility/internals/specifying-vspackage-file-location-to-the-vs-shell.md)

 描述 Vspackage 的加载路径。

- [注册和注销 VSPackage](../../extensibility/registering-and-unregistering-vspackages.md)

 说明如何注册 VSPackage。
