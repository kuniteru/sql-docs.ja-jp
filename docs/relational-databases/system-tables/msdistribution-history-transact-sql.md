---
title: MSdistribution_history (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 03/03/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- MSdistribution_history
- MSdistribution_history_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- MSdistribution_history system table
ms.assetid: 55665bd2-9e1d-4efc-8f60-c63a24f66b28
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d6b60abffcb4831223ee35ac530c979865e03e05
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "85889972"
---
# <a name="msdistribution_history-transact-sql"></a>MSdistribution_history (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  **MSdistribution_history**テーブルには、ローカルディストリビューターに関連付けられているディストリビューションエージェントの履歴行が含まれています。 このテーブルは、ディストリビューションデータベースに格納されます。  
  
## <a name="definition"></a>定義  
  
|列名|データ型|説明|  
|-----------------|---------------|-----------------|  
|**agent_id**|**int**|ディストリビューションエージェントの ID。|  
|**runstatus**|**int**|実行中の状態:<br /><br /> **1** = 開始します。<br /><br /> **2** = 成功します。<br /><br /> **3** = 実行中です。<br /><br /> **4** = アイドル状態。<br /><br /> **5** = 再試行します。<br /><br /> **6** = 失敗。|  
|**start_time**|**datetime**|ジョブの実行開始時刻です。|  
|**time**|**datetime**|メッセージがログに記録される時刻。|  
|**duration**|**int**|メッセージ セッションの実行時間 (秒) です。|  
|**コメント**|**nvarchar (4000)**|メッセージ テキストです。|  
|**xact_seqno**|**varbinary(16)**|最後に処理されたトランザクション シーケンス番号です。|  
|**current_delivery_rate**|**float**|最後の履歴エントリ以降に1秒間に配信されたコマンド数の平均値。|  
|**current_delivery_latency**|**int**|最後の履歴エントリ以降、コマンドがディストリビューションデータベースに入ってからサブスクライバーに適用されるまでの待機時間。 単位はミリ秒。|  
|**delivered_transactions**|**int**|セッションで配信されたトランザクションの合計数。|  
|**delivered_commands**|**int**|セッションで配信されたコマンドの合計数。|  
|**average_commands**|**int**|セッションで配信されたコマンドの平均数。|  
|**delivery_rate**|**float**|1秒間に配信された平均コマンド。|  
|**delivery_latency**|**int**|コマンドがディストリビューション データベースに登録されてからサブスクライバーに適用されるまでの待機時間です。 単位はミリ秒。|  
|**total_delivered_commands**|**bigint**|サブスクリプションが作成されてから配信されたコマンドの合計数。|  
|**error_id**|**int**|**MSrepl_error**システムテーブル内のエラーの ID。|  
|**updateable_row**|**bit**|履歴行を上書きできる場合は、 **1**に設定します。|  
|**timestamp**|**timestamp**|このテーブルのタイムスタンプ列です。|  
  
## <a name="see-also"></a>関連項目  
 [レプリケーションテーブル &#40;Transact-sql&#41;](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [レプリケーション ビュー &#40;Transact-SQL&#41;](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  
