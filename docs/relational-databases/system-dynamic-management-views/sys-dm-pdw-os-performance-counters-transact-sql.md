---
title: dm_pdw_os_performance_counters (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
dev_langs:
- TSQL
ms.assetid: 0673a8f8-8bed-41eb-8959-a9e3e9e03a65
author: CarlRabeler
ms.author: carlrab
monikerRange: '>= aps-pdw-2016 || = sqlallproducts-allversions'
ms.openlocfilehash: 72164d23d8f2dbd27bb30f1341b288c96ab44cc0
ms.sourcegitcommit: df1f0f2dfb9452f16471e740273cd1478ff3100c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "87396611"
---
# <a name="sysdm_pdw_os_performance_counters-transact-sql"></a>dm_pdw_os_performance_counters (Transact-sql)
[!INCLUDE [pdw](../../includes/applies-to-version/pdw.md)]

  のノードの Windows パフォーマンスカウンターに関する情報が含まれてい [!INCLUDE[ssPDW](../../includes/sspdw-md.md)] ます。  
  
|列名|データ型|説明|Range|  
|-----------------|---------------|-----------------|-----------|  
|pdw_node_id|**int**|カウンターを含むノードの ID。<br /><br /> このビューのキーは pdw_node_id と counter_name によって形成されます。|『 [Transact-sql&#41;&#40;dm_pdw_nodes](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-nodes-transact-sql.md)の node_id を参照してください。|  
|counter_name|**nvarchar (255)**|Windows パフォーマンスカウンターの名前。||  
|counter_category|**nvarchar (255)**|Windows パフォーマンスカウンターカテゴリの名前。||  
|instance_name|**nvarchar (255)**|カウンターの特定のインスタンスの名前。||  
|counter_value|**10進数 (38, 10)**|カウンターの現在の値。||  
|last_update_time|**Datetime2 (3)**|値が最後に更新されたときのタイムスタンプ。||  
  
## <a name="see-also"></a>参照  
 [SQL Data Warehouse および並列データウェアハウスの動的管理ビュー &#40;Transact-sql&#41;](../../relational-databases/system-dynamic-management-views/sql-and-parallel-data-warehouse-dynamic-management-views.md)  
  
  
