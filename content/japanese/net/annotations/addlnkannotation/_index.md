---
title: lnk注釈を追加
linktitle: lnk注釈を追加
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して、C# で PDF ドキュメントにインク注釈機能を追加する方法を、ステップバイステップのガイドと完全なソース コードとともに学習します。
type: docs
weight: 20
url: /ja/net/annotations/addlnkannotation/
---
Aspose.PDF for .NET は、開発者がさまざまな PDF 操作を実行できるようにする強力なライブラリです。そのような操作の 1 つは、PDF ドキュメントにインク注釈を追加することです。この記事では、Aspose.PDF for .NET を使用してインク アノテーションを追加するための C# ソース コードを説明するステップバイステップ ガイドを提供します。始めましょう！

## Aspose.PDF for .NET のインク注釈機能について

C# ソース コードに入る前に、まず Ink Annotation とは何か、そしてその用途を理解しましょう。

インク注釈は、PDF ドキュメント上に自由形式のインク注釈を描画する方法です。スタイラスまたはマウスを使用して注釈を作成できます。この機能は、図、スケッチ、またはその他の種類の注釈を描画する必要がある場合に役立ちます。

## ステップ 1: 新しいドキュメントの作成

PDF ドキュメントにインク注釈を追加する最初のステップは、Document クラスの新しいインスタンスを作成することです。これは、次のコード スニペットを使用して実現されます。

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document doc = new Document();
Page pdfPage = doc.Pages.Add();
```

ここでは、Document クラスの新しいインスタンスを作成し、それに新しいページを追加します。

## ステップ 2: インク注釈の作成

次のステップでは、InkAnnotation クラスのインスタンスを作成します。これは、次のコード スニペットを使用して行われます。

```csharp
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList);
ia.Title = "XXX";
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(ストローク.InkColor));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);
```

ここでは、まず System.Drawing.Rectangle クラスを使用して四角形を作成し、FromRect メソッドを使用してそれを Aspose.Pdf.Rectangle に変換します。次に、四角形、点のリスト、および注釈が追加されるページを使用して、InkAnnotation クラスのインスタンスを作成します。

次に、タイトル、色、キャップ スタイル、境界線、不透明度など、InkAnnotation のさまざまなプロパティを設定します。最後に、Annotations.Add メソッドを使用してページに注釈を追加します。

## ステップ 3: ドキュメントを保存する

最後のステップは、インク注釈を追加した PDF ドキュメントを保存することです。これは、次のコード スニペットを使用して実現されます。

```csharp
dataDir = dataDir + "AddlnkAnnotation_out.pdf";
doc.Save(dataDir);
```

ここでは、出力ファイル名をデータ ディレクトリに連結し、Save メソッドを使用してドキュメントを保存します。

### Aspose.PDF for .NET を使用してインク注釈を追加するためのソース コードの例

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DATA DIRECTORY";


Document doc = new Document();
Page pdfPage = doc.Pages.Add();
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList);
ia.Title = "XXX";
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(ストローク.InkColor));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);

dataDir = dataDir + "AddlnkAnnotation_out.pdf";
//出力ファイルを保存する
doc.Save(dataDir);
```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントにインク注釈を追加する方法を検討しました。提供されているステップバイステップ ガイドと C# ソース コードに従うことで、開発者は PDF 処理アプリケーションにインク アノテーション機能を簡単に実装できます。

### よくある質問

#### Q: PDF ドキュメントのインク注釈とは何ですか?

A: PDF ドキュメント内のインク注釈を使用すると、ユーザーはスタイラスまたはマウスを使用して自由形式のインク注釈を描画できます。これは、手書きのスケッチ、図、またはその他のフリーハンドの注釈を PDF に追加するためによく使用されます。

#### Q: インク注釈の外観をカスタマイズできますか?

A: はい。Aspose.PDF for .NET には、色、不透明度、キャップ スタイル、境界線の幅など、インク注釈の外観をカスタマイズするためのさまざまなプロパティが用意されています。開発者は、特定の要件を満たすようにこれらのプロパティを調整できます。

#### Q: 複数のインク注釈を 1 つの PDF ページに追加することはできますか?

A: はい、Aspose.PDF for .NET を使用して、複数のインク注釈を 1 つの PDF ページに追加できます。各インク注釈は、独自のポイントのセットとカスタマイズされた外観を持つことができます。

#### Q: 既存の PDF ドキュメントにインク注釈を追加できますか?

A: はい、Aspose.PDF for .NET を使用すると、新しく作成された PDF ドキュメントと既存の PDF ファイルの両方にインク注釈を追加できます。既存の PDF を開いて、インク注釈を追加し、更新されたドキュメントを保存できます。

#### Q: PDF ドキュメントのインク注釈の一般的な使用例にはどのようなものがありますか?

A: インク注釈は、PDF フォームへの署名や手書きメモの追加、建築設計図やエンジニアリング図面への注釈付け、共同レビュー用の文書のマークアップなど、幅広い用途に役立ちます。