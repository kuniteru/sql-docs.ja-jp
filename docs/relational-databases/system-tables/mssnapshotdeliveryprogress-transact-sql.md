---
title: MSsnapshotdeliveryprogress (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- MSsnapshotdeliveryprogress_TSQL
- MSsnapshotdeliveryprogress
dev_langs:
- TSQL
helpviewer_keywords:
- MSsnapshotdeliveryprogress system table
ms.assetid: 9164bfe2-6fc4-4b52-946a-09ea3cf67041
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: f4cd21fcc026e48c0e0f4ca68ada16bf55855662
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "85889388"
---
# <a name="mssnapshotdeliveryprogress-transact-sql"></a>MSsnapshotdeliveryprogress (Transact-sql)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  **Mssnapshotdeliveryprogress**テーブルは、スナップショットの適用時にサブスクライバーに正常に配信されたファイルを追跡するために使用されます。 マージ エージェントがセッション中にすべてのファイルを配信できなかった場合に、このデータを使用してファイルの配信を再開し、次にマージ エージェントが実行されたときに同じファイルが再度配信されないようにします。 このテーブルは、サブスクライバーのサブスクリプションデータベースに格納されます。  
  
|列名|データ型|説明|  
|-----------------|---------------|-----------------|  
|**session_token**|**nvarchar(260)**|ファイルが正常に配信されたスナップショットフォルダーへのパスを識別します。 パラメーター化されたフィルターを使用するパブリケーションでは、文字列**dynsnap**が値に追加されます。|  
|**progress_token_hash**|**int**|特定の*progress_token*値の参照効率を向上させるために使用される*progress_token*の値に基づいて生成されるハッシュ値。|  
|**progress_token**|**nvarchar (500)**|正常に配信されたファイルを識別します。値は、ファイル名とパスの組み合わせです。|  
|**progress_timestamp**|**datetime**|スナップショットファイルが正常に配信された日時を示す**datetime**値です。|  
  
## <a name="see-also"></a>関連項目  
 [レプリケーションテーブル &#40;Transact-sql&#41;](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [レプリケーション ビュー &#40;Transact-SQL&#41;](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  
