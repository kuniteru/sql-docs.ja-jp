---
title: sp_cdc_scan (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.sp_cdc_scan_TSQL
- sp_cdc_scan
- sys.sp_cdc_scan
- sp_cdc_scan_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sp_cdc_scan
ms.assetid: 46e4294c-97b8-47d6-9ed9-b436a9929353
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 558a2fd9ff62baa3448609eb42e5f31883fbac53
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "85891062"
---
# <a name="syssp_cdc_scan-transact-sql"></a>sys.sp_cdc_scan (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Change data capture ログスキャン操作を実行します。  
  
 ![トピック リンク アイコン](../../database-engine/configure-windows/media/topic-link.gif "トピック リンク アイコン") [Transact-SQL 構文表記規則](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>構文  
  
```  
  
sys.sp_cdc_scan [ [ @maxtrans = ] max_trans ]   
     [ , [ @maxscans = ] max_scans ]   
     [ , [ @continuous = ] continuous ]   
     [ , [ @pollinginterval = ] polling_interval ]   
```  
  
## <a name="arguments"></a>引数  
`[ @maxtrans = ] max_trans`各スキャンサイクルで処理するトランザクションの最大数。 *max_trans*は**int**で、既定値は500です。  
  
`[ @maxscans = ] max_scans`ログからすべての行を抽出するために実行するスキャンサイクルの最大数。 *max_scans*は**int**で、既定値は10です。  
  
`[ @continuous = ] continuous`1回のスキャンサイクル (0) を実行した後にストアドプロシージャを終了するか、連続して実行して、スキャンサイクルを再実行する前に*polling_interval*によって指定された時間一時停止するか (1) を示します。 *continuous*は**tinyint**で、既定値は0です。  
  
`[ @pollinginterval = ] polling_interval`ログスキャンサイクルの間隔を秒数で指定します。 *polling_interval*は**bigint**で、既定値は0です。  
  
## <a name="return-code-values"></a>リターン コードの値  
 **0** (成功) または**1** (失敗)  
  
## <a name="result-sets"></a>結果セット  
 なし  
  
## <a name="remarks"></a>解説  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] エージェントのキャプチャ ジョブが変更データ キャプチャによって使用されている場合、sys.sp_cdc_scan は sys.sp_MScdc_capture_job によって内部的に呼び出されます。 変更データ キャプチャのログ スキャン操作が既にアクティブである場合、またはデータベースのトランザクション レプリケーションが有効になっている場合は、プロシージャは明示的に実行できません。 このストアドプロシージャは、自動的に構成されるキャプチャジョブの動作をカスタマイズする管理者が使用する必要があります。  
  
## <a name="permissions"></a>アクセス許可  
 db_owner 固定データベース ロールのメンバーシップが必要です。  
  
## <a name="see-also"></a>関連項目  
 [dbo. cdc_jobs &#40;Transact-sql&#41;](../../relational-databases/system-tables/dbo-cdc-jobs-transact-sql.md)  
  
  
