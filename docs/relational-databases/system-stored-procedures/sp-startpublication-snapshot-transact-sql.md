---
title: sp_startpublication_snapshot (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- sp_startpublication_snapshot
- sp_startpublication_snapshot_TSQL
helpviewer_keywords:
- sp_startpublication_snapshot
ms.assetid: 2cf568ee-0679-4d19-a394-27210bff61e5
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 4138757f6be1d20c11e9b65111ef28b1b1d93119
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "85892999"
---
# <a name="sp_startpublication_snapshot-transact-sql"></a>sp_startpublication_snapshot (Transact-sql)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  パブリケーションの初期スナップショットを生成するスナップショットエージェントジョブを開始するために使用します。 このストアドプロシージャは、パブリッシャー側でパブリケーションデータベースに対して実行されます。  
  
 ![トピック リンク アイコン](../../database-engine/configure-windows/media/topic-link.gif "トピック リンク アイコン") [Transact-SQL 構文表記規則](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>構文  
  
```  
  
sp_startpublication_snapshot [ @publication = ] 'publication'   
    [ , [ @publisher = ] 'publisher' ]  
```  
  
## <a name="arguments"></a>引数  
`[ @publication = ] 'publication'`パブリケーションの名前を指定します。 *publication*は**sysname**,、既定値はありません。  
  
`[ @publisher = ] 'publisher'`以外のパブリッシャーの名前を指定し [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ます。 *publisher*は**sysname**で、既定値は NULL です。 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] パブリッシャーの場合はこのパラメーターを指定しないでください。  
  
## <a name="return-code-values"></a>リターン コードの値  
 **0** (成功) または**1** (失敗)  
  
## <a name="remarks"></a>注釈  
 **sp_startpublication_snapshot**は、すべての種類のレプリケーションで使用されます。  
  
 以外のパブリッシャーの場合 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 、このストアドプロシージャはディストリビューター側でディストリビューションデータベースに対して実行されます。  
  
## <a name="permissions"></a>アクセス許可  
 **Sp_startpublication_snapshot**を実行できるのは、固定サーバーロール**sysadmin**または固定データベースロール**db_owner**のメンバーだけです。  
  
## <a name="see-also"></a>関連項目  
 [初期スナップショットを作成して適用する](../../relational-databases/replication/create-and-apply-the-initial-snapshot.md)   
 [sp_addpublication_snapshot &#40;Transact-sql&#41;](../../relational-databases/system-stored-procedures/sp-addpublication-snapshot-transact-sql.md)   
 [sp_changepublication_snapshot &#40;Transact-sql&#41;](../../relational-databases/system-stored-procedures/sp-changepublication-snapshot-transact-sql.md)  
  
  
