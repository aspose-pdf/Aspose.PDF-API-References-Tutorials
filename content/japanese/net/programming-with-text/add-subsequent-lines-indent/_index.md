---
title: PDF ファイルで後続の行にインデントを追加する
linktitle: PDF ファイルで後続の行にインデントを追加する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイル内のテキストに後続の行のインデントを追加する方法を学習します。
type: docs
weight: 60
url: /ja/net/programming-with-text/add-subsequent-lines-indent/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイル内のテキストに後続の行のインデントを追加するプロセスについて説明します。提供されている C# ソース コードは、必要な手順を示しています。

## 要件
始める前に、次のものがあることを確認してください。

- マシンにインストールされている Visual Studio またはその他の C# コンパイラ。
- Aspose.PDF for .NET ライブラリ。公式 Aspose Web サイトからダウンロードするか、NuGet などのパッケージ マネージャーを使用してインストールできます。

## ステップ1: プロジェクトを設定する
1. 好みの開発環境で新しい C# プロジェクトを作成します。
2. Aspose.PDF for .NET ライブラリへの参照を追加します。

## ステップ2: 必要な名前空間をインポートする
後続の行のインデントを追加するコード ファイルで、ファイルの先頭に次の using ディレクティブを追加します。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## ステップ3: ドキュメントディレクトリを設定する
コード内で、次の行を見つけます。`string dataDir = "YOUR DOCUMENT DIRECTORY";`置き換えて`"YOUR DOCUMENT DIRECTORY"`ドキュメントが保存されているディレクトリへのパスを指定します。

## ステップ4: 新しいDocumentオブジェクトを作成する
新しいインスタンスを作成する`Document`次のコード行を追加してオブジェクトを作成します。

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

## ステップ5: ドキュメントにページを追加する
ドキュメントに新しいページを追加するには、`Add`方法の`Pages`コレクション。提供されたコードでは、新しいページが変数に割り当てられます`page`.

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

## ステップ6: 後続の行をインデントしたTextFragmentを作成する
インスタンス化する`TextFragment`オブジェクトを作成し、必要なテキストを入力します。提供されたコードでは、テキストは変数に割り当てられます`text`次に初期化します`TextFormattingOptions`のために`TextFragment`指定する`SubsequentLinesIndent`価値。

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog." );
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
     SubsequentLinesIndent = 20
};
```

## ステップ7: TextFragmentをページに追加する
追加する`TextFragment`ページの段落コレクションへのオブジェクト。

```csharp
page.Paragraphs.Add(text);
```

## ステップ8: 追加の行については、ステップ6と7を繰り返します。
同じインデントを持つ後続の行を追加するには、各行に対して手順 6 と 7 を繰り返します。必要に応じてテキスト コンテンツを更新します。

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

## ステップ9: PDF文書を保存する
PDF文書を保存するには、`Save`方法の`Document`オブジェクト。出力ファイルのパスを指定します。

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Aspose.PDF for .NET を使用して後続の行にインデントを追加するためのサンプル ソース コード 
```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//新しいドキュメントオブジェクトを作成する
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = document.Pages.Add();
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog.");
//テキストフラグメントの TextFormattingOptions を初期化し、SubsequentLinesIndent 値を指定します。
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
Aspose.PDF for .NET を使用して、テキストに後続の行のインデントを正常に追加しました。結果の PDF ファイルは、指定された出力ファイル パスにあります。

### よくある質問

#### Q: このチュートリアルの焦点は何ですか?

A: このチュートリアルでは、Aspose.PDF for .NET ライブラリを使用して PDF ファイル内のテキストに後続の行のインデントを追加する方法についての包括的なガイドを提供します。これを実現するために必要な手順を示す C# ソース コードの例が含まれています。

#### Q: このチュートリアルではどの名前空間をインポートする必要がありますか?

A: 後続の行のインデントを追加するコード ファイルで、ファイルの先頭に次の名前空間をインポートします。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### Q: ドキュメントディレクトリを指定するにはどうすればよいですか?

 A: コード内で次の行を見つけます`string dataDir = "YOUR DOCUMENT DIRECTORY";`置き換えて`"YOUR DOCUMENT DIRECTORY"`ドキュメント ディレクトリへの実際のパスを入力します。

#### Q: Document オブジェクトを作成するにはどうすればよいですか?

 A: ステップ4では、新しいインスタンスを作成します。`Document`次のコード行を使用してオブジェクトを作成します。

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

#### Q: ドキュメントにページを追加するにはどうすればよいですか?

 A: ステップ5では、`Add`方法の`Pages`コレクション：

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

#### Q: テキストに後続の行のインデントを追加するにはどうすればよいですか?

 A: ステップ6では、`TextFragment`オブジェクトを作成し、必要なテキストを割り当てます。次に、初期化します`TextFormattingOptions`のために`TextFragment`指定する`SubsequentLinesIndent`価値：

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("Your text here");
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
    SubsequentLinesIndent = 20
};
```

#### Q: TextFragment を PDF ドキュメントに追加するにはどうすればよいですか?

 A: ステップ7では、`TextFragment`物体 （`text`) をページの段落コレクションに追加します。

```csharp
page.Paragraphs.Add(text);
```

#### Q: 追加の行に対してこのプロセスを繰り返すことはできますか?

A: はい、ステップ8で、新しい行を作成して、同じインデントを持つ追加の行に対してこのプロセスを繰り返すことができます。`TextFragment`オブジェクトを抽出し、ページの段落コレクションに追加します。

#### Q: 生成された PDF ドキュメントをどのように保存しますか?

 A: 後続の行をインデントしてテキストを追加した後、`Save`方法の`Document` PDF ドキュメントを保存するオブジェクト:

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

#### Q: このチュートリアルから得られる重要なポイントは何ですか?

A: このチュートリアルでは、Aspose.PDF for .NET を使用して後続の行にインデントを追加することで、PDF ドキュメント内のテキストの読みやすさを向上させる方法を学習しました。この手法は、さまざまな種類のドキュメントやレポートに役立ちます。