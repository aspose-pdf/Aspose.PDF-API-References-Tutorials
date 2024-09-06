---
title: PDF ファイルの画像サイズを設定する
linktitle: PDF ファイルの画像サイズを設定する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイル内の画像のサイズを設定する手順ガイド。
type: docs
weight: 270
url: /ja/net/programming-with-images/set-image-size/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイル内の画像のサイズを設定する方法について説明します。この操作を簡単に実行するには、次の手順に従ってください。

## 前提条件

始める前に、次のものがあることを確認してください。

- Visual Studio またはその他の開発環境がインストールおよび構成されている。
- C# プログラミング言語に関する基本的な知識。
- .NET 用の Aspose.PDF ライブラリがインストールされています。Aspose の公式 Web サイトからダウンロードできます。

## ステップ1: PDFドキュメントの作成

まず、次のコードを使用して新しい PDF ドキュメントを作成します。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Documentオブジェクトをインスタンス化する
Document doc = new Document();

//PDFファイルのページコレクションにページを追加する
Aspose.Pdf.Page page = doc.Pages.Add();
```

## ステップ2: 画像を追加

次に、PDF ドキュメントのページに画像を追加します。次のコードを使用します。

```csharp
//イメージインスタンスを作成する
Aspose.Pdf.Image img = new Aspose.Pdf.Image();

//画像の幅と高さをポイント単位で設定します
img. FixWidth = 100;
img. FixHeight = 100;

//画像タイプを不明 (不明) に設定する
img.FileType = Aspose.Pdf.ImageFileType.Unknown;

//画像ソースファイルへのパス
img.File = dataDir + "aspose-logo.jpg";

//ページの段落コレクションに画像を追加する
page.Paragraphs.Add(img);
```

画像ソース ファイルへの正しいパスを必ず指定してください。

## ステップ3: ページプロパティの設定

最後に、幅や高さなどのページのプロパティを設定します。次のコードを使用します。

```csharp
//ページのプロパティを設定する
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
```

### Aspose.PDF for .NET を使用して画像サイズを設定するサンプル ソース コード 
```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Documentオブジェクトをインスタンス化する
Document doc = new Document();
//PDFファイルのページコレクションにページを追加する
Aspose.Pdf.Page page = doc.Pages.Add();
//イメージインスタンスを作成する
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
//画像の幅と高さをポイントで設定する
img.FixWidth = 100;
img.FixHeight = 100;
//画像タイプをSVGに設定する
img.FileType = Aspose.Pdf.ImageFileType.Unknown;
//ソースファイルのパス
img.File = dataDir + "aspose-logo.jpg";
page.Paragraphs.Add(img);
//ページのプロパティを設定する
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
dataDir = dataDir + "SetImageSize_out.pdf";
//結果のPDFファイルを保存する
doc.Save(dataDir);
Console.WriteLine("\nImage size added successfully.\nFile saved at " + dataDir);
```

## 結論

おめでとうございます！Aspose.PDF for .NET を使用して PDF ドキュメント内の画像のサイズを正常に設定できました。この方法を独自のプロジェクトに適用して、PDF ファイル内の画像のサイズを調整できます。

### PDF ファイルの画像サイズの設定に関する FAQ

#### Q: Aspose.PDF for .NET を使用して PDF ドキュメント内の画像のサイズを設定する目的は何ですか?

A: PDF ドキュメント内の画像のサイズを設定する目的は、PDF に画像を追加するときに画像のサイズを制御することです。これにより、PDF ファイル内の画像の外観とレイアウトを調整できます。

#### Q: PDF ドキュメントで画像のサイズを設定するプロセスはどのように機能しますか?

 A: このプロセスでは、`Aspose.Pdf.Image`インスタンスの幅と高さを指定するには、`FixWidth`そして`FixHeight`プロパティを設定してから、PDF ドキュメントに画像を追加します。また、画像に合わせてページ自体のサイズを設定することもできます。

#### Q: 画像のサイズをページ寸法の特定のパーセンテージに設定できますか?

A: 提供されているコードは、画像の絶対的な幅と高さをポイント単位で設定します。ページ寸法のパーセンテージに基づいて画像のサイズを設定する場合は、それに応じて寸法を計算し、それに応じてコードを調整する必要があります。

####  Q: の意義は何ですか？`FileType` property when adding an image to the PDF document?

 A:`FileType`プロパティはPDF文書に追加される画像の種類を指定します。提供されたコードでは、値`Unknown`画像の種類が不明であることを示しており、Aspose.PDF はファイル拡張子に基づいて画像の種類を判別しようとします。

#### Q: この方法を使用して、1 つのページに複数の画像を追加できますか?

 A: はい、複数の画像を作成することで、1つのページに複数の画像を追加できます。`Aspose.Pdf.Image`インスタンスを作成し、ページの段落コレクションに追加します。必要に応じて、画像の位置とレイアウトを調整してください。

#### Q: ページに追加された画像の配置と配置を制御するにはどうすればよいですか?

 A: 追加した画像の配置と配置は、次のようなプロパティを使用して画像の座標とレイアウトを調整することで制御できます。`img.Left`, `img.Top`、段落書式設定プロパティなど。

####  Q: ページプロパティを設定する目的は何ですか？`page.PageInfo.Width` and `page.PageInfo.Height`?

A: ページ プロパティを設定すると、ページ自体のサイズを定義できます。これにより、追加された画像やページ上のその他のコンテンツがページのサイズに適合するようになります。

#### Q: 同じ PDF ドキュメント内の異なる画像に異なるサイズを設定できますか?

 A: はい、別々の画像を作成することで、画像ごとに異なるサイズを設定できます。`Aspose.Pdf.Image`インスタンスと調整`FixWidth`, `FixHeight`、および各画像の配置プロパティ。

#### Q: この方法を自分のプロジェクトに統合して、PDF ファイルの画像サイズを設定するにはどうすればよいでしょうか?

A: この方法をプロジェクトに統合するには、概説した手順に従い、必要に応じてコードを変更します。この方法を使用すると、アプリケーションの要件に基づいて、特定のサイズの画像を PDF ドキュメントに追加できます。