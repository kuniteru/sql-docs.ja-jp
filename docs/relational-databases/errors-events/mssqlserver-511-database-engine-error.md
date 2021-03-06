---
title: MSSQLSERVER_511 | Microsoft Docs
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: language-reference
helpviewer_keywords:
- 511 (Database Engine error)
ms.assetid: 0c85686a-53c1-4180-ba8c-2000e68a0d63
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b3e094206a4fbbc9620ff7eed96e01c8b0a06f5f
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85715431"
---
# <a name="mssqlserver_511"></a>MSSQLSERVER_511
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  
## <a name="details"></a>詳細  
  
| 属性 | 値 |  
| :-------- | :---- |  
|製品名|SQL Server|  
|イベント ID|511|  
|イベント ソース|MSSQLSERVER|  
|コンポーネント|SQLEngine|  
|シンボル名|ROW_TOOBIG|  
|メッセージ テキスト|1 行のサイズ %d が許容最大値 %d を超えているので行を作成できません。|  
  
## <a name="explanation"></a>説明  
実行しようとした操作が最大行サイズを超えました。 通常、最大行サイズは 8,060 バイトです。 ストレージ形式によっては、データに使用できる行サイズを縮小するオーバーヘッドが含まれる場合があります。 たとえば、スパース列を使用する場合、最大行サイズは 8,018 バイトです。 行を追加または削除する操作や列のデータ型を変更する操作では、データ ページ上の行を書き直すことが必要になる場合があります。その後、元の行は削除されます。 これらの操作では、行サイズの制限を最大値の半分にすると効果的です。 これは、短時間ですが、元の行と変更された行の両方をデータ ページ上に含める必要があるためです。  
  
## <a name="user-action"></a>ユーザーの操作  
できる限り、行のサイズを縮小します。  
  
問題の原因が行の直接の更新であると考えられる場合は、複数の手順でテーブルを変更する必要があります。 新しいテーブルを作成し、新しいテーブルにデータを転送します。 その後、元のテーブルを削除して新しいテーブルの名前を変更するか、元のテーブルを切り捨て、元のテーブル内の行を変更し、そのテーブルにデータを戻します。  
  
