---
title: modify() メソッド (xml データ型)
ms.custom: ''
ms.date: 07/26/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- modify() method
- modify method
ms.assetid: 52430735-51f4-46d1-a308-9aecf8648fda
author: MightyPen
ms.author: genemi
ms.openlocfilehash: 52a2766833d6ab4349c3f6b000f35e9d686396bd
ms.sourcegitcommit: cb620c77fe6bdefb975968837706750c31048d46
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "86393090"
---
# <a name="modify-method-xml-data-type"></a>modify() メソッド (xml データ型)
[!INCLUDE [SQL Server SQL Database](../../includes/applies-to-version/sql-asdb.md)]

  XML ドキュメントのコンテンツを変更します。 **xml** 型の変数または列のコンテンツを変更するには、このメソッドを使用します。 このメソッドは XML DML ステートメントを使用して、XML データのノードの挿入、更新、削除を行います。 **xml** データ型の **modify()** メソッドは、UPDATE ステートメントの SET 句内でしか使用できません。  
  
## <a name="syntax"></a>構文  
  
```  
  
modify (XML_DML)  
```  
  
[!INCLUDE[sql-server-tsql-previous-offline-documentation](../../includes/sql-server-tsql-previous-offline-documentation.md)]

## <a name="arguments"></a>引数
 XML_DML  
 XML DML (データ操作言語) の文字列です。 XML ドキュメントは、この表記に従って更新されます。  
  
> [!NOTE]  
>  **modify()** メソッドが NULL 値を使用して呼び出される場合、または結果が NULL 値になる場合、エラーが返されます。  
  
## <a name="examples"></a>例  
 **modify()** メソッドには XML データ操作言語 (DML) の文字列が必要なので、**modify()** のサンプルは XML DML ステートメントについて説明するトピックに含まれています。 これらの例については、「[&#40;XML DML&#41; の挿入](../../t-sql/xml/insert-xml-dml.md)」、「[&#40;XML DML&#41; の削除](../../t-sql/xml/delete-xml-dml.md)」、および「[&#40;XML DML&#41; の値の置き換え](../../t-sql/xml/replace-value-of-xml-dml.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [XML データのインスタンスの作成](../../relational-databases/xml/create-instances-of-xml-data.md)   
 [xml データ型メソッド](../../t-sql/xml/xml-data-type-methods.md)   
 [XML データ変更言語 &#40;XML DML&#41;](../../t-sql/xml/xml-data-modification-language-xml-dml.md)  
  
  
