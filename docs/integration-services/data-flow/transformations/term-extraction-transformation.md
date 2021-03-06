---
title: 用語抽出変換 | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql13.dts.designer.termextractiontrans.f1
- sql13.dts.designer.termextraction.termextraction.f1
- sql13.dts.designer.termextraction.inclusionexclusion.f1
- sql13.dts.designer.termextraction.advanced.f1
helpviewer_keywords:
- word boundaries [Integration Services]
- extracting data [Integration Services]
- sentence boundaries
- word extractions [Integration Services]
- Term Extraction transformation
- tagging words
- normalized data [Integration Services]
- tokenizing text [Integration Services]
- parts of speech [Integration Services]
- text extraction [Integration Services]
- term extractions [Integration Services]
- stemming words [Integration Services]
ms.assetid: d0821526-1603-4ea6-8322-2d901568fbeb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c76fff59151ffd2e291cd259fbe35fdffd9c4eec
ms.sourcegitcommit: c8e1553ff3fdf295e8dc6ce30d1c454d6fde8088
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2020
ms.locfileid: "86914273"
---
# <a name="term-extraction-transformation"></a>用語抽出変換

[!INCLUDE[sqlserver-ssis](../../../includes/applies-to-version/sqlserver-ssis.md)]


  用語抽出変換は、変換入力列内のテキストから用語を抽出し、変換出力列に書き込みます。 この変換で処理されるテキストは英語テキストのみで、独自の英語辞書および英語に関する言語情報を使用します。  
  
 用語抽出変換を使用すると、データセットの内容を検出できます。 たとえば、電子メール メッセージが含まれるテキストに、製品に関する有用なフィードバックがある場合、用語抽出変換を使用してメッセージに記述されているトピックを抽出し、フィードバックの分析に使用できます。  
  
## <a name="extracted-terms-and-data-types"></a>抽出された用語とデータ型  
 用語抽出変換は、名詞のみ、名詞句のみ、または名詞と名詞句の両方を抽出できます。 名詞とは 1 つの名詞のことです。名詞句とは 2 つ以上の単語で、1 語は名詞、他の語は名詞または形容詞です。 たとえば、この変換が名詞のみのオプションを使用している場合は、 *bicycle* や *landscape*などの用語が抽出されます。名詞句のオプションを使用している場合は、 *new blue bicycle*、 *bicycle helmet*、 *boxed bicycles*などの用語が抽出されます。  
  
 冠詞と代名詞は抽出されません。 たとえば、 *the bicycle* 、 *my bicycle*、および *that bicycle*のテキストからは、用語 *bicycle*が抽出されます。  
  
 用語抽出変換は、抽出する各用語のスコアを生成します。 スコアには、TFIDF 値または生の頻度のどちらかを設定できます。生の頻度とは、正規化された用語が入力内に出現する回数のことです。 どちらの場合も、スコアは 0 より大きい実数で表されます。 たとえば、TFIDF スコアの値は 0.5、頻度は 1.0 または 2.0 などのように表されます。  
  
 用語抽出変換の出力には、2 つの列のみが含まれます。 1 つの列には抽出した用語が含まれ、もう 1 つの列にはスコアが含まれます。 列の既定の名前は、 **Term** と **Score**です。 入力のテキスト列には複数の用語が含まれる場合があるため、通常、用語抽出変換の出力には、入力よりも多くの行が含まれます。  
  
 抽出した用語がテーブルに書き込まれると、用語参照変換、あいまい参照変換、参照変換など、他の参照変換で使用できます。  
  
 用語抽出変換で処理できるテキストは、DT_WSTR または DT_NTEXT データ型のどちらかの列にあるテキストのみです。 列にテキストが含まれていても、これらのデータ型ではない場合、データ変換の変換を使用して、DT_WSTR または DT_NTEXT データ型の列をデータ フローに追加し、列の値を新しい列にコピーできます。 その後、データ変換の変換からの出力を、用語抽出変換への入力として使用できます。 詳細については、「 [Data Conversion Transformation](../../../integration-services/data-flow/transformations/data-conversion-transformation.md)」を参照してください。  
  
