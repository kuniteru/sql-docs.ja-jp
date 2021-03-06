---
title: sys.sysデバイス (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 03/15/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sysdevices
- sysdevices_TSQL
- sys.sysdevices
- sys.sysdevices_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.sysdevices compatibility view
- sysdevices system table
ms.assetid: ac5bcaf4-8fb6-4855-8856-d7643f469361
author: rothja
ms.author: jroth
ms.openlocfilehash: 56196f6a9e4ce1929bd7fd9b65a9853d3794da4d
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "85883751"
---
# <a name="syssysdevices-transact-sql"></a>sys.sysデバイス (Transact-sql)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  ディスクバックアップファイル、テープバックアップファイル、およびデータベースファイルごとに1行のデータを格納します。  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssnoteCompView](../../includes/ssnotecompview-md.md)]  
  
|列名|データ型|説明|  
|-----------------|---------------|-----------------|  
|**name**|**sysname**|バックアップ ファイルまたはデータベース ファイルの論理名。|  
|**size**|**int**|ファイルのサイズ (2 kb ページ単位)。|  
|**low**|**int**|旧バージョンとの互換性のためにだけ用意されています。|  
|**high**|**int**|旧バージョンとの互換性のためにだけ用意されています。|  
|**status**|**smallint**|デバイスの種類を示すビットマップ:<br /><br /> 1 = 既定のディスク<br /><br /> 2 = 物理ディスク<br /><br /> 4 = 論理ディスク<br /><br /> 8 = ヘッダーをスキップ<br /><br /> 16 = バックアップファイル<br /><br /> 32 = シリアル書き込み<br /><br /> 4096 = 読み取り専用|  
|**cntrltype**|**smallint**|コントローラーの種類:<br /><br /> 0 = CD-ROM 以外のデータベースファイル<br /><br /> 2 = ディスクバックアップファイル<br /><br /> 3-4 = フロッピーディスクバックアップファイル<br /><br /> 5 = テープバックアップファイル<br /><br /> 6 = 名前付きパイプファイル|  
|**phyname**|**nvarchar(260)**|物理ファイルの名前。|  
  
## <a name="see-also"></a>関連項目  
 [システムビューへのシステムテーブルのマッピング &#40;Transact-sql&#41;](../../relational-databases/system-tables/mapping-system-tables-to-system-views-transact-sql.md)   
 [互換性ビュー &#40;Transact-SQL&#41;](~/relational-databases/system-compatibility-views/system-compatibility-views-transact-sql.md)  
  
  
