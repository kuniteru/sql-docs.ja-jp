---
title: '@@PACK_SENT (Transact-SQL) | Microsoft Docs'
ms.custom: ''
ms.date: 09/18/2017
ms.prod: sql
ms.prod_service: sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- '@@PACK_SENT'
- '@@PACK_SENT_TSQL'
dev_langs:
- TSQL
helpviewer_keywords:
- number of output packets written
- '@@PACK_SENT function'
- packets [SQL Server], output
- networking [SQL Server], output packets
- connections [SQL Server], packets
- output packets written to network [SQL Server]
ms.assetid: 8a322162-24c9-48e9-bfa4-c060e4e11dba
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: da77f0255a67c175537dd6ba5ea6030555f31c68
ms.sourcegitcommit: 768f046107642f72693514f51bf2cbd00f58f58a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "87110849"
---
# <a name="x40x40pack_sent-transact-sql"></a>&#x40;&#x40;PACK_SENT (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] が起動してからネットワークに書き込まれた出力パケット数を返します。  
  
 ![トピック リンク アイコン](../../database-engine/configure-windows/media/topic-link.gif "トピック リンク アイコン") [Transact-SQL 構文表記規則](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>構文  
  
```sql
@@PACK_SENT  
```  
  
[!INCLUDE[sql-server-tsql-previous-offline-documentation](../../includes/sql-server-tsql-previous-offline-documentation.md)]

## <a name="return-types"></a>戻り値の型
 **integer**  
  
## <a name="remarks"></a>解説  
 いくつか含むレポートを表示する [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 送信または受信されると、パケットをなどの統計情報の実行 **sp_monitor** です。  
  
## <a name="examples"></a>例  
 次の例は、`@@PACK_SENT` の使用方法を示しています。  
  
```sql
SELECT @@PACK_SENT AS 'Pack Sent';  
```  
  
 次に結果セットの例を示します。  
  
```  
Pack Sent  
-----------  
291  
```  
  
## <a name="see-also"></a>参照  
 [@@PACK_RECEIVED &#40;Transact-SQL&#41;](../../t-sql/functions/pack-received-transact-sql.md)   
 [sp_monitor &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-monitor-transact-sql.md)   
 [システム統計関数 &#40;Transact-SQL&#41;](../../t-sql/functions/system-statistical-functions-transact-sql.md)  
  
  
