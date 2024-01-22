---
title: PDF ファイルにテキスト枠を追加する
linktitle: PDF ファイルにテキスト枠を追加する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイルにテキスト境界線を追加する方法を学びます。
type: docs
weight: 70
url: /ja/net/programming-with-text/add-text-border/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイルにテキスト境界線を追加するプロセスを説明します。提供されている C# ソース コードは、必要な手順を示しています。

## 要件
始める前に、以下のものがあることを確認してください。

- マシンにインストールされている Visual Studio またはその他の C# コンパイラー。
- .NET ライブラリ用の Aspose.PDF。 Aspose の公式 Web サイトからダウンロードするか、NuGet などのパッケージ マネージャーを使用してインストールできます。

## ステップ 1: プロジェクトをセットアップする
1. 好みの開発環境で新しい C# プロジェクトを作成します。
2. Aspose.PDF for .NET ライブラリへの参照を追加します。

## ステップ 2: 必要な名前空間をインポートする
テキスト境界線を追加するコード ファイルで、ファイルの先頭に次の using ディレクティブを追加します。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## ステップ 3: ドキュメント ディレクトリを設定する
コード内で、次の行を見つけます。`string dataDir = "YOUR DOCUMENT DIRECTORY";`そして交換してください`"YOUR DOCUMENT DIRECTORY"`ドキュメントが保存されているディレクトリへのパスを置き換えます。

## ステップ 4: 新しい Document オブジェクトを作成する
新しいインスタンスを作成する`Document`次のコード行を追加してオブジェクトを作成します。

```csharp
Document pdfDocument = new Document();
```

## ステップ 5: ドキュメントにページを追加する
を使用してドキュメントに新しいページを追加します。`Add`の方法`Pages`コレクション。提供されたコードでは、新しいページが変数に割り当てられます。`pdfPage`.

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## ステップ 6: TextFragment を作成する
を作成します`TextFragment`オブジェクトを指定し、必要なテキストを入力します。を使用してテキストフラグメントの位置を設定します。`Position`財産。提供されたコードでは、テキストは「メイン テキスト」に設定され、ページ上の (100, 600) に配置されます。

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

## ステップ 7: テキストのプロパティを設定する
フォント サイズ、フォント タイプ、背景色、前景色などのテキスト プロパティをカスタマイズします。提供されたコードでは、フォント サイズ、フォント、背景色、前景色、ストローク色などのプロパティがテキスト フラグメントに設定されます。

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

## ステップ 8: テキスト境界線を有効にする
テキスト境界線を有効にするには、`DrawTextRectangleBorder`テキストフラグメントのプロパティ`TextState`に`true`.

```csharp
textFragment.TextState.DrawTextRectangleBorder = true;
```

## ステップ 9: TextFragment をページに追加する
使用`TextBuilder`追加するクラス`TextFragment`ページに反対します。

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

## ステップ 10: PDF ドキュメントを保存する
PDF ドキュメントを保存するには、`Save`の方法`Document`物体。手順 3 で設定した出力ファイルのパスを指定します。

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

### Aspose.PDF for .NET を使用したテキスト境界線の追加のサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//新しいドキュメントオブジェクトを作成する
Document pdfDocument = new Document();
//特定のページを取得する
Page pdfPage = (Page)pdfDocument.Pages.Add();
//テキストフラグメントを作成する
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
//テキストのプロパティを設定する
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
//テキスト四角形の周囲に境界線 (ストローク) を描画するための StrakingColor プロパティを設定します。
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
// DrawTextRectangleBorder プロパティ値を true に設定します。
textFragment.TextState.DrawTextRectangleBorder = true;
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
//文書を保存する
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

## 結論
Aspose.PDF for .NET を使用して PDF ドキュメントにテキスト境界線を追加することに成功しました。作成された PDF ファイルは、指定した出力ファイル パスに表示されます。

### よくある質問

#### Q: このチュートリアルの主な焦点は何ですか?

A: このチュートリアルでは、Aspose.PDF for .NET ライブラリを使用して PDF ファイルにテキスト境界線を追加するプロセスを説明します。提供されている C# ソース コードは、これを実現するために必要な手順を示しています。

#### Q: このチュートリアルではどの名前空間をインポートする必要がありますか?

A: テキスト境界線を追加するコード ファイルで、ファイルの先頭に次の名前空間をインポートします。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### Q: ドキュメント ディレクトリを指定するにはどうすればよいですか?

 A: コード内で次の行を見つけます。`string dataDir = "YOUR DOCUMENT DIRECTORY";`そして交換してください`"YOUR DOCUMENT DIRECTORY"`ドキュメントディレクトリへの実際のパスを置き換えます。

#### Q: Document オブジェクトを作成するにはどうすればよいですか?

 A: ステップ 4 では、新しいインスタンスを作成します。`Document`次のコード行を使用してオブジェクトを作成します。

```csharp
Document pdfDocument = new Document();
```

#### Q: ドキュメントにページを追加するにはどうすればよいですか?

 A: ステップ 5 では、`Add`の方法`Pages`コレクション：

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

#### Q: TextFragment を作成し、その位置を設定するにはどうすればよいですか?

 A: ステップ 6 では、`TextFragment`オブジェクトを選択し、`Position`財産：

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

#### Q: テキストの境界線を含むテキストのプロパティをカスタマイズするにはどうすればよいですか?

A: ステップ 7 では、フォント サイズ、フォント タイプ、背景色、前景色、テキスト枠などのさまざまなテキスト プロパティをカスタマイズします。

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
textFragment.TextState.DrawTextRectangleBorder = true;
```

#### Q: TextFragment を PDF ドキュメントに追加するにはどうすればよいですか?

 A: ステップ 9 では、`TextBuilder`追加するクラス`TextFragment`ページに対する反対:

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

#### Q: 作成された PDF ドキュメントを保存するにはどうすればよいですか?

 A: 枠線付きのテキストを追加した後、`Save`の方法`Document` PDF ドキュメントを保存するオブジェクト:

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

#### Q: このチュートリアルの主なポイントは何ですか?

A: このチュートリアルに従うことで、Aspose.PDF for .NET を使用してテキスト境界線を追加して PDF ドキュメントを強化する方法を学習できました。これは、PDF ファイル内の特定のテキスト コンテンツを強調する場合に特に便利です。