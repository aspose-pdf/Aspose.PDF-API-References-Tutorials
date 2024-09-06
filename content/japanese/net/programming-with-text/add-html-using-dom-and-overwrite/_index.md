---
title: DOMとPDF上書きを使用してHTMLを追加する
linktitle: DOMを使用してHTMLを追加し上書きする
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET で DOM と PDF 上書きを使用して HTML コンテンツを追加する方法を学習します。
type: docs
weight: 50
url: /ja/net/programming-with-text/add-html-using-dom-and-overwrite/
---
このチュートリアルでは、Aspose.PDF for .NET で DOM (ドキュメント オブジェクト モデル) を使用して HTML コンテンツを追加する手順を説明します。また、HTML コンテンツのスタイルを上書きする方法も学習します。提供されている C# ソース コードで必要な手順が示されています。

## 要件
始める前に、次のものがあることを確認してください。

- マシンにインストールされている Visual Studio またはその他の C# コンパイラ。
- Aspose.PDF for .NET ライブラリ。公式 Aspose Web サイトからダウンロードするか、NuGet などのパッケージ マネージャーを使用してインストールできます。

## ステップ1: プロジェクトを設定する
1. 好みの開発環境で新しい C# プロジェクトを作成します。
2. Aspose.PDF for .NET ライブラリへの参照を追加します。

## ステップ2: 必要な名前空間をインポートする
HTML コンテンツを追加するコード ファイルで、ファイルの先頭に次の using ディレクティブを追加します。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## ステップ3: ドキュメントディレクトリと出力ファイルパスを設定する
コード内で、次の行を見つけます。`string dataDir = "YOUR DOCUMENT DIRECTORY";`置き換えて`"YOUR DOCUMENT DIRECTORY"`ドキュメントが保存されているディレクトリへのパスを指定します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ4: 新しいDocumentオブジェクトを作成する
新しいインスタンスを作成する`Document`次のコード行を追加してオブジェクトを作成します。

```csharp
Document doc = new Document();
```

## ステップ5: ドキュメントにページを追加する
ドキュメントに新しいページを追加するには、`Add`方法の`Pages`コレクション。提供されたコードでは、新しいページが変数に割り当てられます`page`.

```csharp
Page page = doc.Pages.Add();
```

## ステップ6: HTMLコンテンツを含むHtmlFragmentを作成する
インスタンス化する`HtmlFragment`オブジェクトを作成し、必要なHTMLコンテンツを提供します。提供されたコードでは、HTMLコンテンツは変数に割り当てられます`title`必要に応じて HTML コンテンツを変更できます。

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

## ステップ7: HTMLコンテンツのスタイルを上書きする
HTMLコンテンツのスタイルを上書きするには、`TextState`の特性`HtmlFragment`オブジェクト。提供されたコードでは、フォント ファミリが「Arial」に変更され、フォント サイズが 20 に設定されています。

```csharp
title. TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

## ステップ8: 余白情報を設定する
必要に応じて、HTML フラグメントの下部と上部の余白を調整します。提供されているコードでは、下部の余白は 10 に設定され、上部の余白は 400 に設定されています。

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 400;
```

## ステップ9: ページにHtmlFragmentを追加する
追加する`HtmlFragment`ページの段落コレクションへのオブジェクト。

```csharp
page.Paragraphs.Add(title);
```

## ステップ10: PDF文書を保存する
PDF文書を保存するには、`Save`方法の`Document`オブジェクト。手順 3 で設定した出力ファイル パスを指定します。

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

### Aspose.PDF for .NET を使用して HTML を追加し、DOM で上書きするサンプル ソース コード 
```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Documentオブジェクトをインスタンス化する
Document doc = new Document();
//PDFファイルのページコレクションにページを追加する
Page page = doc.Pages.Add();
//HTMLコンテンツでHtmlFragmentをインスタンス化する
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
//フォントファミリーは「Verdana」から「Arial」にリセットされます
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
//下余白情報を設定する
title.Margin.Bottom = 10;
//上余白情報を設定する
title.Margin.Top = 400;
//ページの段落コレクションに HTML フラグメントを追加する
page.Paragraphs.Add(title);
//PDFファイルを保存
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
//PDFファイルを保存
doc.Save(dataDir);
```

## 結論
Aspose.PDF for .NET で DOM を使用して HTML コンテンツを追加し、HTML コンテンツのスタイルを上書きしました。結果の PDF ファイルは、指定した出力ファイル パスにあります。

### よくある質問

#### Q: このチュートリアルの焦点は何ですか?

A: このチュートリアルは、Aspose.PDF for .NET のドキュメント オブジェクト モデル (DOM) を使用して、PDF ドキュメントに HTML コンテンツを追加するプロセスを説明することを目的としています。また、HTML コンテンツのスタイルを上書きして外観をカスタマイズする方法についても学習します。このチュートリアルでは、必要な手順を示す C# ソース コード スニペットを提供します。

#### Q: このチュートリアルではどの名前空間をインポートする必要がありますか?

A: HTML コンテンツを追加するコード ファイルで、ファイルの先頭に次の名前空間をインポートします。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### Q: ドキュメント ディレクトリと出力ファイル パスを指定するにはどうすればよいですか?

 A: コード内で次の行を見つけます`string dataDir = "YOUR DOCUMENT DIRECTORY";`置き換えて`"YOUR DOCUMENT DIRECTORY"`ドキュメント ディレクトリへの実際のパスを入力します。

#### Q: Document オブジェクトを作成するにはどうすればよいですか?

 A: ステップ4では、新しいインスタンスを作成します。`Document`次のコード行を使用してオブジェクトを作成します。

```csharp
Document doc = new Document();
```

#### Q: ドキュメントにページを追加するにはどうすればよいですか?

 A: ステップ5では、`Add`方法の`Pages`コレクション：

```csharp
Page page = doc.Pages.Add();
```

#### Q: DOM を使用して HTML コンテンツを設定するにはどうすればよいですか?

 A: ステップ6では、`HtmlFragment`オブジェクトを作成し、希望するHTMLコンテンツを割り当てます。HTMLコンテンツは変数に割り当てられます`title`:

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

#### Q: HTML コンテンツのスタイルを上書きするにはどうすればよいですか?

 A: ステップ7では、HTMLコンテンツのスタイルを上書きします。`TextState`の特性`HtmlFragment`オブジェクト。たとえば、フォント ファミリを「Arial」に変更し、フォント サイズを 20 に設定できます。

```csharp
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

#### Q: HTML コンテンツの余白を調整できますか?

A: はい、ステップ 8 で、必要に応じて HTML フラグメントの下部と上部の余白を調整できます。

```csharp
title.Margin.Bottom = 10;
title.Margin.Top = 400;
```

#### Q: PDF ドキュメントに HtmlFragment を追加するにはどうすればよいですか?

 A: ステップ9では、`HtmlFragment`物体 （`title`) をページの段落コレクションに追加します。

```csharp
page.Paragraphs.Add(title);
```

#### Q: 生成された PDF ドキュメントをどのように保存しますか?

 A: HTMLコンテンツを追加してスタイルをカスタマイズした後、`Save`方法の`Document` PDF ドキュメントを保存するオブジェクト:

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

#### Q: このチュートリアルから得られる重要なポイントは何ですか?

A: このチュートリアルに従うことで、Aspose.PDF for .NET でドキュメント オブジェクト モデル (DOM) を使用して HTML コンテンツを組み込む方法を習得しました。さらに、スタイルを上書きして、結果の PDF ドキュメント内の HTML コンテンツの外観をカスタマイズする機能も習得しました。