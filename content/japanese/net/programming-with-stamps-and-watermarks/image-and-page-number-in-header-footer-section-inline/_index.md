---
title: ヘッダー フッター セクションのインラインの画像とページ番号
linktitle: ヘッダー フッター セクションのインラインの画像とページ番号
second_title: Aspose.PDF for .NET API リファレンス
description: このステップバイステップ ガイドでは、Aspose.PDF for .NET を使用して PDF のヘッダー セクションに画像とページ番号をインラインで追加する方法を学習します。
type: docs
weight: 120
url: /ja/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
## 導入

Aspose.PDF for .NET は、PDF ファイルの操作と生成のための広範な機能を提供する強力なツールです。画像の追加、ヘッダーとフッターのカスタマイズ、テキストの管理など、必要なことは Aspose.PDF にすべてお任せください。このチュートリアルでは、PDF ドキュメントのヘッダーまたはフッターに画像とページ番号をインラインで追加する方法を説明します。早速、プロセスをステップごとに詳しく見ていきましょう。

## 前提条件

コードに進む前に、必要な準備がすべて整っていることを確認しましょう。

-  Aspose.PDF for .NET: 最新バージョンをダウンロードしてください。[Aspose PDF ダウンロード ページ](https://releases.aspose.com/pdf/net/).
- 開発環境: Visual Studio などの C# IDE が必要です。
- ライセンス: まだライセンスを持っていない場合は、[一時ライセンスはこちら](https://purchase.aspose.com/temporary-license/)または、[Aspose ストア](https://purchase.aspose.com/buy).

前提条件が整いましたので、始めましょう。

## パッケージのインポート

コーディングを始める前に、必要な名前空間をインポートしてください。

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

これらのパッケージを使用すると、PDF ファイルやテキストの操作が可能になります。

## ステップ1: ドキュメントディレクトリを設定する

最初に行う必要があるのは、PDF ファイルを保存するディレクトリへのパスを定義することです。このパスは、プロジェクトのフォルダーまたはマシン上の任意の場所にカスタマイズできます。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

この変数は、ドキュメントが保存される場所を保持します。`"YOUR DOCUMENT DIRECTORY"`実際のパスを使用します。

## ステップ2: PDFドキュメントをインスタンス化する

このステップでは、`Aspose.Pdf.Document`オブジェクト。このオブジェクトは PDF ファイルのバックボーンとして機能します。

```csharp
//空のコンストラクタを呼び出してDocumentオブジェクトをインスタンス化する
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

ここでは、後でコンテンツを追加できる空の PDF ファイルを作成しています。

## ステップ3: PDFにページを追加する

PDF には、ヘッダー、フッター、コンテンツを追加できるページが少なくとも 1 つ必要です。ドキュメントに空白ページを追加してみましょう。

```csharp
// Pdfオブジェクトにページを作成する
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

電話をかける`pdf1.Pages.Add()`ドキュメントに新しいページが追加され、ヘッダーとフッターをカスタマイズできるようになります。

## ステップ4: ヘッダーを作成して設定する

次に、ドキュメントのヘッダーを作成します。ここで、テキスト、画像、ページ番号を追加します。

```csharp
//ドキュメントのヘッダーセクションを作成する
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();
//PDFファイルのヘッダーを設定する
page.Header = header;
```

私たちは`HeaderFooter`オブジェクトに割り当てて`Header`ページのプロパティを設定して、ヘッダーに追加したものがすべてページの上部に表示されるようにします。

## ステップ5: ヘッダーにインラインテキストを追加する

テキストを追加するのは、`TextFragment`プロパティを指定します。ヘッダーに色付きのテキストを追加してみましょう。

```csharp
//テキストオブジェクトを作成する
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");
//色を指定する
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;
```

このステップでは、`TextFragment`「Aspose.Pdfは堅牢なコンポーネントです」という内容で、色を青に設定します。`IsInLineParagraph`プロパティはテキストがインラインであることを保証します。つまり、テキストは他の要素 (画像や追加テキストなど) と同じ行に表示されます。

## ステップ6: ヘッダーにインライン画像を挿入する

ヘッダーを視覚的に魅力的にするには、テキストにインラインで画像を追加できます。会社のロゴやその他のグラフィックを使用できます。

```csharp
//セクションに画像オブジェクトを作成する
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
//画像ファイルのパスを設定する
image1.File = dataDir + "aspose-logo.jpg";
//画像の幅を設定する情報
image1.FixWidth = 50;
image1.FixHeight = 20;
//seg1 の InlineParagraph が画像であることを示します。
image1.IsInLineParagraph = true;
```

ここでは、ヘッダーに画像を追加するために、`Image`オブジェクトを作成し、パスを設定し、幅と高さを調整します。`IsInLineParagraph`画像がテキストと揃うようにします。

## ステップ 7: ヘッダーを完成させるためにインラインテキストを追加する

インライン ヘッダーを完成させるために、さらにテキストを追加してみましょう。

```csharp
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

この部分では、別の`TextFragment`コンテンツに「Pty Ltd.」を追加し、色を栗色に設定します。テキスト フラグメントと画像の両方がヘッダーに追加されます。

## ステップ8: PDFを保存する

ヘッダーを設定したら、PDF を保存します。

```csharp
// PDFを保存する
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

の`Save`メソッドは、最終的な PDF ファイルを指定された場所に書き込みます。

## 結論

おめでとうございます。Aspose.PDF for .NET を使用して、PDF ドキュメントのヘッダーに画像とテキストを正常に追加できました。このチュートリアルでは、ドキュメントの作成、ページの追加、ヘッダーの挿入、テキストや画像などのインライン コンテンツの配置など、基本的な手順について説明しました。Aspose.PDF を使用すると、ヘッダー、フッター、複雑なコンテンツの操作など、PDF を驚くほど柔軟に管理できます。 

## よくある質問

### ヘッダーにもページ番号を追加できますか?
はい！ページ番号を簡単に追加できます。`TextFragment`クラスを作成し、必要に応じてフォーマットします。インライン コンテンツとしてヘッダー セクションに挿入するだけです。

### ヘッダーに背景画像を設定するにはどうすればよいですか?
あなたは`BackgroundImage`の財産`HeaderFooter`背景画像を設定するクラス。ただし、これはインライン コンテンツではなく、ヘッダー領域全体をカバーします。

### JPEG以外の画像形式も使用できますか？
もちろんです! Aspose.PDF は、PNG、BMP、GIF などのさまざまな画像形式をサポートしています。

### ヘッダー内のテキストのフォントをカスタマイズできますか?
はい、`TextState`テキストのフォント、サイズ、スタイルを変更するオブジェクト。

### Aspose.PDF for .NET を使用するにはライセンスが必要ですか?
はい、Aspose.PDFは実稼働で使用するにはライセンスが必要ですが、[無料トライアルはこちら](https://releases.aspose.com/).