---
title: Clustered プロパティ (SqlService)
ms.custom: seo-lt-2019
ms.date: 03/03/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
apiname:
- Clustered Property (SqlService Class)
apilocation:
- sqlmgmproviderxpsp2up.mof
helpviewer_keywords:
- Clustered property
ms.assetid: f714e7f5-c2db-45c6-9536-6ca2cb5b42aa
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 084ade8f77570a04c1f11e3183a2a6102d0388bc
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "85880665"
---
# <a name="clustered-property-sqlservice-class"></a>Clustered プロパティ (SqlService クラス)
[!INCLUDE [SQL Server](../../../includes/applies-to-version/sqlserver.md)]
  サービスがクラスター化インスタンスの一部であるかどうかを指定するブール型のプロパティ値を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
  
object.Clustered [= value]  
```  
  
## <a name="parts"></a>指定項目  
 *object*  
 サービスを表す [SqlService クラス](../../../relational-databases/wmi-provider-configuration-classes/sqlservice-class/sqlservice-class.md) オブジェクト。  
  
## <a name="property-valuereturn-value"></a>プロパティ値/戻り値  
 サービスがクラスター化インスタンスに参加しているかどうかを指定するブール値です。サービスがクラスター化インスタンスに参加している場合は **true** 、サービスがクラスター化インスタンスに参加していない場合は **false** です。  
  
## <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>関連項目  
 [サービスの開始および停止](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)  
  
  
