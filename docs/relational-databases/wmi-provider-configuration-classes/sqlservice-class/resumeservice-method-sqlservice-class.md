---
title: ResumeService メソッド (SqlService)
ms.custom: seo-lt-2019
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
apiname:
- ResumeService Method (SqlService Class)
apilocation:
- sqlmgmproviderxpsp2up.mof
apitype: MOFDef
helpviewer_keywords:
- ResumeService method
ms.assetid: 0b0a5f08-b95e-4626-bf81-309da7a0aacd
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 259c5a1696203b06c0c67a87f6dedc00c29d66ce
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "85880584"
---
# <a name="resumeservice-method-sqlservice-class"></a>ResumeService メソッド (SqlService クラス)
[!INCLUDE [SQL Server](../../../includes/applies-to-version/sqlserver.md)]
  サービスを再開状態にする動作を試行します。  
  
## <a name="syntax"></a>構文  
  
```  
  
object.ResumeService()  
```  
  
## <a name="parts"></a>指定項目  
 *object*  
 サービスを表す [SqlService クラス](../../../relational-databases/wmi-provider-configuration-classes/sqlservice-class/sqlservice-class.md) オブジェクト。  
  
## <a name="property-valuereturn-value"></a>プロパティ値/戻り値  
 Uint32 値。 **ResumeService**要求が受け入れられた場合は0、要求がサポートされていない場合は1、エラーを示すその他の数値。  
  
## <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>関連項目  
 [サービスの開始および停止](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)  
  
  