## <a name="exclusion-terms"></a>除外用語  
 必要に応じて、用語抽出変換は、除外用語を含むテーブルの列を参照できます。除外用語とは、変換によりデータセットから抽出されたときに、スキップされる用語のことです。 これは、ある用語の組み合わせが、非常に高い頻度で発生するためにノイズ ワードになる場合など、特定の業務や事業では既に重要でないと判断されている場合に便利です。 たとえば、特定ブランドの自動車に関する顧客サポート情報が含まれるデータセットから用語を抽出するときに、ブランド名自体は除外します。ブランド名は非常に頻繁に挙げられるので、重要性を持たないためです。 このため、除外一覧の値は処理するデータセットに応じてカスタマイズする必要があります。  
  
 ある用語を除外一覧に追加すると、その用語を含むすべての用語 (単語または名詞句) も除外されます。 たとえば、除外一覧に 1 つの単語 *data*が含まれる場合、 *data*、 *data mining*、 *data integrity*、および *data validation* など、この単語を含むすべての用語も除外されます。 単語 *data*を含む複合語のみを除外する場合、その複合語を除外一覧に明示的に追加する必要があります。 たとえば、 *data*の出現を抽出して、 *data validation*を除外する場合は、 *data validation* を除外一覧に追加し、除外一覧から *data* が削除されていることを確認します。  
  
 参照テーブルは、 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] または Access データベースのテーブルである必要があります。 用語抽出変換は、個別の OLE DB 接続を使用して、参照テーブルに接続します。 詳細については、「 [OLE DB 接続マネージャー](../../../integration-services/connection-manager/ole-db-connection-manager.md)」を参照してください。  
  
 用語抽出変換は、完全な事前キャッシュ モードで動作します。 用語抽出変換は、実行時に参照テーブルの除外用語を読み取って独自のメモリに格納してから、変換入力行を処理します。  
  
## <a name="extraction-of-terms-from-text"></a>テキストからの用語の抽出  
 用語抽出変換は、テキストから用語を抽出するために次のタスクを実行します。  
  
### <a name="identification-of-words"></a>単語の識別  
 最初に、用語抽出変換は次のタスクを実行することによって単語を識別します。  
  
-   スペース、改行、および英語のその他のターミネータを使用して、テキストを単語に分割します。 たとえば、 *?* や *:* などの句読点は、単語を区切るための文字です。  
  
-   ハイフンまたはアンダースコアでつながれている単語を保持します。 たとえば、 *copy-protected* および *read-only* は、1 単語のまま保持されます。  
  
-   ピリオドを含む頭字語をそのまま残します。 たとえば、 *A.B.C* Company は、 **ABC** および **Company**としてトークン化されます。  
  
-   特殊文字の箇所で単語を分割します。 たとえば、単語 *date/time* は *date* および *time*として、 *(bicycle)* は *bicycle*としてそれぞれ抽出され、さらに、C# は C として扱われます。特殊文字は破棄され、語彙化できません。  
  
-   アポストロフィなどの特殊文字が単語を分割しない場合を認識します。 たとえば、単語 *bicycle's* は、2 つの単語に分割されず、1 つの用語 *bicycle* (名詞) になります。  
  
-   時刻式、金額式、電子メール アドレス、および住所を分割します。 たとえば、日付 *January 31, 2004* は、 *January*、 *31*、および *2004*の 3 つのトークンに分割されます。  
  
### <a name="tagged-words"></a>タグ付きの単語  
 次に、用語抽出変換は、次のいずれかの品詞として単語をタグ付けします。  
  
-   単数形の名詞。 たとえば、 *bicycle* や *potato*などです。  
  
-   複数形の名詞。 たとえば、 *bicycles* や *potatoes*などです。 見出し語化されていないすべての複数形の名詞は、語幹を抽出されます。  
  
-   単数形の固有名詞。 たとえば、 *April* や *Peter*などです。  
  
