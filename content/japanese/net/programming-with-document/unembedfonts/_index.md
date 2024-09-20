---
title: フォントの埋め込みを解除して PDF ファイルを最適化する
linktitle: フォントの埋め込みを解除して PDF ファイルを最適化する
second_title: Aspose.PDF for .NET API リファレンス
description: このステップバイステップのチュートリアルでは、Aspose.PDF for .NET を使用してフォントの埋め込みを解除し、PDF ファイルを最適化する方法を学習します。
type: docs
weight: 370
url: /ja/net/programming-with-document/unembedfonts/
---
## 導入

デジタル時代では、PDF はどこにでもあります。レポート、プレゼンテーション、電子書籍などを共有する場合、ドキュメントの整合性を保つには、Portable Document Format (PDF) が最適です。ただし、PDF を作成して共有する回数が増えると、ファイル サイズが大きくなり、送信や保存が面倒になります。ここで、PDF ファイルを最適化する強力なツールを提供する Aspose.PDF for .NET が役立ちます。このチュートリアルでは、Aspose.PDF for .NET を使用してフォントの埋め込みを解除し、PDF ファイルを最適化する方法について詳しく説明します。

## 前提条件

細かい点に入る前に、始めるのに必要なものがすべて揃っていることを確認しましょう。

1. Visual Studio: マシンに Visual Studio がインストールされていることを確認してください。これは、.NET コードを記述して実行するために使用する IDE です。
2.  Aspose.PDF for .NET: Aspose.PDFライブラリをダウンロードしてインストールする必要があります。[ダウンロードリンク](https://releases.aspose.com/pdf/net/).
3. C# の基礎知識: C# プログラミングに精通していると、使用するコード スニペットを理解するのに役立ちます。
4.  PDFファイル: 最適化したいPDFファイルを用意します。どんなPDFでも使えますが、ここでは例として「`OptimizeDocument.pdf`.

## パッケージのインポート

まず、C# プロジェクトに必要なパッケージをインポートする必要があります。手順は次のとおりです。

1. Visual Studio でプロジェクトを開きます。
2. Aspose.PDFへの参照を追加します。ソリューションエクスプローラーでプロジェクトを右クリックし、「NuGetパッケージの管理」を選択して、`Aspose.PDF`パッケージをインストールします。

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

すべての設定が完了したので、最適化プロセスを管理しやすいステップに分解してみましょう。

## ステップ1: ドキュメントディレクトリを設定する

まず最初に、ドキュメント ディレクトリへのパスを定義する必要があります。ここに PDF ファイルが保存されます。手順は次のとおりです。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

交換する`"YOUR DOCUMENT DIRECTORY"` PDF ファイルが配置されている実際のパスを入力します。最適化する PDF がどこにあるかをプログラムが知る必要があるため、これは非常に重要です。

## ステップ2: PDFドキュメントを開く

ディレクトリの設定が完了したので、最適化する PDF ドキュメントを開きます。これを行うためのコードは次のとおりです。

```csharp
//ドキュメントを開く
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

このコード行は新しい`Document`オブジェクトは PDF ファイルを表します。ファイル名がディレクトリにあるファイル名と一致していることを確認してください。

## ステップ3: 最適化オプションを設定する

次に、最適化オプションを指定する必要があります。この場合、フォントの埋め込みを解除します。設定方法は次のとおりです。

```csharp
// UnembedFontsオプションを設定する
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    UnembedFonts = true
};
```

設定により`UnembedFonts`に`true`では、フォントの埋め込みを解除して PDF を最適化するように Aspose.PDF に指示しています。これにより、特に PDF に多くの埋め込みフォントが含まれている場合に、ファイル サイズを大幅に削減できます。

## ステップ4: PDFドキュメントを最適化する

オプションを設定したら、PDF ドキュメントを最適化します。これを行うコードは次のとおりです。

```csharp
Console.WriteLine("Start");
// OptimizationOptionsを使用してPDFドキュメントを最適化する
pdfDocument.OptimizeResources(optimizeOptions);
```

このコードスニペットは、`OptimizeResources`方法`pdfDocument`オブジェクトに、先ほど定義した最適化オプションを適用します。コンソールに、最適化プロセスが開始されたことを示すメッセージが表示されます。

## ステップ5: 更新したドキュメントを保存する

PDF を最適化した後、更新されたドキュメントを保存する必要があります。手順は次のとおりです。

```csharp
//更新されたドキュメントを保存する
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Finished");
```

このコードは最適化されたPDFを次のように保存します。`OptimizeDocument_out.pdf`同じディレクトリにあります。必要に応じて別の名前を選択することもできますが、似たような名前にしておくと、元のバージョンと最適化されたバージョンを識別しやすくなります。

## ステップ6: ファイルサイズを比較する

最後に、どれだけのスペースが節約できたかを確認することをお勧めします。元のファイル サイズと最適化されたファイル サイズを比較する方法は次のとおりです。

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

このコードは、元の PDF と最適化された PDF の両方のファイル サイズを取得し、コンソールに出力します。ファイル サイズがどれだけ削減されたかを確認するのは満足感があります。

## 結論

これで完了です。Aspose.PDF for .NET を使用して、埋め込みフォントを正常に解除し、PDF ファイルを最適化できました。このプロセスは、ファイル サイズを縮小するだけでなく、PDF ドキュメントのパフォーマンスも向上します。電子メールでファイルを共有する場合でも、クラウドに保存する場合でも、ファイル サイズが小さいと大きな違いが生じます。

## よくある質問

### Aspose.PDF for .NET とは何ですか?
Aspose.PDF for .NET は、開発者がプログラムによって PDF ドキュメントを作成、操作、最適化できるようにする強力なライブラリです。

### Aspose.PDF を無料で使用できますか?
はい、Asposeは無料試用版を提供しています。こちらからダウンロードできます。[ここ](https://releases.aspose.com/).

### Aspose.PDF のサポートを受けるにはどうすればよいですか?
サポートを受けるには[Aspose フォーラム](https://forum.aspose.com/c/pdf/10).

### PDF に対してどのような種類の最適化を実行できますか?
フォントの埋め込み解除、画像の圧縮、未使用のオブジェクトの削除などを行って、PDF ファイルを最適化できます。

### Aspose.PDF for .NET はどこで購入できますか?
ライセンスは以下から購入できます。[Aspose 購入ページ](https://purchase.aspose.com/buy).