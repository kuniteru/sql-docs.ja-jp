---
title: プロジェクトの設定 (Azure SQL Database) (SybaseToSQL) |Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
ms.assetid: 57002374-0d4d-43c1-b4e9-cbec02355a9c
author: nahk-ivanov
ms.author: alexiva
ms.openlocfilehash: b79d4e94126676e128d803176463b314348ed8a1
ms.sourcegitcommit: e8f6c51d4702c0046aec1394109bc0503ca182f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2020
ms.locfileid: "87930923"
---
# <a name="project-settings-azure-sql-database--sybasetosql"></a>プロジェクトの設定 (Azure SQL Database) (SybaseToSQL)
Azure SQL Database プロジェクトの設定を使用すると、接続ダイアログに追加する Azure SQL Database データベースサフィックスを構成し、Azure SQL Database 接続でハートビートメカニズムを実装することもできます。  
  
Azure SQL Database ウィンドウは、[プロジェクトの**設定**] ダイアログボックスと [**既定のプロジェクトの設定**] ダイアログボックスで使用できます。  
  
-   [プロジェクトの設定] ダイアログボックスを使用すると、現在のプロジェクトの構成オプションを設定できます。 Azure SQL Database 設定にアクセスするには、[**ツール**] メニューの [**プロジェクトの設定**] を選択し、左側のウィンドウの下部にある [**全般**] をクリックして、[ **Azure SQL Database**] を選択します。  
  
-   [既定のプロジェクトの設定] ダイアログボックスを使用すると、すべてのプロジェクトの構成オプションを設定できます。 Azure SQL Database 設定にアクセスするには、[**ツール**] メニューの [ **Defaultproject の設定**] を選択し、左側のウィンドウの下部にある [**全般**] をクリックして、[ **Azure SQL Database**] を選択します。  
  
## <a name="connectivity"></a>接続  
**ハートビートの間隔**  
  
Azure SQL Database 接続を ' 分: seconds ' 形式で保持するハートビートメカニズムに使用する時間間隔を指定します。  
  
**既定値**: ' 4:45 '  
  
値は、' m:ss ' 形式 (たとえば、' 4:45 ' または ' 0:50 ') で指定する必要があります。  
  
**Azure SQL Database サーバーサフィックス**  
  
Azure SQL Database サーバーのサフィックスを指定します  
  
**既定値**: ' database.windows.net '。  
  
