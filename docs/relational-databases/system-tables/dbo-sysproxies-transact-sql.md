---
title: dbo.sysプロキシ (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- dbo.sysproxies_TSQL
- sysproxies_TSQL
- dbo.sysproxies
- sysproxies
dev_langs:
- TSQL
helpviewer_keywords:
- sysproxies system table
ms.assetid: a73da875-be22-45fc-b5e2-ea7ebd48e2d6
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: f4bcebbdb3926b6444f647f57b3a82c1f9dcb622
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "85890464"
---
# <a name="dbosysproxies-transact-sql"></a>dbo.sysプロキシ (Transact-sql)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  エージェントプロキシアカウントの属性を定義 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] します。 このテーブルは、 **msdb**データベースに格納されます。  
  
|列名|データ型|説明|  
|-----------------|---------------|-----------------|  
|**proxy_id**|**int**|プロキシアカウントの ID。|  
|**name**|**sysname**|プロキシアカウントの名前。|  
|**credential_id**|**int**|プロキシアカウントが使用する資格情報の ID。|  
|**enabled**|**tinyint**|プロキシ アカウントの状態。<br /><br /> **0** = 無効です。 **1** = 有効。|  
|**description**|**nvarchar(512)**|プロキシアカウントの作成時にユーザーが入力した説明。|  
|**user_sid**|**varbinary (85)**|プロキシ資格情報に関連付けられているユーザーまたはグループの Microsoft Windows *security_identifier* 。|  
|**credential_date_created**|**datetime**|資格情報が作成された日付と時刻。|  
  
## <a name="remarks"></a>Remarks  
 **Sysproxies**テーブルにアクセスできるのは、 **sysadmin**固定サーバーロールのメンバーだけです。  
  
## <a name="see-also"></a>関連項目  
 [dbo.sysproxylogin &#40;Transact-sql&#41;](../../relational-databases/system-tables/dbo-sysproxylogin-transact-sql.md)   
 [dbo.sysproxysubsystem &#40;Transact-sql&#41;](../../relational-databases/system-tables/dbo-sysproxysubsystem-transact-sql.md)   
 [dbo.sysサブシステム &#40;Transact-sql&#41;](../../relational-databases/system-tables/dbo-syssubsystems-transact-sql.md)  
  
  
