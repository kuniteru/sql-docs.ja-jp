---
title: AffectEnum |Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- AffectEnum
helpviewer_keywords:
- AffectEnum enumeration [ADO]
ms.assetid: 1ab921a0-6c57-43b4-9291-701b2599f3e8
author: rothja
ms.author: jroth
ms.openlocfilehash: 8c75c83fea1e6c8f4916180889635ddebd9cd915
ms.sourcegitcommit: 216f377451e53874718ae1645a2611cdb198808a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87242802"
---
# <a name="affectenum"></a>AffectEnum
操作の影響を受けるレコードを指定します。  
  
|定数|値|説明|  
|--------------|-----------|-----------------|  
|**adAffectAll**|3|**レコードセット**に[フィルター](../../../ado/reference/ado-api/filter-property.md)が適用されていない場合、はすべてのレコードに影響します。<br /><br /> **Filter**プロパティが文字列条件 ("Author = ' Smith '" など) に設定されている場合、操作は現在のチャプターの表示レコードに影響します。<br /><br /> **Filter**プロパティが[filtergroupenum](../../../ado/reference/ado-api/filtergroupenum.md)またはブックマークの配列のメンバーに設定されている場合、操作は**レコードセット**のすべての行に影響します。 **注: adAffectAll**は Visual Basic オブジェクトブラウザーでは非表示になっています。|  
|**adAffectAllChapters**|4|現在適用されている**フィルター**によって表示されていないものも含め、**レコードセット**のすべての兄弟チャプター内のすべてのレコードに影響します。|  
|**現在のもの**|1|現在のレコードのみに影響します。|  
|**Adています。**|2|現在の[フィルター](../../../ado/reference/ado-api/filter-property.md)プロパティの設定に適合するレコードのみに影響します。 このオプションを使用するには、 **filter**プロパティを**filtergroupenum**値または**ブックマーク**の配列に設定する必要があります。|  
  
## <a name="adowfc-equivalent"></a>同等の ADO/WFC  
 パッケージ: **com. ms. wfc. データ**  
  
|定数|  
|--------------|  
|AdoEnums|  
|AdoEnums. ALLCHAPTERS|  
|AdoEnums. CURRENT|  
|AdoEnums|  
  
## <a name="applies-to"></a>適用対象  

:::row:::
    :::column:::
        [CancelBatch メソッド (ADO)](../../../ado/reference/ado-api/cancelbatch-method-ado.md)  
        [Delete メソッド (ADO Recordset)](../../../ado/reference/ado-api/delete-method-ado-recordset.md)  
    :::column-end:::
    :::column:::
        [Resync メソッド](../../../ado/reference/ado-api/resync-method.md)  
        [UpdateBatch メソッド](../../../ado/reference/ado-api/updatebatch-method.md)  
    :::column-end:::
:::row-end:::
