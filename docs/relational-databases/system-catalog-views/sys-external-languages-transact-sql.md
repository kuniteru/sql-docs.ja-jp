---
title: external_languages (Transact-sql)-SQL Server |Microsoft Docs
ms.custom: ''
ms.date: 05/22/2019
ms.prod: sql
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- external_languages
- external_languages_TSQL
- sys.external_languages
- sys.external_languages_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.external_languages catalog view
author: nelgson
ms.author: negust
ms.reviewer: dphansen
manager: cgronlun
monikerRange: '>=sql-server-ver15||=sqlallproducts-allversions'
ms.openlocfilehash: 225e20e199a401e544be9c86a7b05a078f556530
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85751722"
---
# <a name="sysexternal_languages-transact-sql"></a>external_languages (Transact-sql)
[!INCLUDE[SQL Server 2019](../../includes/applies-to-version/sqlserver2019.md)]

このカタログビューには、データベース内の外部言語の一覧が表示されます。 **R** と **Python** は予約済みの名前であり、それらの特定の名前で外部言語を作成することはできません。

## <a name="sysexternal_languages"></a>sys.external_languages

カタログビューの external_languages には、データベース内の外部言語ごとに1行のデータが表示されます。

|列名 |データ型 | 説明|
|------|------|------|
|external_language_id |INT | 外部言語の ID|
|language |sysname |外部言語の名前。 データベース内で一意です。 R と Python は、インスタンスごとに予約された名前です|
|create_date |datetime2 |作成日時|
|principal_id |INT |この外部ライブラリを所有するプリンシパルの ID|

## <a name="see-also"></a>関連項目  

+ [sys.external_language_files](sys-external-language-files-transact-sql.md)  
+ [外部言語の作成](../../t-sql/statements/create-external-language-transact-sql.md) 
