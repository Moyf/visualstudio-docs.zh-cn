---
title: 如何：通过使用事务来保存数据
description: 查看如何通过在 Visual Studio 中使用数据集工具来保存数据。 使用 system.exception 命名空间将数据保存在事务中。
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- saving data, using transactions
- System.Transactions namespace
- transactions, saving data
- data [Visual Studio], saving
ms.assetid: 8b835e8f-34a3-413d-9bb5-ebaeb87f1198
author: ghogen
ms.author: ghogen
manager: jmartens
ms.workload:
- data-storage
ms.openlocfilehash: c633ed01821f500e958d3c7549febc23cf33c09d
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2021
ms.locfileid: "99858483"
---
# <a name="how-to-save-data-by-using-a-transaction"></a>如何：通过使用事务来保存数据

使用命名空间将数据保存在事务中 <xref:System.Transactions> 。 使用 <xref:System.Transactions.TransactionScope> 对象参与自动管理的事务。

项目不是使用对 *system.web* 程序集的引用创建的，因此，您需要手动添加对使用事务的项目的引用。

实现事务的最简单方法是 <xref:System.Transactions.TransactionScope> 在语句中实例化对象 `using` 。 有关详细信息，请参阅 [using 语句](/dotnet/visual-basic/language-reference/statements/using-statement)和 [using 语句](/dotnet/csharp/language-reference/keywords/using-statement) (。 ) 语句中运行的代码 `using` 参与事务。

若要提交事务，请调用 <xref:System.Transactions.TransactionScope.Complete%2A> 方法，作为 using 块中的最后一条语句。

若要回滚事务，请在调用方法之前引发异常 <xref:System.Transactions.TransactionScope.Complete%2A> 。

## <a name="to-add-a-reference-to-the-systemtransactionsdll"></a>添加对 System.Transactions.dll 的引用

1. 在“项目”菜单中，选择“添加引用”。

2. 在 " **.net** " 选项卡上 (SQL Server) 项目 **SQL Server** "选项卡，选择" **系统**"，然后选择 **" 确定 "**。

     对 *System.Transactions.dll* 的引用将添加到项目。

## <a name="to-save-data-in-a-transaction"></a>在事务中保存数据

- 添加代码以在包含事务的 using 语句中保存数据。 下面的代码演示如何 <xref:System.Transactions.TransactionScope> 在 using 语句中创建并实例化对象：

     [!code-vb[VbRaddataSaving#11](../data-tools/codesnippet/VisualBasic/save-data-by-using-a-transaction_1.vb)]
     [!code-csharp[VbRaddataSaving#11](../data-tools/codesnippet/CSharp/save-data-by-using-a-transaction_1.cs)]

## <a name="see-also"></a>另请参阅

- [将数据保存回数据库](../data-tools/save-data-back-to-the-database.md)
- [演练：在事务中保存数据](../data-tools/save-data-in-a-transaction.md)
