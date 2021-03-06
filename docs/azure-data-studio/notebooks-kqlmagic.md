---
title: Azure Data Studio の Kqlmagic (Kusto クエリ言語) を使用したノートブック
description: このチュートリアルでは、Azure Data Studio で Kqlmagic を作成および実行する方法について説明します。
author: markingmyname
ms.author: maghan
ms.reviewer: jukoesma
ms.topic: tutorial
ms.prod: azure-data-studio
ms.technology: ''
ms.custom: ''
ms.date: 04/27/2020
ms.openlocfilehash: ef59ecb200b30af6c30a5ea602cd89bc2c951e24
ms.sourcegitcommit: c8e1553ff3fdf295e8dc6ce30d1c454d6fde8088
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2020
ms.locfileid: "86920470"
---
# <a name="kqlmagic-extension-in-azure-data-studio"></a>Azure Data Studio の Kqlmagic 拡張機能

**Kqlmagic** は、 **[Azure Data Studio ノートブック](notebooks-guidance.md)** で Python カーネルの機能を拡張するコマンドです。 Python と **[Kusto クエリ言語 (KQL)](https://docs.microsoft.com/azure/data-explorer/kusto/query)** を組み合わせて、`render` コマンドに統合された豊富な Plot.ly ライブラリを使用してデータのクエリと視覚化を実行できます。 Kqlmagic を使用すると、ノートブック、データ分析、Python の豊富な機能の利点がすべて同じ場所にもたらされます。 Kqlmagic でサポートされているデータ ソースには、 **[Azure Data Explorer](https://docs.microsoft.com/azure/data-explorer/data-explorer-overview)** 、 **[Application Insights](https://docs.microsoft.com/azure/azure-monitor/app/app-insights-overview)** 、 **[Azure Monitor ログ](https://docs.microsoft.com/azure/azure-monitor/platform/data-platform-logs)** があります。

この記事では、Kqlmagic 拡張機能を Azure Data Explorer クラスター、Application Insights ログ、および Azure Monitor ログに使用して、Azure Data Studio でノートブックを作成および実行する方法について説明します。

## <a name="prerequisites"></a>前提条件

- [Azure Data Studio](download-azure-data-studio.md)
- [Python](https://www.python.org/downloads/)

## <a name="install-and-set-up-kqlmagic-in-a-notebook"></a>ノートブックに Kqlmagic をインストールしてセットアップする

このセクションのステップはすべて Azure Data Studio ノートブック内で実行されます。

1. 新しいノートブックを作成し、 **[カーネル]** を *[Python 3]* に変更します。

   ![新しい Notebook](media/notebooks-kql-magic/install-new-notebook.png)

2. メッセージが表示されたら、 **[はい]** を選択して、Python パッケージをアップグレードします。

   ![はい](media/notebooks-kql-magic/install-python-yes.png)

3. Kqlmagic をインストールします。

   ```python
   !pip install Kqlmagic --no-cache-dir --upgrade
   ```

   インストールされていることを確認します。

   ```python
   !pip list
   ```

   ![List](media/notebooks-kql-magic/install-list.png)

4. Kqlmagic を読み込みます。

   ```python
   %reload_ext Kqlmagic
   ```

   > [!Note]
   > このステップが失敗した場合は、ファイルを閉じて再度開きます。

   ![Kqlmagic 拡張機能の読み込み](media/notebooks-kql-magic/install-load-kql-magic-ext.png)

5. Kqlmagic が正しく読み込まれているかどうかをテストするには、ヘルプ ドキュメントを参照するか、バージョンを確認します。

   ```python
   %kql --help "help"
   ```

   > [!Note]
   > `Samples@help` がパスワードの入力を求めている場合は、空白のままにして、**Enter** キーを押します。

   ![Help](media/notebooks-kql-magic/install-help.png)

   インストールされている Kqlmagic のバージョンを確認するには、次のコマンドを実行します。

   ```python
   %kql --version
   ```

## <a name="kqlmagic-with-an-azure-data-explorer-cluster"></a>Kqlmagic と Azure Data Explorer クラスター

このセクションでは、Azure Data Explorer クラスターで Kqlmagic を使用してデータ分析を実行する方法について説明します。

### <a name="load-and-authenticate-kqlmagic-for-azure-data-explorer"></a><a name="ade-load-auth"></a> Azure Data Explorer に対して Kqlmagic を読み込んで認証する

   > [!Note]
   > Azure Data Studio で新しいノートブックを作成するたびに、Kqlmagic 拡張機能を読み込む必要があります。

1. **[カーネル]** が *[Python 3]* に設定されていることを確認します。

   ![新しい Notebook](media/notebooks-kql-magic/change-kernel.png)

2. Kqlmagic を読み込みます。

   ```python
   %reload_ext Kqlmagic
   ```

   ![Kqlmagic 拡張機能の読み込み](media/notebooks-kql-magic/install-load-kql-magic-ext.png)

3. クラスターに接続し、認証を行います。

   ```python
   %kql azureDataExplorer://code;cluster='help';database='Samples'
   ```

   デバイスのログインを使用して認証します。 出力からコードをコピーし、**認証**を選択します。これにより、コードを貼り付ける必要があるブラウザーが開きます。 正常に認証されたら、Azure Data Studio に戻って、スクリプトの残りの部分を続行できます。

   ![Azure Data Explorer 認証](media/notebooks-kql-magic/ade-auth.png)

### <a name="query-and-visualize-for-azure-data-explorer"></a>Azure Data Explorer のクエリと視覚化

[render 演算子](https://docs.microsoft.com/azure/data-explorer/kusto/query/renderoperator)を使用してデータのクエリを実行し、ploy.ly ライブラリを使用してデータを視覚化します。 このクエリと視覚化では、ネイティブの KQL を使用する統合されたエクスペリエンスが提供されます。

1. 状態と頻度別に上位 10 個のイベントを分析します。

   ```python
   %kql StormEvents | summarize count() by State | sort by count_ | limit 10
   ```

   Kusto クエリ言語 (KQL) に慣れている場合は、`%kql` の後にクエリを入力できます。

   ![storm イベントの分析](media/notebooks-kql-magic/ade-analyze-storm-events.png)

2. タイムライン グラフの視覚化:

   ```python
   %kql StormEvents \
   | summarize event_count=count() by bin(StartTime, 1d) \
   | render timechart title= 'Daily Storm Events'
   ```

   ![時間グラフの視覚化](media/notebooks-kql-magic/ade-visualize-timechart.png)

3. `%%kql` を使用した複数行のクエリ サンプル。

   ```python
   %%kql
   StormEvents
   | summarize count() by State
   | sort by count_
   | limit 10
   | render columnchart title='Top 10 States by Storm Event count'
   ```

   ![複数行のクエリ サンプル](media/notebooks-kql-magic/ade-multiline-query-sample.png)

## <a name="kqlmagic-with-application-insights"></a>Kqlmagic と Application Insights

### <a name="load-and-authenticate-kqlmagic-for-application-insights"></a><a name="appin-load-auth"></a> Application Insights に対して Kqlmagic を読み込んで認証する

1. **[カーネル]** が *[Python 3]* に設定されていることを確認します。

   ![新しい Notebook](media/notebooks-kql-magic/change-kernel.png)

2. Kqlmagic を読み込みます。

   ```python
   %reload_ext Kqlmagic
   ```

   ![Kqlmagic 拡張機能の読み込み](media/notebooks-kql-magic/install-load-kql-magic-ext.png)

   > [!Note]
   > Azure Data Studio で新しいノートブックを作成するたびに、Kqlmagic 拡張機能を読み込む必要があります。

3. 接続して認証します。

   まず、Application Insights リソースの API キーを生成する必要があります。 次に、アプリケーション ID と API キーを使用して、ノートブックから Application Insights に接続します。

   ```python
   %kql appinsights://appid='DEMO_APP';appkey='DEMO_KEY'
   ```


### <a name="query-and-visualize-for-application-insights"></a>Application Insights のクエリと視覚化

[render 演算子](https://docs.microsoft.com/azure/data-explorer/kusto/query/renderoperator)を使用してデータのクエリを実行し、ploy.ly ライブラリを使用してデータを視覚化します。 このクエリと視覚化では、ネイティブの KQL を使用する統合されたエクスペリエンスが提供されます。

1. ページ ビューの表示:

   ```python
   %%kql
   pageViews
   | limit 10
   ```

   ![ページ ビュー](media/notebooks-kql-magic/appin-page-views.png)

   > [!Note]
   > 特定の日付にズームインするには、マウスを使用してグラフの領域上をドラッグすします。

2. タイムライン グラフでのページ ビューの表示:

   ```python
   %%kql
   pageViews
   | summarize event_count=count() by name, bin(timestamp, 1d)
   | render timechart title= 'Daily Page Views'
   ```

   ![タイムライン グラフ](media/notebooks-kql-magic/appin-timechart.png)

## <a name="kqlmagic-with-azure-monitor-logs"></a>Kqlmagic と Azure Monitor ログ

### <a name="load-and-authenticate-kqlmagic-for-azure-monitor-logs"></a><a name="aml-load-auth"></a> Azure Monitor ログに対して Kqlmagic を読み込んで認証する

1. **[カーネル]** が *[Python 3]* に設定されていることを確認します。

   ![新しい Notebook](media/notebooks-kql-magic/change-kernel.png)

2. Kqlmagic を読み込みます。

   ```python
   %reload_ext Kqlmagic
   ```

   ![Kqlmagic 拡張機能の読み込み](media/notebooks-kql-magic/install-load-kql-magic-ext.png)

   > [!Note]
   > Azure Data Studio で新しいノートブックを作成するたびに、Kqlmagic 拡張機能を読み込む必要があります。

3. 接続と認証:

   ```python
   %kql loganalytics://workspace='DEMO_WORKSPACE';appkey='DEMO_KEY';alias='myworkspace'
   ```

   ![Log Analytics の認証](media/notebooks-kql-magic/aml-auth.png)

### <a name="query-and-visualize-for-azure-monitor-logs"></a>Azure Monitor ログのクエリと視覚化

[render 演算子](https://docs.microsoft.com/azure/data-explorer/kusto/query/renderoperator)を使用してデータのクエリを実行し、ploy.ly ライブラリを使用してデータを視覚化します。 このクエリと視覚化では、ネイティブの KQL を使用する統合されたエクスペリエンスが提供されます。

1. タイムライン グラフの表示:

   ```python
   %%kql
   KubeNodeInventory
   | summarize event_count=count() by Status, bin(TimeGenerated, 1d)
   | render timechart title= 'Daily Kubernetes Nodes'
   ```

   ![Log Analytics の Daily Kubernetes Nodes 時間グラフ](media/notebooks-kql-magic/aml-timechart-daily-kubernetes-nodes.png)

## <a name="next-steps"></a>次のステップ

ノートブックと Kqlmagic についてさらに学習します:

- [Jupyter Notebook と Kqlmagic 拡張機能を使用して Azure Data Explorer 内のデータを分析する](https://docs.microsoft.com/azure/data-explorer/Kqlmagic)
- [Kusto、Application Insights、および LogAnalytics のデータを使用してノートブック エクスペリエンスを実現する、Jupyter Notebook と Jupyter Lab への拡張 (マジック)](https://github.com/Microsoft/jupyter-Kqlmagic)
- [Kqlmagic](https://pypi.org/project/Kqlmagic/)
- [KustoMagicSamples](https://notebooks.azure.com/RknDzgn/projects/KustoMagicSamples/html/Getting%20Started%20with%20Kqlmagic%20on%20Azure%20Data%20Explorer-Copy.ipynb)
- [Azure Data Studio でノートブックを使用する方法](notebooks-guidance.md)
