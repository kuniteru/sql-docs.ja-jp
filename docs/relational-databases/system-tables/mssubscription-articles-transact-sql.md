---
title: MSsubscription_articles (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 03/03/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- MSsubscription_articles
- MSsubscription_articles_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- MSsubscription_articles system table
ms.assetid: dbc1737f-261e-4017-b9cd-703b9fc4ac78
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: e44a88869e4a064896e15a1040e90d6ff66e9da3
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "85889333"
---
# <a name="mssubscription_articles-transact-sql"></a>MSsubscription_articles (Transact-sql)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  **MSsubscription_articles**テーブルには、キューに登録されたサブスクリプション内のアーティクルに関する情報が含まれています。 このテーブルは、レプリケーションの種類がキュー更新の場合と、フェールオーバーとしてキュー更新を行う即時更新の場合にのみ設定されます。  
  
|列名|データ型|説明|  
|-----------------|---------------|-----------------|  
|**agent_id**|**int**|アーティクルを処理するエージェントの ID|  
|**artid**|**int**|**Sysarticles**テーブルのアーティクル ID です。|  
|**記事**|**sysname**|**Sysarticles**テーブルのアーティクルの名前。|  
|**dest_table**|**sysname**|**Sysarticles**テーブルのコピー先テーブルの名前。|  
|**責任**|**sysname**|サブスクリプションの所有者|  
|**cft_table**|**sysname**|キュー更新レプリケーションの種類について、このアーティクルの競合テーブルの名前。|  
  
## <a name="see-also"></a>関連項目  
 [レプリケーションテーブル &#40;Transact-sql&#41;](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [レプリケーション ビュー &#40;Transact-SQL&#41;](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  
