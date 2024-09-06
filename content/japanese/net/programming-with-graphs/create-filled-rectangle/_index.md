---
title: 塗りつぶされた長方形を作成する
linktitle: 塗りつぶされた長方形を作成する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して塗りつぶされた四角形を作成する方法を学びます。塗りつぶしの色をカスタマイズするためのステップ バイ ステップ ガイド。
type: docs
weight: 50
url: /ja/net/programming-with-graphs/create-filled-rectangle/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して塗りつぶされた四角形を作成するための次の C# ソース コードを段階的に説明します。

始める前に、Aspose.PDF ライブラリがインストールされ、開発環境が設定されていることを確認してください。また、C# プログラミングの基本的な知識も必要です。

## ステップ1: ドキュメントディレクトリの設定

提供されているソース コードでは、結果の PDF ファイルを保存するディレクトリを指定する必要があります。「dataDir」変数を目的のディレクトリに変更します。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ2: ドキュメントインスタンスの作成とページの追加

Document クラスのインスタンスを作成し、このドキュメントにページを追加します。

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## ステップ 3: グラフ オブジェクトを作成してページに追加する

指定された寸法の Graph オブジェクトを作成し、それをページの段落コレクションに追加します。

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(graph);
```

## ステップ4: 長方形オブジェクトを作成し、チャートに追加する

指定された寸法の Rectangle オブジェクトを作成し、それをチャートの図形コレクションに追加します。

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
graph.Shapes.Add(rect);
```

## ステップ5: 塗りつぶし色の設定

GraphInfo オブジェクトの FillColor プロパティを使用して、四角形の塗りつぶし色を指定できます。

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

## ステップ6: 結果のPDFファイルを保存する

最後に、結果の PDF ファイルを「CreateFilledRectangle_out.pdf」という名前で、指定したディレクトリに保存します。

```csharp
doc.Save(dataDir + "CreateFilledRectangle_out.pdf");
```

### Aspose.PDF for .NET を使用して塗りつぶされた四角形を作成するためのサンプル ソース コード 

```csharp

//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ドキュメントインスタンスを作成する
Document doc = new Document();
// PDFファイルのページコレクションにページを追加する
Page page = doc.Pages.Add();
//グラフインスタンスを作成する
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
//ページインスタンスの段落コレクションにグラフオブジェクトを追加する
page.Paragraphs.Add(graph);
//長方形インスタンスを作成する
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
//グラフオブジェクトの塗りつぶし色を指定する
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
//グラフオブジェクトの図形コレクションに長方形オブジェクトを追加します。
graph.Shapes.Add(rect);
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
//PDFファイルを保存
doc.Save(dataDir);
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);            

```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して塗りつぶされた四角形を作成する方法を説明しました。この知識を使用して、PDF ファイルにカスタム塗りつぶし色で幾何学的図形を作成できるようになりました。

## よくある質問

#### Q: このチュートリアルの目的は何ですか?

A: このチュートリアルの目的は、Aspose.PDF for .NET を使用して塗りつぶされた四角形を作成し、PDF ファイルに塗りつぶし色付きのカスタム幾何学的図形を追加できるようにするプロセスを説明することです。

#### Q: 始める前に必要な前提条件は何ですか?

A: 始める前に、Aspose.PDF ライブラリがインストールされ、開発環境が設定されていることを確認してください。また、C# プログラミングの基礎を理解しておくことをお勧めします。

#### Q: PDF ファイルを保存するディレクトリを指定するにはどうすればよいですか?

A: 提供されているソース コードで、「dataDir」変数を変更して、結果の PDF ファイルを保存するディレクトリを指定できます。

#### Q: Graph オブジェクトの目的は何ですか?

A: Graph オブジェクトは描画要素のコンテナとして機能します。指定された寸法で作成され、ページの段落コレクションに追加されます。

#### Q: PDF ドキュメントに塗りつぶされた四角形を追加するにはどうすればよいですか?

A: 塗りつぶされた四角形を追加するには、指定された寸法と塗りつぶし色を持つ Rectangle クラスのインスタンスを作成し、それをグラフの図形コレクションに追加します。

#### Q: 長方形の寸法と塗りつぶし色をカスタマイズできますか?

 A: はい、長方形の寸法と塗りつぶし色は、パラメータを変更することでカスタマイズできます。`Aspose.Pdf.Drawing.Rectangle`コンストラクターと FillColor プロパティの設定。

#### Q: 塗りつぶされた四角形を作成した後、結果の PDF ファイルをどのように保存すればよいですか?

 A: 塗りつぶされた四角形を作成したら、`doc.Save(dataDir + "CreateFilledRectangle_out.pdf");`提供されたソースコード内の行。