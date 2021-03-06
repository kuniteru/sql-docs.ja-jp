---
title: Oracle スキーマの変換 (OracleToSQL) |Microsoft Docs
description: オプションを設定し、Oracle および SQL Server に接続した後、oracle データベースオブジェクトを SSMA for Oracle で SQL Server データベースオブジェクトに変換する方法について説明します。
ms.prod: sql
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
helpviewer_keywords:
- Conversion Results
ms.assetid: e021182d-31da-443d-b110-937f5db27272
author: nahk-ivanov
ms.author: alexiva
manager: alexiva
ms.openlocfilehash: 907c04d8acd0859b71d1b31d2839c23d5e4b85e8
ms.sourcegitcommit: e8f6c51d4702c0046aec1394109bc0503ca182f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2020
ms.locfileid: "87935066"
---
# <a name="converting-oracle-schemas-oracletosql"></a>Oracle スキーマの変換 (OracleToSQL)
Oracle に接続し、に接続して、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] プロジェクトとデータのマッピングオプションを設定した後、oracle データベースオブジェクトをデータベースオブジェクトに変換でき [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ます。  
  
## <a name="the-conversion-process"></a>変換処理  
データベースオブジェクトを変換すると、Oracle からオブジェクトの定義が取得され、類似のオブジェクトに変換され [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] て、SSMA メタデータに読み込まれます。 のインスタンスに情報は読み込まれません [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 。 その後、メタデータエクスプローラーを使用して、オブジェクトとそのプロパティを表示でき [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ます。  
  
変換中に SSMA は出力メッセージを出力ウィンドウに出力し、エラーメッセージをエラー一覧ウィンドウに出力します。 出力とエラーの情報を使用して、必要な変換結果を取得するために Oracle データベースまたは変換プロセスを変更する必要があるかどうかを判断します。  
  
## <a name="setting-conversion-options"></a>変換オプションの設定  
オブジェクトを変換する前に、[**プロジェクトの設定**] ダイアログボックスでプロジェクトの変換オプションを確認してください。 このダイアログボックスを使用すると、SSMA が関数とグローバル変数を変換する方法を設定できます。 詳細については、「[プロジェクトの設定 &#40;変換&#41; &#40;OracleToSQL&#41;](../../ssma/oracle/project-settings-conversion-oracletosql.md)」を参照してください。  
  
## <a name="conversion-results"></a>変換結果  
次の表は、変換される Oracle オブジェクトと、結果として得られるオブジェクトを示してい [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ます。  
  
|Oracle オブジェクト|結果の SQL Server オブジェクト|  
|-|-|  
|関数|関数をに直接変換できる場合 [!INCLUDE[tsql](../../includes/tsql-md.md)] 、ssma は関数を作成します。<br /><br />場合によっては、関数をストアド プロシージャに変換する必要があります。 この場合、SSMA によってストアド プロシージャが作成され、ストアド プロシージャを呼び出す関数が作成されます。|  
|手順|プロシージャをに直接変換できる場合は [!INCLUDE[tsql](../../includes/tsql-md.md)] 、ssma によってストアドプロシージャが作成されます。<br /><br />場合によっては、独立したトランザクションでストアドプロシージャを呼び出す必要があります。 この場合は、SSMA によって 2 つのストアド プロシージャが作成されます。1 つはプロシージャを実装するストアド プロシージャで、もう 1 つは実装ストアド プロシージャを呼び出すために使用されるものです。|  
|パッケージ|SSMA により、類似したオブジェクト名で統合される一連のストアド プロシージャと関数が作成されます。|  
|シーケンス|SSMA により、シーケンス オブジェクト (SQL Server 2012 または SQL Server 2014) が作成されるか、Oracle シーケンスがエミュレートされます。|  
|インデックスやトリガーなどの依存オブジェクトを含むテーブル|SSMA によって、依存オブジェクトを含むテーブルが作成されます。|  
|トリガーなどの依存オブジェクトを含むビュー|SSMA によって、依存オブジェクトを含むビューが作成されます。|  
|具体化されたビュー|**SSMA では、いくつかの例外を除き、SQL server 上にインデックス付きビューを作成します。具体化されたビューに次の構造体が1つ以上含まれている場合、変換は失敗します。**<br /><br />ユーザー定義関数<br /><br />SELECT、WHERE、GROUP BY 句での非決定的フィールド/関数/式<br /><br />SELECT *、WHERE、または GROUP BY 句での Float 型列の使用 (以前の問題の特別なケース)<br /><br />カスタム データ型 (入れ子になったテーブルを含む)<br /><br />COUNT(distinct &lt;フィールド&gt;)<br /><br />FETCH<br /><br />外部結合 (LEFT、RIGHT、または FULL)<br /><br />サブクエリ、その他のビュー<br /><br />OVER、RANK、LEAD、LOG<br /><br />MIN、MAX<br /><br />UNION、MINUS、INTERSECT<br /><br />HAVING|  
|トリガー|**SSMA は、次の規則に基づいてトリガーを作成します。**<br /><br />BEFORE トリガーは INSTEAD OF トリガーに変換されます。<br /><br />AFTER トリガーは AFTER トリガーに変換されます。<br /><br />INSTEAD OF トリガーは INSTEAD OF トリガーに変換されます。 同じ操作で複数の INSTEAD OF トリガーが定義されている場合は、1 つのトリガーに結合されます。<br /><br />行レベルのトリガーはカーソルを使用してエミュレートされます。<br /><br />カスケード トリガーは複数の個別のトリガーに変換されます。|  
|シノニム|**シノニムは、次のオブジェクトの種類に対して作成されます。**<br /><br />テーブルとオブジェクト テーブル<br /><br />ビューとオブジェクト ビュー<br /><br />ストアド プロシージャ<br /><br />関数<br /><br />**次のオブジェクトのシノニムが解決され、直接オブジェクト参照に置き換えられます。**<br /><br />シーケンス<br /><br />パッケージ<br /><br />Java クラス スキーマ オブジェクト<br /><br />ユーザー定義オブジェクト型<br /><br />別のシノニムのシノニムを移行して、エラーとしてマークすることはできません。<br /><br />具体化されたビューに対してシノニムは作成されません。|  
|ユーザー定義型|**SSMA では、ユーザー定義型の変換はサポートされていません。PL/SQL プログラムでの使用を含め、ユーザー定義型には、次の規則に従った特殊な変換エラーがマークされます。**<br /><br />ユーザー定義型のテーブル列は、VARCHAR (8000) に変換されます。<br /><br />ストアドプロシージャまたは関数に対するユーザー定義型の引数は、VARCHAR (8000) に変換されます。<br /><br />PL/SQL ブロック内のユーザー定義型の変数は、VARCHAR (8000) に変換されます。<br /><br />オブジェクト テーブルは、標準テーブルに変換されます。<br /><br />オブジェクト ビューは、標準ビューに変換されます。|  
  
## <a name="converting-oracle-database-objects"></a>Oracle Database オブジェクトの変換  
Oracle データベースオブジェクトを変換するには、まず変換するオブジェクトを選択し、SSMA によって変換が実行されるようにします。 変換中に出力メッセージを表示するには、[**表示**] メニューの [**出力**] をクリックします。  
  
**Oracle オブジェクトを SQL Server 構文に変換するには**  
  
1.  Oracle メタデータエクスプローラーで、Oracle サーバーを展開し、[**スキーマ**] を展開します。  
  
2.  変換するオブジェクトの選択:  
  
    -   すべてのスキーマを変換するには、[**スキーマ**] の横にあるチェックボックスをオンにします。  
  
    -   データベースを変換または省略するには、スキーマ名の横にあるチェックボックスをオンにします。  
  
    -   オブジェクトのカテゴリを変換または除外するには、スキーマを展開し、カテゴリの横にあるチェックボックスをオンまたはオフにします。  
  
    -   個々のオブジェクトを変換または除外するには、[カテゴリ] フォルダーを展開し、オブジェクトの横にあるチェックボックスをオンまたはオフにします。  
  
3.  選択したすべてのオブジェクトを変換するには、[**スキーマ**] を右クリックし、[**スキーマの変換**] をクリックします。  
  
    また、オブジェクトまたはオブジェクトのカテゴリを右クリックし、[**スキーマの変換**] を選択して、オブジェクトの個々のカテゴリを変換することもできます。  
  
## <a name="viewing-conversion-problems"></a>変換に関する問題の表示  
一部の Oracle オブジェクトが変換されない可能性があります。 変換の成功率を確認するには、概要変換レポートを表示します。  
  
**概要レポートを表示するには**  
  
1.  Oracle メタデータエクスプローラーで、[**スキーマ**] を選択します。  
  
2.  右ペインで、[**レポート**] タブを選択します。  
  
    このレポートには、評価または変換されたすべてのデータベースオブジェクトの概要評価レポートが表示されます。 個々のオブジェクトの概要レポートを表示することもできます。  
  
    -   個々のスキーマのレポートを表示するには、Oracle メタデータエクスプローラーでスキーマを選択します。  
  
    -   個々のオブジェクトのレポートを表示するには、Oracle メタデータエクスプローラーでオブジェクトを選択します。 変換の問題が発生しているオブジェクトには、赤色のエラーアイコンが付いています。  
  
変換に失敗したオブジェクトの場合、変換に失敗した原因となった構文を確認できます。  
  
**個々の変換の問題を表示するには**  
  
1.  Oracle メタデータエクスプローラーで、[**スキーマ**] を展開します。  
  
2.  赤いエラーアイコンが表示されているスキーマを展開します。  
  
3.  スキーマの下に、赤色のエラーアイコンが表示されているフォルダーを展開します。  
  
4.  赤色のエラーアイコンが付いているオブジェクトを選択します。  
  
5.  右ペインで、[**レポート**] タブをクリックします。  
  
6.  [**レポート**] タブの上部にドロップダウンリストが表示されます。 一覧に**統計**が表示されている場合は、選択範囲を**Source**に変更します。  
  
    SSMA では、コードのすぐ上にソースコードといくつかのボタンが表示されます。  
  
7.  [**次の問題**] ボタンをクリックします。 これは、右を指し示す矢印の付いた赤いエラーアイコンです。  
  
    SSMA は、現在のオブジェクトで検出された最初の問題のソースコードを強調表示します。  
  
変換できなかった項目ごとに、そのオブジェクトをどのように処理するかを決定する必要があります。  
  
-   ソースコードを変更するには、[ **SQL** ] タブで手順を実行します。  
  
-   Oracle データベースのオブジェクトを変更して、問題のあるコードを削除または修正することができます。 更新されたコードを SSMA に読み込むには、メタデータを更新する必要があります。 詳細については、「 [Oracle Database &#40;OracleToSQL&#41;への接続](../../ssma/oracle/connecting-to-oracle-database-oracletosql.md)」を参照してください。  
  
-   オブジェクトを移行から除外することができます。 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]メタデータエクスプローラーと Oracle メタデータエクスプローラーで、項目の横にあるチェックボックスをオフにしてから、oracle からオブジェクトを読み込み、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] データを移行します。  
  
## <a name="next-step"></a>次の手順  
移行プロセスの次の手順では、[変換されたオブジェクトを SQL Server に読み込み](loading-converted-database-objects-into-sql-server-oracletosql.md)ます。  
  
## <a name="see-also"></a>参照  
[Oracle データベースの SQL Server &#40;OracleToSQL&#41;への移行](../../ssma/oracle/migrating-oracle-databases-to-sql-server-oracletosql.md)  
  