-   複数形の固有名詞。 たとえば、 *Aprils* や *Peters*などです。 固有名詞の語幹を抽出するには、標準的な英単語に限定されている内部辞書に固有名詞が含まれている必要があります。  
  
-   形容詞。 たとえば、 *blue*などです。  
  
-   2 つのものを比較する、比較級の形容詞。 たとえば、 *higher* や *taller*などです。  
  
-   少なくとも 3 つ以上のものを比較し、そのうちで最も上位または最も下位のものを識別する、最上級の形容詞。 たとえば、 *highest* や *tallest*などです。  
  
-   数字。 たとえば、 *62* や *2004*などです。  
  
 これらの品詞に含まれない単語は破棄されます。 たとえば、動詞や代名詞は破棄されます。  
  
> [!NOTE]  
>  品詞のタグ付けは統計モデルに基づいており、タグ付けが完全に正確でない場合があります。  
  
 用語抽出変換が名詞のみを抽出するように構成されている場合、名詞および固有名詞の単数形または複数形としてタグ付けされている単語のみが抽出されます。  
  
 用語抽出変換が名詞句のみを抽出するように構成されている場合、名詞、固有名詞、形容詞、および数字としてタグ付けされている単語が組み合わされて名詞句となります。ただし名詞句には、名詞または固有名詞の単数形または複数形としてタグ付けされた単語が、少なくとも 1 つは含まれている必要があります。 たとえば、名詞句 *highest mountain* は、最上級の形容詞としてタグ付けされた単語 (*highest*) と、名詞としてタグ付けされた単語 (*mountain*) が組み合わされています。  
  
 用語抽出が名詞と名詞句の両方を抽出するように構成されている場合、名詞の規則と名詞句の規則の両方が適用されます。 たとえば、変換はテキスト *many beautiful blue bicycles* から、 *bicycle* と *beautiful blue bicycle*を抽出します。  
  
> [!NOTE]  
>  抽出された用語には、変換が使用する用語の最大長と頻度のしきい値がそのまま適用されます。  
  
### <a name="stemmed-words"></a>語幹選択された単語  
 また、用語抽出変換は名詞の語幹のみを使用し、名詞の単数形のみを抽出します。 たとえば、 *men* から *man*、 *mice* から *mouse*、および *bicycles* から *bicycle*が抽出されます。 この変換は、名詞の語幹を抽出する際に独自の辞書を使用します。 動名詞は、辞書にある場合は名詞として扱われます。  
  
 さらに、用語抽出変換では、用語抽出変換の内部辞書を使用して、次の例で示すように辞書形式の単語の語幹を選択します。  
  
-   名詞から *s* を削除します。 たとえば、 *bicycles* は *bicycle*になります。  
  
-   名詞から *es* を削除します。 たとえば、 *stories* は *story*になります。  
  
-   不規則名詞の単数形を、辞書から取得します。 たとえば、 *geese* は *goose*になります。  
  
### <a name="normalized-words"></a>正規化された単語  
 用語抽出変換は、文における位置だけが理由で大文字になっている用語を正規化し、代わりに小文字を使用します。 たとえば、句 *Dogs chase cats* および *Mountain paths are steep*において、 *Dogs* および *Mountain* は、 *dog* および *mountain*に正規化されます。  
  
 用語抽出変換は単語を正規化するため、大文字または小文字で表記された単語は、異なる用語としては扱われません。 たとえば、 *You see many bicycles in Seattle* および *Bicycles are blue*のテキストにおいて、 *bicycles* と *Bicycles* は同じ用語として認識され、変換は *bicycle*のみを保持します。 内部辞書の一覧にない固有名詞と単語は、正規化されません。  
  
### <a name="case-sensitive-normalization"></a>大文字と小文字を区別する正規化  
 用語抽出変換は、大文字と小文字の単語を別個の用語と見なすか、または同一用語の変形として見なすように構成できます。  
  
-   大文字と小文字を区別するように変換を構成した場合、 *Method* および *method* などのような用語は、2 つの異なる用語として抽出されます。 文の最初にない大文字の単語は正規化されず、固有名詞としてタグ付けされます。  
  
