---
title: syspolicy_policy_execution_history (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- syspolicy_policy_execution_history_TSQL
- syspolicy_policy_execution_history
dev_langs:
- TSQL
helpviewer_keywords:
- syspolicy_policy_execution_history view
ms.assetid: b13c44a7-6d49-4d50-abe1-e657fc52bb05
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 9e6f8200b1c49bfe5e4977dc1e8f093537fc950e
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "85900571"
---
# <a name="syspolicy_policy_execution_history-transact-sql"></a>syspolicy_policy_execution_history (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  ポリシーが実行された時刻、各実行の結果、および発生したエラーの詳細が表示されます。 次の表では、syspolicy_policy_execution_history ビュー内の列について説明します。  
  
|列名|データ型|説明|  
|-----------------|---------------|-----------------|  
|history_id|**bigint**|このレコードの識別子。 各レコードは、ポリシーと、開始された時刻を示します。|  
|policy_id|**int**|ポリシーの識別子。|  
|start_date|**datetime**|このポリシーを実行しようとした日付と時刻。|  
|end_date|**datetime**|このポリシーの実行が終了した時刻。|  
|結果|**bit**|ポリシーの成功または失敗。 0 = 失敗、1 = 成功。|  
|exception_message|**nvarchar(max)**|例外が発生した場合は、例外によって生成されたメッセージ。|  
|exception|**nvarchar(max)**|例外が発生した場合の説明。|  
  
## <a name="remarks"></a>Remarks  
 [Syspolicy_policy_execution_history_details](../../relational-databases/system-catalog-views/syspolicy-policy-execution-history-details-transact-sql.md)ビューには、ポリシーのターゲットとテストされた条件式に関する関連情報が含まれています。  
  
## <a name="permissions"></a>アクセス許可  
 msdb データベースの PolicyAdministratorRole ロールのメンバーシップが必要です。  
  
## <a name="see-also"></a>関連項目  
 [ポリシーベースの管理を使用してサーバーを管理する](../../relational-databases/policy-based-management/administer-servers-by-using-policy-based-management.md)   
 [ポリシーベースの管理ビュー &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/policy-based-management-views-transact-sql.md)  
  
  
