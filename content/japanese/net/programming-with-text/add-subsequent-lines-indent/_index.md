---
title: PDF ファイルに後続行のインデントを追加する
linktitle: PDF ファイルに後続行のインデントを追加する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイル内のテキストに後続の行インデントを追加する方法を学びます。
type: docs
weight: 60
url: /ja/net/programming-with-text/add-subsequent-lines-indent/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイル内のテキストに後続の行インデントを追加するプロセスについて説明します。提供されている C# ソース コードは、必要な手順を示しています。

## 要件
始める前に、以下のものがあることを確認してください。

- マシンにインストールされている Visual Studio またはその他の C# コンパイラー。
- .NET ライブラリ用の Aspose.PDF。 Aspose の公式 Web サイトからダウンロードするか、NuGet などのパッケージ マネージャーを使用してインストールできます。

## ステップ 1: プロジェクトをセットアップする
1. 好みの開発環境で新しい C# プロジェクトを作成します。
2. Aspose.PDF for .NET ライブラリへの参照を追加します。

## ステップ 2: 必要な名前空間をインポートする
後続の行のインデントを追加するコード ファイルで、ファイルの先頭に次の using ディレクティブを追加します。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## ステップ 3: ドキュメント ディレクトリを設定する
コード内で、次の行を見つけます。`string dataDir = "YOUR DOCUMENT DIRECTORY";`そして交換してください`"YOUR DOCUMENT DIRECTORY"`ドキュメントが保存されているディレクトリへのパスを置き換えます。

## ステップ 4: 新しい Document オブジェクトを作成する
新しいインスタンスを作成する`Document`次のコード行を追加してオブジェクトを作成します。

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

## ステップ 5: ドキュメントにページを追加する
を使用してドキュメントに新しいページを追加します。`Add`の方法`Pages`コレクション。提供されたコードでは、新しいページが変数に割り当てられます。`page`.

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

## ステップ 6: 後続の行をインデントした TextFragment を作成する
インスタンス化する`TextFragment`オブジェクトを指定し、必要なテキストを入力します。提供されたコードでは、テキストが変数に割り当てられます。`text` 。次に、初期化します`TextFormattingOptions`のために`TextFragment`そして、`SubsequentLinesIndent`価値。

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog." );
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
     SubsequentLinesIndent = 20
};
```

## ステップ 7: TextFragment をページに追加する
を追加します。`TextFragment`ページの段落コレクションに対するオブジェクト。

```csharp
page.Paragraphs.Add(text);
```

## ステップ 8: 追加の行についてステップ 6 と 7 を繰り返します。
同じインデントを持つ後続の行を追加するには、各行に対して手順 6 と 7 を繰り返します。必要に応じてテキストの内容を更新します。

```csharp
text = new Aspose.Pdf.Text.TextFragment("Line2");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line3");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line4");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line5");
page.Paragraphs.Add(text);
```

## ステップ 9: PDF ドキュメントを保存する
PDF ドキュメントを保存するには、`Save`の方法`Document`物体。出力ファイルのパスを指定します。

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Aspose.PDF for .NET を使用した後続行のインデントの追加のサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//新しいドキュメントオブジェクトを作成する
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = document.Pages.Add();
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog.");
//テキスト フラグメントの TextFormattingOptions を初期化し、SubsequentLinesIndent 値を指定します
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
	SubsequentLinesIndent = 20
};
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line2");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line3");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line4");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line5");
page.Paragraphs.Add(text);
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## 結論
Aspose.PDF for .NET を使用して、後続の行のインデントをテキストに追加することに成功しました。作成された PDF ファイルは、指定した出力ファイル パスに表示されます。

### よくある質問

#### Q: このチュートリアルの焦点は何ですか?

A: このチュートリアルでは、Aspose.PDF for .NET ライブラリを使用して PDF ファイル内のテキストに後続の行インデントを追加する方法についての包括的なガイドを提供します。これを実現するために必要な手順を示す C# ソース コードの例が含まれています。

#### Q: このチュートリアルではどの名前空間をインポートする必要がありますか?

A: 後続の行のインデントを追加するコード ファイルで、ファイルの先頭に次の名前空間をインポートします。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### Q: ドキュメント ディレクトリを指定するにはどうすればよいですか?

 A: コード内で次の行を見つけます。`string dataDir = "YOUR DOCUMENT DIRECTORY";`そして交換してください`"YOUR DOCUMENT DIRECTORY"`ドキュメントディレクトリへの実際のパスを置き換えます。

#### Q: Document オブジェクトを作成するにはどうすればよいですか?

 A: ステップ 4 では、新しいインスタンスを作成します。`Document`次のコード行を使用してオブジェクトを作成します。

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

#### Q: ドキュメントにページを追加するにはどうすればよいですか?

 A: ステップ 5 では、`Add`の方法`Pages`コレクション：

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

#### Q: テキストに後続の行のインデントを追加するにはどうすればよいですか?

 A: ステップ 6 では、`TextFragment`オブジェクトを選択し、それに目的のテキストを割り当てます。それでは初期化をしていきます`TextFormattingOptions`のために`TextFragment`そして、`SubsequentLinesIndent`価値：

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("Your text here");
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
    SubsequentLinesIndent = 20
};
```

#### Q: TextFragment を PDF ドキュメントに追加するにはどうすればよいですか?

 A: ステップ 7 で、`TextFragment`物体 （`text`) ページの段落コレクションに追加します。

```csharp
page.Paragraphs.Add(text);
```

#### Q: 追加の行に対してこのプロセスを繰り返すことはできますか?

 A: はい、ステップ 8 で、新しい行を作成することで、同じインデントを持つ追加の行に対してこのプロセスを繰り返すことができます。`TextFragment`オブジェクトを作成し、ページの段落コレクションに追加します。

#### Q: 作成された PDF ドキュメントを保存するにはどうすればよいですか?

 A: 後続の行をインデントしてテキストを追加した後、`Save`の方法`Document` PDF ドキュメントを保存するオブジェクト:

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

#### Q: このチュートリアルの重要なポイントは何ですか?

A: このチュートリアルに従うことで、Aspose.PDF for .NET を使用して後続の行のインデントを追加し、PDF ドキュメント内のテキストの読みやすさを向上させる方法を学習できました。この手法は、さまざまな種類のドキュメントやレポートに役立ちます。