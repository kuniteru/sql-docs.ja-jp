---
title: MSSQLSERVER_3452 | Microsoft Docs
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: language-reference
helpviewer_keywords:
- 3452 (Database Engine error)
ms.assetid: bf838f02-7186-4b33-b01e-361b0c02de1f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 775a141774bf8974aa874f7879ce3b65694cf17d
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85723491"
---
# <a name="mssqlserver_3452"></a>MSSQLSERVER_3452
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  
## <a name="details"></a>詳細  
  
| 属性 | 値 |  
| :-------- | :---- |  
|製品名|SQL Server|  
|イベント ID|3452|  
|イベント ソース|MSSQLSERVER|  
|コンポーネント|SQLEngine|  
|シンボル名|REC_CHECKIDENTITY|  
|メッセージ テキスト|データベース '%.*ls' (%d) の復旧でテーブル %d の ID 値の一貫性が損なわれているのを検出しました。 DBCC CHECKIDENT ('%.\*ls') を実行してください。|  
  
## <a name="explanation"></a>説明  
[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] へのアップグレード作業中に、データベース内の ID 値を復元するプロセスで、メタデータの不整合が検出されました。  
  
## <a name="user-action"></a>ユーザーの操作  
DBCC CHECKIDENT を実行します。  
  