-   大文字と小文字を区別しないように変換を構成した場合、 *Method* および *method* などのような用語は、1 つの単語の変形として認識されます。 入力データセットで最初に出現した単語に応じて、 *Method* または *method*のどちらかが、抽出された用語の一覧に含まれます。 *Method* が、文の最初の単語であることのみの理由で大文字になっている場合は、正規化された形式で抽出されます。  
  
## <a name="sentence-and-word-boundaries"></a>文および単語の境界  
 用語抽出変換は、次の文字を文の境界として使用することにより、テキストを文に分割します。  
  
-   ASCII 改行文字の 0x0d (キャリッジ リターン) および 0x0a (ライン フィード)。 この文字を文の境界として使用するには、1 行に 2 文字以上の改行文字が含まれている必要があります。  
  
-   ハイフン (–)。 この文字を文の境界として使用するには、アンダースコアが左右の文字の間に挟まれていないことが必要です。  
  
-   アンダースコア (_)。 この文字を文の境界として使用するには、アンダースコアが左右の文字の間に挟まれていないことが必要です。  
  
-   0x19 以下または 0x7b 以上のすべての Unicode 文字。  
  
-   数字、句読点、および英文字の組み合わせ。 たとえば、 *A23B#99* は、用語 *A23B*を返します。  
  
-   %、@、&、$、#、\*、:、;、.、 **、** 、!、?、\<, >、+、=、^、~、|、\\、/、(、)、[、]、{、}、"、' 文字。  
  
    > [!NOTE]  
    >  1 つ以上のピリオド (.) が含まれる頭字語は、複数の文に分割されません。  
  
 次に、用語抽出変換は、次の単語の境界を使用して、文を単語に分割します。  
  
-   Space  
  
-   タブ  
  
-   ASCII 0x0d (キャリッジ リターン)  
  
-   ASCII 0x0a (ライン フィード)  
  
    > [!NOTE]  
    >  アポストロフィが、 *we're* や *it's*などの短縮形の単語に含まれている場合、単語はアポストロフィの位置で分けられます。それ以外の場合、アポストロフィに続く文字は切り捨てられます。 たとえば、 *we're* は *we* と *'re*に分割され、 *bicycle's* は切り捨てられて *bicycle*になります。  
  
## <a name="configuration-of-the-term-extraction-transformation"></a>用語抽出変換の構成  
 用語抽出変換は、内部アルゴリズムと統計モデルを使用して変換結果を生成します。 用語抽出変換を複数回実行して結果を検証し、テキスト マイニング ソリューションに役立つ種類の結果を生成するように変換を構成する必要がある場合があります。  
  
 用語抽出変換は、1 つの標準入力、1 つの出力、および 1 つのエラー出力をとります。  
  
 プロパティを設定するには [!INCLUDE[ssIS](../../../includes/ssis-md.md)] デザイナーから行うか、またはプログラムによって設定します。  
  
 **[詳細エディター]** ダイアログ ボックスまたはプログラムで設定できるプロパティの詳細については、次のトピックのいずれかを参照してください。  
  
