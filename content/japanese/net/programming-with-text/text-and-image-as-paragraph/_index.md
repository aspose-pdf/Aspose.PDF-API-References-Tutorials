---
title: PDF ファイルの段落としてのテキストと画像
linktitle: PDF ファイルの段落としてのテキストと画像
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して、PDF ファイルにテキストと画像をインライン段落として追加する方法を学びます。
type: docs
weight: 530
url: /ja/net/programming-with-text/text-and-image-as-paragraph/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイルにテキストと画像をインライン段落として追加する方法について説明します。提供されている C# ソース コードは、プロセスを段階的に示しています。

## 前提条件

チュートリアルを進める前に、次のものが揃っていることを確認してください。

- C# プログラミング言語の基本的な知識。
- Aspose.PDF for .NET ライブラリがインストールされています。 Aspose Web サイトから入手するか、NuGet を使用してプロジェクトにインストールできます。

## ステップ 1: プロジェクトをセットアップする

まず、好みの統合開発環境 (IDE) で新しい C# プロジェクトを作成し、Aspose.PDF for .NET ライブラリへの参照を追加します。

## ステップ 2: 必要な名前空間をインポートする

C# ファイルの先頭に次の using ディレクティブを追加して、必要な名前空間をインポートします。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Drawing;
```

## ステップ 3: ドキュメント ディレクトリへのパスを設定する

を使用してドキュメント ディレクトリへのパスを設定します。`dataDir`変数：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

交換する`"YOUR DOCUMENT DIRECTORY"`ドキュメントディレクトリへの実際のパスを置き換えます。

## ステップ 4: 新しいドキュメントとページを作成する

新しいを作成します`Document`オブジェクトを作成し、そのページ コレクションにページを追加します。

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## ステップ 5: TextFragment を作成し、段落として追加する

を作成します`TextFragment`オブジェクトを取得し、それをページの段落コレクションに追加します。

```csharp
TextFragment text = new TextFragment("Hello World.. ");
page.Paragraphs.Add(text);
```

## ステップ 6: 画像をインライン段落として追加する

を作成します`Aspose.Pdf.Image`オブジェクトを作成し、前の段落の直後に表示されるようにインライン段落として設定します。

```csharp
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
image.IsInLineParagraph = true;
image.File = dataDir + "aspose-logo.jpg";
image.FixHeight = 30; //オプション: 画像の高さを設定します
image.FixWidth = 100; //オプション: 画像の幅を設定します
page.Paragraphs.Add(image);
```

交換する`"aspose-logo.jpg"`実際の画像ファイル名を使用して、必要に応じてオプションの画像の高さと幅を調整します。

## ステップ 7: 別の TextFragment をインライン段落として追加する

再初期化します`TextFragment`異なるコンテンツを含むオブジェクトをインライン段落として追加します。

```csharp
text = new TextFragment(" Hello Again..");
text.IsInLineParagraph = true;
page.Paragraphs.Add(text);
```

## ステップ 8: PDF ドキュメントを保存する

変更した PDF ドキュメントを保存します。

```csharp
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
```

必ず交換してください`"TextAndImageAsParagraph_out.pdf"`希望の出力ファイル名を付けます。

### Aspose.PDF for .NET を使用した段落としてのテキストと画像のサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ドキュメントインスタンスをインスタンス化する
Document doc = new Document();
//Document インスタンスのページ コレクションにページを追加します
Page page = doc.Pages.Add();
//TextFragmnetの作成
TextFragment text = new TextFragment("Hello World.. ");
//Pageオブジェクトの段落コレクションにテキストフラグメントを追加します。
page.Paragraphs.Add(text);
//イメージインスタンスを作成する
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
//画像をインライン段落として設定し、直後に表示されるようにします。
//前の段落オブジェクト (TextFragment)
image.IsInLineParagraph = true;
//画像ファイルのパスを指定する
image.File = dataDir + "aspose-logo.jpg";
//画像の高さの設定 (オプション)
image.FixHeight = 30;
//画像幅の設定 (オプション)
image.FixWidth = 100;
//ページオブジェクトの段落コレクションに画像を追加します
page.Paragraphs.Add(image);
//TextFragment オブジェクトを異なる内容で再初期化する
text = new TextFragment(" Hello Again..");
//TextFragment をインライン段落として設定する
text.IsInLineParagraph = true;
//新しく作成した TextFragment をページの段落コレクションに追加します
page.Paragraphs.Add(text);
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nText and image added successfully as an inline paragraphs.\nFile saved at " + dataDir);
```

