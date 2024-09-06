---
title: 既存の PDF 内の画像にタグを付ける
linktitle: 既存の PDF 内の画像にタグを付ける
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して既存の PDF 内の画像をマークアップする方法を学びます。画像にタグを追加するためのステップバイステップ ガイド。
type: docs
weight: 210
url: /ja/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
この詳細なチュートリアルでは、提供されている C# ソース コードを使用して、Aspose.PDF for .NET を使用して既存の PDF 内の画像をマークアップする方法を段階的に説明します。PDF 内の画像にタグを追加する方法については、以下の手順に従ってください。

## ステップ1: 環境の設定

始める前に、Aspose.PDF for .NET を使用するように開発環境が構成されていることを確認してください。これには、Aspose.PDF ライブラリのインストールと、それを参照するようにプロジェクトを構成することが含まれます。

## ステップ2: 既存のPDF文書を開く

この手順では、Aspose.PDF を使用して既存の PDF ドキュメントを開きます。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//入力および出力ファイルパス
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

//文書を開く
Document document = new Document(inFile);
```

Aspose.PDF を使用して既存の PDF ドキュメントを開きました。

## ステップ3: タグ付けされたコンテンツとルート構造要素を取得する

ここで、PDF ドキュメントのタグ付けされたコンテンツと対応するルート構造要素を取得します。

```csharp
//タグ付けされたコンテンツとルート構造要素を取得する
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

PDF ドキュメントのタグ付けされたコンテンツと対応するルート構造要素を取得しました。

## ステップ4: タグ付きPDF文書のタイトルを設定する

次に、タグ付き PDF ドキュメントのタイトルを設定しましょう。

```csharp
//タグ付きPDF文書のタイトルを定義する
taggedContent.SetTitle("Document with images");
```

タグ付き PDF ドキュメントのタイトルを設定しました。

## ステップ5: 画像に代替テキストと境界ボックスを割り当てる

ここで、各画像要素に代替テキストと境界ボックスを割り当てます。

```csharp
foreach(FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
     //画像に代替テキストを割り当てる
     figureElement.AlternativeText = "Alternative text for image (technique 2)";
     //境界ボックス（bbox）を作成して割り当てる
     StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
     bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
     StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
     figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

PDF ドキュメント内の各画像要素に代替テキストと境界ボックスを割り当てました。

## ステップ6: Span要素を段落内に移動する

次に、Span 要素を段落内に移動します。

```csharp
// Span 要素を段落に移動する (最初の TD で不正な span と段落を見つける)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

//段落内のSpan要素を移動する
spanElement.ChangeParentElement(paragraph);
```

指定された段落に Span 要素を移動しました。

## ステップ7: 変更したPDF文書を保存する

必要な変更を行ったので、変更した PDF ドキュメントを保存します。

```csharp
// PDF文書を保存する
document. Save(outFile);
```

変更された PDF ドキュメントを指定されたディレクトリに保存しました。

### Aspose.PDF for .NET を使用して既存の PDF に画像をタグ付けするためのサンプル ソース コード 

```csharp

//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

//ドキュメントを開く
Document document = new Document(inFile);

//タグ付けされたコンテンツとルート構造要素を取得します
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;

//タグ付き PDF ドキュメントのタイトルを設定する
taggedContent.SetTitle("Document with images");
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
	//図の代替テキストを設定する
	figureElement.AlternativeText = "Figure alternative text (technique 2)";
	//BBox属性の作成と設定
	StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
	bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
	StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
	figureLayoutAttributes.SetAttribute(bboxAttribute);
}

//span 要素を段落に移動する (最初の TD で間違った span と段落を見つける)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// span要素を段落に移動する
spanElement.ChangeParentElement(paragraph);

//ドキュメントを保存
document.Save(outFile);

//ドキュメントの PDF/UA 準拠を確認しています
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して既存の PDF 内の画像をマークアップする方法を学習しました。これで、Aspose.PDF を使用して PDF ドキュメント内の画像にタグを追加したり、編集したりできるようになりました。

### よくある質問

