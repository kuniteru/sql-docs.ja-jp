---
title: 拡張ストアドプロシージャの削除
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- deleting extended stored procedures
- removing extended stored procedures
- extended stored procedures [SQL Server], removing
- dropping extended stored procedures
ms.assetid: 7827e574-3f59-4279-9a9b-532582e041cb
author: rothja
ms.author: jroth
ms.custom: seo-dt-2019
ms.openlocfilehash: 4ec666e49ccc6da12e14f7f1c85ce6eda4b6a4d0
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85723413"
---
# <a name="removing-an-extended-stored-procedure-from-sql-server"></a>SQL Server からの拡張ストアド プロシージャの削除
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] 代わりに CLR Integration を使用してください。  
  
 ユーザー定義の拡張ストアドプロシージャ DLL 内の各拡張ストアドプロシージャ関数を削除するには、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] システム管理者が**sp_dropextendedproc**システムストアドプロシージャを実行して、関数の名前とその関数が存在する DLL の名前を指定する必要があります。 たとえば、次のコマンドは、xp_hello.dll という名前の DLL にある関数**xp_hello**をから削除し [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ます。  
  
```  
sp_dropextendedproc 'xp_hello'  
```  
  
 以降で [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] は、 **sp_dropextendedproc**システムの拡張ストアドプロシージャは削除されません。 代わりに、システム管理者は、拡張ストアドプロシージャに対する EXECUTE 権限を**public**ロールに対して拒否する必要があります。  
  
## <a name="see-also"></a>関連項目  
 [sp_dropextendedproc &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-dropextendedproc-transact-sql.md)  
  
  
