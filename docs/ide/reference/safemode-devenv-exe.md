---
title: -SafeMode (devenv.exe)
description: 了解如何使用 SafeMode devenv 命令行开关在安全模式下启动 Visual Studio，仅加载默认环境和服务。
ms.custom: SEO-VS-2020
ms.date: 12/10/2018
ms.topic: reference
helpviewer_keywords:
- /SafeMode Devenv switch
- Devenv, /SafeMode switch
- SafeMode switch
ms.assetid: b191f6a5-8f12-47ec-bcc7-b68149a22aa8
author: TerryGLee
ms.author: tglee
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: 1626776ec41bdbdfe5ad2b611516e62ada4f15a3
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2021
ms.locfileid: "99957863"
---
# <a name="safemode-devenvexe"></a>/SafeMode (devenv.exe)

在安全模式下启动 Visual Studio，同时仅加载默认环境和服务。

## <a name="syntax"></a>语法

```shell
devenv /SafeMode
```

## <a name="remarks"></a>备注

Visual Studio 启动时，此开关阻止所有第三方 VSPackages 加载，以确保执行稳定。

## <a name="example"></a>示例

下面的示例在安全模式下启动 Visual Studio。

```shell
devenv /safemode
```

## <a name="see-also"></a>另请参阅

- [Devenv 命令行开关](../../ide/reference/devenv-command-line-switches.md)
