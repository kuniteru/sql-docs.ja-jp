---
title: CancelUpdate メソッド (ADO) |Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Recordset15::CancelUpdate
helpviewer_keywords:
- CancelUpdate method [ADO]
ms.assetid: eaa856cc-c786-462e-890c-c896261b1741
author: rothja
ms.author: jroth
ms.openlocfilehash: 0ecc08dde974826846058d4d8927df202367d28d
ms.sourcegitcommit: 216f377451e53874718ae1645a2611cdb198808a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87242409"
---
# <a name="cancelupdate-method-ado"></a>CancelUpdate メソッド (ADO)
[Update](../../../ado/reference/ado-api/update-method.md)メソッドを呼び出す前に、[レコードセット](../../../ado/reference/ado-api/recordset-object-ado.md)オブジェクトの現在または新しい行、または[レコード](../../../ado/reference/ado-api/record-object-ado.md)オブジェクトの[Fields](../../../ado/reference/ado-api/fields-collection-ado.md)コレクションに対して行われたすべての変更をキャンセルします。  
  
## <a name="syntax"></a>構文  
  
```  
  
recordset.CancelUpdaterecord.Fields.CancelUpdate  
```  
  
## <a name="remarks"></a>解説  
  
## <a name="recordset"></a>レコードセット  
 **CancelUpdate**メソッドを使用して、現在の行に対して行われた変更を取り消すか、新しく追加した行を破棄します。 **Update**メソッドを呼び出した後、現在の行または新しい行への変更を取り消すことはできません。ただし、変更がトランザクションの一部である場合は、 [RollbackTrans](../../../ado/reference/ado-api/begintrans-committrans-and-rollbacktrans-methods-ado.md)メソッドを使用してロールバックするか、バッチ更新の一部にする必要があります。 バッチ更新の場合は、 **CancelUpdate**または[CancelBatch](../../../ado/reference/ado-api/cancelbatch-method-ado.md)メソッドを使用して**更新**を取り消すことができます。  
  
 **CancelUpdate**メソッドを呼び出すときに新しい行を追加する場合、現在の行は、 [AddNew](../../../ado/reference/ado-api/addnew-method-ado.md)呼び出しの前の現在の行になります。  
  
 編集モードで、移動、 [NextRecordset](../../../ado/reference/ado-api/nextrecordset-method-ado.md)、または[閉じる](../../../ado/reference/ado-api/close-method-ado.md)メソッドを使用して、現在のレコードから移動する場合は、 **CancelUpdate**を使用して保留[中の変更](../../../ado/reference/ado-api/move-method-ado.md)を取り消すことができます。 更新をデータソースに正常に送信できない場合は、この操作が必要になることがあります。 たとえば、参照整合性違反によって失敗した削除を試みた場合、[削除](../../../ado/reference/ado-api/delete-method-ado-recordset.md)の呼び出し後に、**レコードセット**は編集モードのままになります。  
  
## <a name="record"></a>Record  
 **CancelUpdate**メソッドでは、[フィールド](../../../ado/reference/ado-api/field-object.md)オブジェクトの保留中の挿入または削除がキャンセルされ、既存のフィールドの保留中の更新が取り消され、元の値に復元されます。 **Fields**コレクション内のすべてのフィールドの[Status](../../../ado/reference/ado-api/status-property-ado-recordset.md)プロパティは、 **adFieldOK**に設定されています。  
  
## <a name="applies-to"></a>適用対象  

:::row:::
    :::column:::
        [Fields コレクション (ADO)](../../../ado/reference/ado-api/fields-collection-ado.md)  
    :::column-end:::
    :::column:::
        [Recordset オブジェクト (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)  
    :::column-end:::
:::row-end:::

## <a name="see-also"></a>参照  
 [Update および CancelUpdate メソッドの例 (VB)](../../../ado/reference/ado-api/update-and-cancelupdate-methods-example-vb.md)   
 [Update および CancelUpdate メソッドの例 (VC + +)](../../../ado/reference/ado-api/update-and-cancelupdate-methods-example-vc.md)   
 [AddNew メソッド (ADO)](../../../ado/reference/ado-api/addnew-method-ado.md)   
 [Cancel メソッド (ADO)](../../../ado/reference/ado-api/cancel-method-ado.md)   
 [Cancel メソッド (RDS)](../../../ado/reference/rds-api/cancel-method-rds.md)   
 [CancelBatch メソッド (ADO)](../../../ado/reference/ado-api/cancelbatch-method-ado.md)   
 [CancelUpdate メソッド (RDS)](../../../ado/reference/rds-api/cancelupdate-method-rds.md)   
 [EditMode プロパティ](../../../ado/reference/ado-api/editmode-property.md)   
 [Update メソッド](../../../ado/reference/ado-api/update-method.md)
