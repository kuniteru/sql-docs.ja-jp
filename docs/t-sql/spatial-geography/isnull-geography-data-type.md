---
title: IsNull (geography データ型) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- IsNull (geography Data Type)
dev_langs:
- TSQL
helpviewer_keywords:
- IsNull method
ms.assetid: c031074f-bfda-4584-a3bf-4e7c324f237f
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 98a68bfbdc39bd0731e047e5d6876410d4daf263
ms.sourcegitcommit: b57d98e9b2444348f95c83a24b8eea0e6c9da58d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2020
ms.locfileid: "86552918"
---
# <a name="isnull-geography-data-type"></a>IsNull (geography データ型)
[!INCLUDE [SQL Server SQL Database](../../includes/applies-to-version/sql-asdb.md)]

  **geography** インスタンスが NULL かどうかを指定するプロパティです。 インスタンスが NULL の場合は "TRUE" を、NULL ではない場合は 0 を返します。  
  
## <a name="syntax"></a>構文  
  
```  
  
.IsNull  
```  
  
[!INCLUDE[sql-server-tsql-previous-offline-documentation](../../includes/sql-server-tsql-previous-offline-documentation.md)]

## <a name="return-types"></a>戻り値の型
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 型: **bit**  
  
 CLR の型: **SqlBoolean**  
  
## <a name="remarks"></a>解説  
 `IsNull` では、**geography** インスタンスが NULL かどうかをテストできます。 このテストの結果は若干複雑であるため注意してください。インスタンスが NULL でなければ 0 を返し、インスタンスが NULL であれば NULL を返します。  
  
 このメソッドは、主に [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] インフラストラクチャによって使用されます。**geography** インスタンスが NULL かどうかをテストするために T-SQL 述語の IS NULL を使用することをお勧めします。 T-SQL 述語の IS NULL の詳細については、「[IS NULL &#40;Transact-SQL&#41;](../../t-sql/queries/is-null-transact-sql.md)」を参照してください。  
  
## <a name="examples"></a>例  
  
## <a name="see-also"></a>参照  
 [Geography インスタンスの拡張メソッド](../../t-sql/spatial-geography/extended-methods-on-geography-instances.md)  
  
  
