---
title: 次のフェッチ位置 (Native Client OLE DB provider) |Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- fetching rows
- OLE DB rowsets, fetching
- next fetch position
- rowsets [OLE DB], fetching
ms.assetid: 9ef74b3f-c9c0-492f-9b93-d65738a61abd
author: markingmyname
ms.author: maghan
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: c431e6b69f117e23de9166d6f5798be43e488646
ms.sourcegitcommit: 216f377451e53874718ae1645a2611cdb198808a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87243631"
---
# <a name="fetching-rows---next-fetch--native-client-ole-db-provider"></a>行のフェッチ-次のフェッチ (Native Client OLE DB プロバイダー)
[!INCLUDE[SQL Server Azure SQL Database Synapse Analytics PDW ](../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Native Client OLE DB プロバイダーは、次のフェッチ位置を追跡します。これにより、 **GetNextRows**メソッド (スキップ、方向の変更、または**FindNextRow**、 **Seek**、または**RestartPosition**メソッドへの介在する呼び出しを除く) の一連の呼び出しによって行セット全体が読み取られます。行をスキップしたり、繰り返したりする必要はありません。 **IRowset::GetNextRows**、**IRowset::RestartPosition**、または **IRowsetIndex::Seek** を呼び出すか、*pBookmark* 値に NULL を指定して **FindNextRow** を呼び出すことにより、次のフェッチ位置が変更されます。 *pBookmark* 値に NULL 以外の値を指定して **FindNextRow** を呼び出しても、次のフェッチ位置には影響しません。  
  
## <a name="see-also"></a>参照  
 [行のフェッチ](../../relational-databases/native-client-ole-db-rowsets/fetching-rows.md)  
  
  
