---
title: '[サブスクリプションの再初期化] - [すべてのサブスクリプション] | Microsoft Docs'
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql13.rep.reinit.all.f1
helpviewer_keywords:
- Reinitialize Subscription(s) dialog box
ms.assetid: e1122018-9f74-43e3-8489-7eae33ff23d9
author: MashaMSFT
ms.author: mathoma
monikerRange: =azuresqldb-mi-current||>=sql-server-2016||=sqlallproducts-allversions
ms.openlocfilehash: 9da983b0f59625c6bd2404512e99d4f0928bff01
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85767699"
---
# <a name="reinitialize-subscriptions---all-subscriptions"></a>[サブスクリプションの再初期化] - [すべてのサブスクリプション]
[!INCLUDE [SQL Server SQL MI](../../includes/applies-to-version/sql-asdbmi.md)]
  **[サブスクリプションの再初期化]** ダイアログ ボックスを使用すると、パブリケーションに対してすべてのサブスクリプションを再初期化するように設定できます。 再初期化には各サブスクライバーへのスナップショットの適用が伴います。再初期化は、トランザクション パブリケーションに対するサブスクリプションではディストリビューション エージェントによって実行され、マージ パブリケーションに対するサブスクリプションではマージ エージェントによって実行されます。  
  
## <a name="options"></a>オプション  
 **[現在のスナップショットを使用する]**  
 サブスクリプションに対してディストリビューション エージェントまたはマージ エージェントが次回実行されるとき、各サブスクライバーに現在のスナップショットを適用します。 有効なスナップショットが使用できない場合、このオプションは選択できません。  
  
 **[新しいスナップショットを使用する]**  
 すべてのサブスクリプションを新しいスナップショットで再初期化します。 スナップショットは、スナップショット エージェントによって生成された後でのみ、各サブスクライバーに適用できます。 スナップショット エージェントがスケジュールによって実行されるように設定されている場合、サブスクリプションは、次にスケジュールされているスナップショット エージェントが実行されるまで再初期化されません。  
  
 スナップショット エージェントをすぐに開始するには、 **[今すぐ新しいスナップショットを生成する]** を選択します。  
  
 **[再初期化する前に、同期されていない変更をアップロード]**  
 マージ レプリケーションのみです。 サブスクライバーのデータがスナップショットで上書きされる前に、サブスクリプション データベースのすべての保留中の変更をアップロードします。  
  
 パラメーター化フィルターを追加、削除、変更する場合は、再初期化の際、サブスクライバーで保留中の変更をパブリッシャーにアップロードできません。 保留中の変更をアップロードしたい場合は、フィルターを変更する前にすべてのサブスクリプションを同期してください。  
  
 **[再初期化するように設定]**  
 再初期化するために各サブスクリプションを設定します。 有効なスナップショットが使用できるようになった後、サブスクリプションに対してディストリビューション エージェントまたはマージ エージェントを次回実行するとき、スナップショットはサブスクライバーに適用されます。  
  
## <a name="see-also"></a>参照  
 [サブスクリプションの再初期化](../../relational-databases/replication/reinitialize-subscriptions.md)  
  
  
