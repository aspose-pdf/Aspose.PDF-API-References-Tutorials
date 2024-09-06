---
title: インライン構造要素
linktitle: インライン構造要素
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET でオンライン構造要素を使用するためのステップバイステップ ガイド。見出しと段落を使用して PDF を整理します。
type: docs
weight: 110
url: /ja/net/programming-with-tagged-pdf/inline-structure-elements/
---
このステップバイステップ ガイドでは、Aspose.PDF for .NET でインライン構造要素を使用する方法を説明します。Aspose.PDF は、PDF ドキュメントをプログラムで操作できる強力なライブラリです。インライン構造要素を使用すると、さまざまなレベルの見出しや段落を使用して、PDF ドキュメントに階層構造を作成できます。

コードを調べて、Aspose.PDF for .NET でインライン構造要素を使用する方法を学びましょう。

## 前提条件

始める前に、次のものがあることを確認してください。

1. .NET 用の Aspose.PDF ライブラリがインストールされています。
2. C# プログラミング言語に関する基本的な知識。

## ステップ1: 環境の設定

まず、C# 開発環境を開いて新しいプロジェクトを作成します。プロジェクトに .NET 用の Aspose.PDF ライブラリへの参照を追加したことを確認します。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
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
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

## ステップ5: オンラインで構造要素を追加する

ここで、さまざまなレベルの見出しや段落などのインライン構造要素をドキュメントに追加します。

```csharp
//ルート構造要素を取得する
StructureElement rootElement = taggedContent.RootElement;

//異なるレベルのヘッダーを追加する
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);

//各ヘッダーにコンテンツを追加する
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1.");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 header");
h1.AppendChild(spanH12);

SpanElement spanH21 = taggedContent.CreateSpanElement();
spanH21.SetText("H2.");
h2.AppendChild(spanH21);
SpanElement spanH22 = taggedContent.CreateSpanElement();
spanH22.SetText("Level 2 header");
h2.AppendChild(spanH22);

SpanElement spanH31 = taggedContent.CreateSpanElement();
spanH31.SetText("H3.");
h3.AppendChild(spanH31);
SpanElement spanH32 = taggedContent.CreateSpanElement();
spanH32.SetText("Level 3 header");
h3.AppendChild(spanH32);

SpanElement spanH41 = taggedContent.CreateSpanElement();
spanH41.SetText("H4.");
h4.AppendChild(spanH41);
SpanElement spanH42 = taggedContent.CreateSpanElement();
spanH42.SetText("Level 4 header");
h4.AppendChild(spanH42);

SpanElement spanH51 = taggedContent.CreateSpanElement();
spanH51.SetText("H5.");
h5.AppendChild(spanH51);
SpanElement spanH52 = taggedContent.CreateSpanElement();
spanH52.SetText("Level 5 header");
h5.AppendChild(spanH52);

SpanElement spanH61 = taggedContent.CreateSpanElement();
spanH61.SetText("H6.");
h6.AppendChild(spanH61);
SpanElement spanH62 = taggedContent.CreateSpanElement();
spanH62.SetText("Heading level 6");
h6.AppendChild(spanH62);

//段落を追加する
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P.");
rootElement.AppendChild(p);

//段落にコンテンツを追加する
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit.");
p.AppendChild(span1);
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Aenean nec lectus ac sem faucibus imperdiet.");
p.AppendChild(span2);
SpanElement span3 = taggedContent.CreateSpanElement();
span3.SetText("Sed ut erat ac magna ullamcorper hendrerit.");
p.AppendChild(span3);
SpanElement span4 = taggedContent.CreateSpanElement();
span4.SetText("Cras pellentesque libero semper, gravida magna sed, luctus leo.");
p.AppendChild(span4);
SpanElement span5 = taggedContent.CreateSpanElement();
span5.SetText("Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit.");
p.AppendChild(span5);
SpanElement span6 = taggedContent.CreateSpanElement();
span6.SetText("Interdum et malesuada fames ac ante ipsum primis in faucibus. ");
p.AppendChild(span6);
SpanElement span7 = taggedContent.CreateSpanElement();
span7.SetText("Aliquam lacinia sit amet elit ac consectetur. So cursus condimentum ligula, vitae volutpat sem tristique eget. ");
p.AppendChild(span7);
SpanElement span8 = taggedContent.CreateSpanElement();
span8.SetText("Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. ");
p.AppendChild(span8);
SpanElement span9 = taggedContent.CreateSpanElement();
span9.SetText("Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit.");
p.AppendChild(span9);
SpanElement span10 = taggedContent.CreateSpanElement();
span10.SetText("Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
p.AppendChild(span10);
```

