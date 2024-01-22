---
title: ダッシュの長さ
linktitle: ダッシュの長さ
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用してダッシュの長さを設定する方法を学びます。ダッシュ パターンをカスタマイズするためのステップバイステップ ガイド。
type: docs
weight: 70
url: /ja/net/programming-with-graphs/dash-length/
---
このチュートリアルでは、次の C# ソース コードを段階的に説明し、Aspose.PDF for .NET を使用してダッシュの長さを設定します。

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
Page page = doc.Pages.Add();
```

## ステップ 3: グラフ オブジェクトを作成してページに追加する

指定した寸法で Graph オブジェクトを作成し、それをページの段落コレクションに追加します。

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(canvas);
```

## ステップ 4: 線オブジェクトの作成と構成

指定された座標で Line オブジェクトを作成し、破線の色と長さを構成します。

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## ステップ 5: グラフ オブジェクトに線を追加する

Graph オブジェクトのシェイプ コレクションにラインを追加します。

```csharp
canvas.Shapes.Add(line);
```

## ステップ 6: 結果の PDF ファイルを保存する

最後に、結果の PDF ファイルを「DashLength_out.pdf」という名前で指定したディレクトリに保存します。

```csharp
doc.Save(dataDir + "DashLength_out.pdf");
```

### Aspose.PDF for .NET を使用したダッシュ長のサンプル ソース コード 

```csharp

//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ドキュメントインスタンスをインスタンス化する
Document doc = new Document();
//Document オブジェクトのページ コレクションにページを追加します
Page page = doc.Pages.Add();
//特定の寸法で描画オブジェクトを作成する
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
//ページインスタンスの段落コレクションに描画オブジェクトを追加します
page.Paragraphs.Add(canvas);
//ラインオブジェクトの作成
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
//Lineオブジェクトの色を設定する
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
//線オブジェクトのダッシュ配列を指定します
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
//Lineインスタンスのダッシュフェーズを設定します
line.GraphInfo.DashPhase = 1;
//描画オブジェクトのシェイプコレクションに線を追加します
canvas.Shapes.Add(line);
dataDir = dataDir + "DashLength_out.pdf";
//PDF文書を保存する
doc.Save(dataDir);
Console.WriteLine("\nLength dashed successfully in black and white.\nFile saved at " + dataDir);            

```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用してダッシュの長さを設定する方法を説明しました。この知識を利用して、PDF ファイルにカスタムの破線パターンを含む線を作成できるようになりました。

## よくある質問

#### Q: このチュートリアルの目的は何ですか?

A: このチュートリアルの目的は、Aspose.PDF for .NET を使用して線のダッシュの長さを設定するプロセスをガイドすることです。 PDF ファイルにカスタム破線パターンを使用して線を作成する方法を学習します。

#### Q: 開始する前にどのような前提条件が必要ですか?

A: 開始する前に、Aspose.PDF ライブラリがインストールされ、開発環境がセットアップされていることを確認してください。 C# プログラミングの基本を理解していることも推奨されます。

#### Q: PDF ファイルを保存するディレクトリを指定するにはどうすればよいですか?

A: 提供されたソース コードの「dataDir」変数を変更して、結果の PDF ファイルを保存するディレクトリを指定します。

#### Q: カスタムの破線パターンを含む線を作成するにはどうすればよいですか?

 A: このチュートリアルでは、Line オブジェクトの作成と、`GraphInfo`物体。これらの設定を変更して、目的の破線パターンを実現します。

#### Q: 線の色をカスタマイズできますか?

 A: はい、設定することで線の色をカスタマイズできます。`Color`の財産`GraphInfo` Line に関連付けられたオブジェクト。

#### Q: ダッシュの長さを設定した後、PDF ドキュメントを保存するにはどうすればよいですか?

 A: 希望の破線パターンを使用して Line オブジェクトを構成した後、作成された PDF ドキュメントを次のコマンドを使用して保存できます。`doc.Save(dataDir + "DashLength_out.pdf");`提供されたソースコード内の行。