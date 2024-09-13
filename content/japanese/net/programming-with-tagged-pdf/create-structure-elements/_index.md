---
title: 構造要素を作成する
linktitle: 構造要素を作成する
second_title: Aspose.PDF for .NET API リファレンス
description: このチュートリアルでは、Aspose.PDF for .NET を使用してタグ付き PDF ドキュメントに構造要素を作成する方法を学習します。
type: docs
weight: 60
url: /ja/net/programming-with-tagged-pdf/create-structure-elements/
---
次の C# ソース コードは、Aspose.PDF for .NET を使用して構造要素を作成します。コードの動作を理解するには、以下の手順に従ってください。

## ステップ1: 必要なライブラリをインポートする

```csharp
using Aspose.Pdf;
```

## ステップ2: ドキュメントのディレクトリを定義する

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

ドキュメント ディレクトリへの正しいパスを必ず指定してください。

## ステップ3: PDFドキュメントを作成する

```csharp
Document document = new Document();
```

PDF ドキュメントを表す新しい Document オブジェクトを作成します。

## ステップ4: TaggedPdfでコンテンツを操作する

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

PDF ドキュメントのタグ付けされたコンテンツを取得します。これにより、構造要素を操作できるようになります。

## ステップ5: ドキュメントのタイトルと言語を設定する

```csharp
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

タグ付けされた PDF ドキュメントのタイトルと言語を設定します。これにより、ドキュメントのアクセシビリティが向上します。

## ステップ6: グループ化要素を作成する

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

## ステップ7: 段落構造要素を作成する

```csharp
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
```

段落と見出しのブロックレベルの構造要素を作成します。上記の例は、レベル 1 の見出しの作成を示しています。

## ステップ8: インラインレベルの構造要素を作成する

```csharp
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
```

段落または見出し内に表示されるテキストの部分に対して、インライン レベルの構造要素を作成します。

## ステップ9: アートワーク構造要素を作成する

```csharp
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
```

文書内の図や数式の構造要素を作成します。

## ステップ10: タグ付きPDF文書を保存する

```csharp
document.Save(dataDir + "StructureElements.pdf");
```

作成された構造要素を含むタグ付き PDF ドキュメントを保存します。

### Aspose.PDF for .NET を使用して構造要素を作成するためのサンプル ソース コード 

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
//グループ化要素を作成する
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
//テキストブロックレベルの構造要素を作成する
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
//テキストのインラインレベルの構造要素を作成する
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
//イラスト構造要素を作成する
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
//方法は開発中
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

このチュートリアルでは、Aspose.PDF for .NET を使用して、タグ付き PDF ドキュメントに構造要素を作成する方法を学習しました。構造要素は、ドキュメントのアクセシビリティを向上させ、コンテンツを意味のある方法で整理するのに役立ちます。これで、この知識を使用して、構造化された、ナビゲートしやすい PDF ドキュメントを作成できます。

### よくある質問

#### Q: Aspose.PDF for .NET を使用して PDF ドキュメントに構造要素を作成する目的は何ですか?

A: Aspose.PDF for .NET を使用して PDF ドキュメントに構造要素を作成すると、ドキュメントのコンテンツのアクセシビリティと構成が向上します。構造要素は階層構造を提供し、ナビゲーション、セマンティクス、および支援技術との互換性が向上します。

#### Q: 提供されている C# コードはどのようにして PDF ドキュメント内に構造要素を作成しますか?

A: コード例では、グループ化要素 (パーツ、セクション、div など)、ブロック レベル要素 (段落や見出しなど)、インライン レベル要素 (span、引用、メモ)、アートワーク要素 (図や数式など) など、さまざまな種類の構造要素を作成する方法を示しています。これらの構造要素は、コンテンツを整理するのに役立ちます。

####  Q: 文書のタイトルと言語を設定することが重要なのはなぜですか？`SetTitle` and `SetLanguage` methods?

 A: ドキュメントのタイトルと言語を設定するには、`SetTitle`そして`SetLanguage`メソッドはドキュメントのアクセシビリティとセマンティクスを向上させます。タイトルはドキュメントの目的の簡単な説明を提供し、言語属性は言語固有のレンダリングとアクセシビリティを強化します。

####  Q: グループ化要素、例えば`PartElement` and `SectElement`, contribute to the structure of the PDF document?

A: 要素をグループ化すると、PDF ドキュメント内に階層構造が作成され、関連するコンテンツを論理的に整理してグループ化できるようになります。これにより、ナビゲーションが強化され、ユーザーに明確な構造が提供されます。

#### Q: ブロックレベルとインラインレベルの構造要素とは何ですか? また、それらの違いは何ですか?

A: ブロック レベルの構造要素は、段落や見出しなどのコンテンツの大きなブロックを表します。一方、インライン レベルの要素は、範囲、引用、注釈など、段落または見出し内のテキストの部分を表します。これらは、コンテンツの階層と関係を定義するのに役立ちます。

####  Q: アートワークは、例えば`FigureElement` and `FormulaElement`, contribute to the document?

A: アートワーク構造要素を使用すると、イラスト、図、数式をドキュメントに追加できます。アートワーク構造要素は、視覚的および数学的なコンテンツを構造化された方法で含める手段を提供します。

#### Q: 同様の手法を使用して、リスト、表、注釈などの他の種類の構造要素を作成できますか?

A: はい、同様の手法を使用して、リスト、表、注釈、参照などの他の種類の構造要素を作成できます。Aspose.PDF は、さまざまな構造要素作成方法を提供します。

####  Q: タグ付きPDF文書を`Save` method ensure the preservation of structure elements?

 A:`Save`このメソッドは、作成された構造要素とともに PDF ドキュメントを保存し、アクセシビリティとナビゲーションのためにドキュメントの階層構造とセマンティック構造が保持されるようにします。

#### Q: アクセシビリティと支援技術との互換性の点で、構造要素は PDF ドキュメントにどのような利点をもたらしますか?

A: 構造要素は、ドキュメントに意味のある構造とセマンティクスを提供することでアクセシビリティを向上させます。これにより、スクリーン リーダーなどの支援技術が、障害を持つユーザーにドキュメントのコンテンツをより効果的に解釈して伝えることができます。

#### Q: PDF ドキュメント内のさまざまな種類の構造要素をさらにカスタマイズして組み合わせるにはどうすればよいでしょうか?

A: Aspose.PDF が提供する適切な作成方法を使用して、構造要素を組み合わせたりカスタマイズしたりできます。さまざまな要素とそのプロパティを試して、適切に構造化され整理された PDF ドキュメントを作成してください。