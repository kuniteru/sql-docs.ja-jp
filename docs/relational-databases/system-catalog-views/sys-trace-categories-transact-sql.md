---
title: trace_categories (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 08/09/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- trace_categories
- trace_categories_TSQL
- sys.trace_categories
- sys.trace_categories_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.trace_categories catalog view
ms.assetid: f6a86766-e2a9-4d9f-a073-1b59e888ba7d
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 6d8ffe8d193732b7619051e096b668f2f9c5f2c8
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "85882216"
---
# <a name="systrace_categories-transact-sql"></a>sys.trace_categories (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  類似したイベント クラスは、同じカテゴリに分類されます。 Trace_categories カタログビューの各行は、サーバー全体で一意のカテゴリを識別し**ます**。 これらのカテゴリは、の特定のバージョンでは変更されません [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] 。  
  
 サポートされているトレースイベントの完全な一覧については、「 [SQL Server イベントクラスのリファレンス](../../relational-databases/event-classes/sql-server-event-class-reference.md)」を参照してください。  
  
> **重要:** [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]代わりに拡張イベントカタログビューを使用します。  
  
|列名|データ型|説明|  
|-----------------|---------------|-----------------|  
|**category_id**|**smallint**|このカテゴリの一意の ID。 この列は、 **trace_events**カタログビューにも含まれています。|  
|**name**|**nvarchar(128)**|カテゴリの一意な名前。 このパラメーターはローカライズされていません。|  
|**type**|**tinyint**|カテゴリの種類:<br /><br /> 0 = 通常<br /><br /> 1 = 接続<br /><br /> 2 = エラー|  
  
## <a name="permissions"></a>アクセス許可  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] 詳細については、「 [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [オブジェクトカタログビュー &#40;Transact-sql&#41;](../../relational-databases/system-catalog-views/object-catalog-views-transact-sql.md)   
 [Transact-sql&#41;&#40;のトレース](../../relational-databases/system-catalog-views/sys-traces-transact-sql.md)   
 [trace_columns &#40;Transact-sql&#41;](../../relational-databases/system-catalog-views/sys-trace-columns-transact-sql.md)   
 [trace_events &#40;Transact-sql&#41;](../../relational-databases/system-catalog-views/sys-trace-events-transact-sql.md)   
 [trace_event_bindings &#40;Transact-sql&#41;](../../relational-databases/system-catalog-views/sys-trace-event-bindings-transact-sql.md)   
 [trace_subclass_values &#40;Transact-sql&#41;](../../relational-databases/system-catalog-views/sys-trace-subclass-values-transact-sql.md)  
  
  
