---
title: PDFファイルのテキストページを抽出
linktitle: PDFファイルのテキストページを抽出
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイルの特定のページからテキストを抽出する方法を学びます。
type: docs
weight: 200
url: /ja/net/programming-with-text/extract-text-page/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイルの特定のページからテキストを抽出するプロセスについて説明します。提供されている C# ソース コードは、必要な手順を示しています。

## 要件
始める前に、以下のものがあることを確認してください。

- マシンにインストールされている Visual Studio またはその他の C# コンパイラー。
- .NET ライブラリ用の Aspose.PDF。 Aspose の公式 Web サイトからダウンロードするか、NuGet などのパッケージ マネージャーを使用してインストールできます。

## ステップ 1: プロジェクトをセットアップする
1. 好みの開発環境で新しい C# プロジェクトを作成します。
2. Aspose.PDF for .NET ライブラリへの参照を追加します。

## ステップ 2: 必要な名前空間をインポートする
テキストを抽出するコード ファイルで、ファイルの先頭に次の using ディレクティブを追加します。

```csharp
using Aspose.Pdf;
using System.IO;
```

## ステップ 3: ドキュメント ディレクトリを設定する
コード内で、次の行を見つけます。`string dataDir = "YOUR DOCUMENT DIRECTORY";`そして交換してください`"YOUR DOCUMENT DIRECTORY"`ドキュメントが保存されているディレクトリへのパスを置き換えます。

## ステップ 4: PDF ドキュメントを開く
既存の PDF ドキュメントを開くには、`Document`コンストラクターを呼び出して、入力 PDF ファイルへのパスを渡します。

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## ステップ 5: 特定のページからテキストを抽出する
を作成します`TextAbsorber`オブジェクトを使用してドキュメントからテキストを抽出します。からアクセスして、目的のページのアブソーバを受け入れます。`Pages`のコレクション`pdfDocument`.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages[1].Accept(textAbsorber);
```

## ステップ 6: 抽出されたテキストを取得する
から抽出されたテキストにアクセスします。`TextAbsorber`物体。

```csharp
string extractedText = textAbsorber.Text;
```

## ステップ 7: 抽出したテキストを保存する
を作成します`TextWriter`抽出したテキストを保存するファイルを開きます。抽出したテキストをファイルに書き込み、ストリームを閉じます。

```csharp
dataDir = dataDir + "extracted-text_out.txt";
TextWriter tw = new StreamWriter(dataDir);
tw.WriteLine(extractedText);
tw. Close();
```

### Aspose.PDF for .NET を使用したテキスト ページの抽出のサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開いた文書
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
//テキストを抽出する TextAbsorber オブジェクトを作成する
TextAbsorber textAbsorber = new TextAbsorber();
//特定のページのアブソーバーを受け入れる
pdfDocument.Pages[1].Accept(textAbsorber);
//抽出されたテキストを取得する
string extractedText = textAbsorber.Text;
dataDir = dataDir + "extracted-text_out.txt";
//ライターを作成してファイルを開く
TextWriter tw = new StreamWriter(dataDir);
//ファイルにテキスト行を書き込みます
tw.WriteLine(extractedText);
//ストリームを閉じる
tw.Close();
Console.WriteLine("\nText extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

## 結論
Aspose.PDF for .NET を使用して PDF ドキュメントの特定のページからテキストを抽出することに成功しました。抽出されたテキストは、指定された出力ファイルに保存されました。

### よくある質問

#### Q: このチュートリアルの目的は何ですか?

A: このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイルの特定のページからテキストを抽出するプロセスを説明します。付属の C# ソース コードは、このタスクを達成するために必要な手順を示しています。

#### Q: どの名前空間をインポートする必要がありますか?

A: テキストを抽出するコード ファイルでは、ファイルの先頭に次の using ディレクティブを含めます。

```csharp
using Aspose.Pdf;
using System.IO;
```

#### Q: ドキュメント ディレクトリを指定するにはどうすればよいですか?

 A: コード内で、次の行を見つけます。`string dataDir = "YOUR DOCUMENT DIRECTORY";`そして交換してください`"YOUR DOCUMENT DIRECTORY"`ドキュメントディレクトリへの実際のパスを置き換えます。

#### Q: 既存の PDF ドキュメントを開くにはどうすればよいですか?

 A: ステップ 4 では、`Document`コンストラクターを作成し、入力 PDF ファイルへのパスを提供します。

#### Q: 特定のページからテキストを抽出するにはどうすればよいですか?

 A: ステップ 5 では、`TextAbsorber` PDF ドキュメントからテキストを抽出するオブジェクト。次に、目的のページのアブソーバにアクセスして、アブソーバを受け入れます。`Pages`のコレクション`pdfDocument`.

#### Q: 抽出したテキストにアクセスするにはどうすればよいですか?

 A: ステップ 6 では、ファイルから抽出されたテキストにアクセスする手順を説明します。`TextAbsorber`物体。

#### Q: 抽出したテキストをファイルに保存するにはどうすればよいですか?

 A: ステップ 7 では、`TextWriter`、抽出されたテキストを保存するファイルを開き、抽出されたテキストをファイルに書き込み、ストリームを閉じます。

#### Q: このチュートリアルの重要なポイントは何ですか?

A: このチュートリアルに従うことで、Aspose.PDF for .NET を使用して PDF ドキュメントの特定のページからテキストを抽出する方法を学習しました。抽出されたテキストは指定された出力ファイルに保存されているため、特定のページのテキスト コンテンツをターゲットにして分析することができます。