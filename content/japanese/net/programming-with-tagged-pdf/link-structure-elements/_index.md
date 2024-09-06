---
title: リンク構造要素
linktitle: リンク構造要素
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET でリンク構造要素を使用するためのステップバイステップ ガイド。PDF ドキュメントにハイパーリンクを作成します。
type: docs
weight: 120
url: /ja/net/programming-with-tagged-pdf/link-structure-elements/
---
このステップバイステップ ガイドでは、Aspose.PDF for .NET でリンク構造要素を使用する方法を説明します。Aspose.PDF は、PDF ドキュメントをプログラムで作成および操作できる強力なライブラリです。リンク構造要素を使用すると、PDF ドキュメントにハイパーリンクを追加でき、ユーザーはリンクをクリックしてオンライン リソースに移動できます。

コードを調べて、Aspose.PDF for .NET でリンク構造要素を使用する方法を学びましょう。

## 前提条件

始める前に、次のものがあることを確認してください。

1. .NET 用の Aspose.PDF ライブラリがインストールされています。
2. C# プログラミング言語に関する基本的な知識。

## ステップ1: 環境の設定

まず、C# 開発環境を開いて新しいプロジェクトを作成します。プロジェクトに .NET 用の Aspose.PDF ライブラリへの参照を追加したことを確認します。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";
```

## ステップ2: ドキュメントの作成

最初のステップは、`Document`クラス。

```csharp
// PDFドキュメントを作成する
Document document = new Document();
```

## ステップ3: タグ付けされたコンテンツを操作する

次に、作業するドキュメントのタグ付けされたコンテンツを取得します。

```csharp
//ドキュメントのタグ付けされたコンテンツを取得する
ITaggedContent taggedContent = document.TaggedContent;
```

## ステップ4: ドキュメントのタイトルと言語を設定する

これで、ドキュメントのタイトルと言語を設定できます。

```csharp
//文書のタイトルと言語を定義する
taggedContent.SetTitle("Example Link Items");
taggedContent.SetLanguage("fr-FR");
```

## ステップ5: リンク構造要素を追加する

次に、ドキュメントにリンク構造要素を追加してみましょう。単純なテキスト リンク、画像リンク、複数行リンクなど、さまざまな種類のリンクを作成します。
```csharp
//ルート構造要素（ドキュメント構造要素）を取得する
StructureElement rootElement = taggedContent.RootElement;

//ハイパーリンク付きの段落を追加する
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";

//リッチテキストを含むハイパーリンク付きの段落を追加する
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";

//部分的に書式設定されたテキストを含むハイパーリンクを含む段落を追加する
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("G");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText("oogle");
link3.AppendChild(span31);
link3.SetText("-");
link3.AppendChild(span32);
link3.AlternateDescriptions = "Link to Google";

//複数行のハイパーリンクを含む段落を追加する
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://google.com");
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";

//画像を含むハイパーリンクを含む段落を追加する
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.com");
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
StructureAttributes linkLayoutAttributes = link5.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
StructureAttribute placementAttribute = new StructureAttribute(AttributeKey.Placement);
placementAttribute.SetNameValue(AttributeName.Placement_Block);
linkLayoutAttributes.SetAttribute(placementAttribute);
link5.AppendChild(figure5);
link5.AlternateDescriptions = "Link to Google";
```

## ステップ6: タグ付きPDF文書を保存する

最後に、タグ付けされた PDF ドキュメントを保存します。

```csharp
//タグ付けされたPDF文書を保存する
document. Save(outFile);
```

## ステップ7: PDF/UA準拠を確認する

また、ドキュメントがPDF/UAに準拠しているかどうかを確認するには、`Validate`方法の`Document`クラス。

```csharp
// PDF/UA準拠を確認する
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```


### Aspose.PDF for .NET を使用したリンク構造要素のサンプル ソース コード 
```csharp

//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";

//ドキュメントの作成とタグ付けされたPDFコンテンツの取得
Document document = new Document(); 
ITaggedContent taggedContent = document.TaggedContent;

//文書のタイトルと自然言語の設定
taggedContent.SetTitle("Link Elements Example");
taggedContent.SetLanguage("en-US");

//ルート構造要素（ドキュメント構造要素）の取得
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("G");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText("oogle");
link3.AppendChild(span31);
link3.SetText("-");
link3.AppendChild(span32);
link3.AlternateDescriptions = "Link to Google";
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://google.com");
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.com");
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
StructureAttributes linkLayoutAttributes = link5.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
StructureAttribute placementAttribute = new StructureAttribute(AttributeKey.Placement);
placementAttribute.SetNameValue(AttributeName.Placement_Block);
linkLayoutAttributes.SetAttribute(placementAttribute);
link5.AppendChild(figure5);
link5.AlternateDescriptions = "Link to Google";

