---
title: PDF ファイルにテキスト枠線を追加する
linktitle: PDF ファイルにテキスト枠線を追加する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイルにテキスト境界線を追加する方法を学習します。
type: docs
weight: 70
url: /ja/net/programming-with-text/add-text-border/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイルにテキスト境界線を追加するプロセスについて説明します。提供されている C# ソース コードは、必要な手順を示しています。

## 要件
始める前に、次のものがあることを確認してください。

- マシンにインストールされている Visual Studio またはその他の C# コンパイラ。
- Aspose.PDF for .NET ライブラリ。公式 Aspose Web サイトからダウンロードするか、NuGet などのパッケージ マネージャーを使用してインストールできます。

## ステップ1: プロジェクトを設定する
1. 好みの開発環境で新しい C# プロジェクトを作成します。
2. Aspose.PDF for .NET ライブラリへの参照を追加します。

## ステップ2: 必要な名前空間をインポートする
テキスト境界線を追加するコード ファイルで、ファイルの先頭に次の using ディレクティブを追加します。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## ステップ3: ドキュメントディレクトリを設定する
コード内で、次の行を見つけます。`string dataDir = "YOUR DOCUMENT DIRECTORY";`置き換えて`"YOUR DOCUMENT DIRECTORY"`ドキュメントが保存されているディレクトリへのパスを指定します。

## ステップ4: 新しいDocumentオブジェクトを作成する
新しいインスタンスを作成する`Document`次のコード行を追加してオブジェクトを作成します。

```csharp
Document pdfDocument = new Document();
```

## ステップ5: ドキュメントにページを追加する
ドキュメントに新しいページを追加するには、`Add`方法の`Pages`コレクション。提供されたコードでは、新しいページが変数に割り当てられます`pdfPage`.

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## ステップ6: TextFragmentを作成する
作成する`TextFragment`オブジェクトを作成し、必要なテキストを入力します。テキストフラグメントの位置を`Position`プロパティ。提供されたコードでは、テキストは「メインテキスト」に設定され、ページ上の (100, 600) に配置されます。

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

## ステップ7: テキストプロパティを設定する
フォント サイズ、フォント タイプ、背景色、前景色などのテキスト プロパティをカスタマイズします。提供されているコードでは、テキスト フラグメントに対してフォント サイズ、フォント、背景色、前景色、ストロークの色などのプロパティが設定されています。

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

## ステップ8: テキストの境界線を有効にする
テキストの境界線を有効にするには、`DrawTextRectangleBorder`テキストフラグメントのプロパティ`TextState`に`true`.

```csharp
textFragment.TextState.DrawTextRectangleBorder = true;
```

## ステップ9: TextFragmentをページに追加する
使用`TextBuilder`クラスを追加する`TextFragment`ページにオブジェクトを追加します。

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

## ステップ10: PDF文書を保存する
PDF文書を保存するには、`Save`方法の`Document`オブジェクト。手順 3 で設定した出力ファイル パスを指定します。

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

### Aspose.PDF for .NET を使用してテキスト境界線を追加するためのサンプル ソース コード 
```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//新しいドキュメントオブジェクトを作成する
Document pdfDocument = new Document();
//特定のページを取得する
Page pdfPage = (Page)pdfDocument.Pages.Add();
//テキストフラグメントを作成
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
//テキストプロパティを設定する
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
//テキスト四角形の周囲に境界線（ストローク）を描画するためのStrokingColorプロパティを設定します。
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
// DrawTextRectangleBorderプロパティの値をtrueに設定する
textFragment.TextState.DrawTextRectangleBorder = true;
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
//文書を保存する
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

## 結論
Aspose.PDF for .NET を使用して PDF ドキュメントにテキスト境界線を正常に追加しました。結果の PDF ファイルは、指定した出力ファイル パスにあります。

### よくある質問

#### Q: このチュートリアルの主な焦点は何ですか?

A: このチュートリアルでは、Aspose.PDF for .NET ライブラリを使用して PDF ファイルにテキスト境界線を追加する手順を説明します。提供されている C# ソース コードは、これを実現するために必要な手順を示しています。

#### Q: このチュートリアルではどの名前空間をインポートする必要がありますか?

A: テキスト境界線を追加するコード ファイルで、ファイルの先頭に次の名前空間をインポートします。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### Q: ドキュメントディレクトリを指定するにはどうすればよいですか?

 A: コード内で次の行を見つけます`string dataDir = "YOUR DOCUMENT DIRECTORY";`置き換えて`"YOUR DOCUMENT DIRECTORY"`ドキュメント ディレクトリへの実際のパスを入力します。

#### Q: Document オブジェクトを作成するにはどうすればよいですか?

 A: ステップ4では、新しいインスタンスを作成します。`Document`次のコード行を使用してオブジェクトを作成します。

```csharp
Document pdfDocument = new Document();
```

#### Q: ドキュメントにページを追加するにはどうすればよいですか?

 A: ステップ5では、`Add`方法の`Pages`コレクション：

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

#### Q: TextFragment を作成してその位置を設定するにはどうすればよいですか?

 A: ステップ6では、`TextFragment`オブジェクトを作成し、ページ上の位置を設定します。`Position`財産：

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

#### Q: テキストの境界線を含むテキストのプロパティをカスタマイズするにはどうすればよいですか?

A: ステップ 7 では、フォント サイズ、フォント タイプ、背景色、前景色、テキストの境界線など、さまざまなテキスト プロパティをカスタマイズします。

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
textFragment.TextState.DrawTextRectangleBorder = true;
```

#### Q: TextFragment を PDF ドキュメントに追加するにはどうすればよいですか?

 A: ステップ9では、`TextBuilder`クラスを追加する`TextFragment`ページに異議を唱える:

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

#### Q: 生成された PDF ドキュメントをどのように保存しますか?

A: 枠線付きのテキストを追加した後、`Save`方法の`Document` PDF ドキュメントを保存するオブジェクト:

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

#### Q: このチュートリアルから得られる主な教訓は何ですか?

A: このチュートリアルでは、Aspose.PDF for .NET を使用してテキスト境界線を追加し、PDF ドキュメントを強化する方法を学習しました。これは、PDF ファイル内の特定のテキスト コンテンツを強調する場合に特に便利です。