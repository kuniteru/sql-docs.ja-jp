---
title: pdw_nodes_column_store_dictionaries (Transact-sql)
ms.date: 03/03/2017
ms.prod: sql
ms.technology: data-warehouse
ms.reviewer: ''
ms.custom: seo-dt-2019
ms.topic: language-reference
dev_langs:
- TSQL
ms.assetid: 7ae1c2e4-45c0-4880-a692-1f299fbcfd19
author: ronortloff
ms.author: rortloff
monikerRange: '>= aps-pdw-2016 || = azure-sqldw-latest || = sqlallproducts-allversions'
ms.openlocfilehash: bc82a44fcd536b53b2e49851806262a0bdd230ef
ms.sourcegitcommit: 01297f2487fe017760adcc6db5d1df2c1234abb4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "86197170"
---
# <a name="syspdw_nodes_column_store_dictionaries-transact-sql"></a>pdw_nodes_column_store_dictionaries (Transact-sql)
[!INCLUDE[applies-to-version/asa-pdw](../../includes/applies-to-version/asa-pdw.md)]

  列ストアインデックスで使用されるディクショナリごとに1行の値を格納します。 ディクショナリは、一部のデータ型ではなく一部のデータ型をエンコードするために使用されます。したがって、列ストアインデックスのすべての列がディクショナリを持つわけではありません。 ディクショナリは、プライマリディクショナリ (すべてのセグメント) として存在することができ、場合によっては、列のセグメントのサブセットに使用される他のセカンダリディクショナリとして存在することもあります。  
  
|列名|データ型|説明|  
|-----------------|---------------|-----------------|  
|**partition_id**|**bigint**|パーティション ID を示します。 データベース内で一意です。|  
|**hobt_id**|**bigint**|この列ストアインデックスを持つテーブルのヒープまたは B ツリーインデックス (HoBT) の ID。|  
|**column_id**|**int**|列ストア列の ID。|  
|**dictionary_id**|**int**|ディクショナリの Id。|  
|**version**|**int**|辞書形式のバージョン。|  
|**type**|**int**|辞書の種類:<br /><br /> 1- **int**値を含むハッシュディクショナリ<br /><br /> 2-使用されていません<br /><br /> 3-文字列値を含むハッシュディクショナリ<br /><br /> 4- **float**値を含むハッシュディクショナリ|  
|**last_id**|**int**|ディクショナリ内の最後のデータ id。|  
|**entry_count**|**bigint**|ディクショナリ内のエントリの数。|  
|**on_disc_size**|**bigint**|ディクショナリのサイズ (バイト単位)。|  
|**pdw_node_id**|**int**|ノードの一意識別子 [!INCLUDE[ssSDW](../../includes/sssdw-md.md)] 。|  
  
## <a name="permissions"></a>アクセス許可  
 `VIEW SERVER STATE` 権限が必要です。  
  
## <a name="see-also"></a>関連項目  
 [SQL Data Warehouse and Parallel Data Warehouse Catalog Views (SQL Data Warehouse および Parallel Data Warehouse のカタログ ビュー)](../../relational-databases/system-catalog-views/sql-data-warehouse-and-parallel-data-warehouse-catalog-views.md)   
 [Transact-sql&#41;&#40;列ストアインデックスの作成](../../t-sql/statements/create-columnstore-index-transact-sql.md)   
 [pdw_nodes_column_store_segments &#40;Transact-sql&#41;](../../relational-databases/system-catalog-views/sys-pdw-nodes-column-store-segments-transact-sql.md)   
 [pdw_nodes_column_store_row_groups &#40;Transact-sql&#41;](../../relational-databases/system-catalog-views/sys-pdw-nodes-column-store-row-groups-transact-sql.md)  
  
  
