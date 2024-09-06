---
title: 要素に構造要素を追加する
linktitle: 要素に構造要素を追加する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ドキュメント内の要素に構造要素を追加するためのステップバイステップ ガイド。
type: docs
weight: 20
url: /ja/net/programming-with-tagged-pdf/add-structure-element-into-element/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメント内の要素に構造要素を追加する方法について、ステップ バイ ステップ ガイドを提供します。Aspose.PDF は、プログラムで PDF ドキュメントを作成、操作、変換できる強力なライブラリです。Aspose.PDF のマークされたコンテンツ構造機能を使用すると、PDF ドキュメントに階層構造を作成できます。

## 前提条件

始める前に、次の前提条件が満たされていることを確認してください。

1. .NET フレームワークとともにインストールされた Visual Studio。
2. .NET 用の Aspose.PDF ライブラリ。

## ステップ1: プロジェクトのセットアップ

まず、Visual Studio で新しいプロジェクトを作成し、Aspose.PDF for .NET ライブラリへの参照を追加します。ライブラリは Aspose の公式 Web サイトからダウンロードして、マシンにインストールできます。

## ステップ2: 必要な名前空間をインポートする

C# コード ファイルで、Aspose.PDF によって提供されるクラスとメソッドにアクセスするために必要な名前空間をインポートします。

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## ステップ3: PDF文書を作成し、構造化要素を定義する

次のコードを使用して PDF ドキュメントを作成し、構造化要素を定義します。

```csharp

string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";

Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Text Items");
taggedContent.SetLanguage("fr-FR");

StructureElement rootElement = taggedContent.RootElement;

ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);

ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);

ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("Span_31");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText(" and Span_32");
p3.AppendChild(span31);
p3.AppendChild(span32);
p3.SetText(".");

ParagraphElement p4 = taggedContent.CreateParagraphElement();
root

Element.AppendChild(p4);
SpanElement span41 = taggedContent.CreateSpanElement();
SpanElement span411 = taggedContent.CreateSpanElement();
span411.SetText("Span_411, ");
span41.SetText("Span_41, ");
span41.AppendChild(span411);
SpanElement span42 = taggedContent.CreateSpanElement();
SpanElement span421 = taggedContent.CreateSpanElement();
span421.SetText("Span 421 and ");
span42.AppendChild(span421);
span42.SetText("Span_42");
p4.AppendChild(span41);
p4.AppendChild(span42);
p4.SetText(".");
```

このコードは、空の PDF ドキュメントを作成し、段落や範囲などの構造化要素を追加します。各構造要素は、Aspose.PDF によって提供されるメソッドを使用して作成されます。

## ステップ4: PDFドキュメントを保存する

PDF ドキュメントを保存するには、次のコードを使用します。

```csharp
document. Save(outFile);
```

このコードは、構造化された要素を含む PDF ドキュメントを指定されたファイルに保存します。

### Aspose.PDF for .NET を使用して構造要素を要素に追加するためのサンプル ソース コード 
```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";
//ドキュメントの作成とタグ付けされたPDFコンテンツの取得
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
//文書のタイトルと自然言語の設定
taggedContent.SetTitle("Text Elements Example");
taggedContent.SetLanguage("en-US");
//ルート構造要素（ドキュメント構造要素）の取得
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("Span_31");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText(" and Span_32");
p3.AppendChild(span31);
p3.AppendChild(span32);
p3.SetText(".");
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
SpanElement span41 = taggedContent.CreateSpanElement();
SpanElement span411 = taggedContent.CreateSpanElement();
span411.SetText("Span_411, ");
span41.SetText("Span_41, ");
span41.AppendChild(span411);
SpanElement span42 = taggedContent.CreateSpanElement();
SpanElement span421 = taggedContent.CreateSpanElement();
span421.SetText("Span 421 and ");
span42.AppendChild(span421);
span42.SetText("Span_42");
p4.AppendChild(span41);
p4.AppendChild(span42);
p4.SetText(".");
//タグ付き PDF ドキュメントを保存
document.Save(outFile);
//PDF/UA準拠の確認
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメント内の要素に構造要素を追加する方法を学習しました。Aspose.PDF のマークされたコンテンツ構造機能を使用すると、PDF ドキュメントに階層構造を作成でき、コンテンツの管理とナビゲーションが容易になります。

### よくある質問

#### Q: Aspose.PDF for .NET を使用して PDF ドキュメント内の要素に構造要素を追加する目的は何ですか?

A: Aspose.PDF for .NET を使用して PDF ドキュメント内の要素に構造要素を追加すると、ドキュメントのコンテンツ内に階層構造を作成できます。この階層構造により、コンテンツの整理とナビゲーションが強化され、特定の要素の管理とアクセスが容易になります。

#### Q: Aspose.PDF ライブラリは、PDF ドキュメントに構造要素を追加するのにどのように役立ちますか?

A: Aspose.PDF for .NET は、PDF ドキュメントをプログラムで作成、操作、変換する機能を提供する強力なライブラリです。このチュートリアルでは、ライブラリのマークされたコンテンツ構造機能を利用して、PDF ドキュメントのコンテンツに構造要素を作成し、追加します。

#### Q: Aspose.PDF for .NET を使用して PDF ドキュメントに構造要素を追加するための前提条件は何ですか?

A: 始める前に、.NET フレームワークとともに Visual Studio がインストールされており、プロジェクトで .NET 用の Aspose.PDF ライブラリが参照されていることを確認してください。

#### Q: 提供されている C# コードはどのようにして構造要素を作成し、PDF ドキュメントのコンテンツに追加するのでしょうか?

A: このコードは、PDF ドキュメントを作成し、ルート構造要素を定義し、段落やスパンなどのさまざまな構造化要素を追加する方法を示しています。各構造化要素は Aspose.PDF が提供するメソッドを使用して作成され、階層構造を構築できます。

#### Q: PDF ドキュメントに追加する構造要素の種類をカスタマイズできますか?

A: はい、Aspose.PDF ライブラリが提供するさまざまなメソッドを調べることで、構造要素の種類をカスタマイズできます。コードでは段落と範囲を例として示していますが、必要に応じて他の種類の構造化要素を作成して追加することもできます。

#### Q: 追加された構造要素間の階層関係をどのように定義すればよいですか?

 A: 構造要素間の階層関係は、親要素に追加する順序によって定義されます。コードでは、親子関係は`AppendChild`方法。

#### Q: PDF ドキュメントに階層構造を作成する利点は何ですか?

A: PDF ドキュメントに階層構造を作成すると、アクセシビリティ、ナビゲーション、および構成が向上します。これにより、支援技術がドキュメントのコンテンツをより適切に解釈して伝達できるようになり、障害を持つ人にとってより使いやすくなります。

#### Q: 構造要素を追加した後、PDF/UA 準拠を検証するにはどうすればよいですか?

 A: チュートリアルで提供されるコードは、PDF/UA準拠を検証する方法を示しています。`Validate`方法。ドキュメントを PDF/UA 標準に照らして検証することで、追加された構造要素がアクセシビリティ ガイドラインに準拠していることを確認できます。

#### Q: この方法を使用して、既存の PDF ドキュメントに構造要素を追加できますか?

A: はい、提供されている方法を変更して、既存の PDF ドキュメントに構造要素を追加できます。新しいドキュメントを作成する代わりに、Aspose.PDF を使用して既存のドキュメントを読み込み、同様の手順に従って構造要素を追加します。