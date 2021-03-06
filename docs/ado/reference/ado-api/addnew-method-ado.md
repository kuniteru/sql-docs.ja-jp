---
title: AddNew メソッド (ADO) |Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Recordset15::AddNew
- Recordset15::raw_AddNew
helpviewer_keywords:
- AddNew method [ADO]
ms.assetid: a9f54be9-5763-45d0-a6eb-09981b03bc08
author: rothja
ms.author: jroth
ms.openlocfilehash: a6359d1b9f69963120e9446c47aa5473beedd127
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2020
ms.locfileid: "82760728"
---
# <a name="addnew-method-ado"></a>AddNew メソッド (ADO)
更新可能な[レコードセット](../../../ado/reference/ado-api/recordset-object-ado.md)オブジェクトの新しいレコードを作成します。  
  
## <a name="syntax"></a>構文  
  
```  
  
recordset.AddNew FieldList, Values  
```  
  
#### <a name="parameters"></a>パラメーター  
 *レコードセット*  
 **レコードセット**オブジェクトです。  
  
 *FieldList*  
 任意。 単一の名前、または新しいレコード内のフィールドの名前または序数の配列。  
  
 *値*  
 任意。 単一の値、または新しいレコードのフィールドの値の配列。 *Fieldlist*が配列の場合、*値*も同じメンバー数の配列である必要があります。それ以外の場合は、エラーが発生します。 フィールド名の順序は、各配列のフィールド値の順序と一致している必要があります。  
  
## <a name="remarks"></a>Remarks  
 **AddNew**メソッドを使用して、新しいレコードを作成して初期化します。 現在の**レコードセット**オブジェクトにレコードを追加できるかどうかを確認するには、 **Adaddnew**で[サポート](../../../ado/reference/ado-api/supports-method.md)メソッド ([カーソルオプションの列挙](../../../ado/reference/ado-api/cursoroptionenum.md)値) を使用します。  
  
 **AddNew**メソッドを呼び出すと、新しいレコードが現在のレコードになり、 [Update](../../../ado/reference/ado-api/update-method.md)メソッドを呼び出した後も最新の状態が維持されます。 新しいレコードは**レコードセット**に追加されるため、更新後の**MoveNext**への呼び出しは、**レコードセット**の末尾を越えて移動され、 **EOF**が True になります。 **Recordset**オブジェクトがブックマークをサポートしていない場合、別のレコードに移動すると、新しいレコードにアクセスできなくなることがあります。 カーソルの種類によっては、 [Requery](../../../ado/reference/ado-api/requery-method.md)メソッドを呼び出して、新しいレコードにアクセスできるようにすることが必要になる場合があります。  
  
 現在のレコードを編集しているとき、または新しいレコードを追加しているときに**AddNew**を呼び出した場合、ADO は**Update**メソッドを呼び出して変更を保存し、新しいレコードを作成します。  
  
 **AddNew**メソッドの動作は、**レコードセット**オブジェクトの更新モードと、 *Fieldlist*引数と*Values*引数を渡すかどうかによって異なります。  
  
 **Update**メソッドを呼び出した後、プロバイダーが基になるデータソースに変更を書き込む*即時更新モード*では、引数を指定せずに**AddNew**メソッドを呼び出すと、 [EditMode](../../../ado/reference/ado-api/editmode-property.md)プロパティが**adEditAdd** ( [editmodeenum](../../../ado/reference/ado-api/editmodeenum.md)値) に設定されます。 プロバイダーは、フィールド値の変更をローカルにキャッシュします。 **Update**メソッドを呼び出すと、新しいレコードがデータベースにポストされ、 **EditMode**プロパティが**adEditNone** ( **editmodeenum**値) にリセットされます。 *Fieldlist*引数と*Values*引数を渡すと、ADO はすぐに新しいレコードをデータベースにポストします (**更新**呼び出しは必要ありません)。**EditMode**プロパティ値は変更されません (**adEditNone**)。  
  
 *バッチ更新モード*(プロバイダーによって複数の変更がキャッシュされ、 [UpdateBatch](../../../ado/reference/ado-api/updatebatch-method.md)メソッドを呼び出したときに基になるデータソースに書き込まれる) では、引数を指定せずに**AddNew**メソッドを呼び出すと、 **EditMode**プロパティが**adEditAdd**に設定されます。 プロバイダーは、フィールド値の変更をローカルにキャッシュします。 **Update**メソッドを呼び出すと、現在のレコード**セット**に新しいレコードが追加されますが、プロバイダーは、基になるデータベースに変更を送信したり、 **adEditNone**をリセットしてから、 **UpdateBatch**メソッドを呼び出さ**ないように**したりします。 *Fieldlist*引数と*Values*引数を渡すと、ADO はキャッシュ内のストレージとして新しいレコードをプロバイダーに送信し、 **EditMode**を**adEditAdd**に設定します。新しいレコードを基になるデータベースにポストするには、 **UpdateBatch**メソッドを呼び出す必要があります。  
  
## <a name="example"></a>例  
 次の例は、フィールドリストと値リストを含む AddNew メソッドを使用して、フィールドリストと値リストを配列として含める方法を示しています。  
  
```  
create table aa1 (intf int, charf char(10))  
insert into aa1 values (2, 'aa')  
  
Dim cn As New adodb.Connection  
Dim rs As New adodb.Recordset  
Dim cmd As New adodb.Command  
  
cn.ConnectionString = "Provider=SQLOLEDB;Data Source=alexverb2;uid=sa;pwd=foo$bar00;"  
  
cn.Open  
rs.Open "select * from xxx..aa1", cn, adOpenKeyset, adLockOptimistic  
  
Dim fieldsArray(1) As Variant  
fieldsArray(0) = "intf"  
fieldsArray(1) = "charf"  
Dim values(1) As Variant  
values(0) = 4  
values(1) = "as"  
rs.AddNew fieldsArray, values  
rs.Update  
```  
  
## <a name="applies-to"></a>適用対象  
 [Recordset オブジェクト (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)  
  
## <a name="see-also"></a>参照  
 [AddNew メソッドの例 (VB)](../../../ado/reference/ado-api/addnew-method-example-vb.md)   
 [AddNew メソッドの例 (VBScript)](../../../ado/reference/ado-api/addnew-method-example-vbscript.md)   
 [AddNew メソッドの例 (VC + +)](../../../ado/reference/ado-api/addnew-method-example-vc.md)   
 [CancelUpdate メソッド (ADO)](../../../ado/reference/ado-api/cancelupdate-method-ado.md)   
 [EditMode プロパティ](../../../ado/reference/ado-api/editmode-property.md)   
 [Requery メソッド](../../../ado/reference/ado-api/requery-method.md)   
 [サポートメソッド](../../../ado/reference/ado-api/supports-method.md)   
 [Update メソッド](../../../ado/reference/ado-api/update-method.md)   
 [UpdateBatch メソッド](../../../ado/reference/ado-api/updatebatch-method.md)
