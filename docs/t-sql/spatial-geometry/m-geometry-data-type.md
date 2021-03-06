---
title: M (geometry データ型) | Microsoft Docs
ms.custom: ''
ms.date: 08/03/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- M (geometry Data Type)
- M_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- M (geometry Data Type)
ms.assetid: 443ae2ea-739b-41ef-96cc-ac5dfd65e10b
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: b8d0c4dd1b813ce5da8f0272a0c2e19e7beab1c6
ms.sourcegitcommit: b57d98e9b2444348f95c83a24b8eea0e6c9da58d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2020
ms.locfileid: "86555676"
---
# <a name="m-geometry-data-type"></a>M (geometry データ型)
[!INCLUDE [SQL Server SQL Database](../../includes/applies-to-version/sql-asdb.md)]

  **geometry** インスタンスの **M** (メジャー) 値。 メジャー値のセマンティクスはユーザー定義です。  

## <a name="syntax"></a>構文  
  
```  
  
.M  
```  
  
[!INCLUDE[sql-server-tsql-previous-offline-documentation](../../includes/sql-server-tsql-previous-offline-documentation.md)]

## <a name="arguments"></a>引数
  
## <a name="return-types"></a>戻り値の型  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] の型: **float**  
  
 CLR の型: **SqlDouble**  
  
## <a name="remarks"></a>解説  
 **geometry** インスタンスが **Point** ではない場合や、**Point** インスタンスにこのプロパティの値が設定されていない場合は、このプロパティの値は null になります。  
  
 このプロパティは読み取り専用です。  
  
 **M** 値は、ライブラリによる計算で使用されていないと、ライブラリによる計算によって渡されることはありません。  
  
## <a name="examples"></a>例  
 次の例では、Z (標高) 値と M (メジャー) 値を含む `Point` インスタンスを作成し、`M` を使用してインスタンスの M 値をフェッチします。  
  
```  
DECLARE @g geometry;  
SET @g = geometry::STGeomFromText('POINT(1 2 3 4)', 0);  
SELECT @g.M;  
```  
  
## <a name="see-also"></a>参照  
 [Geometry インスタンスの拡張メソッド](../../t-sql/spatial-geometry/extended-methods-on-geometry-instances.md)   
 [Z &#40;geometry データ型&#41;](../../t-sql/spatial-geometry/z-geometry-data-type.md)   
 [AsTextZM &#40;geometry データ型&#41;](../../t-sql/spatial-geometry/astextzm-geometry-data-type.md)  
  
  

