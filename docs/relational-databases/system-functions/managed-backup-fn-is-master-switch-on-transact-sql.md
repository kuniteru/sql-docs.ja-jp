---
title: managed_backup。 fn_is_master_switch_on (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- fn_is_master_switch_on
- fn_is_master_switch_on_TSQL
- smart_admin.fn_is_master_switch_on
- smart_admin.fn_is_master_switch_on_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- smart_admin.fn_is_master_switch_on
- fn_is_master_switch_on
ms.assetid: e8c2108d-b104-46cb-9645-a15f46112c86
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a697cff22257c49774c91dc0b5c646034e34fba1
ms.sourcegitcommit: 703968b86a111111a82ef66bb7467dbf68126051
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "86053418"
---
# <a name="managed_backupfn_is_master_switch_on-transact-sql"></a>managed_backup。 fn_is_master_switch_on (Transact-sql)
[!INCLUDE [sqlserver2016](../../includes/applies-to-version/sqlserver2016.md)]

  SQL Server のインスタンスにおける [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)]操作の状態を返します。  
  
 この関数を使用すると、[!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)]の現在の状態を取得できます。  
  
 
 ![トピック リンク アイコン](../../database-engine/configure-windows/media/topic-link.gif "トピック リンク アイコン") [Transact-SQL 構文表記規則](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>構文  
  
```sql  
managed_backup.fn_is_master_switch_on ()  
```  
  
##  <a name="arguments"></a><a name="Arguments"></a>数値  
 なし  
  
## <a name="return-type"></a>戻り値の型  
 **16-BIT**  
  
 1 = [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)]はアクティブです。0 = [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)]は一時停止しています。  
  
## <a name="security"></a>Security  
  
### <a name="permissions"></a>アクセス許可  
 この関数に対する SELECT 権限が必要です。  
  
## <a name="see-also"></a>参照  
 [Microsoft Azure への SQL Server マネージド バックアップ](../../relational-databases/backup-restore/sql-server-managed-backup-to-microsoft-azure.md)  
  
  
