---
title: ドキュメントに HTML 順序付きリストを追加する
linktitle: ドキュメントに HTML 順序付きリストを追加する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用してドキュメントに HTML の順序付きリストを追加する方法を学習します。
type: docs
weight: 30
url: /ja/net/programming-with-text/add-html-ordered-list-into-documents/
---
このチュートリアルでは、Aspose.PDF for .NET ライブラリを使用して、ドキュメントに HTML の順序付きリストを追加する方法を学習します。提供されているコードは、このタスクを実行するために必要な手順を示しています。

## 要件
始める前に、次のものがあることを確認してください。

- マシンにインストールされている Visual Studio またはその他の C# コンパイラ。
- Aspose.PDF for .NET ライブラリ。公式 Aspose Web サイトからダウンロードするか、NuGet などのパッケージ マネージャーを使用してインストールできます。

## ステップ1: プロジェクトを設定する
1. 好みの開発環境で新しい C# プロジェクトを作成します。
2. Aspose.PDF for .NET ライブラリへの参照を追加します。

## ステップ2: 必要な名前空間をインポートする
HTML の順序付きリストを追加するコード ファイルで、ファイルの先頭に次の using ディレクティブを追加します。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## ステップ3: ドキュメントディレクトリと出力ファイルパスを設定する
コード内で、次の行を見つけます。`string dataDir = "YOUR DOCUMENT DIRECTORY";`置き換えて`"YOUR DOCUMENT DIRECTORY"`ドキュメントが保存されているディレクトリへのパスを指定します。

次に、`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";`置き換えて`"AddHTMLOrderedListIntoDocuments_out.pdf"`出力 PDF ファイルに希望する名前を付けます。

## ステップ4: 新しいDocumentオブジェクトを作成する
新しいインスタンスを作成する`Document`次のコード行を追加してオブジェクトを作成します。

```csharp
Document doc = new Document();
```

## ステップ5: HTMLコンテンツを含むHtmlFragmentオブジェクトを作成する
インスタンス化する`HtmlFragment`ドキュメントに追加したいHTMLコンテンツを含むオブジェクト。提供されたコードでは、HTMLコンテンツは変数に割り当てられます。`t`必要に応じて HTML コンテンツを変更できます。

```csharp
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li >Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
```

## ステップ6: ドキュメントにページを追加する
ドキュメントに新しいページを追加するには、`Add`方法の`Pages`コレクション。提供されたコードでは、新しいページが変数に割り当てられます`page`.

```csharp
Page page = doc.Pages.Add();
```

## ステップ7: ページにHtmlFragmentを追加する
追加する`HtmlFragment`ページにオブジェクトを追加するには、`Add`方法の`Paragraphs`コレクション。

```csharp
page.Paragraphs.Add(t);
```

## ステップ8: PDF文書を保存する
結果のPDFファイルを`Save`方法の`Document`オブジェクト。手順 3 で設定した出力ファイル パスを指定します。

```csharp
doc.Save(outFile);
```

### Aspose.PDF for .NET を使用してドキュメントに HTMLOrdered List を追加するためのサンプル ソース コード 
```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//出力ドキュメントへのパス。
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
// Documentオブジェクトをインスタンス化する
Document doc = new Document();
//対応するHTMLフラグメントでHtmlFragmentオブジェクトをインスタンス化する
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
//ページコレクションにページを追加する
Page page = doc.Pages.Add();
//ページ内にHtmlFragmentを追加する
page.Paragraphs.Add(t);
//結果のPDFファイルを保存する
doc.Save(outFile);
```

## 結論
Aspose.PDF for .NET を使用して、HTML の順序付きリストをドキュメントに正常に追加しました。結果の PDF ファイルは、指定した出力ファイル パスにあります。

必ず HTML コンテンツをカスタマイズし、特定の要件に応じてコードを調整してください。

### よくある質問

#### Q: このチュートリアルの目的は何ですか?

A: このチュートリアルでは、Aspose.PDF for .NET ライブラリを使用して、HTML の順序付きリストをドキュメントに追加するプロセスについて説明します。このタスクを実行するのに役立つステップバイステップの手順とコード スニペットを提供します。

#### Q: このチュートリアルではどの名前空間をインポートする必要がありますか?

A: コード ファイルの先頭に次の名前空間をインポートする必要があります。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### Q: ドキュメント ディレクトリと出力ファイル パスを指定するにはどうすればよいですか?

 A: コード内で次の行を見つけます`string dataDir = "YOUR DOCUMENT DIRECTORY";`置き換えて`"YOUR DOCUMENT DIRECTORY"`ドキュメントディレクトリへの実際のパスを入力します。また、次の行を見つけます。`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";`置き換えて`"AddHTMLOrderedListIntoDocuments_out.pdf"`希望する出力 PDF ファイル名を入力します。

#### Q: ドキュメントに追加される HTML コンテンツをカスタマイズできますか?

 A: もちろんです！ステップ5では、`HtmlFragment`オブジェクト名`t` HTML コンテンツを保持します。バックティック内の HTML コンテンツを必要に応じて変更できます。

#### Q: ドキュメント内のページに HTML の順序付きリストを追加するにはどうすればよいですか?

 A: ステップ7では、`HtmlFragment`物体 （`t` ）をページに追加します。`Add`方法の`Paragraphs`コレクション。これにより、HTML の順序付きリストがドキュメントにシームレスに統合されます。

#### Q: 生成された PDF ドキュメントをどのように保存しますか?

 A: HTMLコンテンツを追加してページ上に配置した後、`Save`方法の`Document`オブジェクト。前に設定した正しい出力ファイル パスを必ず指定してください。

#### Q: 参考用にサンプルソースコードの概要を提供していただけますか?

A: もちろんです! このチュートリアルで提供されているサンプル ソース コードの要約版を以下に示します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
Document doc = new Document();
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
Page page = doc.Pages.Add();
page.Paragraphs.Add(t);
doc.Save(outFile);
```

#### Q: このチュートリアルから得られる重要なポイントは何ですか?

A: このチュートリアルに従うことで、Aspose.PDF for .NET ライブラリを活用して HTML の順序付きリストをドキュメントに組み込む方法を習得できました。この新しい知識は、ドキュメントの作成および操作プロセスを強化するために適用できます。