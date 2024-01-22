---
title: PDF ファイルにローカル ハイパーリンクを作成
linktitle: PDF ファイルにローカル ハイパーリンクを作成
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して、PDF ファイルにローカル ハイパーリンクを簡単に作成できます。
type: docs
weight: 40
url: /ja/net/programming-with-links-and-actions/create-local-hyperlink/
---
PDF ファイルにローカル ハイパーリンクを作成すると、同じ PDF ドキュメント内の他のページにユーザーを移動するクリック可能なリンクを作成できます。 Aspose.PDF for .NET を使用すると、次のソース コードに従ってそのようなリンクを簡単に作成できます。

## ステップ 1: 必要なライブラリをインポートする

始める前に、C# プロジェクトに必要なライブラリをインポートする必要があります。必要なインポートディレクティブは次のとおりです。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.InteractiveFeatures;
```

## ステップ 2: ドキュメントフォルダーへのパスを設定する

このステップでは、結果の PDF ファイルを保存するフォルダーへのパスを指定する必要があります。交換する`"YOUR DOCUMENT DIRECTORY"`次のコードでは、ドキュメント フォルダーへの実際のパスを指定します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 3: Document のインスタンスを作成する

のインスタンスを作成します。`Document` PDF ドキュメントを表すクラス。対応するコードは次のとおりです。

```csharp
Document doc = new Document();
```

## ステップ 4: ハイパーリンクを含むページとテキストを追加する

このステップでは、PDF ドキュメントにページを追加し、ローカル ハイパーリンクを含むテキストを追加します。各リンクのターゲットページを定義します。対応するコードは次のとおりです。

```csharp
Page page = doc.Pages.Add();

TextFragment text = new TextFragment("Link to page 7");
LocalHyperlink link = new LocalHyperlink();
link.TargetPageNumber = 7;
text. Hyperlink = link;
page.Paragraphs.Add(text);

text = new TextFragment("Link to page 1");
text. IsInNewPage = true;
link = new LocalHyperlink();
link.TargetPageNumber = 1;
text. Hyperlink = link;
page.Paragraphs.Add(text);
```

## ステップ 5: 更新されたドキュメントを保存する

次に、更新された PDF ファイルを保存しましょう。`Save`の方法`doc`物体。対応するコードは次のとおりです。

```csharp
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
doc.Save(dataDir);
```

### Aspose.PDF for .NET を使用してローカル ハイパーリンクを作成するためのサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ドキュメントインスタンスの作成
Document doc = new Document();
// PDF ファイルのページコレクションにページを追加
Page page = doc.Pages.Add();
//テキストフラグメントインスタンスの作成
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("link page number test to page 7");
//ローカル ハイパーリンク インスタンスを作成する
Aspose.Pdf.LocalHyperlink link = new Aspose.Pdf.LocalHyperlink();
//リンクインスタンスのターゲットページを設定する
link.TargetPageNumber = 7;
//TextFragment ハイパーリンクを設定する
text.Hyperlink = link;
//ページの段落コレクションにテキストを追加します
page.Paragraphs.Add(text);
//新しい TextFragment インスタンスを作成する
text = new TextFragment("link page number test to page 1");
//TextFragment は新しいページに追加する必要があります
text.IsInNewPage = true;
//別のローカル ハイパーリンク インスタンスを作成する
link = new LocalHyperlink();
// 番目のハイパーリンクのターゲット ページを設定する
link.TargetPageNumber = 1;
// 番目の TextFragment のリンクを設定します
text.Hyperlink = link;
//ページオブジェクトの段落コレクションにテキストを追加します。
page.Paragraphs.Add(text);    
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
//更新されたドキュメントを保存する
doc.Save(dataDir);
Console.WriteLine("\nLocal hyperlink created successfully.\nFile saved at " + dataDir);            
```

## 結論

おめでとうございます！これで、Aspose.PDF for .NET を使用して PDF にローカル ハイパーリンクを作成するためのステップバイステップ ガイドが完成しました。このコードを使用して、ユーザーを同じドキュメント内の他のページに移動するクリック可能なリンクを作成できます。

高度なハイパーリンク機能の詳細については、公式の Aspose.PDF ドキュメントを必ずご確認ください。

### PDF ファイルにローカル ハイパーリンクを作成する場合の FAQ

#### Q: PDF ファイル内のローカル ハイパーリンクとは何ですか?

A: PDF ファイル内のローカル ハイパーリンクは、同じドキュメント内の別のページにユーザーを移動するクリック可能なリンクです。これらのリンクによりナビゲーションが強化され、読者は関連セクションにすばやくアクセスできるようになります。

#### Q: ローカル ハイパーリンクは PDF ドキュメントにどのようなメリットをもたらしますか?

A: ローカル ハイパーリンクは、同じ PDF ドキュメント内の関連コンテンツを接続する効率的な方法を提供します。読者がドキュメント全体をスクロールせずに特定のセクションにすばやくジャンプできるようにすることで、ユーザー エクスペリエンスが向上します。

#### Q: Aspose.PDF for .NET はローカル ハイパーリンクの作成をどのようにサポートしていますか?
A: Aspose.PDF for .NET は、ローカル ハイパーリンクの作成に対する包括的なサポートを提供します。このガイドで提供されるステップバイステップのチュートリアルでは、C# を使用して PDF ドキュメントにローカル ハイパーリンクを追加する方法を示します。

#### Q: ローカル ハイパーリンクの外観をカスタマイズできますか?

A: はい。ローカル ハイパーリンクの外観 (テキストの色やスタイルなど) をカスタマイズして、ドキュメントのデザインに一致させ、一貫した視覚エクスペリエンスを提供することができます。

#### Q: 単一の PDF ページ内に複数のローカル ハイパーリンクを作成することはできますか?

A: もちろんです！単一の PDF ページ内に複数のローカル ハイパーリンクを作成すると、読者が必要に応じてさまざまなセクションやページにジャンプできるようになります。各ローカル ハイパーリンクは、それぞれのターゲットに合わせて調整できます。

#### Q: ローカル ハイパーリンクを使用して、ページの特定のセクションにリンクできますか?

A: ローカル ハイパーリンクは通常、ページ全体に移動しますが、PDF ドキュメント内にアンカーまたはブックマークを作成して、ターゲットを絞ったリンクを実現できます。 Aspose.PDF for .NET は、さまざまなハイパーリンク オプションをサポートしています。

#### Q: ローカル ハイパーリンクが正しく機能していることを確認するにはどうすればよいですか?

A: 提供されているチュートリアルとサンプル コードに従うことで、機能するローカル ハイパーリンクを自信を持って作成できます。生成された PDF ドキュメントを開いてハイパーリンクされたテキストをクリックすると、リンクをテストできます。

#### Q: ローカル ハイパーリンクを使用する場合、制限はありますか?

A: ローカル ハイパーリンクはドキュメントのナビゲーションを強化する効果的な方法ですが、ドキュメントの構造が明確で直感的なものであることが重要です。適切にラベル付けされたハイパーリンクとアンカーは、ポジティブなユーザー エクスペリエンスに貢献します。

#### Q: 表または画像内にローカル ハイパーリンクを作成できますか?

A: はい、表、画像、テキストなど、PDF ドキュメントのさまざまな要素内にローカル ハイパーリンクを作成できます。 Aspose.PDF for .NET は、さまざまな種類のコンテンツにハイパーリンクを柔軟に追加できます。