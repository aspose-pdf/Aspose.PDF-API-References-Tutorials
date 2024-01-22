---
title: 構造要素の作成
linktitle: 構造要素の作成
second_title: Aspose.PDF for .NET API リファレンス
description: このチュートリアルでは、Aspose.PDF for .NET を使用して、タグ付き PDF ドキュメント内に構造要素を作成する方法を学習します。
type: docs
weight: 60
url: /ja/net/programming-with-tagged-pdf/create-structure-elements/
---
次の C# ソース コードでは、Aspose.PDF for .NET を使用して構造要素を作成します。コードがどのように機能するかを理解するには、次の手順に従ってください。

## ステップ 1: 必要なライブラリをインポートする

```csharp
using Aspose.Pdf;
```

## ステップ 2: ドキュメントのディレクトリを定義する

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

ドキュメント ディレクトリへの正しいパスを必ず指定してください。

## ステップ 3: PDF ドキュメントを作成する

```csharp
Document document = new Document();
```

PDF ドキュメントを表す新しい Document オブジェクトを作成します。

## ステップ 4: TaggedPdf で動作するコンテンツを取得する

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

PDF ドキュメントのタグ付きコンテンツを取得します。これにより、構造要素を操作できるようになります。

## ステップ 5: ドキュメントのタイトルと言語を設定する

```csharp
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

タグ付けされた PDF ドキュメントのタイトルと言語を設定します。これにより、ドキュメントのアクセシビリティが向上します。

## ステップ 6: グループ化要素を作成する

```csharp
PartElement partElement = taggedContent.CreatePartElement();
ArtElement artElement = taggedContent.CreateArtElement();
SectElement sectElement = taggedContent.CreateSectElement();
DivElement divElement = taggedContent.CreateDivElement();
BlockQuoteElement blockQuoteElement = taggedContent.CreateBlockQuoteElement();
CaptionElement captionElement = taggedContent.CreateCaptionElement();
TOCElement tocElement = taggedContent.CreateTOCElement();
TOCIElement tociElement = taggedContent.CreateTOCIElement();
IndexElement indexElement = taggedContent.CreateIndexElement();
NonStructElement nonStructElement = taggedContent.CreateNonStructElement();
PrivateElement privateElement = taggedContent.CreatePrivateElement();
```

PDF ドキュメント内のコンテンツをグループ化するために、さまざまな構造要素を作成します。

## ステップ 7: 段落構造要素を作成する

```csharp
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
```

段落と見出しのブロックレベルの構造要素を作成します。上の例は、レベル 1 ヘッダーの作成を示しています。

## ステップ 8: インラインレベル構造要素を作成する

```csharp
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
```

段落または見出し内に表示されるテキストの部分に対して、インライン レベルの構造要素を作成します。

## ステップ 9: アートワーク構造要素を作成する

```csharp
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
```

文書内にあるイラストや数式の構造要素を作成します。

## ステップ 10: タグ付けされた PDF ドキュメントを保存する

```csharp
document.Save(dataDir + "StructureElements.pdf");
```

作成された構造要素を含むタグ付き PDF ドキュメントを保存します。

### Aspose.PDF for .NET を使用して構造要素を作成するためのサンプル ソース コード 

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
//グループ化要素の作成
PartElement partElement = taggedContent.CreatePartElement();
ArtElement artElement = taggedContent.CreateArtElement();
SectElement sectElement = taggedContent.CreateSectElement();
DivElement divElement = taggedContent.CreateDivElement();
BlockQuoteElement blockQuoteElement = taggedContent.CreateBlockQuoteElement();
CaptionElement captionElement = taggedContent.CreateCaptionElement();
TOCElement tocElement = taggedContent.CreateTOCElement();
TOCIElement tociElement = taggedContent.CreateTOCIElement();
IndexElement indexElement = taggedContent.CreateIndexElement();
NonStructElement nonStructElement = taggedContent.CreateNonStructElement();
PrivateElement privateElement = taggedContent.CreatePrivateElement();
//テキストブロックレベルの構造要素の作成
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
//テキストのインラインレベル構造要素の作成
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
//イラスト構造要素の作成
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
//メソッドは開発中です
ListElement listElement = taggedContent.CreateListElement();
TableElement tableElement = taggedContent.CreateTableElement();
ReferenceElement referenceElement = taggedContent.CreateReferenceElement();
BibEntryElement bibEntryElement = taggedContent.CreateBibEntryElement();
CodeElement codeElement = taggedContent.CreateCodeElement();
LinkElement linkElement = taggedContent.CreateLinkElement();
AnnotElement annotElement = taggedContent.CreateAnnotElement();
RubyElement rubyElement = taggedContent.CreateRubyElement();
WarichuElement warichuElement = taggedContent.CreateWarichuElement();
FormElement formElement = taggedContent.CreateFormElement();
//タグ付き PDF ドキュメントを保存
document.Save(dataDir + "StructureElements.pdf");

```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用してタグ付き PDF ドキュメント内に構造要素を作成する方法を学びました。構造要素は、ドキュメントのアクセシビリティを向上させ、コンテンツを有意義な方法で整理するのに役立ちます。この知識を利用して、構造化され、ナビゲートしやすい PDF ドキュメントを作成できるようになりました。

