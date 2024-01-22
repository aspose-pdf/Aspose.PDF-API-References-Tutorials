---
title: PDF ファイル内の列テキストを抽出する
linktitle: PDF ファイル内の列テキストを抽出する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイル内の列テキストを抽出する方法を学びます。
type: docs
weight: 150
url: /ja/net/programming-with-text/extract-columns-text/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイル内の列テキストを抽出するプロセスについて説明します。提供されている C# ソース コードは、必要な手順を示しています。

## 要件
始める前に、以下のものがあることを確認してください。

- マシンにインストールされている Visual Studio またはその他の C# コンパイラー。
- .NET ライブラリ用の Aspose.PDF。 Aspose の公式 Web サイトからダウンロードするか、NuGet などのパッケージ マネージャーを使用してインストールできます。

## ステップ 1: プロジェクトをセットアップする
1. 好みの開発環境で新しい C# プロジェクトを作成します。
2. Aspose.PDF for .NET ライブラリへの参照を追加します。

## ステップ 2: 必要な名前空間をインポートする
列のテキストを抽出するコード ファイルで、ファイルの先頭に次の using ディレクティブを追加します。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

## ステップ 3: ドキュメント ディレクトリを設定する
コード内で、次の行を見つけます。`string dataDir = "YOUR DOCUMENT DIRECTORY";`そして交換してください`"YOUR DOCUMENT DIRECTORY"`ドキュメントが保存されているディレクトリへのパスを置き換えます。

## ステップ 4: PDF ドキュメントを開く
既存の PDF ドキュメントを開くには、`Document`コンストラクターを呼び出して、入力 PDF ファイルへのパスを渡します。

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## ステップ5: フォントサイズを調整する
テキスト フラグメントのフォント サイズを 0.7 分の 1 に縮小して、可読性を高め、柱状のテキストをより適切に表現します。

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach(TextFragment tf in tfc)
{
     tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
```

## ステップ 6: 列からテキストを抽出する
変更した PDF ドキュメントをメモリ ストリームに保存し、新しいドキュメントとして再ロードします。次に、`TextAbsorber`列からテキストを抽出するクラス。

```csharp
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument);
```

## ステップ 7: 抽出したテキストを保存する
抽出したテキストを、指定した出力ファイル パスにあるテキスト ファイルに保存します。

```csharp
dataDir = dataDir + "ExtractColumnsText_out.txt";
File.WriteAllText(dataDir, extractedText);
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

### Aspose.PDF for .NET を使用した列テキストの抽出のサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開いた文書
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
Aspose.PDF for .NET を使用して PDF ドキュメントから列テキストを正常に抽出しました。抽出されたテキストは、指定された出力ファイルに保存されました。

### よくある質問

#### Q: このチュートリアルの目的は何ですか?

A: このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイルからテキスト列を抽出する方法を段階的に説明します。付属の C# ソース コードは、必要な手順の実践的なデモンストレーションを提供します。

#### Q: どの名前空間をインポートする必要がありますか?

A: テキスト列を抽出するコード ファイルでは、ファイルの先頭に次の using ディレクティブを含めます。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

#### Q: ドキュメント ディレクトリを指定するにはどうすればよいですか?

 A: 行を見つけてください`string dataDir = "YOUR DOCUMENT DIRECTORY";`コードに追加して置き換えます`"YOUR DOCUMENT DIRECTORY"`ドキュメントディレクトリへの実際のパスを置き換えます。

#### Q: 既存の PDF ドキュメントを開くにはどうすればよいですか?

 A: ステップ 4 では、`Document`コンストラクターを作成し、入力 PDF ファイルへのパスを提供します。

#### Q: フォントサイズが調整されるのはなぜですか?

A: ステップ 5 では、テキスト フラグメントのフォント サイズを 0.7 分の 1 に縮小します。この調整により読みやすさが向上し、柱状のテキストがより正確に表現されます。

#### Q: 列からテキストを抽出するにはどうすればよいですか?

 A: ステップ 6 では、変更された PDF ドキュメントをメモリ ストリームに保存し、新しいドキュメントとして再ロードして、`TextAbsorber`列からテキストを抽出するクラス。

#### Q: 抽出したテキストを保存する目的は何ですか?

A: ステップ 7 では、抽出したテキストを、指定された出力ファイル パスにあるテキスト ファイルに保存します。

#### Q: 抽出前にフォント サイズを小さくするのはなぜですか?

A: フォント サイズを小さくすると、抽出されたテキストが列内で適切に配置され、元のレイアウトがより正確に表現されるようになります。

#### Q: このチュートリアルの重要なポイントは何ですか?

A: このチュートリアルに従うことで、Aspose.PDF for .NET を使用して PDF ドキュメントからテキスト列を抽出するために必要な知識とスキルを習得したことになります。結果のテキストは、指定された出力ファイルに保存されました。