## 結論

おめでとう！ Aspose.PDF for .NET を使用して、PDF ドキュメントにテキストと画像をインライン段落として追加する方法を学習しました。このチュートリアルでは、プロジェクトのセットアップから変更したドキュメントの保存までのステップバイステップのガイドを提供しました。このコードを独自の C# プロジェクトに組み込んで、PDF ファイル内のテキストと画像のレイアウトをカスタマイズできるようになりました。

### よくある質問

#### Q: 「PDF ファイルの段落としてのテキストと画像」チュートリアルの目的は何ですか?

A: 「PDF ファイルの段落としてのテキストと画像」チュートリアルは、Aspose.PDF for .NET を使用して PDF ドキュメント内にテキストと画像の両方をインライン段落として追加する方法をユーザーにガイドすることを目的としています。このチュートリアルでは、プロセスをデモンストレーションするための段階的な手順と C# コード サンプルが提供されます。

#### Q: このチュートリアルは、テキストと画像をインライン段落として追加する際にどのように役立ちますか?

A: このチュートリアルは、Aspose.PDF for .NET を使用してテキストと画像の両方を PDF ドキュメント内のインライン段落として組み込む方法をユーザーが理解するのに役立ちます。提供されている手順とコード例に従うことで、ユーザーはテキストと画像を組み合わせたカスタム レイアウトの PDF ファイルを作成できます。

#### Q: このチュートリアルに従うにはどのような前提条件が必要ですか?

A: チュートリアルを開始する前に、C# プログラミング言語の基本を理解しておく必要があります。さらに、Aspose.PDF for .NET ライブラリをインストールする必要があります。 Aspose Web サイトから入手するか、NuGet を使用してプロジェクトにインストールできます。

#### Q: このチュートリアルに従うようにプロジェクトを設定するにはどうすればよいですか?

A: まず、お好みの統合開発環境 (IDE) で新しい C# プロジェクトを作成し、Aspose.PDF for .NET ライブラリへの参照を追加します。これにより、PDF ドキュメント、テキストの断片、画像を操作するためのライブラリの機能を利用できるようになります。

#### Q: このチュートリアルを使用して、PDF に複数のテキストと画像の段落を追加できますか?

A: はい、提供されているコード サンプルを使用して、同じ PDF ドキュメント内にテキストと画像の両方の段落の複数のインスタンスを追加できます。このチュートリアルでは、インライン段落を作成して、テキストと画像のさまざまな組み合わせを簡単に含める方法を説明します。

#### Q: テキスト段落と画像の内容と外観を指定するにはどうすればよいですか?

 A: チュートリアルでは作成方法を示しています。`TextFragment`テキスト段落を表すオブジェクトと`Aspose.Pdf.Image`画像を表現するオブジェクト。提供されているコード サンプルを使用して、テキストと画像の両方の内容、サイズ、外観をカスタマイズできます。

#### Q: インライン段落のレイアウトを調整できますか?

 A: はい、インライン段落の位置、サイズ、ページ内での順序を制御することで、インライン段落のレイアウトを調整できます。このチュートリアルでは、次のようなインライン属性を設定する方法を示します。`IsInLineParagraph`、テキストと画像の段落のレイアウトを制御します。

#### Q: 変更した PDF ドキュメントを保存するにはどうすればよいですか?

 A: 変更した PDF ドキュメントを保存するには、`Save`の方法`Document`物体。このチュートリアルでは、結果の PDF ドキュメントを保存する方法を示すコード サンプルを提供します。