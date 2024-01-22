---
title: PDF ファイルに線オブジェクトを追加
linktitle: PDF ファイルに線オブジェクトを追加
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイルにカスタム ライン オブジェクトを追加する方法を学習します。
type: docs
weight: 30
url: /ja/net/programming-with-graphs/add-line-object/
---
このチュートリアルでは、次の C# ソース コードを段階的に説明し、Aspose.PDF for .NET を使用して線オブジェクトを追加します。

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

## ステップ 4: 線オブジェクトを作成してチャートに追加する

指定された座標で Line オブジェクトを作成し、それをチャートの形状コレクションに追加します。

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
graph.Shapes.Add(line);
```

## ステップ 5: 回線の設定

破線の種類や破線の位相など、線のプロパティを指定できます。

```csharp
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## ステップ 6: PDF ファイルを保存する

最後に、結果の PDF ファイルを「AddLineObject_out.pdf」という名前で指定したディレクトリに保存します。

```csharp
doc.Save(dataDir + "AddLineObject_out.pdf");
```

### Aspose.PDF for .NET を使用した行オブジェクトの追加のサンプル ソース コード 

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
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
//グラフオブジェクトの塗りつぶし色を指定する
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
//Graph オブジェクトの Shapes コレクションに Rectangle オブジェクトを追加します
graph.Shapes.Add(line);
dataDir = dataDir + "AddLineObject_out.pdf";
//PDFファイルを保存する
doc.Save(dataDir);
Console.WriteLine("\nLine object added successfully to pdf.\nFile saved at " + dataDir);            

```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して線オブジェクトを追加する方法を段階的に説明しました。この知識を利用して、アプリケーションでカスタム行を含む PDF ドキュメントを作成できるようになりました。

### PDF ファイルに行オブジェクトを追加する場合の FAQ

#### Q: このチュートリアルの目的は何ですか?

A: このチュートリアルは、Aspose.PDF for .NET を使用して線オブジェクトを追加し、PDF ドキュメントを強化するプロセスをガイドすることを目的としています。

#### Q: 開始する前にどのような前提条件が必要ですか?

A: 始める前に、Aspose.PDF ライブラリがインストールされ、開発環境がセットアップされていることを確認してください。さらに、C# プログラミングの基本を理解していることをお勧めします。

#### Q: PDF ファイルを保存するディレクトリを指定するにはどうすればよいですか?

A: 提供されたソース コードで、「dataDir」変数を変更して、結果の PDF ファイルを保存するディレクトリを指定できます。

#### Q: Graph オブジェクトの目的は何ですか?

A: Graph オブジェクトは、描画要素のコンテナとして機能します。指定されたサイズで作成され、ページの段落コレクションに追加されます。

#### Q: PDF ドキュメントに線オブジェクトを追加するにはどうすればよいですか?

A: ライン オブジェクトを追加するには、指定した座標を使用して Line クラスのインスタンスを作成し、それをグラフの形状コレクションに追加します。

#### Q: 線の外観をカスタマイズできますか?

A: はい、Line オブジェクトの GraphInfo プロパティを使用して破線の種類や破線の位相などのプロパティを設定することで、線の外観をカスタマイズできます。

#### Q: ダッシュ配列とダッシュ位相を指定する目的は何ですか?

A: ダッシュ配列プロパティとダッシュ フェーズ プロパティを使用すると、特定のパターンで破線または点線を作成できます。

#### Q: ラインオブジェクトを追加した後、PDF ファイルを保存するにはどうすればよいですか?

 A: 線オブジェクトを追加した後、作成された PDF ファイルを次のコマンドを使用して保存できます。`doc.Save(dataDir + "AddLineObject_out.pdf");`提供されたソースコード内の行。

#### Q: サンプルのソースコードはありますか?

A: はい、チュートリアルには、説明されている手順を実装するために参照できるサンプル ソース コードが含まれています。