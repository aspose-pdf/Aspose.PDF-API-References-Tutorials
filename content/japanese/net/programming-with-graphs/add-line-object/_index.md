---
title: PDF ファイルに線オブジェクトを追加する
linktitle: PDF ファイルに線オブジェクトを追加する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイルにカスタム ライン オブジェクトを追加する方法を学習します。
type: docs
weight: 30
url: /ja/net/programming-with-graphs/add-line-object/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して線オブジェクトを追加する方法について、次の C# ソース コードを手順ごとに説明します。

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

## ステップ3: グラフオブジェクトを作成し、ページに追加する

指定された寸法の Graph オブジェクトを作成し、それをページの段落コレクションに追加します。

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(graph);
```

## ステップ4: 線オブジェクトを作成してチャートに追加する

指定された座標を持つ Line オブジェクトを作成し、それをグラフの図形コレクションに追加します。

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
graph.Shapes.Add(line);
```

## ステップ5: 回線設定

破線の種類や破線の位相など、線のプロパティを指定できます。

```csharp
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## ステップ6: PDFファイルを保存する

最後に、結果の PDF ファイルを「AddLineObject_out.pdf」という名前で指定したディレクトリに保存します。

```csharp
doc.Save(dataDir + "AddLineObject_out.pdf");
```

### Aspose.PDF for .NET を使用して線オブジェクトを追加するためのサンプル ソース コード 

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
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
//グラフオブジェクトの塗りつぶし色を指定する
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
//グラフオブジェクトの図形コレクションに長方形オブジェクトを追加します。
graph.Shapes.Add(line);
dataDir = dataDir + "AddLineObject_out.pdf";
//PDFファイルを保存
doc.Save(dataDir);
Console.WriteLine("\nLine object added successfully to pdf.\nFile saved at " + dataDir);            

```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して線オブジェクトを追加する方法を段階的に説明しました。この知識を使用して、アプリケーションでカスタム線を含む PDF ドキュメントを作成できます。

### PDF ファイルに線オブジェクトを追加する方法に関する FAQ

#### Q: このチュートリアルの目的は何ですか?

A: このチュートリアルでは、Aspose.PDF for .NET を使用して線オブジェクトを追加し、PDF ドキュメントを強化するプロセスについて説明します。

#### Q: 始める前に必要な前提条件は何ですか?

A: 始める前に、Aspose.PDF ライブラリがインストールされ、開発環境が設定されていることを確認してください。また、C# プログラミングの基礎を理解しておくことをお勧めします。

#### Q: PDF ファイルを保存するディレクトリを指定するにはどうすればよいですか?

A: 提供されているソース コードで、「dataDir」変数を変更して、結果の PDF ファイルを保存するディレクトリを指定できます。

#### Q: Graph オブジェクトの目的は何ですか?

A: Graph オブジェクトは描画要素のコンテナとして機能します。指定された寸法で作成され、ページの段落コレクションに追加されます。

#### Q: PDF ドキュメントに線オブジェクトを追加するにはどうすればよいですか?

A: 線オブジェクトを追加するには、指定された座標を持つ Line クラスのインスタンスを作成し、それをグラフの図形コレクションに追加します。

#### Q: ラインの外観をカスタマイズできますか?

A: はい、Line オブジェクトの GraphInfo プロパティを使用して、破線の種類や破線フェーズなどのプロパティを設定することで、線の外観をカスタマイズできます。

#### Q: ダッシュ配列とダッシュフェーズを指定する目的は何ですか?

A: ダッシュ配列プロパティとダッシュ位相プロパティを使用すると、特定のパターンの破線または点線を作成できます。

#### Q: 線オブジェクトを追加した後、PDF ファイルを保存するにはどうすればよいですか?

 A: 線オブジェクトを追加した後、結果のPDFファイルを`doc.Save(dataDir + "AddLineObject_out.pdf");`提供されたソースコード内の行。

#### Q: サンプルソースコードはありますか?

A: はい、チュートリアルには、説明されている手順を実装するために参照できるサンプル ソース コードが含まれています。