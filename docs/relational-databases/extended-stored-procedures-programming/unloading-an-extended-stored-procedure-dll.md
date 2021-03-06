---
title: 拡張ストアドプロシージャ DLL のアンロード |Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- extended stored procedures [SQL Server], unloading
- unloading extended stored procedures
ms.assetid: 4c75ab14-af54-4965-b376-8d75d385c941
author: rothja
ms.author: jroth
ms.openlocfilehash: 76007876547b863f050d1e3fa494cbd8b30a5fc0
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85717656"
---
# <a name="unloading-an-extended-stored-procedure-dll"></a>拡張ストアド プロシージャ DLL のアンロード
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] 代わりに CLR Integration を使用してください。  
  
 [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]dll のいずれかの関数が呼び出されるとすぐに、拡張ストアドプロシージャ DLL を読み込みます。 DLL がロードされた状態は、サーバーがシャットダウンするか、DBCC ステートメントを使用してシステム管理者によってアンロードされるまで、維持されます。 たとえば、次のコマンドは、 **xp_hello.dll**をアンロードします。これにより、システム管理者は、サーバーをシャットダウンすることなく、このファイルの新しいバージョンをディレクトリにコピーできます。  
  
```  
DBCC xp_hello(FREE)  
```  
  
## <a name="see-also"></a>関連項目  
 [DBCC dllname &#40;FREE&#41; &#40;Transact-sql&#41;](../../t-sql/database-console-commands/dbcc-dllname-free-transact-sql.md)  
  
  