### よくある質問

#### Q: Aspose.PDF for .NET を使用して PDF ドキュメント内に構造要素を作成する目的は何ですか?

A: Aspose.PDF for .NET を使用して PDF ドキュメント内に構造要素を作成すると、ドキュメントのコンテンツのアクセシビリティと構成が強化されます。構造要素は、ナビゲーション、セマンティクス、支援技術との互換性を向上させる階層構造を提供します。

#### Q: 提供されている C# コードは PDF ドキュメント内に構造要素をどのように作成しますか?

A: このコード例では、グループ化要素 (パーツ、セクション、div など)、ブロック レベルの要素 (段落や見出しなど)、インライン レベルの要素 (スパン、引用符、メモなど) を含む、さまざまなタイプの構造要素を作成する方法を示しています。 ）、およびアートワーク要素（図や数式など）。これらの構造要素は、コンテンツを整理するのに役立ちます。

####  Q: ドキュメントのタイトルと言語を設定することが重要なのはなぜですか?`SetTitle` and `SetLanguage` methods?

 A: ドキュメントのタイトルと言語を設定するには、`SetTitle`そして`SetLanguage`メソッドにより、ドキュメントのアクセシビリティとセマンティクスが向上します。タイトルはドキュメントの目的の簡単な説明を提供し、言語属性は言語固有のレンダリングとアクセシビリティを強化します。

####  Q: 要素をグループ化するにはどうすればよいですか?`PartElement` and `SectElement`, contribute to the structure of the PDF document?

A: 要素をグループ化すると、PDF ドキュメント内に階層構造が作成され、関連するコンテンツを論理的に整理してグループ化できるようになります。これによりナビゲーションが強化され、ユーザーに明確な構造が提供されます。

#### Q: ブロックレベルとインラインレベルの構造要素とは何ですか?また、それらはどのように異なりますか?

A: ブロック レベルの構造要素は、段落や見出しなど、より大きなコンテンツ ブロックを表します。一方、インライン レベルの要素は、スパン、引用符、メモなど、段落または見出し内のテキストの一部を表します。これらは、コンテンツの階層と関係を定義するのに役立ちます。

####  Q: アートワークの要素はどのように構成されていますか?`FigureElement` and `FormulaElement`, contribute to the document?

A: アートワーク構造要素を使用すると、ドキュメントにイラスト、図、数式を追加できます。これらは、視覚的および数学的なコンテンツを含めるための構造化された方法を提供します。

#### Q: 同様の手法を使用して、リスト、テーブル、注釈などの他のタイプの構造要素を作成できますか?

A: はい、同様の手法を使用して、リスト、テーブル、注釈、参照などの他のタイプの構造要素を作成できます。 Aspose.PDF は、幅広い構造要素の作成方法を提供します。

####  Q: タグ付けされた PDF ドキュメントを保存するには、`Save` method ensure the preservation of structure elements?

 A:`Save`このメソッドは、作成された構造要素とともに PDF ドキュメントを保存し、アクセシビリティとナビゲーションのためにドキュメントの階層構造と意味構造が確実に保持されるようにします。

#### Q: アクセシビリティと支援技術との互換性の観点から、構造要素は PDF ドキュメントにどのような利点をもたらしますか?

A: 構造要素は、ドキュメントに意味のある構造とセマンティクスを提供することでアクセシビリティを強化します。これにより、スクリーン リーダーなどの支援技術が文書の内容を解釈し、障害のあるユーザーにより効果的に伝えることができるようになります。

#### Q: PDF ドキュメント内のさまざまなタイプの構造要素をさらにカスタマイズして組み合わせるにはどうすればよいですか?

A: Aspose.PDF が提供する適切な作成メソッドを使用して、構造要素を結合およびカスタマイズできます。さまざまな要素とそのプロパティを試して、適切に構造化され、整理された PDF ドキュメントを作成します。