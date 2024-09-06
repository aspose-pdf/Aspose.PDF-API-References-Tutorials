---
title: アルファカラーで長方形を作成する
linktitle: アルファカラーで長方形を作成する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して透明色の四角形を作成する方法を学びます。透明度をカスタマイズするためのステップバイステップ ガイド。
type: docs
weight: 60
url: /ja/net/programming-with-graphs/create-rectangle-with-alpha-color/
---
このチュートリアルでは、Aspose.PDF for .NET を使用してアルファ カラー付きの四角形を作成するための次の C# ソース コードを段階的に説明します。

始める前に、Aspose.PDF ライブラリがインストールされ、開発環境が設定されていることを確認してください。また、C# プログラミングの基本的な知識も必要です。

## ステップ1: ドキュメントディレクトリの設定

提供されているソース コードでは、結果の PDF ファイルを保存するディレクトリを指定する必要があります。「dataDir」変数を目的のディレクトリに変更します。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ 2: ドキュメント オブジェクトのインスタンス化とページの追加

Document クラスのインスタンスを作成し、このドキュメントにページを追加します。

```csharp
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## ステップ3: グラフオブジェクトと四角形を作成する

指定された寸法のグラフ オブジェクトと特定の寸法の四角形を作成します。

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
```

## ステップ4: 四角形のアルファカラーを設定する

System.Drawing.Color クラスの FromArgb メソッドを使用して、四角形のアルファ カラーを指定できます。

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
```

## ステップ5: グラフオブジェクトに四角形を追加する

Graph オブジェクトの図形コレクションに四角形を追加します。

```csharp
canvas.Shapes.Add(rect);
```

## ステップ6: 異なるアルファカラーを持つ2番目の四角形を作成する

特定の寸法と別のアルファ カラーを持つ 2 番目の長方形を作成します。

```csharp
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
```

## ステップ 7: グラフ オブジェクトをページに追加する

Graph オブジェクトを Page オブジェクトの Paragraph コレクションに追加します。

```csharp
page.Paragraphs.Add(canvas);
```

## ステップ8: 結果のPDFファイルを保存する

最後に、結果の PDF ファイルを「CreateRectangleWithAlphaColor_out.pdf」という名前で、指定したディレクトリに保存します。

```csharp
doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");
```

### Aspose.PDF for .NET を使用してアルファカラー付きの四角形を作成するサンプル ソース コード 

```csharp

//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ドキュメントインスタンスをインスタンス化する
Document doc = new Document();
// PDFファイルのページコレクションにページを追加する
Aspose.Pdf.Page page = doc.Pages.Add();
//グラフインスタンスを作成する
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
//特定の寸法の長方形オブジェクトを作成する
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
//32 ビット ARGB 値から System.Drawing.Color 構造体のグラフの塗りつぶし色を設定します。
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// Graphインスタンスの図形コレクションに長方形オブジェクトを追加します。
canvas.Shapes.Add(rect);
// 2番目の長方形オブジェクトを作成する
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
//ページオブジェクトの段落コレクションにグラフインスタンスを追加する
page.Paragraphs.Add(canvas);
dataDir = dataDir + "CreateRectangleWithAlphaColor_out.pdf";
//PDFファイルを保存
doc.Save(dataDir);
Console.WriteLine("\nRectangle object created successfully with alpha color.\nFile saved at " + dataDir);            

```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用してアルファ カラーの四角形を作成する方法を説明しました。この知識を使用して、PDF ファイルで透明な色の幾何学的図形を作成できるようになりました。

## よくある質問

#### Q: このチュートリアルの目的は何ですか?

A: このチュートリアルでは、Aspose.PDF for .NET を使用してアルファ カラーの四角形を作成する手順を説明します。透明色の幾何学的図形を PDF ファイルに追加する方法を学びます。

#### Q: 始める前に必要な前提条件は何ですか?

A: 始める前に、Aspose.PDF ライブラリがインストールされ、開発環境が設定されていることを確認してください。また、C# プログラミングの基礎を理解しておくことをお勧めします。

#### Q: PDF ファイルを保存するディレクトリを指定するにはどうすればよいですか?

A: 提供されているソース コードで、「dataDir」変数を変更して、結果の PDF ファイルを保存するディレクトリを指定できます。

#### Q: Graph オブジェクトと Rectangle の目的は何ですか?

A: Graph オブジェクトは描画要素のコンテナーとして機能し、Rectangle は PDF に追加する幾何学的形状を表します。

#### Q: 長方形のアルファカラーを設定するにはどうすればよいですか?

 A: 四角形のアルファカラーを指定するには、`FillColor`の財産`GraphInfo`オブジェクトと`Color.FromRgb`ARGB 値を使用する方法。

#### Q: 異なるアルファカラーを持つ複数の長方形を作成できますか?

A: はい、チュートリアルで説明されているのと同様の手順に従うことで、異なるアルファ カラーを持つ複数の四角形を作成できます。

#### Q: アルファカラーで長方形を作成した後、結果の PDF ファイルを保存するにはどうすればよいですか?

 A: アルファカラーで四角形を作成した後、結果のPDFファイルを`doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");`提供されたソースコード内の行。