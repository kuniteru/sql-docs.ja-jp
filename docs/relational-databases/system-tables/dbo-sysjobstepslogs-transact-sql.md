---
title: dbo.sysjobstepslogs (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- dbo.sysjobstepslogs_TSQL
- sysjobstepslogs_TSQL
- sysjobstepslogs
- dbo.sysjobstepslogs
dev_langs:
- TSQL
helpviewer_keywords:
- sysjobstepslogs system table
ms.assetid: 128c25db-0b71-449d-bfb2-38b8abcf24a0
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 1807760e10c6a158ab2ef05162e391290e073ab4
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "85890431"
---
# <a name="dbosysjobstepslogs-transact-sql"></a>dbo.sysjobstepslogs (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ジョブステップの出力をテーブルに書き込むように構成されているすべてのエージェントジョブステップのジョブステップログを格納します。 このテーブルは、 **msdb**データベースに格納されます。  
  
|列名|データ型|説明|  
|-----------------|---------------|-----------------|  
|**log_id**|**int**|ジョブ ステップ ログの ID。|  
|**出力**|**nvarchar(max)**|ジョブステップのログの内容。|  
|**date_created**|**datetime**|ジョブ ステップ ログが作成された日時。|  
|**date_modified**|**datetime**|ジョブ ステップ ログが最後に変更された日時。|  
|**log_size**|**int**|ジョブステップのログのサイズ (バイト単位)。|  
|**step_uid**|**uniqueidentifier**|ジョブステップの一意識別子。|  
  
## <a name="see-also"></a>関連項目  
 [sp_help_jobsteplog &#40;Transact-sql&#41;](../../relational-databases/system-stored-procedures/sp-help-jobsteplog-transact-sql.md)   
 [sp_delete_jobsteplog &#40;Transact-sql&#41;](../../relational-databases/system-stored-procedures/sp-delete-jobsteplog-transact-sql.md)  
  
  