#### Q: Aspose.PDF for .NET を使用して既存の PDF 内の画像にタグを付けるこのチュートリアルの主な目的は何ですか?

A: このチュートリアルの主な目的は、Aspose.PDF for .NET を使用して既存の PDF ドキュメント内の画像をマークアップするプロセスを説明することです。このチュートリアルでは、画像に代替テキストと境界ボックスを割り当てる方法、ドキュメント内で要素を移動する方法、画像にタグを追加する方法を理解するのに役立つ、ステップバイステップの手順と C# ソース コードの例を示します。

#### Q: Aspose.PDF for .NET を使用して PDF 内の画像にタグを付ける方法に関するこのチュートリアルを実行するための前提条件は何ですか?

A: 開始する前に、Aspose.PDF for .NET を使用するように開発環境が設定されていることを確認してください。これには、Aspose.PDF ライブラリをインストールし、それを参照するようにプロジェクトを構成することが含まれます。

#### Q: Aspose.PDF for .NET を使用して既存の PDF ドキュメントを開き、タグ付けされたコンテンツにアクセスするにはどうすればよいですか?

A: チュートリアルでは、Aspose.PDF for .NET を使用して既存の PDF ドキュメントを開き、タグ付けされたコンテンツにアクセスしてさらに操作する方法を示す C# ソース コードの例を提供します。

#### Q: PDF ドキュメント内の画像に代替テキストと境界ボックスを割り当てる目的は何ですか?

A: 画像に代替テキストと境界ボックスを割り当てると、画像の説明テキストが提供され、ドキュメント内でのレイアウトと位置が定義されるため、アクセシビリティが向上します。この情報は、スクリーン リーダーやその他の支援技術にとって非常に重要です。

#### Q: Aspose.PDF for .NET を使用してタグ付き PDF ドキュメントのタイトルを設定するにはどうすればよいですか?

A: チュートリアルには、Aspose.PDF for .NET を使用してタグ付き PDF ドキュメントのタイトルを設定する方法を示す C# ソース コードの例が含まれています。

#### Q: PDF ドキュメント内で要素を移動するプロセスには何が含まれますか?

A: PDF ドキュメント内で要素を移動すると、特定の要素の親要素が変更されます。このチュートリアルでは、Span 要素をテーブル内の指定された Paragraph 要素に移動する方法を学習します。

#### Q: タグを追加したり画像を編集した後、変更した PDF ドキュメントを保存するにはどうすればよいですか?

 A: タグを追加し、代替テキストを割り当て、境界ボックスを設定し、PDF文書を編集したら、提供されているC#ソースコードの例を使用して、変更したPDF文書を保存できます。`Save()`方法。

#### Q: チュートリアルで提供されているサンプル ソース コードの目的は何ですか?

A: サンプル ソース コードは、Aspose.PDF for .NET を使用して画像のタグ付けと操作を実装するための実用的なリファレンスとして役立ちます。このコードを開始点として使用し、特定の要件に合わせて変更できます。

#### Q: これらのテクニックは、画像だけでなく、PDF ドキュメント内の他の種類の要素にも適用できますか?

A: はい、このチュートリアルで紹介したテクニックは、PDF ドキュメント内のさまざまな種類の要素に適用できます。同様の原則を適用して、テキスト、表などの他の要素にタグを付けたり操作したりできます。

#### Q: 変更された PDF ドキュメントの PDF/UA 準拠を検証するにはどうすればよいですか?

 A: このチュートリアルでは、C#ソースコードの例を示し、変更されたPDF文書のPDF/UA準拠を検証する方法を示します。`Validate()`メソッドを実行して XML レポートを生成します。

#### Q: Aspose.PDF for .NET には、PDF ドキュメントを操作するための他のどのような機能がありますか?

A: Aspose.PDF for .NET は、テキスト操作、画像の挿入、表の作成、フォーム フィールドの管理、デジタル署名、注釈など、PDF ドキュメントを操作するための幅広い機能を提供します。詳細については、公式ドキュメントとリソースを参照してください。