ここでは、さまざまなレベルの見出しや段落などのインライン構造要素を作成し、それらにコンテンツを追加します。

## ステップ6: タグ付きPDF文書を保存する

最後に、タグ付けされた PDF ドキュメントを保存します。

```csharp
//タグ付けされたPDF文書を保存する
document.Save(dataDir + "InlineStructureElements.pdf");
```

### Aspose.PDF for .NET を使用したインライン構造要素のサンプル ソース コード 

```csharp

//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//PDFドキュメントを作成
Document document = new Document();

//TaggedPdfで作業用のコンテンツを取得する
ITaggedContent taggedContent = document.TaggedContent;

//ドキュメントのタイトルと言語を設定する
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");

//ルート構造要素を取得
StructureElement rootElement = taggedContent.RootElement;
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1. ");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 Header");
h1.AppendChild(spanH12);
SpanElement spanH21 = taggedContent.CreateSpanElement();
spanH21.SetText("H2. ");
h2.AppendChild(spanH21);
SpanElement spanH22 = taggedContent.CreateSpanElement();
spanH22.SetText("Level 2 Header");
h2.AppendChild(spanH22);
SpanElement spanH31 = taggedContent.CreateSpanElement();
spanH31.SetText("H3. ");
h3.AppendChild(spanH31);
SpanElement spanH32 = taggedContent.CreateSpanElement();
spanH32.SetText("Level 3 Header");
h3.AppendChild(spanH32);
SpanElement spanH41 = taggedContent.CreateSpanElement();
spanH41.SetText("H4. ");
h4.AppendChild(spanH41);
SpanElement spanH42 = taggedContent.CreateSpanElement();
spanH42.SetText("Level 4 Header");
h4.AppendChild(spanH42);
SpanElement spanH51 = taggedContent.CreateSpanElement();
spanH51.SetText("H5. ");
h5.AppendChild(spanH51);
SpanElement spanH52 = taggedContent.CreateSpanElement();
spanH52.SetText("Level 5 Header");
h5.AppendChild(spanH52);
SpanElement spanH61 = taggedContent.CreateSpanElement();
spanH61.SetText("H6. ");
h6.AppendChild(spanH61);
SpanElement spanH62 = taggedContent.CreateSpanElement();
spanH62.SetText("Level 6 Header");
h6.AppendChild(spanH62);
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P. ");
rootElement.AppendChild(p);
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit. ");
p.AppendChild(span1);
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Aenean nec lectus ac sem faucibus imperdiet. ");
p.AppendChild(span2);
SpanElement span3 = taggedContent.CreateSpanElement();
span3.SetText("Sed ut erat ac magna ullamcorper hendrerit. ");
p.AppendChild(span3);
SpanElement span4 = taggedContent.CreateSpanElement();
span4.SetText("Cras pellentesque libero semper, gravida magna sed, luctus leo. ");
p.AppendChild(span4);
SpanElement span5 = taggedContent.CreateSpanElement();
span5.SetText("Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit. ");
p.AppendChild(span5);
SpanElement span6 = taggedContent.CreateSpanElement();
span6.SetText("Interdum et malesuada fames ac ante ipsum primis in faucibus. ");
p.AppendChild(span6);
SpanElement span7 = taggedContent.CreateSpanElement();
span7.SetText("Aliquam lacinia sit amet elit ac consectetur. Donec cursus condimentum ligula, vitae volutpat sem tristique eget. ");
p.AppendChild(span7);
SpanElement span8 = taggedContent.CreateSpanElement();
span8.SetText("Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. ");
p.AppendChild(span8);
SpanElement span9 = taggedContent.CreateSpanElement();
span9.SetText("Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit. ");
p.AppendChild(span9);
SpanElement span10 = taggedContent.CreateSpanElement();
span10.SetText("Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
p.AppendChild(span10);

//タグ付き PDF ドキュメントを保存
document.Save(dataDir + "InlineStructureElements.pdf");

```

## 結論

