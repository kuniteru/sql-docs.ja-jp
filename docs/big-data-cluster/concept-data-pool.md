---
title: データ プールとは
titleSuffix: SQL Server big data clusters
description: この記事では、SQL Server 2019 ビッグ データ クラスターのデータ プールについて説明します。
author: MikeRayMSFT
ms.author: mikeray
ms.reviewer: mihaelab
ms.date: 08/21/2019
ms.topic: conceptual
ms.prod: sql
ms.technology: big-data-cluster
ms.openlocfilehash: 547f3e14d0e73b944cc7bde31f657dbf4ad49d41
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85773658"
---
# <a name="what-are-data-pools-in-a-sql-server-big-data-cluster"></a>SQL Server ビッグ データ クラスターのデータ プールとは

[!INCLUDE[SQL Server 2019](../includes/applies-to-version/sqlserver2019.md)]

この記事では、[!INCLUDE[big-data-clusters-2019](../includes/ssbigdataclusters-ver15.md)]での *SQL Server データ プール*の役割について説明します。 以下のセクションでは、SQL データ プールのアーキテクチャと機能について説明します。

この 5 分間のビデオでは、データ プールについて説明し、データ プールからデータのクエリを実行する方法について説明します。

> [!VIDEO https://channel9.msdn.com/Shows/Data-Exposed/Querying-Data-from-Big-Data-Cluster-Data-Pool/player?WT.mc_id=dataexposed-c9-niner]

## <a name="data-pool-architecture"></a>データ プールのアーキテクチャ

データ プールは、1 つまたは複数の SQL Server データ プール インスタンスで構成されます。 SQL データ プール インスタンスにより、クラスターに対して永続的な SQL Server ストレージが提供されます。 データ プールは、SQL クエリまたは Spark ジョブからデータを取り込むために使用されます。 大規模なデータセット全体でパフォーマンスを向上させるために、データ プール内のデータは、メンバーである SQL データ プール インスタンス全体のシャードに分散されます。

## <a name="scale-out-data-marts"></a>スケールアウト データ マート

データ プールを使用すると、複数のソースからの外部データがデータ プールに取り込まれるスケールアウト データ マートを作成できます。 データがデータ プール インスタンス間に分散されるため、まとめられたデータに対する並列クエリがより効率的になります。

![スケールアウト データ マート](media/concept-data-pool/data-virtualization-improvements.png)

## <a name="next-steps"></a>次のステップ

[!INCLUDE[big-data-clusters-2019](../includes/ssbigdataclusters-ss-nover.md)] の詳細については、次のリソースを参照してください。

- [[!INCLUDE[big-data-clusters-2019](../includes/ssbigdataclusters-ver15.md)]とは](big-data-cluster-overview.md)
- [ワークショップ: Microsoft [!INCLUDE[big-data-clusters-2019](../includes/ssbigdataclusters-ss-nover.md)] アーキテクチャ](https://github.com/Microsoft/sqlworkshops/tree/master/sqlserver2019bigdataclusters)
