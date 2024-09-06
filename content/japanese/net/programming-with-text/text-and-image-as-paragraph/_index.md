---
title: PDF ファイル内の段落としてのテキストと画像
linktitle: PDF ファイル内の段落としてのテキストと画像
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して、PDF ファイルにインライン段落としてテキストと画像を追加する方法を学習します。
type: docs
weight: 530
url: /ja/net/programming-with-text/text-and-image-as-paragraph/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して、PDF ファイルにテキストと画像をインライン段落として追加する方法について説明します。提供されている C# ソース コードでは、プロセスを段階的に示しています。

## 前提条件

チュートリアルを進める前に、次のものを用意してください。

- C# プログラミング言語に関する基本的な知識。
- Aspose.PDF for .NET ライブラリがインストールされています。Aspose Web サイトから入手するか、NuGet を使用してプロジェクトにインストールできます。

## ステップ1: プロジェクトを設定する

まず、好みの統合開発環境 (IDE) で新しい C# プロジェクトを作成し、Aspose.PDF for .NET ライブラリへの参照を追加します。

## ステップ2: 必要な名前空間をインポートする

必要な名前空間をインポートするには、C# ファイルの先頭に次の using ディレクティブを追加します。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Drawing;
```

## ステップ3: ドキュメントディレクトリへのパスを設定する

ドキュメントディレクトリへのパスを設定するには、`dataDir`変数：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

交換する`"YOUR DOCUMENT DIRECTORY"`ドキュメント ディレクトリへの実際のパスを入力します。

## ステップ4: 新しいドキュメントとページを作成する

新規作成`Document`オブジェクトを作成し、そのページ コレクションにページを追加します。

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## ステップ5: TextFragmentを作成し、段落として追加する

作成する`TextFragment`オブジェクトを作成し、それをページの段落コレクションに追加します。

```csharp
TextFragment text = new TextFragment("Hello World.. ");
page.Paragraphs.Add(text);
```

## ステップ6: インライン段落として画像を追加する

作成する`Aspose.Pdf.Image`オブジェクトを作成し、インライン段落として設定して、前の段落の直後に表示されるようにします。

```csharp
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
image.IsInLineParagraph = true;
image.File = dataDir + "aspose-logo.jpg";
image.FixHeight = 30; //オプション: 画像の高さを設定する
image.FixWidth = 100; //オプション: 画像の幅を設定する
page.Paragraphs.Add(image);
```

交換する`"aspose-logo.jpg"`実際の画像ファイル名を入力し、必要に応じてオプションの画像の高さと幅を調整します。

## ステップ7: インライン段落として別のTextFragmentを追加する

再初期化する`TextFragment`異なるコンテンツを持つオブジェクトを作成し、インライン段落として追加します。

```csharp
text = new TextFragment(" Hello Again..");
text.IsInLineParagraph = true;
page.Paragraphs.Add(text);
```

## ステップ8: PDF文書を保存する

変更した PDF ドキュメントを保存します。

```csharp
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
```

必ず交換してください`"TextAndImageAsParagraph_out.pdf"`希望する出力ファイル名を指定します。

### Aspose.PDF for .NET を使用したテキストと画像の段落としてのサンプル ソース コード 
```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ドキュメントインスタンスをインスタンス化する
Document doc = new Document();
//Documentインスタンスのページコレクションにページを追加する
Page page = doc.Pages.Add();
//TextFragmnet を作成する
TextFragment text = new TextFragment("Hello World.. ");
//Pageオブジェクトの段落コレクションにテキストフラグメントを追加する
page.Paragraphs.Add(text);
//イメージインスタンスを作成する
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
//画像をインライン段落として設定し、直後に表示されるようにする
//前の段落オブジェクト (TextFragment)
image.IsInLineParagraph = true;
//画像ファイルのパスを指定する
image.File = dataDir + "aspose-logo.jpg";
//画像の高さを設定する（オプション）
image.FixHeight = 30;
//画像の幅を設定する（オプション）
image.FixWidth = 100;
//ページオブジェクトの段落コレクションに画像を追加する
page.Paragraphs.Add(image);
//異なる内容で TextFragment オブジェクトを再初期化する
text = new TextFragment(" Hello Again..");
//TextFragment をインライン段落として設定する
text.IsInLineParagraph = true;
//新しく作成した TextFragment をページの段落コレクションに追加します。
page.Paragraphs.Add(text);
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nText and image added successfully as an inline paragraphs.\nFile saved at " + dataDir);
```

## 結論

おめでとうございます! Aspose.PDF for .NET を使用して、PDF ドキュメントにテキストと画像をインライン段落として追加する方法を学習しました。このチュートリアルでは、プロジェクトのセットアップから変更したドキュメントの保存まで、ステップ バイ ステップのガイドを提供しました。これで、このコードを独自の C# プロジェクトに組み込んで、PDF ファイル内のテキストと画像のレイアウトをカスタマイズできます。

### よくある質問

#### Q: 「PDF ファイル内の段落としてのテキストと画像」チュートリアルの目的は何ですか?

A: 「PDF ファイル内の段落としてのテキストと画像」チュートリアルは、Aspose.PDF for .NET を使用して、PDF ドキュメント内にインライン段落としてテキストと画像の両方を追加する方法をユーザーに説明することを目的としています。このチュートリアルでは、プロセスを示す手順ごとの手順と C# コード サンプルが提供されます。

#### Q: このチュートリアルは、テキストや画像をインライン段落として追加する際にどのように役立ちますか?

A: このチュートリアルは、Aspose.PDF for .NET を使用して、テキストと画像の両方を PDF ドキュメント内のインライン段落として組み込む方法をユーザーが理解するのに役立ちます。提供されている手順とコード例に従うことで、ユーザーはテキストと画像を組み合わせたカスタム レイアウトの PDF ファイルを作成できます。

#### Q: このチュートリアルを実行するために必要な前提条件は何ですか?

A: チュートリアルを始める前に、C# プログラミング言語の基礎を理解しておく必要があります。また、Aspose.PDF for .NET ライブラリがインストールされている必要があります。Aspose Web サイトから入手するか、NuGet を使用してプロジェクトにインストールできます。

#### Q: このチュートリアルに従うためにプロジェクトを設定するにはどうすればよいですか?

A: まず、お好みの統合開発環境 (IDE) で新しい C# プロジェクトを作成し、Aspose.PDF for .NET ライブラリへの参照を追加します。これにより、ライブラリの機能を利用して PDF ドキュメント、テキスト フラグメント、および画像を操作できるようになります。

#### Q: このチュートリアルを使用して、PDF に複数のテキストと画像の段落を追加できますか?

A: はい、提供されているコード サンプルを使用して、同じ PDF ドキュメント内にテキストと画像の段落の複数のインスタンスを追加できます。このチュートリアルでは、インライン段落を作成し、テキストと画像のさまざまな組み合わせを簡単に含める方法を説明します。

#### Q: テキスト段落と画像の内容と外観を指定するにはどうすればよいですか?

 A: チュートリアルでは作成方法を説明します`TextFragment`テキスト段落を表すオブジェクトと`Aspose.Pdf.Image`オブジェクトを使用して画像を表します。提供されているコード サンプルを使用して、テキストと画像の両方のコンテンツ、寸法、外観をカスタマイズできます。

#### Q: インライン段落のレイアウトを調整できますか?

 A: はい、インライン段落の配置、寸法、ページ内の順序を制御することで、インライン段落のレイアウトを調整できます。チュートリアルでは、次のようなインライン属性を設定する方法を説明します。`IsInLineParagraph`、テキストと画像の段落のレイアウトを制御します。

#### Q: 変更した PDF ドキュメントを保存するにはどうすればよいですか?

 A: 変更したPDF文書を保存するには、`Save`方法の`Document`オブジェクト。このチュートリアルでは、生成された PDF ドキュメントを保存する方法を示すコード サンプルを提供します。