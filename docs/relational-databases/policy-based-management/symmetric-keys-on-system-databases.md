---
title: システム データベースの対称キー | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 28e25ae3-d3dc-45ec-b316-f219512a1a47
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 890612fdf4502de67283e7b2bb55e75b372d5388
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85774127"
---
# <a name="symmetric-keys-on-system-databases"></a>システム データベースの対称キー
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  このルールでは、master、msdb、model、および tempdb の各データベースにあるユーザーが作成した対称キーについて確認します。  
  
## <a name="best-practices-recommendations"></a>ベスト プラクティスと推奨事項  
 システム データベースには対称キーを作成しないでください。  
  
## <a name="for-more-information"></a>詳細情報  
 [暗号化アルゴリズムの選択](../../relational-databases/security/encryption/choose-an-encryption-algorithm.md)  
  
## <a name="see-also"></a>参照  
 [ポリシーベースの管理を使用したベスト プラクティスの監視と実行](../../relational-databases/policy-based-management/monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
