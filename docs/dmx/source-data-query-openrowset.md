---
title: OPENROWSET (DMX) |Microsoft Docs
ms.date: 06/07/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: dmx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: b19b897b65ffb3a4c9e940370ffdead1e10b6d31
ms.sourcegitcommit: 205de8fa4845c491914902432791bddf11002945
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "86970323"
---
# <a name="ltsource-data-querygt---openrowset"></a>&lt;ソースデータクエリ &gt; -OPENROWSET
[!INCLUDE[ssas](../includes/applies-to-version/ssas.md)]

  ソースデータクエリをクエリに置き換えます。 INSERT、SELECT FROM 予測結合、および SELECT FROM ナチュラル予測結合ステートメントでは、 **OPENROWSET**がサポートされています。  
  
## <a name="syntax"></a>構文  
  
```  
  
OPENROWSET(provider_name,provider_string,query_syntax)  
```  
  
## <a name="arguments"></a>引数  
 *provider_name*  
 OLE DB プロバイダー名。  
  
 *provider_string*  
 指定したプロバイダーの OLE DB 接続文字列。  
  
 *query_syntax*  
 行セットを返すクエリ構文です。  
  
## <a name="remarks"></a>注釈  
 データマイニングプロバイダーは、 *provider_name*と*provider_string*を使用してデータソースオブジェクトへの接続を確立し、 *query_syntax*で指定されたクエリを実行して、ソースデータから行セットを取得します。  
  
## <a name="examples"></a>例  
 次の例は、予測結合ステートメント内で、SELECT ステートメントを使用してデータベースからデータを取得するために使用でき [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] [!INCLUDE[tsql](../includes/tsql-md.md)] ます。  
  
```  
OPENROWSET  
(  
'SQLOLEDB.1',  
'Provider=SQLOLEDB.1;Integrated Security=SSPI;Persist Security     Info=False;Initial Catalog=AdventureWorksDW2012;Data Source=localhost',  
'SELECT TOP 1000 * FROM vTargetMail'  
)  
```  
  
## <a name="see-also"></a>参照  
 [&#60;ソースデータクエリ&#62;](../dmx/source-data-query.md)   
 [DMX&#41; データ操作ステートメントを &#40;データマイニング拡張機能](../dmx/dmx-statements-data-manipulation.md)   
 [データ マイニング拡張機能 &#40;DMX&#41; ステートメント リファレンス](../dmx/data-mining-extensions-dmx-statements.md)  
  
  