おめでとうございます。Aspose.PDF for .NET でインライン構造要素を使用する方法を学習しました。これで、さまざまなレベルの見出しと段落を使用して、PDF ドキュメントに階層構造を作成できます。Aspose.PDF のその他の機能を調べて、その可能性を最大限に引き出してください。

### よくある質問

#### Q: PDF ドキュメントのインライン構造要素とは何ですか? また、それらは階層構造の作成にどのように貢献しますか?

A: PDF ドキュメント内のインライン構造要素 (さまざまなレベルの見出しや段落など) は、コンテンツを構造的に整理して表示する階層構造を作成するために使用されます。これらの要素を使用すると、ドキュメント内で明確な階層と情報の流れを確立できます。

#### Q: インライン構造要素により、PDF ドキュメントの読みやすさと構成がどのように向上しますか?

A: インライン構造要素、特に見出しと段落は、論理的な構造を提供することで、PDF ドキュメントの読みやすさと構成を改善するのに役立ちます。見出しはさまざまな重要度を示し、読者がコンテンツ内を移動するのに役立ちます。一方、段落は関連する情報をグループ化します。

#### Q: Aspose.PDF for .NET では、インライン構造要素の使用がどのようにして容易になりますか?

A: Aspose.PDF for .NET には、見出しや段落などのインライン構造要素を作成および操作するためのクラスとメソッドが用意されています。これらの要素はカスタマイズしたり、階層的に整理したり、コンテンツを追加したりして、ドキュメントの視覚的なプレゼンテーションとアクセシビリティを向上させることができます。

####  Q: の目的は何ですか？`taggedContent` object in relation to inline structure elements?

 A:`taggedContent`オブジェクトは、`TaggedContent`の財産`Document`では、インライン構造要素を含む構造化要素を操作できます。これにより、ドキュメント内の見出しや段落を作成、カスタマイズ、整理できます。

#### Q: インライン構造要素は、明確なドキュメント階層の作成にどのように役立ちますか?

A: さまざまなレベルの見出しなどのインライン構造要素は、ドキュメント内で明確で明確に定義された階層を確立するのに役立ちます。読者はメイントピック、サブトピック、関連コンテンツをすばやく識別できるため、ドキュメントのナビゲートと理解が容易になります。

#### Q: Aspose.PDF for .NET を使用してインライン構造要素の外観と書式をカスタマイズできますか?

A: はい、インライン構造要素の外観と書式をカスタマイズできます。フォント スタイル、サイズ、色、配置、インデント、間隔などのプロパティを設定して、見出しや段落の視覚的なプレゼンテーションを希望どおりに実現できます。

#### Q: Aspose.PDF for .NET のインライン構造要素を使用して、PDF ドキュメントにさまざまなレベルの見出しを作成して追加するにはどうすればよいですか?

 A: 異なるレベルの見出しを作成するには、`CreateHeaderElement`メソッドを使用して、ルート構造要素に追加します。その後、各見出し要素にコンテンツを追加できます。`CreateSpanElement`テキストの範囲を作成する方法。

#### Q: インライン構造要素を使用して、PDF ドキュメント内にリスト、箇条書き、またはその他の種類のコンテンツ構成を作成できますか?

A: インライン構造要素自体は主に見出しや段落に使用されますが、Aspose.PDF for .NET が提供する他の機能と組み合わせて使用することで、リスト、箇条書き、表、その他の種類のコンテンツ編成を作成し、包括的なドキュメント構造を作成できます。

#### Q: インライン構造要素はドキュメントのアクセシビリティにどのように貢献しますか?

A: インライン構造要素は、ドキュメントのアクセシビリティを向上させる上で重要な役割を果たします。適切に構造化された見出しと段落は、明確なドキュメント階層を提供し、スクリーン リーダーやその他の支援技術が障害のあるユーザーにコンテンツを正確に解釈して伝えるのに役立ちます。

#### Q: インタラクティブな要素の作成やマルチメディアの埋め込みなど、インライン構造要素のより高度な使用方法を調べることはできますか?

A: もちろんです! このチュートリアルでは見出しと段落の作成に焦点を当てていますが、Aspose.PDF for .NET には、インタラクティブな要素の作成、マルチメディアの埋め込み、ハイパーリンクの追加などを行う高度な機能が備わっています。これらの高度な機能について詳しくは、ライブラリのドキュメントと例を確認してください。