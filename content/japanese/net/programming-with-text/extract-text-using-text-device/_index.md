---
title: テキストデバイスを使用してテキストを抽出する
linktitle: テキストデバイスを使用してテキストを抽出する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET のテキスト デバイスを使用して PDF ドキュメントからテキストを抽出する方法を学習します。
type: docs
weight: 210
url: /ja/net/programming-with-text/extract-text-using-text-device/
---
このチュートリアルでは、Aspose.PDF for .NET のテキスト デバイスを使用して PDF ドキュメントからテキストを抽出するプロセスについて説明します。提供されている C# ソース コードは、必要な手順を示しています。

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
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

## ステップ3: ドキュメントディレクトリを設定する
コード内で、次の行を見つけます。`string dataDir = "YOUR DOCUMENT DIRECTORY";`置き換えて`"YOUR DOCUMENT DIRECTORY"`ドキュメントが保存されているディレクトリへのパスを指定します。

## ステップ4: PDF文書を開く
既存のPDF文書を開くには、`Document`コンストラクターを呼び出して、入力 PDF ファイルへのパスを渡します。

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## ステップ5: テキストデバイスを使用してテキストを抽出する
作成する`StringBuilder`抽出したテキストを保持するオブジェクト。文書の各ページを反復処理し、`TextDevice`各ページからテキストを抽出します。

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

## ステップ6: 抽出したテキストを保存する
出力ファイルのパスを指定し、抽出したテキストをテキストファイルに保存するには、`File.WriteAllText`方法。

```csharp
dataDir = dataDir + "input_Text_Extracted_out.txt";
File.WriteAllText(dataDir, builder.ToString());
```

### Aspose.PDF for .NET を使用してテキスト デバイスでテキストを抽出するためのサンプル ソース コード 
```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ドキュメントを開く
Document pdfDocument = new Document( dataDir + "input.pdf");
System.Text.StringBuilder builder = new System.Text.StringBuilder();
//抽出されたテキストを保持する文字列
string extractedText = "";
foreach (Page pdfPage in pdfDocument.Pages)
{
	using (MemoryStream textStream = new MemoryStream())
	{
		//テキストデバイスを作成する
		TextDevice textDevice = new TextDevice();
		//テキスト抽出オプションの設定 - テキスト抽出モードの設定 (Raw または Pure)
		TextExtractionOptions textExtOptions = new
		TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
		textDevice.ExtractionOptions = textExtOptions;
		//特定のページを変換し、テキストをストリームに保存する
		textDevice.Process(pdfPage, textStream);
		//特定のページを変換し、テキストをストリームに保存する
		textDevice.Process(pdfDocument.Pages[1], textStream);
		//メモリストリームを閉じる
		textStream.Close();
		//メモリストリームからテキストを取得する
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
Aspose.PDF for .NET のテキスト デバイスを使用して、PDF ドキュメントからテキストを正常に抽出しました。抽出されたテキストは、指定された出力ファイルに保存されました。

### よくある質問

#### Q: このチュートリアルの目的は何ですか?

A: このチュートリアルでは、Aspose.PDF for .NET のテキスト デバイス機能を使用して PDF ドキュメントからテキストを抽出する方法について説明します。付属の C# ソース コードは、このタスクを実行するために必要な手順を示しています。

#### Q: どの名前空間をインポートすればよいですか?

A: テキストを抽出する予定のコード ファイルで、ファイルの先頭に次の using ディレクティブを含めます。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

#### Q: ドキュメントディレクトリを指定するにはどうすればよいですか?

 A: コードの中で、`string dataDir = "YOUR DOCUMENT DIRECTORY";`置き換えて`"YOUR DOCUMENT DIRECTORY"`ドキュメント ディレクトリへの実際のパスを入力します。

#### Q: 既存の PDF ドキュメントを開くにはどうすればよいですか?

 A: ステップ4では、既存のPDF文書を`Document`コンストラクターを呼び出して、入力 PDF ファイルへのパスを指定します。

#### Q: テキスト デバイスを使用してテキストを抽出するにはどうすればよいですか?

 A: ステップ5では、`StringBuilder`抽出したテキストを保持するオブジェクトを作成します。次に、ドキュメントの各ページを反復処理し、`TextDevice`とともに`TextExtractionOptions`各ページからテキストを抽出します。

#### Q: 抽出したテキストをファイルに保存するにはどうすればよいですか?

 A: ステップ6では、出力ファイルのパスを指定して、`File.WriteAllText`抽出したテキストをテキスト ファイルに保存する方法。

#### Q: このチュートリアルから得られる重要なポイントは何ですか?

A: このチュートリアルでは、Aspose.PDF for .NET のテキスト デバイス機能を利用して PDF ドキュメントからテキストを抽出する方法を学習しました。抽出されたテキストは指定された出力ファイルに保存され、必要に応じて抽出されたコンテンツを操作および利用できるようになります。