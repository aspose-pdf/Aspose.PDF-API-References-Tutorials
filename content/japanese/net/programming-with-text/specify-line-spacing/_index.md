---
title: PDFファイル内の行間隔を指定する
linktitle: PDFファイル内の行間隔を指定する
second_title: Aspose.PDF for .NET API リファレンス
description: このステップバイステップ ガイドでは、Aspose.PDF for .NET を使用して PDF の行間隔を指定する方法を学習します。正確なテキスト書式設定を求める開発者に最適です。
type: docs
weight: 510
url: /ja/net/programming-with-text/specify-line-spacing/
---
## 導入

PDF ファイルの行間隔の制御に苦労したことはありませんか? テキストが詰め込まれすぎているように見えたり、思ったほど洗練されていないように見えたりしたことがあるかもしれません。このチュートリアルでは、Aspose.PDF for .NET を使用して PDF の行間隔を簡単に指定する方法を説明します。簡単なステップ バイ ステップ ガイドを使用して、空白の PDF からカスタム行間隔を含む PDF を作成します。これは、レポート、請求書、証明書などのドキュメントのテキスト レイアウトに精度が必要な場合に最適です。

## 前提条件

コードに進む前に、必要なものがすべて揃っていることを確認しましょう。

1.  Aspose.PDF for .NETがインストールされています。まだインストールされていない場合は、[Aspose.PDF ダウンロード ページ](https://releases.aspose.com/pdf/net/).
2. .NET 開発環境 (Visual Studio など)。
3. TrueTypeフォントファイル（`.ttf` ）を使用します。任意のフォントを使用できますが、このガイドでは`HPSimplified.TTF`フォント。
4. C# と PDF 操作に関する基本的な知識。

準備ができたら、必要なパッケージのインポートに進みましょう。

## パッケージのインポート

C# プロジェクトでは、PDF 機能を使用するために Aspose.PDF 名前空間をインポートする必要があります。手順は次のとおりです。

```csharp
using Aspose.Pdf.Text;
using System.IO;
```

これらの名前空間を使用すると、PDF ドキュメントを作成および操作できるほか、テキストの書式設定やフォント オプションを操作できます。

これを簡単な手順に分割して、簡単に実行できるようにします。各手順では、PDF の設定から行間隔の指定まで、プロセスの重要な部分に焦点を当てます。

## ステップ1: プロジェクトを設定し、ドキュメントディレクトリを定義する

最初に行う必要があるのは、ファイルの場所を定義することです。これにより、プログラムはフォントが見つかる場所と、結果の PDF を保存する場所を認識できるようになります。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string fontFile = dataDir + "HPSimplified.TTF";
```

このステップでは、`"YOUR DOCUMENT DIRECTORY"`ファイルを実際に保存する場所のパスを入力します。これがフォントファイルを置く場所になります（`HPSimplified.TTF`) と PDF が保存される場所を指定します。

## ステップ2: PDF文書を読み込む

ここで、新しい PDF ドキュメントを作成する必要があります。このガイドでは、空白のドキュメントから始めますが、必要に応じて既存の PDF を読み込むこともできます。

```csharp
Document doc = new Document();
```

これにより、新しい空の PDF ドキュメントが作成されます。簡単ですよね?

## ステップ3: テキストの書式設定オプションを設定する

ここで魔法が起こります。PDFに追加したいテキストの行間モードを指定します。Aspose.PDFにはいくつかのオプションがありますが、このガイドでは`LineSpacingMode.FullSize`これにより、行間隔が完全に確保されます。

```csharp
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
```

このコードは行間隔モードを`FullSize`適切な間隔でテキストが表示されるようにします。他にも次のようなオプションがあります。`Proportional`異なる間隔の動作が必要な場合は、今のところは`FullSize`.

## ステップ4: テキストフラグメントを作成する

ここで、PDF に配置される実際のテキストを作成します。このテキストは、定義した行間隔に従います。

```csharp
TextFragment textFragment = new TextFragment("Hello world");
```

文字列を含むテキストフラグメントを作成しました`"Hello world"`もちろん、このテキストは好きなようにカスタマイズできます。

## ステップ5: カスタムフォントをロードして適用する

テキストを目立たせるために、ファイルからカスタム TrueType フォントを読み込みます。この手順はオプションですが、PDF にプロフェッショナルなタッチを加えることができます。

```csharp
if (fontFile != "")
{
    using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
    {
        textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
```

ここでは、フォント ファイルをロードしてテキスト フラグメントに適用します。ファイル パスが有効な場合は、フォントが使用されます。そうでない場合は、既定のフォントが適用されます。

## ステップ6: テキストの位置と書式を設定する

次に、PDF 上のテキストを配置する必要があります。また、先ほど作成した書式設定オプションも適用します。

```csharp
textFragment.Position = new Position(100, 600);
textFragment.TextState.FormattingOptions = formattingOptions;
```

の`Position`メソッドは、テキストがページ上に表示される座標を設定します (この場合は、左から 100 単位、下から 600 単位)。行間隔モードなどの書式設定オプションは、ここに適用されます。

## ステップ7: PDFページにテキストを追加する

テキストの書式設定と配置が完了したら、それを PDF ドキュメントに追加します。

```csharp
var page = doc.Pages.Add();
page.Paragraphs.Add(textFragment);
```

このコードは、PDF ドキュメントに新しいページを作成し、そこにテキスト フラグメントを追加します。

## ステップ8: PDFを保存する

最後のステップに到達しました。すべての設定が完了したら、PDF を保存しましょう。

```csharp
dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
doc.Save(dataDir);
```

これにより、指定した行間隔で PDF が保存され、ファイルの準備が整います。

## 結論

これで完了です。Aspose.PDF for .NET を使用して、カスタムの行間隔を持つ PDF ドキュメントを作成しました。これは、PDF ファイルのあらゆる側面を制御できる強力なツールであり、これは実現可能なことのほんの一例にすぎません。テキストの配置から書式設定まで、可能性は無限です。

PDF 操作をさらに深く探求したい場合、Aspose.PDF には探索すべき豊富な機能が用意されています。ぜひ試して、ドキュメントで実行できることの限界を押し広げてください。

## よくある質問

### 行間隔を他のモードに合わせて調整できますか?  
はい、他のモードも使用できます。`Proportional`または`Fixed`ニーズに応じて。

### ファイルではなくシステムからフォントを読み込むことは可能ですか?  
はい、システムにインストールされたフォントを読み込むことができます。`FontRepository`.

### Aspose.PDF for .NET を他のファイル形式で使用できますか?  
もちろんです! Aspose.PDF for .NET は、XML、HTML など、さまざまな形式をサポートしています。

### Aspose.PDF for .NET を使用するにはライセンスが必要ですか?  
はい、完全な機能を使用するにはライセンスが必要です。ライセンスは取得できます[ここ](https://purchase.aspose.com/buy).

### 複数の段落の行間隔を設定するにはどうすればよいですか?  
申請できます`TextFormattingOptions`それぞれに`TextFragment`または`TextParagraph`複数の行または段落の間隔を制御します。