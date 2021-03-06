---
title: sp_db_selective_xml_index (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_db_selective_xml_index_TSQL
- sp_db_selective_xml_index
dev_langs:
- TSQL
helpviewer_keywords:
- sp_db_selective_xml_index procedure
ms.assetid: 017301a2-4a23-4e68-82af-134f3d4892b3
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: eeed1432c6f3c3ba4f6dcd80608c2c40bd0db374
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85728211"
---
# <a name="sp_db_selective_xml_index-transact-sql"></a>sp_db_selective_xml_index (Transact-sql)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] データベースに対して選択的 XML インデックス機能を有効または無効にします。 パラメーターを指定しないでストアド プロシージャを呼び出すと、選択的 XML インデックスが特定のデータベースで有効になっている場合は 1 が返されます。  
  
> [!NOTE]  
>  このストアドプロシージャを使用して選択的 XML インデックスを無効にするには、 [transact-sql&#41;コマンド &#40;ALTER DATABASE SET オプション](../../t-sql/statements/alter-database-transact-sql-set-options.md)を使用して、データベースを単純復旧モードにする必要があります。  
  
 ![トピック リンク アイコン](../../database-engine/configure-windows/media/topic-link.gif "トピック リンク アイコン") [Transact-SQL 構文表記規則](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>構文  
  
```sql  
  
      sys.sp_db_selective_xml_index[[ @db_name = ] 'db_name'],   
[[ @action = ] 'action']  
```  
  
## <a name="arguments"></a>引数  
`[ @ db_name = ] 'db_name'`選択的 XML インデックスを有効または無効にするデータベースの名前。 *Db_name*が NULL の場合、現在のデータベースが想定されます。  
  
`[ @action = ] 'action'`インデックスを有効にするか無効にするかを決定します。 ' On '、' true '、' off '、または ' false ' 以外の別の値が渡された場合は、エラーが発生します。  
  
```  
  
Allowed values: 'on', 'off', 'true', 'false'  
```  
  
## <a name="return-code-values"></a>リターン コードの値  
 選択的 XML インデックスが特定のデータベースで有効になっている場合は**1**です。  
  
## <a name="examples"></a>例  
  
### <a name="a-enable-selective-xml-index-functionality"></a>A. 選択的 XML インデックス機能を有効にする  
 次の例では、現在のデータベースに対して選択的 XML インデックスを有効にします。  
  
```  
EXECUTE sys.sp_db_selective_xml_index  
    @db_name = NULL  
  , @action = N'on';  
GO  
```  
  
 次の例では、AdventureWorks2012 データベースで選択的 XML インデックスを有効にします。  
  
```  
EXECUTE sys.sp_db_selective_xml_index  
    @db_name = N'AdventureWorks2012'  
  , @action = N'true';  
GO  
```  
  
### <a name="b-disable-selective-xml-index-functionality"></a>B: 選択的 XML インデックス機能を無効にする  
 次の例では、現在のデータベースで選択的 XML インデックスを無効にします。  
  
```  
EXECUTE sys.sp_db_selective_xml_index  
    @db_name = NULL  
  , @action = N'off';  
GO  
```  
  
 次の例では、AdventureWorks2012 データベースに対して選択的 XML インデックスを無効にします。  
  
```  
EXECUTE sys.sp_db_selective_xml_index  
    @db_name = N'AdventureWorks2012'  
  , @action = N'false';  
GO  
```  
  
### <a name="c-detect-if-selective-xml-index-is-enabled"></a>C: 選択的 XML インデックスが有効かどうかを検出します  
 次の例では、選択的 XML インデックスが有効になっているかどうかを検出します。 選択的 XML インデックスが有効になっている場合は1を返します。  
  
```  
EXECUTE sys.sp_db_selective_xml_index;  
GO  
```  
  
## <a name="see-also"></a>関連項目  
 [選択的 XML インデックス &#40;SXI&#41;](../../relational-databases/xml/selective-xml-indexes-sxi.md)  
  
  
