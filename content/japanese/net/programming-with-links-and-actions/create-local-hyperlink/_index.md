---
title: PDF ファイルにローカル ハイパーリンクを作成する
linktitle: PDF ファイルにローカル ハイパーリンクを作成する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して、PDF ファイルにローカル ハイパーリンクを簡単に作成します。
type: docs
weight: 40
url: /ja/net/programming-with-links-and-actions/create-local-hyperlink/
---
PDF ファイルにローカル ハイパーリンクを作成すると、クリック可能なリンクを作成して、同じ PDF ドキュメント内の他のページにユーザーを移動できます。Aspose.PDF for .NET を使用すると、次のソース コードに従って、このようなリンクを簡単に作成できます。

## ステップ1: 必要なライブラリをインポートする

始める前に、C# プロジェクトに必要なライブラリをインポートする必要があります。必要なインポート ディレクティブは次のとおりです。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.InteractiveFeatures;
```

## ステップ2: ドキュメントフォルダへのパスを設定する

このステップでは、結果のPDFファイルを保存するフォルダへのパスを指定する必要があります。`"YOUR DOCUMENT DIRECTORY"`次のコードでは、ドキュメント フォルダーへの実際のパスを指定します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ3: Documentのインスタンスを作成する

インスタンスを作成します`Document`PDF ドキュメントを表すクラスです。対応するコードは次のとおりです。

```csharp
Document doc = new Document();
```

## ステップ4: ハイパーリンク付きのページとテキストを追加する

このステップでは、PDF ドキュメントにページを追加し、ローカル ハイパーリンクを含むテキストを追加します。各リンクのターゲット ページを定義します。対応するコードは次のとおりです。

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

## ステップ5: 更新したドキュメントを保存する

更新したPDFファイルを保存してみましょう。`Save`方法の`doc`オブジェクト。対応するコードは次のとおりです。

```csharp
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
doc.Save(dataDir);
```

### Aspose.PDF for .NET を使用してローカル ハイパーリンクを作成するためのサンプル ソース コード 
```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ドキュメントインスタンスを作成する
Document doc = new Document();
// PDFファイルのページコレクションにページを追加する
Page page = doc.Pages.Add();
//テキストフラグメントインスタンスを作成する
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("link page number test to page 7");
//ローカルハイパーリンクインスタンスを作成する
Aspose.Pdf.LocalHyperlink link = new Aspose.Pdf.LocalHyperlink();
//リンクインスタンスのターゲットページを設定する
link.TargetPageNumber = 7;
//TextFragmentハイパーリンクを設定する
text.Hyperlink = link;
//ページの段落コレクションにテキストを追加する
page.Paragraphs.Add(text);
//新しい TextFragment インスタンスを作成する
text = new TextFragment("link page number test to page 1");
//TextFragment は新しいページに追加する必要があります
text.IsInNewPage = true;
//別のローカルハイパーリンクインスタンスを作成する
link = new LocalHyperlink();
//2番目のハイパーリンクのターゲットページを設定する
link.TargetPageNumber = 1;
//2番目のTextFragmentのリンクを設定する
text.Hyperlink = link;
//ページオブジェクトの段落コレクションにテキストを追加する
page.Paragraphs.Add(text);    
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
//更新されたドキュメントを保存する
doc.Save(dataDir);
Console.WriteLine("\nLocal hyperlink created successfully.\nFile saved at " + dataDir);            
```

## 結論

おめでとうございます! Aspose.PDF for .NET を使用して PDF にローカル ハイパーリンクを作成する手順を学習しました。このコードを使用して、ユーザーを同じドキュメント内の他のページに移動するクリック可能なリンクを作成できます。

高度なハイパーリンク機能の詳細については、Aspose.PDF の公式ドキュメントを必ず確認してください。

### PDF ファイルにローカル ハイパーリンクを作成するための FAQ

#### Q: PDF ファイル内のローカルハイパーリンクとは何ですか?

A: PDF ファイル内のローカル ハイパーリンクはクリック可能なリンクで、ユーザーを同じドキュメント内の別のページに移動します。これらのリンクによりナビゲーションが強化され、読者は関連するセクションにすばやくアクセスできます。

#### Q: ローカル ハイパーリンクは PDF ドキュメントにどのようなメリットをもたらしますか?

A: ローカル ハイパーリンクは、同じ PDF ドキュメント内の関連コンテンツを効率的に接続する方法を提供します。これにより、読者はドキュメント全体をスクロールせずに特定のセクションにすばやくジャンプできるため、ユーザー エクスペリエンスが向上します。

#### Q: Aspose.PDF for .NET はローカル ハイパーリンクの作成をどのようにサポートしますか?
A: Aspose.PDF for .NET は、ローカル ハイパーリンクの作成を包括的にサポートしています。このガイドで提供されるステップバイステップのチュートリアルでは、C# を使用して PDF ドキュメントにローカル ハイパーリンクを追加する方法を説明します。

#### Q: ローカルハイパーリンクの外観をカスタマイズできますか?

A: はい、テキストの色やスタイルなど、ローカル ハイパーリンクの外観をカスタマイズして、ドキュメントのデザインと一致し、一貫した視覚的エクスペリエンスを提供できます。

#### Q: 1 つの PDF ページ内に複数のローカル ハイパーリンクを作成することは可能ですか?

A: もちろんです! 1 つの PDF ページ内に複数のローカル ハイパーリンクを作成できるため、読者は必要に応じてさまざまなセクションやページにジャンプできます。各ローカル ハイパーリンクは、それぞれのターゲットに合わせてカスタマイズできます。

#### Q: ローカル ハイパーリンクを使用してページの特定のセクションにリンクできますか?

A: ローカル ハイパーリンクは通常、ページ全体に移動しますが、PDF ドキュメント内にアンカーまたはブックマークを作成して、対象を絞ったリンクを実現できます。Aspose.PDF for .NET は、さまざまなハイパーリンク オプションをサポートしています。

#### Q: ローカル ハイパーリンクが正しく機能していることを確認するにはどうすればよいですか?

A: 提供されているチュートリアルとサンプル コードに従うことで、機能的なローカル ハイパーリンクを自信を持って作成できます。生成された PDF ドキュメントを開き、ハイパーリンクされたテキストをクリックして、リンクをテストできます。

#### Q: ローカルハイパーリンクを使用する場合、何か制限はありますか?

A: ローカル ハイパーリンクはドキュメントのナビゲーションを強化する効果的な方法ですが、ドキュメントの構造が明確で直感的であることを確認することが重要です。適切にラベル付けされたハイパーリンクとアンカーは、ユーザー エクスペリエンスの向上に貢献します。

#### Q: 表や画像内にローカルハイパーリンクを作成できますか?

A: はい、表、画像、テキストなど、PDF ドキュメントのさまざまな要素内にローカル ハイパーリンクを作成できます。Aspose.PDF for .NET では、さまざまな種類のコンテンツにハイパーリンクを柔軟に追加できます。