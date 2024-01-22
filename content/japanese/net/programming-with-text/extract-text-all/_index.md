---
title: PDF ファイル内のテキストをすべて抽出する
linktitle: PDF ファイル内のテキストをすべて抽出
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイル内のすべてのテキストを抽出する方法を学びます。
type: docs
weight: 180
url: /ja/net/programming-with-text/extract-text-all/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイル内のすべてのテキストを抽出するプロセスについて説明します。提供されている C# ソース コードは、必要な手順を示しています。

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
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

## ステップ 5: すべてのテキストを抽出する
を作成します`TextAbsorber`オブジェクトを使用してドキュメントからテキストを抽出します。次に、すべてのページの吸収体を受け入れます。

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
```

## ステップ 6: 抽出されたテキストを取得する
から抽出されたテキストにアクセスします。`TextAbsorber`物体。

```csharp
string extractedText = textAbsorber.Text;
```

## ステップ 7: 抽出したテキストを保存する
を作成します`TextWriter`抽出したテキストを保存するファイルを開きます。抽出したテキストをファイルに書き込み、ストリームを閉じます。

```csharp
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
tw.WriteLine(extractedText);
tw. Close();
```

### Aspose.PDF for .NET を使用したすべてのテキストの抽出のサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開いた文書
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
//テキストを抽出する TextAbsorber オブジェクトを作成する
TextAbsorber textAbsorber = new TextAbsorber();
//すべてのページに吸収体を受け入れる
pdfDocument.Pages.Accept(textAbsorber);
//抽出されたテキストを取得する
string extractedText = textAbsorber.Text;
//ライターを作成してファイルを開く
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
//ファイルにテキスト行を書き込みます
tw.WriteLine(extractedText);
//ストリームを閉じる
tw.Close();
```

## 結論
Aspose.PDF for .NET を使用して PDF ドキュメントからすべてのテキストを正常に抽出しました。抽出されたテキストは、指定された出力ファイルに保存されました。

### よくある質問

#### Q: このチュートリアルの目的は何ですか?

A: このチュートリアルは、Aspose.PDF for .NET を使用して PDF ファイルからすべてのテキストを抽出するのに役立つガイドとして機能します。付属の C# ソース コードには、このタスクを実行するための段階的な手順が記載されています。

#### Q: どの名前空間をインポートする必要がありますか?

A: テキストを抽出するコード ファイルでは、ファイルの先頭に次の using ディレクティブを含めます。

```csharp
using Aspose.Pdf;
using System.IO;
```

#### Q: ドキュメント ディレクトリを指定するにはどうすればよいですか?

 A: 行を見つけてください`string dataDir = "YOUR DOCUMENT DIRECTORY";`コードに追加して置き換えます`"YOUR DOCUMENT DIRECTORY"`ドキュメントディレクトリへの実際のパスを置き換えます。

#### Q: 既存の PDF ドキュメントを開くにはどうすればよいですか?

 A: ステップ 4 では、`Document`コンストラクターを作成し、入力 PDF ファイルへのパスを提供します。

#### Q: ドキュメントからすべてのテキストを抽出するにはどうすればよいですか?

 A: ステップ 5 では、`TextAbsorber` PDF ドキュメントからテキストを抽出するオブジェクト。次に、すべてのページの吸収材を受け入れます。

#### Q: 抽出したテキストにアクセスするにはどうすればよいですか?

 A: ステップ 6 では、ファイルから抽出されたテキストにアクセスする手順を説明します。`TextAbsorber`物体。

#### Q: 抽出したテキストをファイルに保存するにはどうすればよいですか?

 A: ステップ 7 では、`TextWriter`、抽出されたテキストを保存するファイルを開き、抽出されたテキストをファイルに書き込み、ストリームを閉じます。

#### Q: このチュートリアルの重要なポイントは何ですか?

A: このチュートリアルに従うことで、Aspose.PDF for .NET を使用して PDF ドキュメントからすべてのテキストを抽出する方法を学習しました。抽出されたテキストは指定された出力ファイルに保存され、ドキュメントのテキスト内容を分析および操作できるようになります。