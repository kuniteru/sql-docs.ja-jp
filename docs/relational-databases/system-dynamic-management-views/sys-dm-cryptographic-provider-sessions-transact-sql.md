---
title: dm_cryptographic_provider_sessions (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.dm_cryptographic_provider_sessions
- dm_cryptographic_provider_sessions_TSQL
- sys.dm_cryptographic_provider_sessions_TSQL
- dm_cryptographic_provider_sessions
dev_langs:
- TSQL
helpviewer_keywords:
- sys.dm_cryptographic_provider_sessions dynamic management function
ms.assetid: 9a4de02b-1a07-4850-979a-0861fddb7f9d
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 852566e9f337536717273c18b8034f3854fd7d48
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "85894562"
---
# <a name="sysdm_cryptographic_provider_sessions-transact-sql"></a>sys.dm_cryptographic_provider_sessions (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  暗号プロバイダーの開いているセッションに関する情報を返します。  
 
## <a name="syntax"></a>構文  
  
```  
  
sys.dm_cryptographic_provider_sessions(session_identifier)  
```  
  
## <a name="arguments"></a>引数  
 *session_identifier*  
 返されるセッションを示す整数。  
  
 0 = 現在の接続のみ  
  
 1 = すべての暗号接続  
  
## <a name="table-returned"></a>返されるテーブル  
  
|列名|データ型|説明|  
|-----------------|---------------|-----------------|  
|**provider_id**|**int**|暗号化サービスプロバイダーの識別番号。|  
|**session_handle**|**varbytes (8)**|暗号化セッションハンドル。|  
|**identity**|**nvarchar(128)**|暗号化サービスプロバイダーでの認証に使用する id。|  
|**調べる**|**short**|接続のセッション ID SPID。 詳細については、「[@@SPID &#40;Transact-SQL&#41;](../../t-sql/functions/spid-transact-sql.md)」を参照してください。|  
  
## <a name="remarks"></a>Remarks  
 現在の接続では、 **dm_cryptographic_provider_sessions**ビューがパブリックに表示されます。 すべての暗号化接続を表示するには、 **CONTROL** server 権限が必要です。  
  
## <a name="see-also"></a>関連項目  
 [セキュリティカタログビュー &#40;Transact-sql&#41;](../../relational-databases/system-catalog-views/security-catalog-views-transact-sql.md)   
 [拡張キー管理 &#40;EKM&#41;](../../relational-databases/security/encryption/extensible-key-management-ekm.md)   
 [Transact-sql&#41;&#40;暗号化サービスプロバイダーを作成する](../../t-sql/statements/create-cryptographic-provider-transact-sql.md)   
 [暗号化階層](../../relational-databases/security/encryption/encryption-hierarchy.md)  
  
  
