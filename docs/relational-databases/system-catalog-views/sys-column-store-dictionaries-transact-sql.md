---
title: column_store_dictionaries (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.column_store_dictionaries_TSQL
- column_store_dictionaries
- column_store_dictionaries_TSQL
- sys.column_store_dictionaries
dev_langs:
- TSQL
helpviewer_keywords:
- sys.column_store_dictionaries catalog view
ms.assetid: 56efd563-2f72-4caf-94e3-8a182385c173
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: e7ccd7c93d42cb30eeb2fc24b79c358d519579b6
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85764765"
---
# <a name="syscolumn_store_dictionaries-transact-sql"></a>sys.column_store_dictionaries (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  XVelocity メモリ最適化列ストアインデックスで使用されるディクショナリごとに1行の値を格納します。 ディクショナリは、一部のデータ型ではなく一部のデータ型をエンコードするために使用されます。したがって、列ストアインデックスのすべての列がディクショナリを持つわけではありません。 ディクショナリは、プライマリディクショナリ (すべてのセグメント) として存在することができ、場合によっては、列のセグメントのサブセットに使用される他のセカンダリディクショナリとして存在することもあります。  
  
|列名|データ型|説明|  
|-----------------|---------------|-----------------|  
|**hobt_id**|**bigint**|この列ストアインデックスを持つテーブルのヒープまたは B ツリーインデックス (HoBT) の ID。|  
|**column_id**|**int**|1から始まる列ストア列の ID。 最初の列の ID が1、2番目の列の ID が2、など。|  
|**dictionary_id**|**int**|列セグメントに関連付けられている辞書には、グローバルとローカルの2種類があります。 Dictionary_id 0 は、その列のすべての列セグメント (行グループごとに1つ) 間で共有されるグローバルディクショナリを表します。|  
|**version**|**int**|辞書形式のバージョン。|  
|**type**|**int**|辞書の種類:<br /><br /> 1- **int**値を含むハッシュディクショナリ<br /><br /> 2-使用されていません<br /><br /> 3-文字列値を含むハッシュディクショナリ<br /><br /> 4- **float**値を含むハッシュディクショナリ<br /><br /> ディクショナリの詳細については、「[列ストアインデックスガイド](~/relational-databases/indexes/columnstore-indexes-overview.md)」を参照してください。|  
|**last_id**|**int**|ディクショナリ内の最後のデータ ID。|  
|**entry_count**|**bigint**|ディクショナリ内のエントリの数。|  
|**on_disk_size**|**bigint**|ディクショナリのサイズ (バイト単位)。|  
|**partition_id**|**bigint**|パーティション ID を示します。 データベース内で一意です。|  
  
## <a name="permissions"></a>アクセス許可  
テーブルに対する権限が必要です `VIEW DEFINITION` 。 次の列は、ユーザーがアクセス許可を持っていない場合は null を返し `SELECT` ます last_id、entry_count、data_ptr です。  
  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] 詳細については、「 [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [オブジェクトカタログビュー &#40;Transact-sql&#41;](../../relational-databases/system-catalog-views/object-catalog-views-transact-sql.md)   
 [Transact-sql&#41;&#40;カタログビュー](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [SQL Server システムカタログに対するクエリについてよく寄せられる質問](../../relational-databases/system-catalog-views/querying-the-sql-server-system-catalog-faq.md)   
 [&#40;Transact-sql&#41;の列](../../relational-databases/system-catalog-views/sys-columns-transact-sql.md)   
 [all_columns &#40;Transact-sql&#41;](../../relational-databases/system-catalog-views/sys-all-columns-transact-sql.md)   
 [computed_columns &#40;Transact-sql&#41;](../../relational-databases/system-catalog-views/sys-computed-columns-transact-sql.md)   
 [列ストアインデックスガイド](~/relational-databases/indexes/columnstore-indexes-overview.md)   
 [列ストアインデックスガイド](~/relational-databases/indexes/columnstore-indexes-overview.md)   
 [sys.column_store_segments &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-column-store-segments-transact-sql.md)  
  
  

