---
title: 塗りつぶされた長方形の作成
linktitle: 塗りつぶされた長方形の作成
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して塗りつぶされた四角形を作成する方法を学びます。塗りつぶしの色をカスタマイズするためのステップバイステップのガイド。
type: docs
weight: 50
url: /ja/net/programming-with-graphs/create-filled-rectangle/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して塗りつぶされた四角形を作成するために、次の C# ソース コードを段階的に説明します。

始める前に、Aspose.PDF ライブラリをインストールし、開発環境をセットアップしていることを確認してください。 C# プログラミングの基本的な知識も必要です。

## ステップ 1: ドキュメント ディレクトリのセットアップ

提供されたソース コードでは、結果の PDF ファイルを保存するディレクトリを指定する必要があります。 「dataDir」変数を目的のディレクトリに変更します。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ 2: ドキュメント インスタンスの作成とページの追加

Document クラスのインスタンスを作成し、このドキュメントにページを追加します。

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## ステップ 3: グラフ オブジェクトを作成してページに追加する

指定した寸法で Graph オブジェクトを作成し、それをページの段落コレクションに追加します。

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(graph);
```

## ステップ 4: 長方形オブジェクトを作成してチャートに追加する

指定された寸法を持つ Rectangle オブジェクトを作成し、それをチャートの形状コレクションに追加します。

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
graph.Shapes.Add(rect);
```

## ステップ 5: 塗りつぶしの色の設定

GraphInfo オブジェクトの FillColor プロパティを使用して、四角形の塗りつぶしの色を指定できます。

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

## ステップ 6: 結果の PDF ファイルを保存する

最後に、結果の PDF ファイルを「CreateFilledRectangle_out.pdf」という名前で指定したディレクトリに保存します。

```csharp
doc.Save(dataDir + "CreateFilledRectangle_out.pdf");
```

### Aspose.PDF for .NET を使用して塗りつぶされた四角形を作成するためのサンプル ソース コード 

```csharp

//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ドキュメントインスタンスの作成
Document doc = new Document();
// PDF ファイルのページコレクションにページを追加
Page page = doc.Pages.Add();
//グラフインスタンスの作成
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
//ページインスタンスの段落コレクションにグラフオブジェクトを追加します。
page.Paragraphs.Add(graph);
// Rectangle インスタンスの作成
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
//グラフオブジェクトの塗りつぶし色を指定する
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
//Graph オブジェクトの Shapes コレクションに Rectangle オブジェクトを追加します
graph.Shapes.Add(rect);
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
//PDFファイルを保存する
doc.Save(dataDir);
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);            

```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して塗りつぶされた四角形を作成する方法を説明しました。この知識を利用して、PDF ファイル内にカスタムの塗りつぶし色を使用して幾何学的図形を作成できるようになりました。

## よくある質問

#### Q: このチュートリアルの目的は何ですか?

A: このチュートリアルの目的は、Aspose.PDF for .NET を使用して塗りつぶされた四角形を作成するプロセスをガイドし、塗りつぶしの色を持つカスタムの幾何学的形状を PDF ファイルに追加できるようにすることです。

#### Q: 開始する前にどのような前提条件が必要ですか?

A: 始める前に、Aspose.PDF ライブラリがインストールされ、開発環境がセットアップされていることを確認してください。さらに、C# プログラミングの基本を理解していることをお勧めします。

#### Q: PDF ファイルを保存するディレクトリを指定するにはどうすればよいですか?

A: 提供されたソース コードで、「dataDir」変数を変更して、結果の PDF ファイルを保存するディレクトリを指定できます。

#### Q: Graph オブジェクトの目的は何ですか?

A: Graph オブジェクトは、描画要素のコンテナとして機能します。指定されたサイズで作成され、ページの段落コレクションに追加されます。

#### Q: PDF ドキュメントに塗りつぶされた四角形を追加するにはどうすればよいですか?

A: 塗りつぶされた四角形を追加するには、指定された寸法と塗りつぶしの色で Rectangle クラスのインスタンスを作成し、それをグラフの形状コレクションに追加します。

#### Q: 長方形の寸法と塗りつぶしの色をカスタマイズできますか?

 A: はい、に渡されるパラメータを変更することで、長方形の寸法と塗りつぶしの色をカスタマイズできます。`Aspose.Pdf.Drawing.Rectangle`コンストラクターと FillColor プロパティの設定。

#### Q: 塗りつぶされた長方形を作成した後、結果の PDF ファイルを保存するにはどうすればよいですか?

 A: 塗りつぶされた四角形を作成した後、作成された PDF ファイルを次のコマンドを使用して保存できます。`doc.Save(dataDir + "CreateFilledRectangle_out.pdf");`提供されたソースコード内の行。