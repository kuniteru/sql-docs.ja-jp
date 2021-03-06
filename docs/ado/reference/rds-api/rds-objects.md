---
title: RDS オブジェクト |Microsoft Docs
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.prod: sql
ms.prod_service: connectivity
ms.topic: conceptual
helpviewer_keywords:
- objects [ADO], RDS
- RDS objects [ADO]
ms.assetid: f2ac8b3b-f968-41c4-a504-7aee3538b7c7
author: rothja
ms.author: jroth
ms.openlocfilehash: 7ba592cd0bb0dc10c094784fbb7d41585d5b6dd6
ms.sourcegitcommit: 591bbf4c7e4e2092f8abda6a2ffed263cb61c585
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2020
ms.locfileid: "86942294"
---
# <a name="rds-objects"></a>RDS オブジェクト
> [!IMPORTANT]
>  Windows 8 と windows Server 2012 以降では、RDS サーバーコンポーネントが Windows オペレーティングシステムに含まれなくなりました (詳細については、「Windows 8 および[Windows server 2012 の互換性に関するクックブック](https://www.microsoft.com/download/details.aspx?id=27416)」を参照してください)。 RDS クライアントコンポーネントは、今後のバージョンの Windows では削除される予定です。 新規の開発作業ではこの機能を使用しないようにし、現在この機能を使用しているアプリケーションは修正することを検討してください。 RDS を使用するアプリケーションは、 [WCF Data Service](https://go.microsoft.com/fwlink/?LinkId=199565)に移行する必要があります。  
  
|Object|説明|  
|-|-|  
|[DataControl (RDS)](../../../ado/reference/rds-api/datacontrol-object-rds.md)|データクエリ**レコードセット**を1つ以上のコントロール (たとえば、テキストボックス、グリッドコントロール、またはコンボボックス) にバインドして、Web ページに**レコードセット**データを表示します。<br /><br /> **DataControl**オブジェクトは、スクリプト作成には安全です。|  
|[DataFactory (RDSServer)](../../../ado/reference/rds-api/datafactory-object-rdsserver.md)|クライアント側アプリケーションの指定されたデータソースへの読み取り/書き込みデータアクセスを提供するメソッドを実装します。<br /><br /> **DataFactory**オブジェクトは、スクリプト作成には安全ではありません。|  
|[領域スペース (RDS)](../../../ado/reference/rds-api/dataspace-object-rds.md)|は、中間層に配置されているカスタムビジネスオブジェクトに対してクライアント側プロキシを作成します。<br /><br /> オブジェクト**スペース**オブジェクトは、スクリプト作成には安全です。|  
|[IRDSService インターフェイス (RDS)](../../../ado/reference/rds-api/irdsservice-interface-rds.md)|[InvokeService (RDS)](../../../ado/reference/rds-api/invokeservice-rds.md)メソッドを公開します。これは、オブジェクトのサポートされているバージョンで、要求されたインターフェイスへのポインターを返すために使用されます。|  
  
## <a name="see-also"></a>参照  
 [RDS の API リファレンス](../../../ado/reference/rds-api/rds-api-reference.md)


