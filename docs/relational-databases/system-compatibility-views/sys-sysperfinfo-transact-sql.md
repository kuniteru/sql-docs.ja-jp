---
title: sys.sysperfinfo (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 03/15/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sysperfinfo_TSQL
- sys.sysperfinfo_TSQL
- sys.sysperfinfo
- sysperfinfo
dev_langs:
- TSQL
helpviewer_keywords:
- sys.sysperfinfo compatibility view
- sysperfinfo system table
ms.assetid: e22a81cd-27de-4690-9443-6aad6393bd3c
author: rothja
ms.author: jroth
ms.openlocfilehash: a2cdadb112dbceb6a3b031707b8ba8b889bad822
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "85895849"
---
# <a name="syssysperfinfo-transact-sql"></a>sys.sysperfinfo (Transact-sql)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] Windows システムモニターを使用して表示できる内部パフォーマンスカウンターの表現が含まれます。  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssnoteCompView](../../includes/ssnotecompview-md.md)]  
  
|列名|データ型|説明|  
|-----------------|---------------|-----------------|  
|**object_name**|**nchar(128)**|**Sqlserver: lockmanager**や**Sqlserver: buffermanager**などのパフォーマンスオブジェクト名。|  
|**counter_name**|**nchar(128)**|**要求された****ページ要求**やロックなど、オブジェクト内のパフォーマンスカウンターの名前。|  
|**instance_name**|**nchar(128)**|カウンターの名前付きインスタンス。 たとえば、**テーブル**、**ページ**、**キー**など、ロックの種類ごとに保持されるカウンターがあります。 類似したカウンターはインスタンス名で区別されます。|  
|**cntr_value**|**bigint**|実際のカウンター値。 多くの場合、これは、インスタンス イベントの発生数を表すレベルまたは単純増加のカウンターになります。|  
|**cntr_type**|**int**|Windows パフォーマンスアーキテクチャで定義されているカウンターの種類。|  
  
## <a name="see-also"></a>関連項目  
 [システムビューへのシステムテーブルのマッピング &#40;Transact-sql&#41;](../../relational-databases/system-tables/mapping-system-tables-to-system-views-transact-sql.md)   
 [互換性ビュー &#40;Transact-SQL&#41;](~/relational-databases/system-compatibility-views/system-compatibility-views-transact-sql.md)  
  
  
