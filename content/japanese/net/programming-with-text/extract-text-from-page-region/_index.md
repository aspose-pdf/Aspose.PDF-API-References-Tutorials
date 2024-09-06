---
title: PDF ファイルのページ領域からテキストを抽出する
linktitle: PDF ファイルのページ領域からテキストを抽出する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイルのページ上の特定の領域からテキストを抽出する方法を学習します。
type: docs
weight: 190
url: /ja/net/programming-with-text/extract-text-from-page-region/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイルのページ上の特定の領域からテキストを抽出するプロセスについて説明します。提供されている C# ソース コードは、必要な手順を示しています。

## 要件
始める前に、次のものがあることを確認してください。

- マシンにインストールされている Visual Studio またはその他の C# コンパイラ。
- Aspose.PDF for .NET ライブラリ。公式 Aspose Web サイトからダウンロードするか、NuGet などのパッケージ マネージャーを使用してインストールできます。

## ステップ1: プロジェクトを設定する
1. 好みの開発環境で新しい C# プロジェクトを作成します。
2. Aspose.PDF for .NET ライブラリへの参照を追加します。

## ステップ2: 必要な名前空間をインポートする
テキストを抽出するコード ファイルで、ファイルの先頭に次の using ディレクティブを追加します。

```csharp
using Aspose.Pdf;
using System.IO;
```

## ステップ3: ドキュメントディレクトリを設定する
コード内で、次の行を見つけます。`string dataDir = "YOUR DOCUMENT DIRECTORY";`置き換えて`"YOUR DOCUMENT DIRECTORY"`ドキュメントが保存されているディレクトリへのパスを指定します。

## ステップ4: PDF文書を開く
既存のPDF文書を開くには、`Document`コンストラクターを呼び出して、入力 PDF ファイルへのパスを渡します。

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

## ステップ5: ページ領域からテキストを抽出する
作成する`TextAbsorber`オブジェクトを使用して文書からテキストを抽出します。`TextSearchOptions`四角形で定義された特定のページ領域に検索を制限します。

```csharp
TextAbsorber absorb = new TextAbsorber();
absorb.TextSearchOptions.LimitToPageBounds = true;
absorb.TextSearchOptions.Rectangle = new Aspose.Pdf.Rectangle(100, 200, 250, 350);
pdfDocument.Pages[1].Accept(absorb);
```

## ステップ6: 抽出したテキストを取得する
抽出したテキストにアクセスする`TextAbsorber`物体。

```csharp
string extractedText = absorb.Text;
```

## ステップ7: 抽出したテキストを保存する
作成する`TextWriter`抽出したテキストを保存するファイルを開きます。抽出したテキストをファイルに書き込み、ストリームを閉じます。

```csharp
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
tw.WriteLine(extractedText);
tw. Close();
```

### Aspose.PDF for .NET を使用してページ領域からテキストを抽出するためのサンプル ソース コード 
```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ドキュメントを開く
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
//テキストを抽出するためのTextAbsorberオブジェクトを作成する
TextAbsorber absorber = new TextAbsorber();
absorber.TextSearchOptions.LimitToPageBounds = true;
absorber.TextSearchOptions.Rectangle = new Aspose.Pdf.Rectangle(100, 200, 250, 350);
//最初のページの吸収剤を受け入れる
pdfDocument.Pages[1].Accept(absorber);
//抽出したテキストを取得する
string extractedText = absorber.Text;
//ライターを作成してファイルを開く
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
//ファイルにテキスト行を書き込む
tw.WriteLine(extractedText);
//ストリームを閉じる
tw.Close();
```

## 結論
Aspose.PDF for .NET を使用して、PDF ドキュメントのページ上の特定の領域からテキストを正常に抽出しました。抽出されたテキストは、指定された出力ファイルに保存されました。

### よくある質問

#### Q: このチュートリアルの目的は何ですか?

A: このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイルのページ上の特定の領域からテキストを抽出するプロセスについて説明します。付属の C# ソース コードには、このタスクを実行するための手順が段階的に説明されています。

#### Q: どの名前空間をインポートすればよいですか?

A: テキストを抽出するコード ファイルで、ファイルの先頭に次の using ディレクティブを含めます。

```csharp
using Aspose.Pdf;
using System.IO;
```

#### Q: ドキュメントディレクトリを指定するにはどうすればよいですか?

 A: 線を見つける`string dataDir = "YOUR DOCUMENT DIRECTORY";`コード内の`"YOUR DOCUMENT DIRECTORY"`ドキュメント ディレクトリへの実際のパスを入力します。

#### Q: 既存の PDF ドキュメントを開くにはどうすればよいですか?

 A: ステップ4では、既存のPDF文書を`Document`コンストラクターを呼び出して、入力 PDF ファイルへのパスを指定します。

#### Q: 特定のページ領域からテキストを抽出するにはどうすればよいですか?

 A: ステップ5では、`TextAbsorber`オブジェクトを使用してPDF文書からテキストを抽出します。次に、`TextSearchOptions`座標を使用してページ上の特定の長方形領域を定義します。

#### Q: 抽出されたテキストにアクセスするにはどうすればいいですか?

 A: ステップ6では、抽出したテキストにアクセスする手順を説明します。`TextAbsorber`物体。

#### Q: 抽出したテキストをファイルに保存するにはどうすればよいですか?

 A: ステップ7では、`TextWriter`抽出したテキストを保存するファイルを開き、抽出したテキストをファイルに書き込んでから、ストリームを閉じます。

#### Q: このチュートリアルから得られる重要なポイントは何ですか?

A: このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントのページの特定の領域からテキストを抽出する方法を学習しました。抽出されたテキストは指定された出力ファイルに保存され、必要なテキスト コンテンツを正確にターゲットにして分析できます。