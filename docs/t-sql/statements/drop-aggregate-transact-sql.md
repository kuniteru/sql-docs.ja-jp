---
title: DROP AGGREGATE (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 05/10/2017
ms.prod: sql
ms.prod_service: sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- DROP_AGGREGATE_TSQL
- DROP AGGREGATE
dev_langs:
- TSQL
helpviewer_keywords:
- aggregate functions [SQL Server], removing
- removing user-defined functions
- dropping user-defined functions
- user-defined functions [CLR integration]
- deleting user-defined functions
- DROP AGGREGATE statement
ms.assetid: 84ffc4e7-c451-4f1f-9a67-7fc3a120e53f
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 3af850b4154726ea300688a0d155c39c1b262828
ms.sourcegitcommit: edba1c570d4d8832502135bef093aac07e156c95
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "86483641"
---
# <a name="drop-aggregate-transact-sql"></a>DROP AGGREGATE (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  ユーザー定義集計関数を現在のデータベースから削除します。 ユーザー定義集計関数は、[CREATE AGGREGATE](../../t-sql/statements/create-aggregate-transact-sql.md) を使用して作成されます。  
  
 ![トピック リンク アイコン](../../database-engine/configure-windows/media/topic-link.gif "トピック リンク アイコン") [Transact-SQL 構文表記規則](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>構文  
  
```  
DROP AGGREGATE [ IF EXISTS ] [ schema_name . ] aggregate_name  
```  
  
[!INCLUDE[sql-server-tsql-previous-offline-documentation](../../includes/sql-server-tsql-previous-offline-documentation.md)]

## <a name="arguments"></a>引数
 *IF EXISTS*  
 **適用対象**: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ([!INCLUDE[ssSQL15](../../includes/sssql15-md.md)] から[現在のバージョン](https://go.microsoft.com/fwlink/p/?LinkId=299658)まで)。  
  
 条件付きでは既に存在する場合にのみ、集計を削除します。  
  
 *schema_name*  
 ユーザー定義集計関数が所属しているスキーマの名前です。  
  
 *aggregate_name*  
 削除するユーザー定義集計関数の名前です。  
  
## <a name="remarks"></a>解説  
 削除対象のユーザー定義集計関数を参照するスキーマ バインドで作成された、ビュー、関数、またはストアド プロシージャが存在する場合は、DROP AGGREGATE は実行されません。  
  
## <a name="permissions"></a>アクセス許可  
 DROP AGGREGATE を実行するには、少なくとも、ユーザー定義集計関数が属するスキーマに対する ALTER 権限か、集計関数自体に対する CONTROL 権限が必要です。  
  
## <a name="examples"></a>例  
 次の例では、集計関数 `Concatenate` を削除します。  
  
```  
DROP AGGREGATE dbo.Concatenate;  
```  
  
## <a name="see-also"></a>参照  
 [CREATE AGGREGATE &#40;Transact-SQL&#41;](../../t-sql/statements/create-aggregate-transact-sql.md)   
 [ユーザー定義集計の作成](../../relational-databases/user-defined-functions/create-user-defined-aggregates.md)  
  
  
