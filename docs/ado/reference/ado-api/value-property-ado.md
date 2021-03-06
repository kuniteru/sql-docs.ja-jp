---
title: Value プロパティ (ADO) |Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 03/20/2018
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Field20::Value
- _Parameter::Value
helpviewer_keywords:
- Value property [ADO]
ms.assetid: 48919c74-86d4-462e-99b9-8854ceb8d683
author: rothja
ms.author: jroth
ms.openlocfilehash: c84ab6806924649bdad9bb712f730c24011cdb38
ms.sourcegitcommit: 216f377451e53874718ae1645a2611cdb198808a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87243163"
---
# <a name="value-property-ado"></a>Value プロパティ (ADO)

[フィールド](../../../ado/reference/ado-api/field-object.md)、[パラメーター](../../../ado/reference/ado-api/parameter-object.md)、または[プロパティ](../../../ado/reference/ado-api/property-object-ado.md)オブジェクトに割り当てられた値を示します。
  
## <a name="settings-and-return-values"></a>設定と戻り値

オブジェクトの値を示す**バリアント**値を設定または返します。 既定値は[Type](../../../ado/reference/ado-api/type-property-ado.md)プロパティによって異なります。
  
## <a name="remarks"></a>解説

**Value**プロパティを使用して、**フィールド**オブジェクトのデータを設定または取得します。また、**パラメーターオブジェクトを**使用してパラメーター値を設定または取得するか、プロパティオブジェクトを使用し**てプロパティ設定**を設定または取得します。 **値**プロパティが読み取り/書き込みか、読み取り専用かは、さまざまな要因によって決まります。 詳細については、各オブジェクトのトピックを参照してください。

ADO では、 **Value**プロパティを使用して長いバイナリデータを設定し、返すことができます。
  
> [!NOTE]
> **パラメーター**オブジェクトの場合、ADO は、プロバイダーから**値**プロパティを1回だけ読み取ります。 **値**プロパティが空である**パラメーター**がコマンドに含まれていて、コマンドから[レコードセット](../../../ado/reference/ado-api/recordset-object-ado.md)を作成する場合は、まず、**値**プロパティを取得する前に**レコードセット**を閉じてください。 それ以外の場合、一部のプロバイダーでは、 **value**プロパティが空で、適切な値が含まれません。
> 
> [レコード](../../../ado/reference/ado-api/record-object-ado.md)オブジェクトの[Fields](../../../ado/reference/ado-api/fields-collection-ado.md)コレクションに追加された新しい**Field**オブジェクトの場合は、他の**フィールド**プロパティを指定する前に、 **Value**プロパティを設定する必要があります。 最初に、**値**プロパティの特定の値が割り当てられており、という**フィールド**コレクションで[更新](../../../ado/reference/ado-api/update-method.md)されている必要があります。 その後、[型](../../../ado/reference/ado-api/type-property-ado.md)や[属性](../../../ado/reference/ado-api/attributes-property-ado.md)などの他のプロパティにアクセスできます。
  
## <a name="applies-to"></a>適用対象

:::row:::
    :::column:::
        [Field オブジェクト](../../../ado/reference/ado-api/field-object.md)  
    :::column-end:::
    :::column:::
        [Parameter オブジェクト](../../../ado/reference/ado-api/parameter-object.md)  
    :::column-end:::
    :::column:::
        [Property オブジェクト (ADO)](../../../ado/reference/ado-api/property-object-ado.md)  
    :::column-end:::
:::row-end:::

## <a name="see-also"></a>参照

[Value プロパティの例 (VB)](../../../ado/reference/ado-api/value-property-example-vb.md) 
[Value プロパティの例 (VC + +)](../../../ado/reference/ado-api/value-property-example-vc.md) 
