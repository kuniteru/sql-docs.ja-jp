---
title: ProtocolDLL プロパティ (ClientNetworkProtocol)
ms.custom: seo-lt-2019
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
apiname:
- ProtocolDLL Property (ClientNetworkProtocol Class)
apilocation:
- sqlmgmproviderxpsp2up.mof
apitype: MOFDef
helpviewer_keywords:
- ProtocolDLL property
ms.assetid: fe8650d5-7b9d-46f8-bf74-baf1d9d2a06a
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 4e93c5ed625cd5c81f9b3f7bea73c203ae590c7a
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "85889003"
---
# <a name="protocoldll-property-clientnetworkprotocol-class"></a>ProtocolDLL プロパティ (ClientNetworkProtocol クラス)
[!INCLUDE [SQL Server](../../../includes/applies-to-version/sqlserver.md)]
  [クライアントプロトコルの構成](https://technet.microsoft.com/library/ms181035.aspx)によって指定されたネットワークプロトコルに必要な .dll ファイルの名前を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
  
object.ProtocolDLL [= value]  
```  
  
## <a name="parts"></a>指定項目  
 *object*  
 クライアントによって使用されるネットワークプロトコルを表す[Clientnetworkprotocol クラス](../../../relational-databases/wmi-provider-configuration-classes/clientnetworkprotocol-class/clientnetworkprotocol-class.md)オブジェクト [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 。  
  
## <a name="property-valuereturn-value"></a>プロパティ値/戻り値  
 クライアント ネットワーク プロトコルに必要なプロトコル .dll ファイルを指定する文字列値。  
  
## <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>関連項目  
 [クライアントのネットワーク プロトコルと Net-Library の構成](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
