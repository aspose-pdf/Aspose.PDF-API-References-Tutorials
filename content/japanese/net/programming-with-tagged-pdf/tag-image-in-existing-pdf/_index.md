---
title: 既存の PDF 内の画像にタグを付ける
linktitle: 既存の PDF 内の画像にタグを付ける
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して既存の PDF 内の画像をマークアップする方法を学びます。画像にタグを追加するためのステップバイステップ ガイド。
type: docs
weight: 210
url: /ja/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
この詳細なチュートリアルでは、提供されている C# ソース コードを段階的に説明し、Aspose.PDF for .NET を使用して既存の PDF 内の画像をマークアップします。 PDF 内の画像にタグを追加する方法を理解するには、以下の手順に従ってください。

## ステップ 1: 環境をセットアップする

始める前に、Aspose.PDF for .NET を使用するように開発環境が構成されていることを確認してください。これには、Aspose.PDF ライブラリのインストールと、それを参照するようにプロジェクトを構成することが含まれます。

## ステップ 2: 既存の PDF ドキュメントを開く

このステップでは、Aspose.PDF を使用して既存の PDF ドキュメントを開きます。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//入力および出力ファイルのパス
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

//文書を開く
Document document = new Document(inFile);
```

Aspose.PDF を使用して既存の PDF ドキュメントを開きました。

## ステップ 3: タグ付きコンテンツとルート構造要素を取得する

次に、PDF ドキュメントのタグ付きコンテンツと、対応するルート構造要素を取得します。

```csharp
//タグ付けされたコンテンツとルート構造要素を取得する
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

PDF ドキュメントのタグ付きコンテンツと、対応するルート構造要素を取得しました。

## ステップ 4: タグ付き PDF ドキュメントのタイトルを設定する

次に、タグ付き PDF ドキュメントのタイトルを設定しましょう。

```csharp
//タグ付けされた PDF ドキュメントのタイトルを定義します
taggedContent.SetTitle("Document with images");
```

タグ付けされた PDF ドキュメントのタイトルを設定しました。

## ステップ 5: 画像に代替テキストと境界ボックスを割り当てる

ここで、各画像要素に代替テキストと境界ボックスを割り当てます。

```csharp
foreach(FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
     //画像に代替テキストを割り当てる
     figureElement.AlternativeText = "Alternative text for image (technique 2)";
     //境界ボックス (bbox) を作成して割り当てます。
     StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
     bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
     StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
     figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

PDF ドキュメント内の各画像要素に代替テキストと境界ボックスを割り当てました。

## ステップ 6: Span 要素を段落に移動する

次に、Span 要素を段落に移動しましょう。

```csharp
//スパン要素を段落に移動します (最初の TD で間違ったスパンと段落を見つけます)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

//段落内の Span 要素を移動する
spanElement.ChangeParentElement(paragraph);
```

Span 要素を指定された段落に移動しました。

## ステップ 7: 変更した PDF ドキュメントを保存する

必要な変更を行ったので、変更した PDF ドキュメントを保存します。

```csharp
// PDF ドキュメントを保存する
document. Save(outFile);
```

変更した PDF ドキュメントを指定したディレクトリに保存しました。

### Aspose.PDF for .NET を使用した既存 PDF のタグ画像のサンプル ソース コード 

```csharp

//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

//開いた文書
Document document = new Document(inFile);

//タグ付けされたコンテンツとルート構造要素を取得します
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;

//タグ付けされた PDF ドキュメントのタイトルを設定する
taggedContent.SetTitle("Document with images");
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
	//図の代替テキストを設定する
	figureElement.AlternativeText = "Figure alternative text (technique 2)";
	//BBox 属性の作成と設定
	StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
	bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
	StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
	figureLayoutAttributes.SetAttribute(bboxAttribute);
}

//スパン要素を段落に移動 (最初の TD で間違ったスパンと段落を見つけます)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

//スパン要素を段落に移動
spanElement.ChangeParentElement(paragraph);

//文書の保存
document.Save(outFile);

//出力ドキュメントの PDF/UA 準拠のチェック
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して既存の PDF 内の画像をマークアップする方法を学びました。 Aspose.PDF を使用してタグを追加し、PDF ドキュメント内の画像を編集できるようになりました。

