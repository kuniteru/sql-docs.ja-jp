---
title: fn_MSxe_read_event_stream (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- fn_MSxe_read_event_stream_TSQL
- sys.fn_MSxe_read_event_stream_TSQL
- sys.fn_MSxe_read_event_stream
- fn_MSxe_read_event_stream
dev_langs:
- TSQL
helpviewer_keywords:
- sys.fn_MSxe_read_event_stream
- fn_MSxe_read_event_stream
ms.assetid: 5edb1162-625a-41e0-8ec9-1edc8ab9a74a
author: rothja
ms.author: jroth
ms.openlocfilehash: 05be6f4b30e42ddc1213231a6d96a823dfc9f1cd
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85783103"
---
# <a name="sysfn_msxe_read_event_stream-transact-sql"></a>sys.fn_MSxe_read_event_stream (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  拡張イベントは、拡張イベントのユーザーインターフェイス (UI) によって内部で使用されるテーブル値関数 (TVF) を提供します。 テーブルは、ユーザーによる利用が可能なデータを提供しません。  
  
 イベントデータを表示するには、次のいずれかを使用します。  
  
-   拡張イベントの新しいセッション UI。  
  
-   fn_xe_file_target_read_file TVF。 詳細については、「[sys.fn_xe_file_target_read_file &#40;Transact-SQL&#41;](../../relational-databases/system-functions/sys-fn-xe-file-target-read-file-transact-sql.md)」を参照してください。  
  
  
 ![トピック リンク アイコン](../../database-engine/configure-windows/media/topic-link.gif "トピック リンク アイコン") [Transact-SQL 構文表記規則](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>構文  
  
```  
  
sys.fn_MSxe_read_event_stream ( session_name)  
```  
  
## <a name="arguments"></a>引数  
 *Session_name*  
 サーバー上で実行されているセッションの名前。  
  
## <a name="table-returned"></a>返されるテーブル  
  
|列名|データ型|説明|  
|-----------------|---------------|-----------------|  
|type|**整数 (4)**|イベントの種類。 NULL 値は許可されません。|  
|data|**画像 (16)**|イベントイメージデータ。 NULL 値が許可されます。|  
  
## <a name="see-also"></a>関連項目  
 [拡張イベントの動的管理ビュー](../../relational-databases/system-dynamic-management-views/extended-events-dynamic-management-views.md)   
 [拡張イベントのカタログビュー &#40;Transact-sql&#41;](../../relational-databases/system-catalog-views/extended-events-catalog-views-transact-sql.md)   
 [拡張イベント](../../relational-databases/extended-events/extended-events.md)  
  
  
