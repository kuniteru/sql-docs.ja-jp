---
title: catalog.check_schema_version | Microsoft Docs
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: language-reference
ms.assetid: e0d5e9f5-59c6-4118-87b5-4aa5c37a7df6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d8b492f69eae6e3ffea4afe6fc61ae64528c80da
ms.sourcegitcommit: c8e1553ff3fdf295e8dc6ce30d1c454d6fde8088
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2020
ms.locfileid: "86913590"
---
# <a name="catalogcheck_schema_version"></a>catalog.check_schema_version 

[!INCLUDE[sqlserver-ssis](../../includes/applies-to-version/sqlserver-ssis.md)]


[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  SSISDB カタログ スキーマと [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] バイナリ (ISServerExec および SQLCLR アセンブリ) に互換性があるかどうかを示します。  
  
 スキーマとバイナリに互換性がない場合、ISServerExec.exc でエラー メッセージが記録されます。  
  
 SSISDB スキーマのバージョンは、修正プログラムや更新プログラムの適用時にスキーマが変更された場合に増加します。 SSISDB バックアップの復元後にこのストアド プロシージャを実行して、スキーマとバイナリに互換性があるようにすることをお勧めします。  
  
## <a name="syntax"></a>構文  
  
```sql  
catalog.check_schema_version [ @use32bitruntime = ] use32bitruntime  
```  
  
## <a name="arguments"></a>引数  
 [ @use32bitruntime= ] *use32bitruntime*  
 パラメーターが **1** に設定されている場合、32 ビット バージョンの dtexec が呼び出されます。 *use32bitruntime* は、**int** です。  
  
## <a name="result-set"></a>結果セット  
 なし  
  
## <a name="permissions"></a>アクセス許可  
 このストアド プロシージャには、次の権限が必要です。  
  
-   **ssis_admin** データベース ロールのメンバーシップ。  
  
  
