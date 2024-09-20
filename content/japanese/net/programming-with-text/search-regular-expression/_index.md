---
title: PDF ファイル内の正規表現を検索する
linktitle: PDF ファイル内の正規表現を検索する
second_title: Aspose.PDF for .NET API リファレンス
description: このステップバイステップのチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイル内の正規表現を検索する方法を学びます。正規表現を使用して生産性を向上させます。
type: docs
weight: 440
url: /ja/net/programming-with-text/search-regular-expression/
---
## 導入

大きな PDF ドキュメントを扱う場合、日付、電話番号、その他の構造化データなどの特定のパターンや形式を検索することがあります。PDF を手動で調べるのは面倒ですよね。ここで、正規表現 (regex) が役立ちます。このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイル内で正規表現パターンを検索する方法について説明します。このガイドでは、各手順を順を追って説明し、.NET アプリケーションに簡単に実装できるようにします。

## 前提条件

ステップバイステップのチュートリアルに進む前に、準備しておく必要があるものを確認しましょう。

-  Aspose.PDF for .NET: このライブラリをインストールする必要があります。まだインストールしていない場合は、[ここからダウンロード](https://releases.aspose.com/pdf/net/).
- IDE: Visual Studio またはその他の C# 互換 IDE。
- .NET Framework: プロジェクトが適切なバージョンの .NET Framework で設定されていることを確認します。
- C# の基礎知識: このガイドは詳細ですが、C# の基本的な理解が役立ちます。

### パッケージのインポート

まず、Aspose.PDF for .NET から必要な名前空間をプロジェクトにインポートする必要があります。これらのパッケージは、PDF の操作や正規表現を使用した検索操作の実行に不可欠です。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

Aspose.PDF を使用して PDF ファイル内の正規表現を検索するプロセスを複数のステップに分解してみましょう。

## ステップ1: ドキュメントディレクトリを設定する

すべてのPDF操作は、文書がどこにあるかを指定することから始まります。PDFファイルへのパスを定義する必要があります。これは、`dataDir`変数。

### ステップ 1.1: ドキュメント パスを定義する

```csharp
// PDFドキュメントへのパスを定義する
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

交換する`"YOUR DOCUMENT DIRECTORY"`PDF ファイルへの実際のパスを入力します。この手順は、操作するファイルをコードに指定するため、非常に重要です。

### ステップ1.2: PDFドキュメントを開く

次に、PDF文書を`Document` Aspose.PDF からのクラス。

```csharp
//文書を開く
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
```

ここ、`"SearchRegularExpressionAll.pdf"`正規表現検索を実行するサンプル PDF ファイルです。

## ステップ2: TextFragmentAbsorberを設定する

ここで魔法が起こるのです！`TextFragmentAbsorber`クラスは、特定のパターンまたは正規表現に一致するテキストの断片をキャプチャするのに役立ちます。

正規表現を使用してパターンを見つけるようにアブソーバーを設定しましょう。この場合、「1999-2000」のような年のパターンを検索します。

```csharp
//正規表現に一致するすべてのフレーズを検索するTextAbsorberオブジェクトを作成します。
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // 1999-2000年のように
```

正規表現`\\d{4}-\\d{4}` 桁の数字の後にハイフンとさらに 4 桁の数字が続くパターンを検索します。これは、年の範囲でよく使用されます。

## ステップ3: 正規表現検索を有効にする

検索操作がパターンを正規表現として解釈するようにするには、`TextSearchOptions`クラス。

```csharp
//正規表現の使用を指定するためのテキスト検索オプションを設定します
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
```

設定`TextSearchOptions`に`true`アブソーバーがプレーンテキストではなく正規表現ベースの検索を使用することを保証します。

## ステップ4: テキストアブソーバーを受け入れる

この段階では、PDF文書にテキストアブソーバーを適用して検索操作を実行できるようにします。これは、`Accept`方法`Pages` PDF ドキュメントのオブジェクト。

```csharp
//すべてのページの吸収剤を受け入れる
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

このコマンドは、PDF のすべてのページを処理し、正規表現に一致するテキストを検索します。

## ステップ5: 結果を抽出して表示する

検索が完了したら、結果を抽出する必要があります。`TextFragmentAbsorber`これらの結果を`TextFragmentCollection`このコレクションをループして、一致する各テキスト フラグメントにアクセスし、表示することができます。

### ステップ5.1: 抽出されたテキストフラグメントを取得する

```csharp
//抽出されたテキストフラグメントを取得する
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

フラグメントを収集したので、それらをループして、テキスト、位置、フォントの詳細などの関連する詳細を表示します。

### ステップ5.2: フラグメントをループする

```csharp
//フラグメントをループする
foreach (TextFragment textFragment in textFragmentCollection)
{
    Console.WriteLine("Text : {0} ", textFragment.Text);
    Console.WriteLine("Position : {0} ", textFragment.Position);
    Console.WriteLine("XIndent : {0} ", textFragment.Position.XIndent);
    Console.WriteLine("YIndent : {0} ", textFragment.Position.YIndent);
    Console.WriteLine("Font - Name : {0}", textFragment.TextState.Font.FontName);
    Console.WriteLine("Font - IsAccessible : {0} ", textFragment.TextState.Font.IsAccessible);
    Console.WriteLine("Font - IsEmbedded : {0} ", textFragment.TextState.Font.IsEmbedded);
    Console.WriteLine("Font - IsSubset : {0} ", textFragment.TextState.Font.IsSubset);
    Console.WriteLine("Font Size : {0} ", textFragment.TextState.FontSize);
    Console.WriteLine("Foreground Color : {0} ", textFragment.TextState.ForegroundColor);
}
```

それぞれ`TextFragment`フォント サイズ、フォント名、位置などの詳細が印刷されます。これにより、テキストの検索が容易になるだけでなく、正確な書式設定と位置もわかります。

## 結論

これで完了です。正規表現を使用して PDF ファイル内のパターンを検索する機能は、特に日付、電話番号、類似のパターンなどの構造化テキストの場合に非常に強力です。Aspose.PDF for .NET は、このような操作を簡単にシームレスに実行する方法を提供します。これで、正規表現の力を活用して PDF テキスト検索を自動化し、ワークフローをより効率的にすることができます。

## よくある質問

### 1 つの PDF で複数のパターンを検索できますか?
はい、複数実行できます`TextFragmentAbsorber`同じ PDF 内に、それぞれ異なる正規表現パターンを持つオブジェクトが存在します。

### Aspose.PDF は大文字と小文字を区別しないパターンの検索をサポートしていますか?
もちろんです！`TextSearchOptions`検索で大文字と小文字を区別しないようにします。

### 検索できる PDF のサイズに制限はありますか?
厳密な制限はありませんが、PDF のサイズと正規表現パターンの複雑さに応じてパフォーマンスが異なる場合があります。

### PDF 内で見つかったテキストを強調表示できますか?
はい、Aspose.PDF では、アブソーバーを使用して見つかったテキストを強調表示したり、置き換えたりすることができます。

### パターンが見つからない場合、エラーをどのように処理すればよいですか?
一致するものが見つからない場合は、`TextFragmentCollection`空になります。結果をループする前に簡単なチェックを行うことで、このシナリオを処理できます。