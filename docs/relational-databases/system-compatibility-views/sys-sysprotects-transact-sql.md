---
title: sys.sysによる保護 (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 03/15/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sysprotects
- sys.sysprotects_TSQL
- sys.sysprotects
- sysprotects_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.sysprotects compatibility view
- sysprotects system table
ms.assetid: 49c9658d-fb51-4c77-94a0-fba699b0102d
author: rothja
ms.author: jroth
ms.openlocfilehash: bfda1be56b5fc373d0ae1b9e8d5141ac046b717e
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "85884471"
---
# <a name="syssysprotects-transact-sql"></a>sys.sysによる保護 (Transact-sql)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  GRANT ステートメントと DENY ステートメントを使用して、データベース内のセキュリティアカウントに適用されている権限に関する情報を格納します。  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssnoteCompView](../../includes/ssnotecompview-md.md)]  
  
|列名|データ型|説明|  
|-----------------|---------------|-----------------|  
|**id**|**int**|これらのアクセス許可を適用するオブジェクトの ID。|  
|**uid**|**smallint**|これらのアクセス許可が適用されるユーザーまたはグループの ID。 ユーザーおよびロールの数が32767を超えた場合、オーバーフローまたは NULL を返します。|  
|**action**|**tinyint**|次のいずれかのアクセス許可を持つことができます。<br /><br /> 26 = REFERENCES<br /><br /> 178 = 関数の作成<br /><br /> 193 = SELECT<br /><br /> 195 = 挿入<br /><br /> 196 = 削除<br /><br /> 197 = 更新<br /><br /> 198 = CREATE TABLE<br /><br /> 203 = CREATE DATABASE<br /><br /> 207 = CREATE VIEW<br /><br /> 222 = CREATE PROCEDURE<br /><br /> 224 = EXECUTE<br /><br /> 228 = BACKUP DATABASE<br /><br /> 233 = 既定値の作成<br /><br /> 235 = BACKUP LOG<br /><br /> 236 = ルールの作成|  
|**protecttype**|**tinyint**|には次の値を指定できます。<br /><br /> 204 = GRANT_W_GRANT<br /><br /> 205 = GRANT<br /><br /> 206 = 拒否|  
|**欄**|**varbinary(8000)**|これらの SELECT または UPDATE 権限を適用する列のビットマップです。<br /><br /> ビット 0 = すべての列。<br /><br /> ビット 1 = 権限を適用する列<br /><br /> NULL = 情報がありません。|  
|**権限**|**smallint**|GRANT または DENY 権限を発行したユーザーのユーザー ID です。 ユーザーおよびロールの数が32767を超えた場合、オーバーフローまたは NULL を返します。|  
  
## <a name="see-also"></a>関連項目  
 [システムビューへのシステムテーブルのマッピング &#40;Transact-sql&#41;](../../relational-databases/system-tables/mapping-system-tables-to-system-views-transact-sql.md)   
 [互換性ビュー &#40;Transact-SQL&#41;](~/relational-databases/system-compatibility-views/system-compatibility-views-transact-sql.md)  
  
  