-   [Common Properties](https://msdn.microsoft.com/library/51973502-5cc6-4125-9fce-e60fa1b7b796)  
  
-   [変換のカスタム プロパティ](../../../integration-services/data-flow/transformations/transformation-custom-properties.md)  
  
 プロパティの設定方法の詳細については、「 [データ フロー コンポーネントのプロパティを設定する](../../../integration-services/data-flow/set-the-properties-of-a-data-flow-component.md)」を参照してください。  
  
## <a name="term-extraction-transformation-editor-term-extraction-tab"></a>[用語抽出変換エディター] ([用語抽出] タブ)
  **[用語抽出変換エディター]** ダイアログ ボックスの **[用語抽出]** タブを使用すると、抽出するテキストを含むテキスト列を指定できます。  
  
### <a name="options"></a>オプション  
 **使用できる入力列**  
 チェック ボックスを使用して、用語の抽出に使用するテキスト列を 1 つ選択します。  
  
 **用語**  
 抽出された用語を格納する出力列の名前を指定します。  
  
 **スコア**  
 抽出されたそれぞれの用語のスコアを格納する出力列の名前を指定します。  
  
 **エラー出力の構成**  
 [[エラー出力の構成]](https://msdn.microsoft.com/library/5f8da390-fab5-44f8-b268-d8fa313ce4b9) ダイアログ ボックスは、エラーが発生した行に対するエラー処理を指定するために使用します。  
  
## <a name="term-extraction-transformation-editor-exclusion-tab"></a>[用語抽出変換エディター] ([除外] タブ)
  **[用語抽出変換エディター]** ダイアログ ボックスの **[除外]** タブを使用すると、除外テーブルへの接続を設定し、除外用語が含まれている列を指定できます。  
  
### <a name="options"></a>オプション  
 **[除外用語を使用する]**  
 除外用語が含まれている列を指定することにより、用語抽出のときに特定の用語を除外するかどうかを示します。 用語を除外する場合は、次のソース プロパティを指定する必要があります。  
  
 **[キャッシュなし]**  
 既存の OLE DB 接続マネージャーを選択するか、 **[新規作成]** をクリックして新しい接続を作成します。  
  
 **[新規作成]**  
 **[OLE DB 接続マネージャーの構成]** ダイアログ ボックスを使用して、データベースへの新しい接続を作成します。  
  
 **[テーブルまたはビュー]**  
 除外用語が含まれているテーブルまたはビューを選択します。  
  
 **列**  
 除外用語が含まれているテーブルまたはビューの列を選択します。  
  
 **エラー出力の構成**  
 [[エラー出力の構成]](https://msdn.microsoft.com/library/5f8da390-fab5-44f8-b268-d8fa313ce4b9) ダイアログ ボックスは、エラーが発生した行に対するエラー処理を指定するために使用します。  
  
## <a name="term-extraction-transformation-editor-advanced-tab"></a>[用語抽出変換エディター] ([詳細設定] タブ)
  **[用語抽出変換エディター]** ダイアログ ボックスの **[詳細設定]** タブを使用すると、頻度、長さ、語または句の抽出の有無など、抽出に関するプロパティを指定できます。  
  
### <a name="options"></a>オプション  
 **[名詞]**  
 変換によって個別の名詞のみを抽出するように指定します。  
  
 **[名詞句]**  
 変換によって個別の名詞句のみを抽出するように指定します。  
  
 **[名詞と名詞句]**  
 変換によって名詞と名詞句を両方とも抽出するように指定します。  
  
 **頻度**  
 スコアが用語の頻度であることを指定します。  
  
 **[TFIDF]**  
 スコアが用語の TFIDF 値であることを指定します。 TFIDF スコアは、Term Frequency と Inverse Document Frequency の積です。"用語 T の TFIDF = (T の頻度) * log( (入力の行数) / (T を含む行数) )" として定義されます。  
  
 **[頻度のしきい値]**  
 語または句を抽出する前の語または句の出現回数を指定します。 既定値は 2 です。  
  
 **[用語の最大長]**  
 句の最大長を語数で指定します。 このオプションは、名詞句のみに影響を与えます。 既定値は 12 です。  
  
 **[用語抽出で大文字と小文字を区別する]**  
 抽出で大文字と小文字を区別するかどうかを指定します。 既定値は **False**です。  
  
 **エラー出力の構成**  
 [[エラー出力の構成]](https://msdn.microsoft.com/library/5f8da390-fab5-44f8-b268-d8fa313ce4b9) ダイアログ ボックスは、エラーが発生した行に対するエラー処理を指定するために使用します。  
  
## <a name="see-also"></a>参照  
 [Integration Services のエラーおよびメッセージのリファレンス](../../../integration-services/integration-services-error-and-message-reference.md)   
 [用語参照変換](../../../integration-services/data-flow/transformations/term-lookup-transformation.md)  

