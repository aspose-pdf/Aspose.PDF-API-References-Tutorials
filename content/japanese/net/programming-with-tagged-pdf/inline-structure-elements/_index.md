---
title: インライン構造要素
linktitle: インライン構造要素
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET でオンライン構造要素を使用するためのステップバイステップ ガイド。 PDF を見出しと段落で整理します。
type: docs
weight: 110
url: /ja/net/programming-with-tagged-pdf/inline-structure-elements/
---
このステップバイステップ ガイドでは、Aspose.PDF for .NET でインライン構造要素を使用する方法を説明します。 Aspose.PDF は、PDF ドキュメントをプログラムで操作できる強力なライブラリです。インライン構造要素を使用すると、さまざまなレベルと段落の見出しを使用して PDF ドキュメント内に階層構造を作成できます。

コードを詳しく見て、Aspose.PDF for .NET でインライン構造要素を使用する方法を学びましょう。

## 前提条件

始める前に、以下のものがあることを確認してください。

1. .NET 用の Aspose.PDF ライブラリがインストールされています。
2. C# プログラミング言語の基本的な知識。

## ステップ 1: 環境をセットアップする

まず、C# 開発環境を開き、新しいプロジェクトを作成します。プロジェクトに .NET 用の Aspose.PDF ライブラリへの参照を追加していることを確認してください。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ 2: ドキュメントの作成

最初のステップは、`Document`クラス。

```csharp
// PDFドキュメントを作成する
Document document = new Document();
```

## ステップ 3: タグ付きコンテンツを操作する

次に、処理するドキュメントのタグ付けされたコンテンツを取得します。

```csharp
//ドキュメントのタグ付けされたコンテンツを取得します
ITaggedContent taggedContent = document.TaggedContent;
```

## ステップ 4: ドキュメントのタイトルと言語を設定する

ドキュメントのタイトルと言語を設定できるようになりました。

```csharp
//ドキュメントのタイトルと言語を定義する
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

## ステップ 5: 構造要素をオンラインで追加する

次に、さまざまなレベルや段落の見出しなどのインライン構造要素をドキュメントに追加します。

```csharp
//ルート構造要素を取得する
StructureElement rootElement = taggedContent.RootElement;

//さまざまなレベルのヘッダーを追加する
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

## ステップ 6: タグ付けされた PDF ドキュメントを保存する

最後に、タグ付けされた PDF ドキュメントを保存します。

```csharp
//タグ付けされた PDF ドキュメントを保存する
document.Save(dataDir + "InlineStructureElements.pdf");
```

### Aspose.PDF for .NET を使用したインライン構造要素のサンプル ソース コード 

```csharp

//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//PDFドキュメントの作成
Document document = new Document();

//TaggedPdf で作業するためのコンテンツを取得する
ITaggedContent taggedContent = document.TaggedContent;

//ドキュメントのタイトルと言語を設定する
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");

//ルート構造要素の取得
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

おめでとうございます！ Aspose.PDF for .NET でインライン構造要素を使用する方法を学習しました。さまざまなレベルと段落の見出しを使用して、PDF ドキュメントに階層構造を作成できるようになりました。 Aspose.PDF の機能をさらに探索して、その可能性を最大限に発見してください。

### よくある質問

#### Q: PDF ドキュメントのインライン構造要素とは何ですか?また、それらは階層構造の作成にどのように影響しますか?

A: PDF ドキュメント内のインライン構造要素 (さまざまなレベルや段落の見出しなど) は、コンテンツを構造化して表示する階層構造を作成するために使用されます。これらの要素により、文書内に明確な階層と情報の流れを確立できます。

#### Q: インライン構造要素を使用すると、PDF ドキュメントの読みやすさと構成をどのように強化できますか?

A: インライン構造要素、特に見出しと段落は、論理構造を提供することで PDF ドキュメントの読みやすさと構成を向上させるのに役立ちます。見出しはさまざまなレベルの重要性を示し、読者がコンテンツをナビゲートするのに役立ちます。一方、段落は関連情報をグループ化します。

#### Q: Aspose.PDF for .NET はどのようにしてインライン構造要素の使用を容易にするのですか?

A: Aspose.PDF for .NET は、見出しや段落などのインライン構造要素を作成および操作するためのクラスとメソッドを提供します。これらの要素をカスタマイズし、階層的に編成し、コンテンツを充実させて、ドキュメントの視覚的なプレゼンテーションとアクセシビリティを向上させることができます。

####  Q：その目的は何ですか？`taggedContent` object in relation to inline structure elements?

 A:`taggedContent`から取得したオブジェクト`TaggedContent`の財産`Document`を使用すると、インライン構造要素を含む構造化要素を操作できます。これにより、文書内の見出しと段落を作成、カスタマイズ、整理できます。

#### Q: インライン構造要素は、明確なドキュメント階層の作成にどのように役立ちますか?

A: さまざまなレベルの見出しなどのインライン構造要素は、文書内に明確で明確に定義された階層を確立するのに役立ちます。読者はメイントピック、サブトピック、関連コンテンツを素早く識別できるため、文書の移動と理解が容易になります。

#### Q: Aspose.PDF for .NET を使用して、インライン構造要素の外観と書式設定をカスタマイズできますか?

A: はい、インライン構造要素の外観と書式設定をカスタマイズできます。フォント スタイル、サイズ、色、配置、インデント、間隔などのプロパティを設定して、見出しや段落に必要な視覚的なプレゼンテーションを実現できます。

#### Q: Aspose.PDF for .NET のインライン構造要素を使用して、さまざまなレベルの見出しを作成し、PDF ドキュメントに追加するにはどうすればよいですか?

 A: を使用して、さまざまなレベルの見出しを作成できます。`CreateHeaderElement`メソッドを作成し、ルート構造要素に追加します。その後、次のコマンドを使用して、各見出し要素にコンテンツを追加できます。`CreateSpanElement`テキストのスパンを作成するメソッド。

#### Q: インライン構造要素を使用して、PDF ドキュメント内にリスト、箇条書き、またはその他のタイプのコンテンツ構成を作成できますか?

A: インライン構造要素自体は主に見出しと段落に使用されますが、Aspose.PDF for .NET が提供する他の機能と組み合わせて使用して、リスト、箇条書き、表、およびその他のタイプのコンテンツ編成を作成して、包括的なコンテンツを作成することができます。文書構造。

#### Q: インライン構造要素はドキュメントのアクセシビリティにどのように貢献しますか?

A: インライン構造要素は、ドキュメントのアクセシビリティを高める上で重要な役割を果たします。適切に構造化された見出しと段落は、スクリーン リーダーやその他の支援技術がコンテンツを正確に解釈し、障害のあるユーザーに伝えるのに役立つ明確な文書階層を提供します。

#### Q: インタラクティブな要素の作成やマルチメディアの埋め込みなど、インライン構造要素のより高度な使用方法を検討できますか?

A: もちろんです！このチュートリアルでは見出しと段落の作成に焦点を当てていますが、Aspose.PDF for .NET は、インタラクティブな要素の作成、マルチメディアの埋め込み、ハイパーリンクの追加などの高度な機能を提供します。これらの高度な機能を詳しく調べるには、ライブラリのドキュメントと例を確認してください。