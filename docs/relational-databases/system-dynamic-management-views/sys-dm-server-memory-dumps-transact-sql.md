---
title: dm_server_memory_dumps (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.dm_server_memory_dumps_TSQL
- dm_server_memory_dumps_TSQL
- dm_server_memory_dumps
- sys.dm_server_memory_dumps
dev_langs:
- TSQL
helpviewer_keywords:
- sys.dm_server_memory_dumps dynamic management view
ms.assetid: 41782719-f54d-4e11-941a-c050c7576e23
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 40e8457a4f31e0961560c1c48cc5885fa3cfd053
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "85898641"
---
# <a name="sysdm_server_memory_dumps-transact-sql"></a>sys.dm_server_memory_dumps (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  によって生成されたメモリダンプファイルごとに1行の値を返し [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] ます。 この動的管理ビューを使用して、潜在的な問題のトラブルシューティングを行います。  
 
|列名|データ型|説明|  
|-----------------|---------------|-----------------|  
|**filename**|**nvarchar(256)**|メモリダンプファイルのパスと名前。 null にすることはできません。|  
|**creation_time**|**datetimeoffset(7)**|ファイルが作成された日付と時刻。 null にすることはできません。|  
|**size_in_bytes**|**bigint**|ファイルのサイズ (バイト単位)。 NULL 値が許可されます。|  
  
## <a name="general-remarks"></a>全般的な解説  
 ダンプの種類として、ミニダンプ、すべてのスレッドのダンプ、または完全なダンプを使用できます。 ファイルの拡張子は mdmp です。  
  
## <a name="security"></a>セキュリティ  
 ダンプ ファイルには機密情報が含まれている場合があります。 機密情報を保護するには、アクセス制御リスト (ACL) を使用してこのファイルへのアクセスを制限するか、アクセスが制限されたフォルダーにファイルをコピーすることができます。 たとえば、デバッグファイルを Microsoft サポートサービスに送信する前に、機密情報または機密情報をすべて削除することをお勧めします。  
  
### <a name="permissions"></a>アクセス許可  
 VIEW SERVER STATE 権限が必要です。  
  
  
