---
title: ダッシュの長さ
linktitle: ダッシュの長さ
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して破線の長さを設定する方法を学びます。破線パターンをカスタマイズするためのステップ バイ ステップ ガイド。
type: docs
weight: 70
url: /ja/net/programming-with-graphs/dash-length/
---
このチュートリアルでは、Aspose.PDF for .NET を使用してダッシュの長さを設定するために、次の C# ソース コードを段階的に説明します。

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
Page page = doc.Pages.Add();
```

## ステップ3: グラフオブジェクトを作成し、ページに追加する

指定された寸法の Graph オブジェクトを作成し、それをページの段落コレクションに追加します。

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(canvas);
```

## ステップ4: ラインオブジェクトの作成と設定

指定された座標で Line オブジェクトを作成し、破線の色と長さを設定します。

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## ステップ5: グラフオブジェクトに線を追加する

Graph オブジェクトの図形コレクションに線を追加します。

```csharp
canvas.Shapes.Add(line);
```

## ステップ6: 結果のPDFファイルを保存する

最後に、結果の PDF ファイルを「DashLength_out.pdf」という名前で指定したディレクトリに保存します。

```csharp
doc.Save(dataDir + "DashLength_out.pdf");
```

### Aspose.PDF for .NET を使用した Dash Length のサンプル ソース コード 

```csharp

//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ドキュメントインスタンスをインスタンス化する
Document doc = new Document();
//Documentオブジェクトのページコレクションにページを追加する
Page page = doc.Pages.Add();
//特定の寸法を持つ図面オブジェクトを作成する
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
//ページインスタンスの段落コレクションに描画オブジェクトを追加する
page.Paragraphs.Add(canvas);
//ラインオブジェクトを作成する
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
//線オブジェクトの色を設定する
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
//線オブジェクトの破線配列を指定する
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
//ラインインスタンスのダッシュフェーズを設定する
line.GraphInfo.DashPhase = 1;
//描画オブジェクトの図形コレクションに線を追加する
canvas.Shapes.Add(line);
dataDir = dataDir + "DashLength_out.pdf";
//PDF文書を保存
doc.Save(dataDir);
Console.WriteLine("\nLength dashed successfully in black and white.\nFile saved at " + dataDir);            

```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して破線の長さを設定する方法について説明しました。これで、この知識を使用して、PDF ファイルにカスタム破線パターンの線を作成できます。

## よくある質問

#### Q: このチュートリアルの目的は何ですか?

A: このチュートリアルの目的は、Aspose.PDF for .NET を使用して線の破線の長さを設定する手順を説明することです。PDF ファイルでカスタム破線パターンを使用して線を作成する方法を学習します。

#### Q: 始める前に必要な前提条件は何ですか?

A: 始める前に、Aspose.PDF ライブラリがインストールされ、開発環境が設定されていることを確認してください。C# プログラミングの基礎知識があることも推奨されます。

#### Q: PDF ファイルを保存するディレクトリを指定するにはどうすればよいですか?

A: 提供されたソース コード内の「dataDir」変数を変更して、結果の PDF ファイルを保存するディレクトリを指定します。

#### Q: カスタム破線パターンで線を作成するにはどうすればよいですか?

 A: このチュートリアルでは、Lineオブジェクトを作成し、その色、ダッシュ配列、ダッシュ位相を`GraphInfo`オブジェクト。これらの設定を変更して、目的のダッシュ パターンを実現します。

#### Q: 線の色をカスタマイズできますか?

 A: はい、設定することで線の色をカスタマイズできます。`Color`の財産`GraphInfo`ラインに関連付けられたオブジェクト。

#### Q: ダッシュの長さを設定した後、PDF ドキュメントを保存するにはどうすればよいですか?

 A: 希望する破線パターンで線オブジェクトを設定した後、結果のPDF文書を`doc.Save(dataDir + "DashLength_out.pdf");`提供されたソースコード内の行。