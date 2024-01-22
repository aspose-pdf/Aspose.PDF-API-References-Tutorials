---
title: DOM を使用して HTML を追加し、PDF を上書きする
linktitle: DOM を使用して HTML を追加して上書きする
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET で DOM と PDF の上書きを使用して HTML コンテンツを追加する方法を学びます。
type: docs
weight: 50
url: /ja/net/programming-with-text/add-html-using-dom-and-overwrite/
---
このチュートリアルでは、Aspose.PDF for .NET で DOM (ドキュメント オブジェクト モデル) を使用して HTML コンテンツを追加するプロセスについて説明します。さらに、HTML コンテンツのスタイルを上書きする方法も学習します。提供されている C# ソース コードは、必要な手順を示しています。

## 要件
始める前に、以下のものがあることを確認してください。

- マシンにインストールされている Visual Studio またはその他の C# コンパイラー。
- .NET ライブラリ用の Aspose.PDF。 Aspose の公式 Web サイトからダウンロードするか、NuGet などのパッケージ マネージャーを使用してインストールできます。

## ステップ 1: プロジェクトをセットアップする
1. 好みの開発環境で新しい C# プロジェクトを作成します。
2. Aspose.PDF for .NET ライブラリへの参照を追加します。

## ステップ 2: 必要な名前空間をインポートする
HTML コンテンツを追加するコード ファイルで、ファイルの先頭に次の using ディレクティブを追加します。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## ステップ 3: ドキュメント ディレクトリと出力ファイル パスを設定する
コード内で、次の行を見つけます。`string dataDir = "YOUR DOCUMENT DIRECTORY";`そして交換してください`"YOUR DOCUMENT DIRECTORY"`ドキュメントが保存されているディレクトリへのパスを置き換えます。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 4: 新しい Document オブジェクトを作成する
新しいインスタンスを作成する`Document`次のコード行を追加してオブジェクトを作成します。

```csharp
Document doc = new Document();
```

## ステップ 5: ドキュメントにページを追加する
を使用してドキュメントに新しいページを追加します。`Add`の方法`Pages`コレクション。提供されたコードでは、新しいページが変数に割り当てられます。`page`.

```csharp
Page page = doc.Pages.Add();
```

## ステップ 6: HTML コンテンツを使用して HtmlFragment を作成する
インスタンス化する`HtmlFragment`オブジェクトを作成し、必要な HTML コンテンツを提供します。提供されたコードでは、HTML コンテンツが変数に割り当てられます。`title`。必要に応じて HTML コンテンツを変更できます。

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

## ステップ 7: HTML コンテンツのスタイルを上書きする
HTML コンテンツのスタイルを上書きするには、`TextState`のプロパティ`HtmlFragment`物体。提供されたコードでは、フォント ファミリが「Arial」に変更され、フォント サイズが 20 に設定されています。

```csharp
title. TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

## ステップ 8: 余白情報を設定する
必要に応じて、HTML フラグメントの上下の余白を調整します。提供されたコードでは、下マージンが 10 に設定され、上マージンが 400 に設定されています。

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 400;
```

## ステップ 9: HtmlFragment をページに追加する
を追加します。`HtmlFragment`ページの段落コレクションに対するオブジェクト。

```csharp
page.Paragraphs.Add(title);
```

## ステップ 10: PDF ドキュメントを保存する
PDF ドキュメントを保存するには、`Save`の方法`Document`物体。手順 3 で設定した出力ファイルのパスを指定します。

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

### DOM を使用して HTML を追加し、Aspose.PDF for .NET を使用して上書きするためのサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Documentオブジェクトをインスタンス化する
Document doc = new Document();
//PDF ファイルのページコレクションにページを追加する
Page page = doc.Pages.Add();
//HTML コンテンツを使用して HtmlFragment をインスタンス化する
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
//「Verdana」のフォントファミリーは「Arial」にリセットされます
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
//下マージン情報の設定
title.Margin.Bottom = 10;
//上マージン情報の設定
title.Margin.Top = 400;
//ページの段落コレクションに HTML フラグメントを追加します
page.Paragraphs.Add(title);
//PDFファイルを保存する
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
//PDFファイルを保存する
doc.Save(dataDir);
```

## 結論
Aspose.PDF for .NET で DOM を使用して HTML コンテンツを追加し、HTML コンテンツのスタイルを上書きしました。作成された PDF ファイルは、指定した出力ファイル パスに表示されます。

### よくある質問

#### Q: このチュートリアルの焦点は何ですか?

A: このチュートリアルは、Aspose.PDF for .NET のドキュメント オブジェクト モデル (DOM) を使用して、PDF ドキュメントに HTML コンテンツを追加するプロセスを説明するように設計されています。さらに、HTML コンテンツのスタイルを上書きして、その外観をカスタマイズする方法を学びます。このチュートリアルでは、必要な手順を示すための C# ソース コード スニペットが提供されます。

#### Q: このチュートリアルではどの名前空間をインポートする必要がありますか?

A: HTML コンテンツを追加するコード ファイルで、ファイルの先頭に次の名前空間をインポートします。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### Q: ドキュメント ディレクトリと出力ファイルのパスを指定するにはどうすればよいですか?

 A: コード内で次の行を見つけます。`string dataDir = "YOUR DOCUMENT DIRECTORY";`そして交換してください`"YOUR DOCUMENT DIRECTORY"`ドキュメントディレクトリへの実際のパスを置き換えます。

#### Q: Document オブジェクトを作成するにはどうすればよいですか?

 A: ステップ 4 では、新しいインスタンスを作成します。`Document`次のコード行を使用してオブジェクトを作成します。

```csharp
Document doc = new Document();
```

#### Q: ドキュメントにページを追加するにはどうすればよいですか?

 A: ステップ 5 では、`Add`の方法`Pages`コレクション：

```csharp
Page page = doc.Pages.Add();
```

#### Q: DOM を使用して HTML コンテンツを設定するにはどうすればよいですか?

 A: ステップ 6 では、`HtmlFragment`オブジェクトを作成し、目的の HTML コンテンツをそれに割り当てます。 HTML コンテンツが変数に割り当てられます。`title`:

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

#### Q: HTML コンテンツのスタイルを上書きするにはどうすればよいですか?

 A: ステップ 7 では、HTML コンテンツのスタイルを上書きします。`TextState`のプロパティ`HtmlFragment`物体。たとえば、フォント ファミリーを「Arial」に変更し、フォント サイズを 20 に設定できます。

```csharp
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

#### Q: HTML コンテンツの余白を調整できますか?

A: はい、ステップ 8 で、必要に応じて HTML フラグメントの上下の余白を調整できます。

```csharp
title.Margin.Bottom = 10;
title.Margin.Top = 400;
```

#### Q: PDF ドキュメントに HtmlFragment を追加するにはどうすればよいですか?

 A: ステップ 9 で、`HtmlFragment`物体 （`title`) ページの段落コレクションに追加します。

```csharp
page.Paragraphs.Add(title);
```

#### Q: 作成された PDF ドキュメントを保存するにはどうすればよいですか?

 A: HTML コンテンツを追加し、そのスタイルをカスタマイズした後、`Save`の方法`Document` PDF ドキュメントを保存するオブジェクト:

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

#### Q: このチュートリアルの重要なポイントは何ですか?

A: このチュートリアルに従うことで、Aspose.PDF for .NET のドキュメント オブジェクト モデル (DOM) を使用して HTML コンテンツを組み込む方法を学習したことになります。さらに、スタイルを上書きして、結果の PDF ドキュメント内の HTML コンテンツの外観を調整できるようになりました。