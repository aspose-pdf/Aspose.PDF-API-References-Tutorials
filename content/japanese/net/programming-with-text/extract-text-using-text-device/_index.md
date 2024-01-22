---
title: テキストデバイスを使用してテキストを抽出する
linktitle: テキストデバイスを使用してテキストを抽出する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET の Text Device を使用して PDF ドキュメントからテキストを抽出する方法を学びます。
type: docs
weight: 210
url: /ja/net/programming-with-text/extract-text-using-text-device/
---
このチュートリアルでは、Aspose.PDF for .NET のテキスト デバイスを使用して PDF ドキュメントからテキストを抽出するプロセスについて説明します。提供されている C# ソース コードは、必要な手順を示しています。

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
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

## ステップ 3: ドキュメント ディレクトリを設定する
コード内で、次の行を見つけます。`string dataDir = "YOUR DOCUMENT DIRECTORY";`そして交換してください`"YOUR DOCUMENT DIRECTORY"`ドキュメントが保存されているディレクトリへのパスを置き換えます。

## ステップ 4: PDF ドキュメントを開く
既存の PDF ドキュメントを開くには、`Document`コンストラクターを呼び出して、入力 PDF ファイルへのパスを渡します。

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## ステップ 5: Text Device を使用してテキストを抽出する
を作成します`StringBuilder`抽出されたテキストを保持するオブジェクト。ドキュメントの各ページを繰り返し処理し、`TextDevice`各ページからテキストを抽出します。

```csharp
StringBuilder builder = new StringBuilder();
string extractedText = "";
foreach(Page pdfPage in pdfDocument.Pages)
{
using (MemoryStream textStream = new MemoryStream())
{
TextDevice textDevice = new TextDevice();
TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
textDevice.ExtractionOptions = textExtOptions;
textDevice.Process(pdfPage, textStream);
textStream. Close();
extractedText = Encoding.Unicode.GetString(textStream.ToArray());
}
builder. Append(extractedText);
}
```

## ステップ 6: 抽出したテキストを保存する
出力ファイルのパスを指定し、抽出したテキストをテキスト ファイルに保存します。`File.WriteAllText`方法。

```csharp
dataDir = dataDir + "input_Text_Extracted_out.txt";
File.WriteAllText(dataDir, builder.ToString());
```

### Aspose.PDF for .NET を使用したテキスト デバイスを使用したテキストの抽出のサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開いた文書
Document pdfDocument = new Document( dataDir + "input.pdf");
System.Text.StringBuilder builder = new System.Text.StringBuilder();
//抽出されたテキストを保持する文字列
string extractedText = "";
foreach (Page pdfPage in pdfDocument.Pages)
{
	using (MemoryStream textStream = new MemoryStream())
	{
		//テキストデバイスの作成
		TextDevice textDevice = new TextDevice();
		//テキスト抽出オプションの設定 - テキスト抽出モード (Raw または Pure) を設定します。
		TextExtractionOptions textExtOptions = new
		TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
		textDevice.ExtractionOptions = textExtOptions;
		//特定のページを変換し、テキストをストリームに保存します
		textDevice.Process(pdfPage, textStream);
		//特定のページを変換し、テキストをストリームに保存します
		textDevice.Process(pdfDocument.Pages[1], textStream);
		//メモリストリームを閉じる
		textStream.Close();
		//メモリ ストリームからテキストを取得する
		extractedText = Encoding.Unicode.GetString(textStream.ToArray());
	}
	builder.Append(extractedText);
}
dataDir = dataDir + "input_Text_Extracted_out.txt";
//抽出したテキストをテキストファイルに保存する
File.WriteAllText(dataDir, builder.ToString());
Console.WriteLine("\nText extracted successfully using text device from page of PDF Document.\nFile saved at " + dataDir);
```

## 結論
Aspose.PDF for .NET の Text Device を使用して PDF ドキュメントからテキストを抽出することに成功しました。抽出されたテキストは、指定された出力ファイルに保存されました。

### よくある質問

#### Q: このチュートリアルの目的は何ですか?

A: このチュートリアルでは、Aspose.PDF for .NET のテキスト デバイス機能を使用して PDF ドキュメントからテキストを抽出する方法について説明します。付属の C# ソース コードは、このタスクを達成するために必要な手順を示しています。

#### Q: どの名前空間をインポートする必要がありますか?

A: テキストを抽出するコード ファイルでは、ファイルの先頭に次の using ディレクティブを含めます。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

#### Q: ドキュメント ディレクトリを指定するにはどうすればよいですか?

 A: コード内で、次の行を見つけます。`string dataDir = "YOUR DOCUMENT DIRECTORY";`そして交換してください`"YOUR DOCUMENT DIRECTORY"`ドキュメントディレクトリへの実際のパスを置き換えます。

#### Q: 既存の PDF ドキュメントを開くにはどうすればよいですか?

 A: ステップ 4 では、`Document`コンストラクターを作成し、入力 PDF ファイルへのパスを提供します。

#### Q: テキスト デバイスを使用してテキストを抽出するにはどうすればよいですか?

 A: ステップ 5 では、`StringBuilder`抽出されたテキストを保持するオブジェクト。次に、ドキュメントの各ページを繰り返し処理し、`TextDevice`とともに`TextExtractionOptions`各ページからテキストを抽出します。

#### Q: 抽出したテキストをファイルに保存するにはどうすればよいですか?

 A: ステップ 6 では、出力ファイルのパスを指定し、`File.WriteAllText`抽出したテキストをテキスト ファイルに保存するメソッド。

#### Q: このチュートリアルの重要なポイントは何ですか?

A: このチュートリアルに従うことで、Aspose.PDF for .NET のテキスト デバイス機能を利用して PDF ドキュメントからテキストを抽出する方法を学びました。抽出されたテキストは指定された出力ファイルに保存されているため、必要に応じて抽出されたコンテンツを操作して利用できます。