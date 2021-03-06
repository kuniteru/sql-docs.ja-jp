---
title: sys.elastic_pool_resource_stats
titleSuffix: Azure SQL Database
ms.date: 01/28/2019
ms.service: sql-database
ms.prod_service: sql-database
ms.reviewer: ''
ms.topic: reference
f1_keywords:
- sys.elastic_pool_resource_stats catalog view
helpviewer_keywords:
- sys.elastic_pool_resource_stats_TSQL
- sys.elastic_pool_resource_stats
- elastic_pool_resource_stats_TSQL
- elastic_pool_resource_stats
ms.assetid: f242c1bd-3cc8-4c8b-8aaf-c79b6a8a0329
author: CarlRabeler
ms.author: carlrab
ms.custom: seo-dt-2019
monikerRange: = azuresqldb-current || = sqlallproducts-allversions
ms.openlocfilehash: 4c6d2e7cccc7e1aa07327480415c0acd2a3db192
ms.sourcegitcommit: 777704aefa7e574f4b7d62ad2a4c1b10ca1731ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "87822933"
---
# <a name="syselastic_pool_resource_stats-azure-sql-database"></a>sys.elastic_pool_resource_stats (Azure SQL Database)
[!INCLUDE[Azure SQL Database Azure SQL Managed Instance](../../includes/applies-to-version/asdb-asdbmi.md)]

  SQL Database サーバー内のすべてのエラスティック プールのリソース使用状況の統計を返します。 各エラスティック プールのレポート間隔は、15 秒に 1 行 (1 分あたり 4 行) です。 これには、プール内のすべてのデータベースごとの CPU、I/O、ログ、ストレージ消費、および同時実行要求/セッション使用率が含まれます。 このデータは14日間保持されます。 
  
||  
|-|  
|**に適用さ**れます: [!INCLUDE[ssSDS](../../includes/sssds-md.md)] V12。|  
  
|列名|データ型|説明|  
|-----------------|---------------|-----------------|  
|**start_time**|**datetime2**|15秒のレポート間隔の開始を示す UTC 時刻。|  
|**end_time**|**datetime2**|15秒のレポート間隔の終了を示す UTC 時刻。|  
|**elastic_pool_name**|**nvarchar(128)**|エラスティックデータベースプールの名前。|  
|**avg_cpu_percent**|**decimal (5, 2)**|プールの限度に対する割合で表した平均コンピューティング使用率。|  
|**avg_data_io_percent**|**decimal (5, 2)**|プールの限度に対する割合で表した平均 I/O 使用率。|  
|**avg_log_write_percent**|**decimal (5, 2)**|プールの限度に対する割合で表した平均書き込みリソース使用率。|  
|**avg_storage_percent**|**decimal (5, 2)**|プールのストレージ限度に対する割合で表した平均ストレージ使用率。|  
|**max_worker_percent**|**decimal (5, 2)**|プールの限度に対する割合で表した最大同時実行ワーカー (要求) 数。|  
|**max_session_percent**|**decimal (5, 2)**|プールの限度に対する割合で表した最大同時実行セッション数。|  
|**elastic_pool_dtu_limit**|**int**|この期間中のこのエラスティック プールに対する現在の最大エラスティック プール DTU 設定。|  
|**elastic_pool_storage_limit_mb**|**bigint**|この期間中のこのエラスティック プールに対する現在の最大エラスティック プール ストレージ制限 (メガバイト単位)。|
|**avg_allocated_storage_percent**|**decimal (5, 2)**|エラスティックプール内のすべてのデータベースによって割り当てられたデータ領域の割合。  これは、エラスティックプールのデータの最大サイズに割り当てられたデータ領域の比率です。  詳細については[、「SQL Database でのファイル領域管理](https://docs.microsoft.com/azure/sql-database/sql-database-file-space-management)」を参照してください。|  
  
## <a name="remarks"></a>Remarks

 このビューは、SQL Database サーバーの master データベースに存在します。 **Elastic_pool_resource_stats**を照会するには、master データベースに接続している必要があります。  
  
## <a name="permissions"></a>アクセス許可

 **Dbmanager**ロールのメンバーシップが必要です。  
  
## <a name="examples"></a>例

 次の例では、現在の SQL Database サーバーのすべてのエラスティックデータベースプールについて、最新の時刻によって並べ替えられたリソース使用率データを返します。  
  
```sql
SELECT * FROM sys.elastic_pool_resource_stats
ORDER BY end_time DESC;  
```

 次の例では、指定されたプールの平均 DTU 使用率を計算します。  

```sql
SELECT start_time, end_time,
  (SELECT Max(v)
FROM (VALUES (avg_cpu_percent), (avg_data_io_percent), (avg_log_write_percent)) AS value(v)) AS [avg_DTU_percent]
FROM sys.elastic_pool_resource_stats
WHERE elastic_pool_name = '<your pool name>'
ORDER BY end_time DESC;  
```

## <a name="see-also"></a>参照

 [エラスティックデータベースによる爆発的な成長の緩和](https://azure.microsoft.com/documentation/articles/sql-database-elastic-pool/)   
 [SQL Database エラスティックデータベースプールの作成と管理 (プレビュー)](https://azure.microsoft.com/documentation/articles/sql-database-elastic-pool-portal/)   
 [resource_stats &#40;Azure SQL Database&#41;](../../relational-databases/system-catalog-views/sys-resource-stats-azure-sql-database.md)   
 [dm_db_resource_stats &#40;Azure SQL Database&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-db-resource-stats-azure-sql-database.md)  
  
  
