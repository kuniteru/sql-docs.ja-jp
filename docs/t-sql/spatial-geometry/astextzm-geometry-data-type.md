---
title: AsTextZM (geometry データ型) | Microsoft Docs
ms.custom: ''
ms.date: 08/03/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- AsTextZM_TSQL
- AsTextZM
- AsTextZM (geometry Data Type)
- AsTextZM_(geometry_Data_Type)_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- AsTextZM (geometry Data Type)
ms.assetid: 08ac8aa0-aff7-4b22-87e0-1a1d55dcbc04
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: d3a321893f6764eb2d6d8de97cf2d3d1dc5fbc65
ms.sourcegitcommit: b57d98e9b2444348f95c83a24b8eea0e6c9da58d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2020
ms.locfileid: "86555707"
---
# <a name="astextzm-geometry-data-type"></a>AsTextZM (geometry データ型)
[!INCLUDE [SQL Server SQL Database](../../includes/applies-to-version/sql-asdb.md)]

インスタンスに格納されている **Z** (標高) 値および **M** (メジャー) 値で補完された geometry インスタンスについて、Open Geospatial Consortium (OGC) Well-Known Text (WKT) 表現を返します。
  
## <a name="syntax"></a>構文  
  
```  
  
.AsTextZM ()  
```  
  
[!INCLUDE[sql-server-tsql-previous-offline-documentation](../../includes/sql-server-tsql-previous-offline-documentation.md)]

## <a name="return-types"></a>戻り値の型
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 戻り値の型: **nvarchar(max)**  
  
 CLR の戻り値の型: **SqlChars**  
  
## <a name="remarks"></a>解説  
  
## <a name="examples"></a>例  
 **Z** (標高) 値および **M** (メジャー) 値を含む `Point` インスタンスを作成する例を次に示します。 `STAsText()` は WKT 値 (1 2) を選択します。`AsTextZM()` は同じ WKT 値を選択し、**Z** および **M** の値も返すため、(1 2 3 4) が出力されます。  
  
```  
DECLARE @g geometry;  
SET @g = geometry::STGeomFromText('POINT(1 2 3 4)', 0);  
SELECT @g.STAsText();  
SELECT @g.AsTextZM();  
```  
  
## <a name="see-also"></a>参照  
 [Geometry インスタンスの拡張メソッド](../../t-sql/spatial-geometry/extended-methods-on-geometry-instances.md)   
 [M &#40;geometry データ型&#41;](../../t-sql/spatial-geometry/m-geometry-data-type.md)   
 [Z &#40;geometry データ型&#41;](../../t-sql/spatial-geometry/z-geometry-data-type.md)  
  
  

