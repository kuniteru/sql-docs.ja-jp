---
title: コンテキスト接続
description: コンテキスト接続について説明します。
ms.date: 08/15/2019
ms.assetid: e443ca86-9243-4234-a822-ed10a53a9de0
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.topic: conceptual
author: David-Engel
ms.author: v-daenge
ms.reviewer: v-kaywon
ms.openlocfilehash: a70614ce43ee94894d88e1bc9aaae0c2ed87076a
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2020
ms.locfileid: "80928882"
---
# <a name="the-context-connection"></a>コンテキスト接続

[!INCLUDE[Driver_ADONET_Download](../../../includes/driver_adonet_download.md)]

内部データへのアクセスに関する問題は、ごく一般的なものです。 内部データにアクセスすることは、CLR (共通言語ランタイム) ストアド プロシージャや関数を実行しているサーバーへのアクセスを考えることです。 これを実現する 1 つの選択肢として、<xref:Microsoft.Data.SqlClient.SqlConnection> を使用して接続を作成し、ローカル サーバーを指す接続文字列を指定して、接続を開く方法があります。 これには、ログインのための資格情報を指定することが必要になります。 接続が、ストアド プロシージャや関数とは別のデータベース セッションにある場合、`SET` オプションが異なっている場合、別のトランザクションに存在している場合、一時テーブルを認識しない場合なども考えられます。 マネージド ストアド プロシージャや関数のコードが SQL Server プロセスで実行されているということは、だれかがそのサーバーに接続して、マネージド コードを呼び出す SQL ステートメントを実行したことを意味します。 このような場合、その接続のコンテキストで、その接続のトランザクションや `SET` オプションと共存する形で、ストアド プロシージャまたは関数を実行することを考えます。 これを "コンテキスト接続" と呼びます。  
  
コンテキスト接続を使用すると、コードを最初に呼び出したのと同じコンテキストで Transact-SQL ステートメントを実行することができます。 詳細については、SQL Server オンライン ブックの「[コンテキスト接続](https://go.microsoft.com/fwlink/?LinkId=115395)」を参照してください。
