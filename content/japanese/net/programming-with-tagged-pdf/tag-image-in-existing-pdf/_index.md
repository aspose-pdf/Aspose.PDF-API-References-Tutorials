---
title: 既存の PDF 内の画像にタグを付ける
linktitle: 既存の PDF 内の画像にタグを付ける
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して既存の PDF 内の画像にタグを付ける方法を学習します。PDF/UA 準拠でアクセシビリティを強化するためのステップバイステップ ガイドです。
type: docs
weight: 210
url: /ja/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
## 導入

このチュートリアルでは、Aspose.PDF for .NET を使用して既存の PDF 内の画像にタグを付ける方法について説明します。このガイドの最後まで学習すると、画像の代替テキストを設定し、レイアウト属性を調整し、PDF がアクセシビリティ標準に準拠していることを確認できるようになります。

## 前提条件

始める前に、始めるのに必要なものを確認しましょう。

-  Aspose.PDF for .NET: Aspose.PDF for .NET の最新バージョンをダウンロードしてインストールしたことを確認してください。[ダウンロードはこちら](https://releases.aspose.com/pdf/net/).
- .NET Framework: Visual Studio などの .NET 開発環境がセットアップされていることを確認します。
- PDF 構造の基本的な理解: 段落、スパン、表、画像などの PDF 構造要素に関する知識。
- 有効なライセンス：ライセンスを購入するか、[ここ](https://purchase.aspose.com/buy)または一時的なものを使用する[ここ](https://purchase.aspose.com/temporary-license/).

## パッケージのインポート

コーディングを開始するには、Aspose.PDF for .NET から重要な名前空間をインポートする必要があります。これにより、PDF ドキュメントを操作するために必要なクラスとメソッドにアクセスできるようになります。

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

準備ができたので、画像にタグを付けるプロセスを複数のステップに分解してみましょう。

## ステップ1: 既存のPDF文書を読み込む

最初のステップは、作業する PDF ファイルを読み込むことです。これは、タグ付けする画像を含む任意の PDF ファイルです。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

//文書を開く
Document document = new Document(inFile);
```

- 交換する`"YOUR DOCUMENT DIRECTORY"`ファイルへの実際のパスを入力します。
- の`Document`クラスを使用すると、既存の PDF を読み込むことができます。この PDF を変更して画像にタグを付けます。

## ステップ2: タグ付けされたコンテンツとルート構造要素にアクセスする

PDF を開いたら、次のステップは、タグ付けされたコンテンツにアクセスし、ルート構造要素を特定することです。これは、PDF 内の要素間を移動して変更を加えることができるため、非常に重要です。

```csharp
//タグ付けされたコンテンツとルート構造要素を取得する
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

- `TaggedContent`PDF 内の構造化された要素にアクセスできるようにします。
- の`RootElement`最上位の構造要素であり、ここから段落、表、画像などの他の要素に移動できます。

## ステップ3: タグ付きPDF文書のタイトルを設定する

タグ付き PDF ドキュメントにタイトルを追加すると、ドキュメントが適切にラベル付けされ、アクセシビリティと PDF/UA 準拠に役立ちます。

```csharp
//タグ付きPDF文書のタイトルを設定する
taggedContent.SetTitle("Document with images");
```

- タグ付き PDF にタイトルを設定すると、アクセシビリティが向上し、スクリーン リーダーや支援技術によるドキュメントの明瞭性が向上します。

## ステップ4: 画像を見つけてタグ付けする

さて、画像要素（`FigureElement` Aspose.PDF では、代替テキストを設定し、レイアウト属性を構成します。

```csharp
//すべての図要素（画像）をループし、代替テキストとレイアウト属性を設定します。
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
    //図の代替テキストを設定する
    figureElement.AlternativeText = "Figure alternative text (technique 2)";
    
    //BBox属性（バウンディングボックス）の作成と設定
    StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
    bboxAttribute.SetRectangleValue(new Aspose.Pdf.Rectangle(0.0, 0.0, 100.0, 100.0));
    
    //図のレイアウト属性を設定する
    StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
    figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

- このコードは、`FigureElement`ルート構造内の画像を表すオブジェクト。
- アクセシビリティのための代替テキストを設定します (スクリーン リーダーはこれを使用して画像を説明します)。
- 境界ボックス（`BBox`は、画像のレイアウトの座標を指定し、ドキュメント内に画像が正しく表示されるようにします。

## ステップ5: テーブル内のSpan要素を変更する

場合によっては、表内のspan要素を変更する必要があるかもしれません。ここでは、`SpanElement`それを段落に移動します。

```csharp
//表、スパン、段落要素を見つける
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

//span要素を段落内に移動する
spanElement.ChangeParentElement(paragraph);
```

- ここでは、`TableElement`, `SpanElement` 、 そして`ParagraphElement` PDF 内にあります。
- 使用方法`ChangeParentElement`メソッドでは、適切なタグ付けと構造を確保するために、span を段落内に移動します。

## ステップ6: ドキュメントを保存し、PDF/UA準拠を検証する

すべての変更が完了したら、最後のステップとして更新された PDF を保存し、PDF/UA 標準に準拠しているかどうかを確認します。

```csharp
//更新されたPDF文書を保存する
document.Save(outFile);

// PDF/UA準拠を検証する
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));
```

- の`Validate`このメソッドは、PDF ドキュメントを PDF/UA 標準に照らしてチェックし、結果を記録します。
- コンプライアンスを確保することで、アクセシビリティが向上し、ドキュメント公開に関する規制要件を満たすことができます。

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して既存の PDF 内の画像にタグを付ける方法を説明しました。代替テキストを設定し、レイアウト属性を調整し、ドキュメントの PDF/UA 準拠を検証することで、PDF がアクセシビリティに対応し、最新の標準に準拠していることを確認できます。Aspose.PDF を使用すると、構造化された要素を簡単に操作できるため、ドキュメントのレイアウトとアクセシビリティを制御できます。

## よくある質問

### Aspose.PDF for .NET は何に使用されますか?
Aspose.PDF for .NET は、.NET 環境でプログラムによって PDF ドキュメントを作成、編集、操作するために使用される強力なライブラリです。

### PDF/UA 準拠を確実にするにはどうすればよいですか?
 Aspose.PDFの`Validate`ドキュメントに変更を加えた後に PDF/UA 準拠を確認する方法。

### PDF の代替テキストとは何ですか?
代替テキストは、特にスクリーン リーダーを使用するユーザーのアクセシビリティを向上させるために PDF 内の画像に追加される説明です。

### Aspose.PDF を使用して PDF 内のテーブルとスパンを操作できますか?
はい、Aspose.PDF を使用すると、PDF ドキュメント内のテーブル、スパン、その他の構造化要素を操作できます。

### Aspose.PDF for .NET はどこからダウンロードできますか?
 Aspose.PDF for .NETの最新バージョンをダウンロードできます。[ここ](https://releases.aspose.com/pdf/net/).