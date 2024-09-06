---
title: PDF ファイル内の列テキストの抽出
linktitle: PDF ファイル内の列テキストの抽出
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイル内の列テキストを抽出する方法を学習します。
type: docs
weight: 150
url: /ja/net/programming-with-text/extract-columns-text/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイル内の列テキストを抽出するプロセスについて説明します。提供されている C# ソース コードは、必要な手順を示しています。

## 要件
始める前に、次のものがあることを確認してください。

- マシンにインストールされている Visual Studio またはその他の C# コンパイラ。
- Aspose.PDF for .NET ライブラリ。公式 Aspose Web サイトからダウンロードするか、NuGet などのパッケージ マネージャーを使用してインストールできます。

## ステップ1: プロジェクトを設定する
1. 好みの開発環境で新しい C# プロジェクトを作成します。
2. Aspose.PDF for .NET ライブラリへの参照を追加します。

## ステップ2: 必要な名前空間をインポートする
列のテキストを抽出するコード ファイルで、ファイルの先頭に次の using ディレクティブを追加します。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

## ステップ3: ドキュメントディレクトリを設定する
コード内で、次の行を見つけます。`string dataDir = "YOUR DOCUMENT DIRECTORY";`置き換えて`"YOUR DOCUMENT DIRECTORY"`ドキュメントが保存されているディレクトリへのパスを指定します。

## ステップ4: PDF文書を開く
既存のPDF文書を開くには、`Document`コンストラクターを呼び出して、入力 PDF ファイルへのパスを渡します。

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## ステップ5: フォントサイズを調整する
読みやすさを向上させ、列形式のテキストをより適切に表現するために、テキスト フラグメントのフォント サイズを 0.7 倍に縮小します。

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach(TextFragment tf in tfc)
{
     tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
```

## ステップ6: 列からテキストを抽出する
変更したPDF文書をメモリストリームに保存し、新しい文書として再読み込みします。次に、`TextAbsorber`列からテキストを抽出するクラス。

```csharp
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument);
```

## ステップ7: 抽出したテキストを保存する
抽出したテキストを、指定された出力ファイル パスのテキスト ファイルに保存します。

```csharp
dataDir = dataDir + "ExtractColumnsText_out.txt";
File.WriteAllText(dataDir, extractedText);
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

### Aspose.PDF for .NET を使用して列テキストを抽出するためのサンプル ソース コード 
```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ドキュメントを開く
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");                
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach (TextFragment tf in tfc)
{
	//フォントサイズを少なくとも70%縮小する必要がある
	tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument); 
dataDir = dataDir + "ExtractColumnsText_out.txt";
System.IO.File.WriteAllText(dataDir, extractedText);           
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

## 結論
Aspose.PDF for .NET を使用して PDF ドキュメントから列のテキストを正常に抽出しました。抽出されたテキストは指定された出力ファイルに保存されました。

### よくある質問

#### Q: このチュートリアルの目的は何ですか?

A: このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイルからテキストの列を抽出する手順を段階的に説明します。付属の C# ソース コードでは、必要な手順を実際に示します。

#### Q: どの名前空間をインポートすればよいですか?

A: テキストの列を抽出するコード ファイルでは、ファイルの先頭に次の using ディレクティブを含めます。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

#### Q: ドキュメントディレクトリを指定するにはどうすればよいですか?

 A: 線を見つける`string dataDir = "YOUR DOCUMENT DIRECTORY";`コード内の`"YOUR DOCUMENT DIRECTORY"`ドキュメント ディレクトリへの実際のパスを入力します。

#### Q: 既存の PDF ドキュメントを開くにはどうすればよいですか?

 A: ステップ4では、既存のPDF文書を`Document`コンストラクターを呼び出して、入力 PDF ファイルへのパスを指定します。

#### Q: フォントサイズが調整されるのはなぜですか?

A: ステップ 5 では、テキスト フラグメントのフォント サイズを 0.7 分の 1 に縮小します。この調整により、読みやすさが向上し、列形式のテキストがより正確に表現されます。

#### Q: 列からテキストを抽出するにはどうすればよいですか?

 A: ステップ6は、変更されたPDF文書をメモリストリームに保存し、それを新しい文書として再読み込みし、`TextAbsorber`列からテキストを抽出するクラス。

#### Q: 抽出したテキストを保存する目的は何ですか?

A: ステップ 7 では、抽出したテキストを指定された出力ファイル パスのテキスト ファイルに保存します。

#### Q: 抽出前にフォント サイズを縮小するのはなぜですか?

A: フォント サイズを小さくすると、抽出されたテキストが列内で適切に配置されるようになり、元のレイアウトがより正確に表現されます。

#### Q: このチュートリアルから得られる重要なポイントは何ですか?

A: このチュートリアルに従うことで、Aspose.PDF for .NET を使用して PDF ドキュメントからテキストの列を抽出するために必要な知識とスキルを習得しました。結果のテキストは、指定された出力ファイルに保存されています。