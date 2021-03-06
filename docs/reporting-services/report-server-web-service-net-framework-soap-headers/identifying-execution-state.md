---
title: 実行状態の識別 | Microsoft Docs
description: 複数の方法でレポートを操作できるようにするため、Reporting Services を使用して実行状態を識別する方法について説明します。
ms.date: 03/03/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.technology: report-server-web-service-net-framework-soap-headers
ms.topic: reference
helpviewer_keywords:
- session states [Reporting Services]
- lifetimes [Reporting Services]
- sessions [Reporting Services]
- SessionHeader SOAP header
ms.assetid: d8143a4b-08a1-4c38-9d00-8e50818ee380
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 0977cc384dac80f28d6b7c5b7a0149ba200f1794
ms.sourcegitcommit: ff82f3260ff79ed860a7a58f54ff7f0594851e6b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2020
ms.locfileid: "80215601"
---
# <a name="identifying-execution-state"></a>実行状態の識別
  Hypertext Transfer Protocol (HTTP) はコネクションレスおよびステートレス プロトコルです。つまり、同じクライアントから異なる要求が来ているかどうかは自動的に検出されません。さらに、ページまたはサイトを表示している 1 つのブラウザーが現在アクティブであるかどうかも、自動的には示されません。 セッションが論理接続を作成し、HTTP を介したサーバーとクライアント間の状態を保持します。 特定のセッションに関連するユーザー固有情報は、セッション状態と呼ばれます。  
  
 セッション管理には、HTTP 要求を同じセッションから生成された他の以前の要求と相関させることが含まれます。 セッション管理を使用しないと、HTTP プロトコルがコネクションレスでステートレスな性質であるため、このような要求がレポート サーバー Web サービスと関係なく表示されます。  
  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] には、[!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] におけるようなセッション状態の全体的な概念はありません。 ただし、レポートを実行する場合に、レポート サーバーは**実行**の形式でメソッド呼び出し間で状態を保持します。 実行によって、レポート サーバーからレポートを読み込む、レポートの資格情報とパラメーターを設定する、レポートを表示するなど、ユーザーが複数の方法でレポートと対話することができます。  
  
 レポート サーバーと通信中は、クライアントが実行を使用して、レポートの表示、ユーザーによるレポートの他のページへのナビゲーション、およびレポートのセクションの表示と非表示を管理します。 クライアント アプリケーションが実行しているレポートごとに、固有の実行が存在します。  
  
 一般的に、ユーザーがブラウザーまたはクライアント アプリケーションにナビゲートし、表示するレポートを選択したときに、実行の有効期間が開始します。 実行に対する最後の要求が受信された後にタイムアウト時間が経過すると、実行が破棄されます。既定のタイムアウトは 20 分です。  
  
 Web サービスのタイムアウトが開始するのは、レポート サーバー Web サービス <xref:ReportExecution2005.ReportExecutionService.LoadReport%2A>、<xref:ReportExecution2005.ReportExecutionService.LoadReportDefinition%2A>、または <xref:ReportExecution2005.ReportExecutionService.Render%2A> メソッドが呼び出されたときです。 アプリケーションは、他のメソッドを使用してアクティブな実行を操作できます (パラメーターの設定やデータ ソースの設定など)。 実行に対する最後の要求が受信された後にタイムアウト時間が経過すると、実行が破棄されます。既定のタイムアウトは 20 分です。  
  
 アプリケーションは、<xref:ReportExecution2005.ReportExecutionService.Render%2A> (<xref:ReportExecution2005.ReportExecutionService.RenderStream%2A> メソッドと <xref:ReportExecution2005.ExecutionHeader.ExecutionID%2A> メソッドの SOAP ヘッダーで返される) を保存することによって、Web サービスの <xref:ReportExecution2005.ReportExecutionService.LoadReport%2A> メソッドと <xref:ReportExecution2005.ReportExecutionService.LoadReportDefinition%2A> メソッド間の複数のアクティブな実行を追跡します。  
  
 次のダイアグラムは、レポートに対する処理と表示のパスを示しています。  
  
 ![レポートの処理および表示 パス](../../reporting-services/report-server-web-service-net-framework-soap-headers/media/rs-render-process-diagram.gif "レポートの処理および表示パス")  
  
 上記のような関数をサポートするために、現在の SOAP Render メソッドを複数のメソッドに分割して、初期化フェーズ、処理フェーズ、および表示フェーズの実行を網羅しました。  
  
 プログラムによってレポートを表示するには、次の操作を行う必要があります。  
  
-   <xref:ReportExecution2005.ReportExecutionService.LoadReport%2A> または <xref:ReportExecution2005.ReportExecutionService.LoadReportDefinition%2A> を使用して、レポートまたはレポート定義を読み込みます。  
  
-   レポートに資格情報またはパラメーターが必要かどうかを確認します。このとき、<xref:ReportExecution2005.ExecutionInfo.CredentialsRequired%2A> または <xref:ReportExecution2005.ExecutionInfo.ParametersRequired%2A> によって返された <xref:ReportExecution2005.ExecutionInfo> オブジェクトの <xref:ReportExecution2005.ReportExecutionService.LoadReport%2A> プロパティと <xref:ReportExecution2005.ReportExecutionService.LoadReportDefinition%2A> プロパティの値を確認します。  
  
-   必要に応じて、<xref:ReportExecution2005.ReportExecutionService.SetExecutionCredentials%2A> メソッドおよび <xref:ReportExecution2005.ReportExecutionService.SetExecutionParameters%2A> メソッドを使用して、資格情報またはパラメーター、あるいはその両方を設定します。  
  
-   <xref:ReportExecution2005.ReportExecutionService.Render%2A> メソッドを呼び出してレポートを表示します。  
  
 レポートがセッション中の間は、レポート サーバー データベースに格納された基になるレポートを変更できます。 たとえば、レポート定義の変更、レポートの削除や移動、ユーザー権限の変更ができます。 レポートがアクティブなセッション中の場合は、基になるレポート (レポート サーバー データベースに格納されたレポート) への変更による影響を受けません。  
  
 URL アクセス コマンドを使用して、レポート セッションを管理することもできます。  
  
## <a name="see-also"></a>参照  
 <xref:ReportExecution2005.ReportExecutionService.Render%2A>   
 [テクニカル リファレンス (SSRS)](../../reporting-services/technical-reference-ssrs.md)   
 [Reporting Services SOAP ヘッダーの使用](../../reporting-services/report-server-web-service-net-framework-soap-headers/using-reporting-services-soap-headers.md)  
  
  
