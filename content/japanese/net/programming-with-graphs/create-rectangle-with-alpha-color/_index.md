---
title: アルファカラーを使用して長方形を作成する
linktitle: アルファカラーを使用して長方形を作成する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して透明色の四角形を作成する方法を学びます。透明度をカスタマイズするためのステップバイステップのガイド。
type: docs
weight: 60
url: /ja/net/programming-with-graphs/create-rectangle-with-alpha-color/
---
このチュートリアルでは、Aspose.PDF for .NET を使用してアルファ カラーを持つ四角形を作成するために、次の C# ソース コードを段階的に説明します。

始める前に、Aspose.PDF ライブラリをインストールし、開発環境をセットアップしていることを確認してください。 C# プログラミングの基本的な知識も必要です。

## ステップ 1: ドキュメント ディレクトリのセットアップ

提供されたソース コードでは、結果の PDF ファイルを保存するディレクトリを指定する必要があります。 「dataDir」変数を目的のディレクトリに変更します。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ 2: ドキュメント オブジェクトのインスタンス化とページの追加

Document クラスのインスタンスを作成し、このドキュメントにページを追加します。

```csharp
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## ステップ 3: グラフ オブジェクトと四角形の作成

指定された寸法を持つ Graph オブジェクトと、特定の寸法を持つ四角形を作成します。

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
```

## ステップ 4: 長方形のアルファカラーを設定する

System.Drawing.Color クラスの FromArgb メソッドを使用して、四角形のアルファ カラーを指定できます。

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
```

## ステップ 5: グラフ オブジェクトに四角形を追加する

Graph オブジェクトのシェイプ コレクションに四角形を追加します。

```csharp
canvas.Shapes.Add(rect);
```

## ステップ 6: 異なるアルファ カラーで 2 番目の長方形を作成する

特定の寸法と別のアルファ カラーを使用して 2 番目の長方形を作成します。

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

## ステップ 8: 結果の PDF ファイルを保存する

最後に、結果の PDF ファイルを「CreateRectangleWithAlphaColor_out.pdf」という名前で指定したディレクトリに保存します。

```csharp
doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");
```

### Aspose.PDF for .NET を使用してアルファ カラーで四角形を作成するためのサンプル ソース コード 

```csharp

//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ドキュメントインスタンスをインスタンス化する
Document doc = new Document();
// PDF ファイルのページコレクションにページを追加
Aspose.Pdf.Page page = doc.Pages.Add();
//グラフインスタンスの作成
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
//特定の寸法の長方形オブジェクトを作成する
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
//32 ビット ARGB 値の System.Drawing.Color 構造体からグラフの塗りつぶしの色を設定します
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
//Graph インスタンスのシェイプ コレクションに四角形オブジェクトを追加します
canvas.Shapes.Add(rect);
// 番目の長方形オブジェクトを作成する
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
//ページオブジェクトの段落コレクションにグラフインスタンスを追加
page.Paragraphs.Add(canvas);
dataDir = dataDir + "CreateRectangleWithAlphaColor_out.pdf";
//PDFファイルを保存する
doc.Save(dataDir);
Console.WriteLine("\nRectangle object created successfully with alpha color.\nFile saved at " + dataDir);            

```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用してアルファ カラーを持つ四角形を作成する方法を説明しました。この知識を利用して、PDF ファイル内に透明な色の幾何学的形状を作成できるようになりました。

## よくある質問

#### Q: このチュートリアルの目的は何ですか?

A: このチュートリアルは、Aspose.PDF for .NET を使用してアルファ カラーを持つ四角形を作成するプロセスをガイドすることを目的としています。透明色の幾何学的図形を PDF ファイルに追加する方法を学習します。

#### Q: 開始する前にどのような前提条件が必要ですか?

A: 始める前に、Aspose.PDF ライブラリがインストールされ、開発環境がセットアップされていることを確認してください。さらに、C# プログラミングの基本を理解していることをお勧めします。

#### Q: PDF ファイルを保存するディレクトリを指定するにはどうすればよいですか?

A: 提供されたソース コードで、「dataDir」変数を変更して、結果の PDF ファイルを保存するディレクトリを指定できます。

#### Q: Graph オブジェクトと Rectangle の目的は何ですか?

A: Graph オブジェクトは描画要素のコンテナとして機能し、Rectangle は PDF に追加する幾何学的形状を表します。

#### Q: 長方形のアルファカラーを設定するにはどうすればよいですか?

A: 四角形のアルファ カラーを指定するには、`FillColor`の財産`GraphInfo`オブジェクトと`Color.FromRgb`ARGB 値を使用するメソッド。

#### Q: 異なるアルファカラーを使用して複数の長方形を作成できますか?

A: はい、チュートリアルで説明したのと同様の手順に従って、異なるアルファ カラーを持つ複数の四角形を作成できます。

#### Q: アルファ カラーを使用して長方形を作成した後、結果の PDF ファイルを保存するにはどうすればよいですか?

 A: アルファ カラーを使用して四角形を作成した後、作成された PDF ファイルを次のコマンドを使用して保存できます。`doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");`提供されたソースコード内の行。