//タグ付き PDF ドキュメントを保存
document.Save(outFile);

//PDF/UA準拠の確認
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```
## 結論

おめでとうございます。Aspose.PDF for .NET でリンク構造要素を使用する方法を学習しました。これで、PDF ドキュメントにハイパーリンクを作成して、ユーザーがオンライン リソースに移動できるようにすることができます。Aspose.PDF のその他の機能を試して探索し、インタラクティブで充実した PDF ドキュメントを作成してください。

### よくある質問

#### Q: PDF ドキュメント内のリンク構造要素とは何ですか? また、リンク構造要素によってドキュメントのインタラクティブ性がどのようにして強化されるのですか?

A: PDF ドキュメント内のリンク構造要素は、ユーザーがオンライン リソースやドキュメント内の特定の場所へ移動できるようにするハイパーリンクを作成するために使用されます。これらの要素は、ユーザーが関連コンテンツや外部 Web サイトにアクセスできるようにするクリック可能なリンクを提供することで、インタラクティブ性を高めます。

#### Q: PDF ドキュメントでリンク構造要素を使用するとどのようなメリットがありますか?

A: リンク構造要素は、PDF ドキュメントをインタラクティブにすることで、ユーザー エクスペリエンスを向上させます。リンク構造要素により、追加情報、関連コンテンツ、外部 Web サイト、またはドキュメント内の特定のセクションにすばやくアクセスできるようになり、ナビゲーションが改善され、情報の検索が容易になります。

#### Q: Aspose.PDF for .NET のリンク構造要素を使用して、さまざまな種類のハイパーリンクを作成できますか?

A: はい、リンク構造要素を使用してさまざまな種類のハイパーリンクを作成できます。Aspose.PDF for .NET を使用すると、プレーン テキスト、リッチ テキスト、画像、複数行の説明を含むハイパーリンクを作成できるため、外部コンテンツやドキュメント内の場所にリンクする方法に柔軟性がもたらされます。

#### Q: Aspose.PDF for .NET を使用して PDF ドキュメント内のリンク構造要素を設定および初期化するにはどうすればよいですか?

 A: リンク構造要素を使用するには、まず、`Document`クラス。次に、`TaggedContent`ドキュメントのプロパティ。そこから、リンク構造要素を作成およびカスタマイズし、ルート構造要素に追加できます。

#### Q: リンク構造要素を使用して単純なテキストハイパーリンクを作成するにはどうすればよいですか?
 A: 単純なテキストハイパーリンクを作成するには、`LinkElement`そしてその設定`Hyperlink`財産を`WebHyperlink`リンク先のURLを入力します。また、`SetText`方法。

#### Q: リンク構造要素を使用して画像にハイパーリンクを作成することは可能ですか?

 A: はい、リンク構造要素を使用して画像にハイパーリンクを作成できます。`LinkElement`そして、`FigureElement`これに画像を追加します。これにより、画像ベースのハイパーリンクを作成できます。

#### Q: ハイパーリンクを含む PDF ドキュメントがアクセシビリティの PDF/UA 標準に準拠していることを確認するにはどうすればよいですか?

 A: Aspose.PDF for .NETは、PDFドキュメントがPDF/UA標準に準拠していることを検証する機能を提供します。`Validate`方法の`Document`クラス。これにより、ドキュメントのハイパーリンクが障害を持つユーザーにもアクセス可能になります。

#### Q: リンク構造要素の代替説明とは何ですか? また、なぜ重要ですか?

A: リンク構造要素の代替説明 (alt テキスト) は、ハイパーリンクのテキスト説明を提供します。これらの説明はアクセシビリティに不可欠であり、視覚障害のあるユーザーがリンクの目的とリンク先を理解できるようにします。

#### Q: リンク構造要素を使用して作成されたハイパーリンクの外観と動作をカスタマイズできますか?

A: リンク構造要素は主にハイパーリンクの作成に重点を置いていますが、Aspose.PDF for .NET が提供する他の機能を使用して、ハイパーリンクの外観と動作をさらにカスタマイズできます。これには、色、スタイル、リンク アクションの指定が含まれます。

#### Q: リンク構造要素は、PDF ドキュメントをよりインタラクティブでユーザーフレンドリーにするのにどのように役立ちますか?

A: リンク構造要素は、クリック可能なハイパーリンクを追加することで、静的な PDF ドキュメントをインタラクティブなエクスペリエンスに変換します。このインタラクティブ性により、ユーザーのエンゲージメントが向上し、関連するコンテンツ間のシームレスなナビゲーションが可能になり、ドキュメント全体の使いやすさが向上します。