### よくある質問

#### Q: Aspose.PDF for .NET を使用して既存の PDF 内の画像にタグ付けするこのチュートリアルの主な目的は何ですか?

A: このチュートリアルの主な目的は、Aspose.PDF for .NET を使用して既存の PDF ドキュメント内の画像をマークアップするプロセスをガイドすることです。このチュートリアルでは、代替テキストと境界ボックスを画像に割り当てる方法、ドキュメント内で要素を移動する方法、画像にタグを追加する方法を理解するのに役立つ、段階的な手順と C# ソース コードの例を示します。

#### Q: Aspose.PDF for .NET を使用して PDF 内の画像にタグ付けするこのチュートリアルに従うための前提条件は何ですか?

A: 始める前に、Aspose.PDF for .NET を使用するように開発環境が設定されていることを確認してください。これには、Aspose.PDF ライブラリをインストールし、それを参照するようにプロジェクトを構成することが含まれます。

#### Q: Aspose.PDF for .NET を使用して、既存の PDF ドキュメントを開いてそのタグ付きコンテンツにアクセスするにはどうすればよいですか?

A: このチュートリアルでは、Aspose.PDF for .NET を使用して既存の PDF ドキュメントを開き、そのタグ付きコンテンツにアクセスしてさらに操作する方法を示す C# ソース コードの例を提供します。

#### Q: PDF ドキュメント内の画像に代替テキストと境界ボックスを割り当てる目的は何ですか?

A: 代替テキストと境界ボックスを画像に割り当てると、画像に説明テキストが提供され、文書内でのレイアウトと位置が定義されるため、アクセシビリティが向上します。この情報は、スクリーン リーダーやその他の支援技術にとって非常に重要です。

#### Q: Aspose.PDF for .NET を使用してタグ付き PDF ドキュメントのタイトルを設定するにはどうすればよいですか?

A: チュートリアルには、Aspose.PDF for .NET を使用してタグ付き PDF ドキュメントのタイトルを設定する方法を示す C# ソース コードの例が含まれています。

#### Q: PDF ドキュメント内で要素を移動するプロセスには何が関係しますか?

A: PDF ドキュメント内で要素を移動するには、特定の要素の親要素を変更する必要があります。このチュートリアルでは、Span 要素をテーブル内の指定された段落要素に移動する方法を学習します。

#### Q: タグを追加して画像を編集した後、変更した PDF ドキュメントを保存するにはどうすればよいですか?

 A: タグを追加し、代替テキストを割り当て、境界ボックスを設定し、PDF ドキュメントを編集したら、提供されている C# ソース コード サンプルを使用して、変更した PDF ドキュメントを保存できます。`Save()`方法。

#### Q: チュートリアルで提供されるサンプル ソース コードの目的は何ですか?

A: サンプル ソース コードは、Aspose.PDF for .NET を使用して画像のタグ付けと操作を実装するための実用的なリファレンスとして機能します。このコードを開始点として使用し、特定の要件に合わせて変更することができます。

#### Q: これらのテクニックを画像だけでなく、PDF ドキュメント内の他のタイプの要素に適用できますか?

A: はい、このチュートリアルで説明した手法は、PDF ドキュメント内のさまざまなタイプの要素を操作するように適応できます。同様の原則を適用して、テキスト、表などの他の要素にタグを付けたり、操作したりできます。

#### Q: 変更された PDF ドキュメントの PDF/UA 準拠を検証するにはどうすればよいですか?

 A: このチュートリアルでは、変更された PDF ドキュメントの PDF/UA 準拠を検証する方法を示す C# ソース コードの例を提供します。`Validate()`メソッドを使用して XML レポートを生成します。

#### Q: Aspose.PDF for .NET は、PDF ドキュメントを操作するために他にどのような機能を提供しますか?

A: Aspose.PDF for .NET は、テキスト操作、画像挿入、テーブル作成、フォーム フィールド管理、デジタル署名、注釈など、PDF ドキュメントを操作するための幅広い機能を提供します。さらに詳しく調べるには、公式ドキュメントとリソースを参照してください。