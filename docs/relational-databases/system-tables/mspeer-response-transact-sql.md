---
title: MSpeer_response (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- MSpeer_response
- MSpeer_response_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- MSpeer_response system table
ms.assetid: 510e24cf-0292-47a9-b1d9-71a30fef030f
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 371ee711cbae4c97dc95e9d31d51739c29e85d14
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "85889629"
---
# <a name="mspeer_response-transact-sql"></a>MSpeer_response (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  **MSpeer_response**テーブルは、ピアツーピアレプリケーションで、各ノードの応答をパブリケーションステータス要求に格納するために使用されます。 このテーブルは、パブリケーションデータベースに格納されます。  
  
## <a name="definition"></a>定義  
  
|列名|データ型|説明|  
|-----------------|---------------|-----------------|  
|**request_id**|**int**|[MSpeer_request](../../relational-databases/system-tables/mspeer-request-transact-sql.md)テーブル内の状態要求エントリを識別します。|  
|**家**|**sysname**|応答を生成したピア。|  
|**peer_db**|**sysname**|応答を生成したピアのサブスクリプションデータベース。|  
|**received_date**|**datetime**|ピア要求を受信した日付と時刻。|  
  
## <a name="see-also"></a>関連項目  
 [レプリケーション テーブル &#40;Transact-SQL&#41;](../../relational-databases/system-tables/replication-tables-transact-sql.md)  
  
  
