---
title: XML データの一括読み込みの実行 (SQLXML)
description: SQLXML 4.0 で XML 一括読み込みを使用して Microsoft SQL Server テーブルに半構造化 XML データを読み込む方法について説明します。
ms.date: 03/17/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XML Bulk Load [SQLXML]
- bulk load [SQLXML]
- data insertions [SQLXML]
- SQLXML, bulk loading
- XSD schemas [SQLXML], XML Bulk Load
- XDR schemas [SQLXML], XML Bulk Load
- inserting data
ms.assetid: 3708b493-322e-4f3c-9b27-441d0c0ee346
author: MightyPen
ms.author: genemi
ms.custom: seo-lt-2019
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: c696f39c3e41afa42f5f4f0fac5c7dfd1a4dd080
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85773075"
---
# <a name="performing-bulk-load-of-xml-data-sqlxml-40"></a>XML データの一括読み込みの実行 (SQLXML 4.0)
[!INCLUDE [SQL Server Azure SQL Database](../../../includes/applies-to-version/sql-asdb.md)]
  XML 一括読み込みはスタンドアロン COM オブジェクトであり、これを使用すると、半構造化された XML データを Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] テーブルに読み込むことができます。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [XML 一括読み込みの概要 &#40;SQLXML 4.0&#41;](../../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/introduction-to-xml-bulk-load-sqlxml-4-0.md)  
 XML 一括読み込みユーティリティで XML データの一括読み込みを実行する際の一般的な情報を提供します。 たとえば、XML データ ストリーミングや、トランザクション モードとトランザクション以外のモードでの一括読み込み操作について説明します。  
  
 [SQLXML 4.0&#41;&#40;レコード生成プロセス](../../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/record-generation-process-sqlxml-4-0.md)  
 XML 一括読み込みのレコードが生成されるプロセスと規則について説明します。  
  
 [SQLXML 4.0 &#40;の注釈の解釈&#41;](../../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/annotation-interpretation-sqlxml-4-0.md)  
 XML 一括読み込みで XSD および XDR スキーマ内の注釈がどのように解釈されるかについて説明します。  
  
 [SQL Server XML 一括読み込みオブジェクトモデル &#40;SQLXML 4.0&#41;](../../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/sql-server-xml-bulk-load-object-model-sqlxml-4-0.md)  
 SQLXMLBulkLoad オブジェクトとそのメソッドとプロパティについて説明します。  
  
 [XML 一括読み込みの例 &#40;SQLXML 4.0&#41;](../../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/xml-bulk-load-examples-sqlxml-4-0.md)  
 XML 一括読み込みを使用したコードの例を提供します。  
  
 [データ型と XML 一括読み込みの動作 &#40;SQLXML 4.0&#41;](../../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/data-types-and-xml-bulk-load-behavior-sqlxml-4-0.md)  
 XSD と XDR での、さまざまな XML 一括読み込み動作について説明します。  
  
 [XML 一括読み込みのガイドラインと制限 &#40;SQLXML 4.0&#41;](../../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/guidelines-and-limitations-of-xml-bulk-load-sqlxml-4-0.md)  
 XML 一括読み込みを扱うときに注意すべき問題をいくつか示します。  
  
  
