---
title: sp_xtp_control_proc_exec_stats (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 03/15/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.sp_xtp_control_proc_exec_stats
- sys.sp_xtp_control_proc_exec_stats_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.sp_xtp_control_proc_exec_stats
ms.assetid: f5119808-76a1-4522-8529-9e02ee39adcb
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 9d011be97c90f156b8cd26cfb8fcc85963b75161
ms.sourcegitcommit: 039fb38c583019b3fd06894160568387a19ba04e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2020
ms.locfileid: "87442401"
---
# <a name="syssp_xtp_control_proc_exec_stats-transact-sql"></a>sys.sp_xtp_control_proc_exec_stats (Transact-SQL)
[!INCLUDE[sqlserver](../../includes/applies-to-version/sqlserver.md)]

  インスタンスのネイティブコンパイルストアドプロシージャの統計コレクションを有効にします。  
  
 ネイティブコンパイルストアドプロシージャのクエリレベルで統計コレクションを有効にするには、「 [sys. sp_xtp_control_query_exec_stats &#40;transact-sql&#41;](../../relational-databases/system-stored-procedures/sys-sp-xtp-control-query-exec-stats-transact-sql.md)」を参照してください。  
  
## <a name="syntax"></a>構文  
  
```  
sp_xtp_control_proc_exec_stats [ [ @new_collection_value = ] collection_value ], [ @old_collection_value]  
```  
  
## <a name="arguments"></a>引数  
 @new_collection_value=*値*  
 プロシージャレベルの統計コレクションが on (1) か off (0) かを指定します。  
  
 @new_collection_valueまたはデータベースの起動時には、は0に設定され [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ます。  
  
 @old_collection_value=*値*  
 現在の状態を返します。  
  
## <a name="return-code"></a>リターンコード  
 成功した場合は 0。 エラーの場合は0以外の。  
  
## <a name="permissions"></a>アクセス許可  
 固定 sysadmin ロールのメンバーシップが必要です。  
  
## <a name="code-samples"></a>コード サンプル  
 @new_collection_valueの値を設定してクエリを実行するには@new_collection_value:  
  
```  
exec [sys].[sp_xtp_control_proc_exec_stats] @new_collection_value = 1  
declare @c bit  
exec sp_xtp_control_proc_exec_stats @old_collection_value=@c output  
select @c as 'collection status'  
```  
  
## <a name="see-also"></a>参照  
 [システムストアドプロシージャ &#40;Transact-sql&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)   
 [インメモリ OLTP &#40;インメモリ最適化&#41;](../../relational-databases/in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
