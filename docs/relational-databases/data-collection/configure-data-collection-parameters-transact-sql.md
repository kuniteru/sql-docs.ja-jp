---
title: データ コレクションのパラメーターの構成 (T-SQL)
ms.date: 06/03/2020
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- data collection [SQL Server]
ms.assetid: 850905b6-35d2-4ed1-ab51-de64daa832b2
author: MashaMSFT
ms.author: mathoma
ms.custom: seo-lt-2019
ms.openlocfilehash: 47d18830d262bc817061aa3637cc3a4871accfd3
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85733890"
---
# <a name="configure-data-collection-parameters-transact-sql"></a>データ コレクションのパラメーターの構成 (Transact-SQL)
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  カスタム コレクション セットを作成する前に、データ コレクションのパラメーターを構成しておく必要があります。 これには、データ コレクターで用意されているストアド プロシージャを使用します。 この作業には、 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] のクエリ エディターを使用した次の手順の実行も含まれます。  
  
> [!NOTE]  
>  データ コレクションのパラメーターは一度構成するだけです。 構成後に作成した追加のコレクション セットには、すべてこれらのパラメーターが使用されます。  
  
### <a name="configure-data-collection-parameters"></a>データ コレクションのパラメーターの構成  
  
1.  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]で、カスタム コレクション セットを作成するデータベースに接続します。  
  
2.  クエリ エディターで、次のステートメントを実行します。  

    ```sql  
    USE msdb;  
    EXEC sp_syscollector_set_warehouse_instance_name N'INSTANCE_NAME';-- where instance name is the name of the SQL Server instance  
    EXEC sp_syscollector_set_warehouse_database_name N'MDW';  
    EXEC sp_syscollector_set_cache_directory N'D:\tempdata';  
    ```  
  
## <a name="see-also"></a>参照  
 [[データ コレクション]](../../relational-databases/data-collection/data-collection.md)   
 [データ コレクター ストアド プロシージャ &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql.md)  
  
  
