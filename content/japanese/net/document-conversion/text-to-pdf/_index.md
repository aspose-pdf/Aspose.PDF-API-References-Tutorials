---
title: テキストを PDF に変換
linktitle: テキストを PDF に変換
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して、テキスト ファイルを PDF に簡単かつ効率的に変換します。
type: docs
weight: 300
url: /ja/net/document-conversion/text-to-pdf/
---
このチュートリアルでは、Aspose.PDF for .NET を使用してテキスト ファイルを PDF ファイルに変換する手順を説明します。 Aspose.PDF は、テキストの書式設定と表示を維持しながら、プレーン テキストを PDF に変換するためのシンプルで効果的なソリューションを提供します。この変換を実行するには、次の手順に従ってください。

## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。

- C# プログラミング言語の基本的な知識。
- .NET 用の Aspose.PDF ライブラリがシステムにインストールされています。
- Visual Studio などの開発環境。

## ステップ 1: テキスト ファイルを読み取る
最初のステップは、次のコマンドを使用してテキスト ファイルの内容を読み取ることです。`StreamReader`クラス。次のコードを使用します。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//テキストファイルを読む
TextReader tr = new StreamReader(dataDir + "log.txt");
```

必ず交換してください`"YOUR DOCUMENTS DIRECTORY"`テキストファイルが置かれている実際のディレクトリに置き換えます。

## ステップ 2: PDF ドキュメントの作成
 番目のステップは、`Document`最終的な PDF ドキュメントを表すオブジェクト。次のコードを使用します。

```csharp
//ドキュメントオブジェクトを作成する
Document doc = new Document();
```

## ステップ 3: ドキュメントにテキストを追加する
番目のステップは、読み取ったテキストを PDF ドキュメントのページに追加することです。次のコードを使用します。

```csharp
//ドキュメントに新しいページを追加する
Page page = doc.Pages.Add();

// TextFragment オブジェクトを作成し、読み取ったテキストを引数として渡します
TextFragment text = new TextFragment(tr.ReadToEnd());

//テキスト段落をページに追加する
page.Paragraphs.Add(text);
```

## ステップ 4: PDF ファイルを保存する
最後に、目的のパスとファイル名を指定して、結果の PDF ファイルを保存します。次のコードを使用します。

```csharp
//結果の PDF ファイルを保存する
doc.Save(dataDir + "TexttoPDF_out.pdf");
```

生成される PDF ファイルのパスとファイル名を必ず指定してください。

### Aspose.PDF for .NET を使用した Text to PDF のソース コード例

```csharp
try
{
	
	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//ソーステキストファイルを読む
	TextReader tr = new StreamReader(dataDir + "log.txt");

	//空のコンストラクターを呼び出して Document オブジェクトをインスタンス化します。
	Document doc = new Document();

	// Document の Pages コレクションに新しいページを追加します
	Page page = doc.Pages.Add();

	//TextFragmet のインスタンスを作成し、リーダー オブジェクトからのテキストをそのコンストラクターに引数として渡します
	TextFragment text = new TextFragment(tr.ReadToEnd());
	//Text.TextState.Font = FontRepository.FindFont("Arial Unicode MS");

	//新しいテキスト段落を段落コレクションに追加し、TextFragment オブジェクトを渡します。
	page.Paragraphs.Add(text);

	//結果の PDF ファイルを保存する
	doc.Save(dataDir + "TexttoPDF_out.pdf"); 
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 結論
このチュートリアルでは、Aspose.PDF for .NET を使用してテキスト ファイルを PDF ファイルに変換する方法を学びました。上記の手順に従うことで、この変換を簡単に実行できます。この方法を使用してテキスト ファイルを PDF に変換し、Aspose.PDF の柔軟性と品質を活用してください。

### よくある質問

#### Q: Aspose.PDF for .NET とは何ですか?

A: Aspose.PDF for .NET は、開発者が C# アプリケーションで PDF ドキュメントを操作できるようにする強力なライブラリです。プレーンテキストを PDF に変換するなど、さまざまな機能を提供します。

#### Q: テキスト ファイルを PDF に変換する必要があるのはなぜですか?

A: テキスト ファイルを PDF 形式に変換すると、ドキュメントの管理、共有、配布が向上します。 PDF ファイルは、さまざまなデバイスやオペレーティング システム間で一貫した形式を提供します。

#### Q: テキスト ファイルをロードし、Aspose.PDF for .NET を使用して PDF に変換するにはどうすればよいですか?

A: テキスト ファイルをロードするには、`StreamReader`ファイルの内容を読み取るクラス。次に、`Document` PDF ドキュメントを表すオブジェクト。新しいページを追加し、`TextFragment`テキスト ファイルのテキストが含まれています。最後に、結果の PDF を次のコマンドを使用して保存します。`Save`の方法`Document`物体。

#### Q: PDF 内のテキストの外観をカスタマイズできますか?

A: はい。Aspose.PDF for .NET には、フォント スタイル、サイズ、色、配置など、生成される PDF 内のテキストの外観をカスタマイズするためのさまざまなオプションが用意されています。

#### Q: テキストの書式設定は、結果の PDF に保持されますか?

A: はい。Aspose.PDF for .NET は、テキストから PDF への変換中にテキストの書式設定とレイアウトを保持し、元のコンテンツを正確に表現します。