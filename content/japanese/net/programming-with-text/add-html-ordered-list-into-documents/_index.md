---
title: HTML 順序付きリストをドキュメントに追加する
linktitle: HTML順序付きリストをドキュメントに追加する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して、HTML 順序付きリストをドキュメントに追加する方法を学びます。
type: docs
weight: 30
url: /ja/net/programming-with-text/add-html-ordered-list-into-documents/
---
このチュートリアルでは、Aspose.PDF for .NET ライブラリを使用して、HTML 順序付きリストをドキュメントに追加する方法を学習します。提供されているコードは、このタスクを実行するために必要な手順を示しています。

## 要件
始める前に、以下のものがあることを確認してください。

- マシンにインストールされている Visual Studio またはその他の C# コンパイラー。
- .NET ライブラリ用の Aspose.PDF。 Aspose の公式 Web サイトからダウンロードするか、NuGet などのパッケージ マネージャーを使用してインストールできます。

## ステップ 1: プロジェクトをセットアップする
1. 好みの開発環境で新しい C# プロジェクトを作成します。
2. Aspose.PDF for .NET ライブラリへの参照を追加します。

## ステップ 2: 必要な名前空間をインポートする
HTML 順序付きリストを追加するコード ファイルで、ファイルの先頭に次の using ディレクティブを追加します。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## ステップ 3: ドキュメント ディレクトリと出力ファイル パスを設定する
コード内で、次の行を見つけます。`string dataDir = "YOUR DOCUMENT DIRECTORY";`そして交換してください`"YOUR DOCUMENT DIRECTORY"`ドキュメントが保存されているディレクトリへのパスを置き換えます。

次に、次の行を見つけます。`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";`そして交換してください`"AddHTMLOrderedListIntoDocuments_out.pdf"`出力 PDF ファイルの任意の名前を付けます。

## ステップ 4: 新しい Document オブジェクトを作成する
新しいインスタンスを作成する`Document`次のコード行を追加してオブジェクトを作成します。

```csharp
Document doc = new Document();
```

## ステップ 5: HTML コンテンツを含む HtmlFragment オブジェクトを作成する
インスタンス化する`HtmlFragment`オブジェクトに、ドキュメントに追加する HTML コンテンツを含めます。提供されたコードでは、HTML コンテンツが変数に割り当てられます。`t`。必要に応じて HTML コンテンツを変更できます。

```csharp
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li >Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
```

## ステップ 6: ドキュメントにページを追加する
を使用してドキュメントに新しいページを追加します。`Add`の方法`Pages`コレクション。提供されたコードでは、新しいページが変数に割り当てられます。`page`.

```csharp
Page page = doc.Pages.Add();
```

## ステップ 7: HtmlFragment をページに追加する
を追加します。`HtmlFragment`を使用してページに反対します`Add`の方法`Paragraphs`コレクション。

```csharp
page.Paragraphs.Add(t);
```

## ステップ 8: PDF ドキュメントを保存する
結果の PDF ファイルを次のコマンドを使用して保存します。`Save`の方法`Document`物体。手順 3 で設定した出力ファイルのパスを指定します。

```csharp
doc.Save(outFile);
```

### Aspose.PDF for .NET を使用して HTMLOrdered List をドキュメントに追加するためのサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//出力ドキュメントへのパス。
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
// Documentオブジェクトをインスタンス化する
Document doc = new Document();
//対応する HTML フラグメントを使用して HtmlFragment オブジェクトをインスタンス化します。
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
//ページ コレクションにページを追加する
Page page = doc.Pages.Add();
//ページ内に HtmlFragment を追加
page.Paragraphs.Add(t);
//結果の PDF ファイルを保存する
doc.Save(outFile);
```

## 結論
Aspose.PDF for .NET を使用して、HTML 順序付きリストをドキュメントに正常に追加しました。作成された PDF ファイルは、指定した出力ファイル パスに表示されます。

必ず HTML コンテンツをカスタマイズし、特定の要件に従ってコードを調整してください。

### よくある質問

#### Q: このチュートリアルの目的は何ですか?

A: このチュートリアルは、Aspose.PDF for .NET ライブラリを使用して HTML 順序付きリストをドキュメントに追加するプロセスをガイドすることを目的としています。このタスクを達成するのに役立つ段階的な手順とコード スニペットが提供されます。

#### Q: このチュートリアルではどの名前空間をインポートする必要がありますか?

A: コード ファイルの先頭に次の名前空間をインポートする必要があります。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### Q: ドキュメント ディレクトリと出力ファイルのパスを指定するにはどうすればよいですか?

 A: コード内で次の行を見つけます。`string dataDir = "YOUR DOCUMENT DIRECTORY";`そして交換してください`"YOUR DOCUMENT DIRECTORY"`ドキュメントディレクトリへの実際のパスを置き換えます。また、行を見つけてください`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";`そして交換してください`"AddHTMLOrderedListIntoDocuments_out.pdf"`希望する出力 PDF ファイル名を付けます。

#### Q: ドキュメントに追加される HTML コンテンツをカスタマイズできますか?

 A: もちろんです！ステップ 5 では、`HtmlFragment`という名前のオブジェクト`t`HTML コンテンツを保持します。要件に合わせてバッククォート内の HTML コンテンツを変更できます。

#### Q: HTML 順序付きリストをドキュメント内のページに追加するにはどうすればよいですか?

 A: ステップ 7 で、`HtmlFragment`物体 （`t` ) を使用してページに移動します。`Add`の方法`Paragraphs`コレクション。これにより、HTML 順序付きリストがドキュメントにシームレスに統合されます。

#### Q: 作成された PDF ドキュメントを保存するにはどうすればよいですか?

 A: HTML コンテンツを追加してページ上に配置した後、次のコマンドを使用して PDF ドキュメントを保存できます。`Save`の方法`Document`物体。前に設定した正しい出力ファイルのパスを必ず指定してください。

#### Q: 参考としてサンプル ソース コードの概要を提供してもらえますか?

A：確かに！このチュートリアルで提供されるサンプル ソース コードの要約版を次に示します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
Document doc = new Document();
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
Page page = doc.Pages.Add();
page.Paragraphs.Add(t);
doc.Save(outFile);
```

#### Q: このチュートリアルの重要なポイントは何ですか?

A: このチュートリアルに従うことで、Aspose.PDF for .NET ライブラリを利用して HTML 順序付きリストをドキュメントに組み込む方法を学習できました。この新たに得られた知識は、ドキュメントの作成および操作プロセスを強化するために適用できます。