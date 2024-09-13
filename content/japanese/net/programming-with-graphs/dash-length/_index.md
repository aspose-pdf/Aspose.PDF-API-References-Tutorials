---
title: ダッシュの長さ
linktitle: ダッシュの長さ
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF 内の破線パターンをカスタマイズする方法を、ステップバイステップ ガイドで学習します。ドキュメントにスタイルを追加するのに最適です。
type: docs
weight: 70
url: /ja/net/programming-with-graphs/dash-length/
---
## 導入

さまざまな破線パターンで線をカスタマイズして、PDF ドキュメントに創造性を加えたいとお考えですか? Aspose.PDF for .NET を使用すると、ドキュメントのニーズに合わせて線のスタイルを簡単に変更できます。このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメント内の線の破線の長さを調整する方法について説明します。破線や点線のパターンのどちらを狙う場合でも、このガイドでは、目的の結果を達成するために必要なツールと手順が提供されます。

## 前提条件

チュートリアルを始める前に、いくつか必要なものがあります。

1. Aspose.PDF の .NET 版: Aspose.PDF for .NETがインストールされていることを確認してください。まだインストールしていない場合は、以下からダウンロードできます。[Aspose.PDF for .NET](https://releases.aspose.com/pdf/net/).
2. C# の基礎知識: このチュートリアルでは、読者が C# プログラミングの基礎を理解していることを前提としています。C# を初めて使用する場合は、まず基礎を復習することをお勧めします。
3. Visual Studio: 任意の IDE を使用できますが、このガイドでは、C# コードの作成と実行に Visual Studio を使用することを前提としています。
4.  Asposeアカウント: 追加のリソースとサポートについては、Asposeのアカウントをお持ちであることを確認してください。[無料トライアル](https://releases.aspose.com/)またはライセンスを購入する[ここ](https://purchase.aspose.com/buy).

## パッケージのインポート

Aspose.PDF for .NET の使用を開始するには、関連する名前空間をインポートする必要があります。手順は次のとおりです。

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

これらの名前空間には、PDF ドキュメント、図面、線の操作に必要なクラスとメソッドが含まれます。

## ステップ1: プロジェクトの設定

コーディングを始める前に、Visual Studio で新しい C# プロジェクトをセットアップします。NuGet 経由または DLL を手動で参照して、Aspose.PDF for .NET ライブラリをプロジェクトに追加します。 

## ステップ2: ドキュメントを初期化する

まず、新しい PDF ドキュメントを作成し、そこにページを追加します。これが線を描くキャンバスになります。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//ドキュメントインスタンスをインスタンス化する
Document doc = new Document();

// Documentオブジェクトのページコレクションにページを追加する
Page page = doc.Pages.Add();
```

ここでは、`Document`オブジェクトを追加して新しい`Page`これに線を引くための基礎が築かれます。

## ステップ3: 描画オブジェクトを作成する

次に、`Graph`描画する領域を表すオブジェクト。要件に応じて寸法を定義します。

```csharp
//特定の寸法を持つ図面オブジェクトを作成する
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100.0, 400.0);

//ページインスタンスの段落コレクションに描画オブジェクトを追加する
page.Paragraphs.Add(canvas);
```

の`Graph`オブジェクトは描画要素のコンテナとして機能します。ここでは、幅が 100 単位、高さが 400 単位に設定されています。

## ステップ4: 線を定義する

次は、`Line`オブジェクト。線の始点と終点を指定し、そのスタイルをカスタマイズします。

```csharp
//ラインオブジェクトを作成する
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
```

この線は座標 (100, 100) から始まり、座標 (200, 100) で終わります。これらの座標は、特定のニーズに合わせて調整できます。

## ステップ5: 線のスタイルをカスタマイズする

線の色と破線パターンを設定します。ここで線を目立たせることができます。

```csharp
//線オブジェクトの色を設定する
line.GraphInfo.Color = Aspose.Pdf.Color.Red;

//線オブジェクトの破線配列を指定する
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };

//ラインインスタンスのダッシュフェーズを設定する
line.GraphInfo.DashPhase = 1;
```

- `line.GraphInfo.Color`線の色を設定します。この場合は赤です。
- `line.GraphInfo.DashArray` : 破線パターンを定義します。ここでは、`{ 0, 1, 0 }`破線パターンを表します。
- `line.GraphInfo.DashPhase`: ダッシュパターンの開始点を調整します。

## ステップ6: 図面に線を追加する

線のスタイルを設定したら、`Graph`物体。

```csharp
//描画オブジェクトの図形コレクションに線を追加する
canvas.Shapes.Add(line);
```

これにより、線が描画キャンバスに統合されます。

## ステップ7: ドキュメントを保存する

最後に、ドキュメントを指定したパスに保存します。ここで PDF ファイルが作成されます。

```csharp
dataDir = dataDir + "DashLength_out.pdf";

// PDF文書を保存
doc.Save(dataDir);
Console.WriteLine("\nLength dashed successfully in black and white.\nFile saved at " + dataDir);
```

このコード行は PDF ドキュメントを保存し、ファイルが保存された場所を示す確認メッセージを表示します。

## 結論

PDF ドキュメントの線のスタイルをカスタマイズすると、レポート、プレゼンテーション、その他のドキュメントにプロフェッショナルなタッチを加えることができます。このチュートリアルでは、Aspose.PDF for .NET を使用して線の破線の長さを調整する方法を学習しました。単純な破線を作成する場合でも、より複雑なパターンを作成する場合でも、Aspose.PDF はドキュメントを目立たせるために必要な柔軟性を提供します。さまざまな破線パターンと色を試して、ニーズに最適なスタイルを見つけてください。

## よくある質問

### Aspose.PDF for .NET をインストールするにはどうすればよいですか?
 Visual StudioのNuGet経由でインストールするか、以下からダウンロードすることができます。[Asposeのウェブサイト](https://releases.aspose.com/pdf/net/).

### Aspose.PDF for .NET を無料で使用できますか?
はい、Asposeは[無料トライアル](https://releases.aspose.com/)ライセンスを購入する前に機能をテストすることができます。

### PDF 内の行に対して他にどのようなカスタマイズを行うことができますか?
線の太さ、色、破線パターンを調整できます。[ドキュメント](https://reference.aspose.com/pdf/net/)詳細についてはこちらをご覧ください。

### 問題が発生した場合、どうすればサポートを受けることができますか?
サポートは以下からアクセスできます。[Aspose フォーラム](https://forum.aspose.com/c/pdf/10).

### Aspose.PDF for .NET のライセンスはどこで購入できますか?
ライセンスを購入することができます[ここ](https://purchase.aspose.com/buy).