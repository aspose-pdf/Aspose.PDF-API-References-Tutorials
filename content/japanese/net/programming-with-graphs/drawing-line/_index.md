---
title: 線を引く
linktitle: 線を引く
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用してページ全体に線を引く方法を学びます。カスタムラインを作成するためのステップバイステップのガイド。
type: docs
weight: 80
url: /ja/net/programming-with-graphs/drawing-line/
---
このチュートリアルでは、次の C# ソース コードを段階的に説明し、Aspose.PDF for .NET を使用して線を描画します。

始める前に、Aspose.PDF ライブラリをインストールし、開発環境をセットアップしていることを確認してください。 C# プログラミングの基本的な知識も必要です。

## ステップ 1: ドキュメント ディレクトリのセットアップ

提供されたソース コードでは、結果の PDF ファイルを保存するディレクトリを指定する必要があります。 「dataDir」変数を目的のディレクトリに変更します。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ 2: ドキュメント インスタンスの作成とページの追加

Document クラスのインスタンスを作成し、このドキュメントにページを追加します。

```csharp
Document pDoc = new Document();
Page pg = pDoc.Pages.Add();
```

## ステップ 3: ページ余白の設定

ページの余白をすべての辺で 0 に設定します。

```csharp
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
```

## ステップ 4: グラフ オブジェクトと最初の行の作成

ページの寸法と同じ寸法の Graph オブジェクトを作成し、ページの左下隅から右上隅に向かう最初の線を描画します。

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width, (float)pg.PageInfo.Height);
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect. URY });
graph.Shapes.Add(line);
```

## ステップ 5: 2 番目の線を描画する

ページの左上隅から右下隅に向かう 2 番目の線を描きます。

```csharp
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect. LLX });
graph.Shapes.Add(line2);
```

## ステップ 6: グラフ オブジェクトをページに追加する

Graph オブジェクトをページの段落コレクションに追加します。

```csharp
pg.Paragraphs.Add(graph);
```

## ステップ 7: 結果の PDF ファイルを保存する

最後に、結果の PDF ファイルを「DrawingLine_out.pdf」という名前で指定したディレクトリに保存します。

```csharp
pDoc.Save(dataDir + "DrawingLine_out.pdf");
```

### Aspose.PDF for .NET を使用した描画線のサンプル ソース コード 

```csharp

//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ドキュメントインスタンスの作成
Document pDoc = new Document();
//PDF ドキュメントのページコレクションにページを追加
Page pg = pDoc.Pages.Add();
//ページの四辺の余白を 0 に設定します。
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
//幅と高さがページの寸法と等しいグラフ オブジェクトを作成します。
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width , (float)pg.PageInfo.Height);
//ページの左下隅から右上隅まで始まる最初の行オブジェクトを作成します
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect.URY });
//Graph オブジェクトのシェイプ コレクションにラインを追加します
graph.Shapes.Add(line);
//ページの左上隅からページの右下隅まで線を引きます
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect.LLX });
//Graph オブジェクトのシェイプ コレクションにラインを追加します
graph.Shapes.Add(line2);
//ページの段落コレクションに Graph オブジェクトを追加します
pg.Paragraphs.Add(graph);
dataDir = dataDir + "DrawingLine_out.pdf";
//PDFファイルを保存する
pDoc.Save(dataDir);
Console.WriteLine("\nLine drawn successfully across the page.\nFile saved at " + dataDir);            

```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して線を描画する方法を説明しました。この知識を利用して、PDF ファイル内にカスタム線を含む幾何学的形状を作成できるようになりました。

### よくある質問

#### Q: このチュートリアルの目的は何ですか?

A: このチュートリアルの目的は、Aspose.PDF for .NET を使用して線を描画するプロセスをガイドすることです。 PDF ページに線を作成し、その外観をカスタマイズする方法を学習します。

#### Q: 開始する前にどのような前提条件が必要ですか?

A: 始める前に、Aspose.PDF ライブラリをインストールし、開発環境をセットアップしていることを確認してください。 C# プログラミングの基本的な知識も推奨されます。

#### Q: PDF ファイルを保存するディレクトリを指定するにはどうすればよいですか?

A: 提供されたソース コードの「dataDir」変数を変更して、結果の PDF ファイルを保存するディレクトリを指定します。

#### Q: PDF ページに線を作成するにはどうすればよいですか?

A: このチュートリアルでは、ページの寸法を使用して Graph オブジェクトを作成し、それに Line オブジェクトを追加する方法を示します。 Line オブジェクトの座標とプロパティを変更して、目的の線を作成します。

#### Q: 線の外観をカスタマイズできますか?

A: はい、Line オブジェクトのプロパティを変更することで、線の外観をカスタマイズできます。これには、座標、色、厚さ、その他のグラフィック属性の変更が含まれます。

#### Q: 線を引いた後、PDF 文書を保存するにはどうすればよいですか?

A: Line オブジェクトを含む Graph オブジェクトをページに追加した後、作成された PDF ドキュメントを`pDoc.Save(dataDir + "DrawingLine_out.pdf");`提供されたソースコード内の行。

#### Q: 異なる角度や方向の線を引くことはできますか?

A: はい、グラフ内の Line オブジェクトの座標とプロパティを調整することで、さまざまな角度や方向の線を描くことができます。