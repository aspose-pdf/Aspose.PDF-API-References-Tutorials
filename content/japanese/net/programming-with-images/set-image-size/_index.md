---
title: PDF ファイルの画像サイズを設定する
linktitle: PDF ファイルの画像サイズを設定する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイル内の画像のサイズを設定するためのステップバイステップのガイド。
type: docs
weight: 270
url: /ja/net/programming-with-images/set-image-size/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイル内の画像のサイズを設定する方法を説明します。この操作を簡単に実行するには、次の手順に従います。

## 前提条件

始める前に、以下のものがあることを確認してください。

- Visual Studio またはその他の開発環境がインストールされ、構成されている。
- C# プログラミング言語の基本的な知識。
- .NET 用の Aspose.PDF ライブラリがインストールされています。 Aspose公式Webサイトからダウンロードできます。

## ステップ 1: PDF ドキュメントの作成

まず、次のコードを使用して新しい PDF ドキュメントを作成します。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//Document オブジェクトをインスタンス化する
Document doc = new Document();

// PDF ファイルのページのコレクションにページを追加します。
Aspose.Pdf.Page page = doc.Pages.Add();
```

## ステップ 2: 画像を追加しました

次に、PDF ドキュメントのページに画像を追加します。次のコードを使用します。

```csharp
//イメージインスタンスを作成する
Aspose.Pdf.Image img = new Aspose.Pdf.Image();

//画像の幅と高さをポイント単位で設定します
img. FixWidth = 100;
img. FixHeight = 100;

//画像タイプを不明 (Unknown) に設定します
img.FileType = Aspose.Pdf.ImageFileType.Unknown;

//画像ソースファイルへのパス
img.File = dataDir + "aspose-logo.jpg";

//ページの段落コレクションに画像を追加します
page.Paragraphs.Add(img);
```

必ず画像ソース ファイルへの正しいパスを指定してください。

## ステップ 3: ページのプロパティを設定する

最後に、幅や高さなどのページのプロパティを設定します。次のコードを使用します。

```csharp
//ページのプロパティを設定する
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
```

### Aspose.PDF for .NET を使用した画像サイズの設定のサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Documentオブジェクトをインスタンス化する
Document doc = new Document();
//PDF ファイルのページコレクションをページに追加
Aspose.Pdf.Page page = doc.Pages.Add();
//イメージインスタンスを作成する
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
//画像の幅と高さをポイント単位で設定します
img.FixWidth = 100;
img.FixHeight = 100;
//画像タイプをSVGとして設定します
img.FileType = Aspose.Pdf.ImageFileType.Unknown;
//ソースファイルのパス
img.File = dataDir + "aspose-logo.jpg";
page.Paragraphs.Add(img);
//ページのプロパティを設定する
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
dataDir = dataDir + "SetImageSize_out.pdf";
//結果の PDF ファイルを保存する
doc.Save(dataDir);
Console.WriteLine("\nImage size added successfully.\nFile saved at " + dataDir);
```

## 結論

おめでとうございます！ Aspose.PDF for .NET を使用して PDF ドキュメント内の画像のサイズを正常に設定できました。この方法を独自のプロジェクトに適用して、PDF ファイル内の画像のサイズを調整できるようになりました。

### PDFファイルの画像サイズ設定に関するFAQ

#### Q: Aspose.PDF for .NET を使用して PDF ドキュメント内の画像のサイズを設定する目的は何ですか?

A: PDF ドキュメント内の画像のサイズを設定する目的は、PDF に追加される画像の寸法を制御することです。これにより、PDF ファイル内の画像の外観とレイアウトを調整できます。

#### Q: PDF ドキュメントで画像のサイズを設定するプロセスはどのように機能しますか?

 A: このプロセスには、`Aspose.Pdf.Image`インスタンスを使用して幅と高さを指定します。`FixWidth`そして`FixHeight`プロパティを設定し、画像を PDF ドキュメントに追加します。さらに、画像を収容できるようにページ自体のサイズを設定できます。

#### Q: 画像のサイズをページ寸法の特定の割合に設定できますか?

A: 提供されたコードは、画像の絶対的な幅と高さをポイント単位で設定します。ページの寸法のパーセンテージに基づいて画像のサイズを設定する場合は、それに応じて寸法を計算し、それに応じてコードを調整する必要があります。

####  Q: の重要性は何ですか?`FileType` property when adding an image to the PDF document?

 A:`FileType`プロパティは、PDF ドキュメントに追加される画像のタイプを指定します。提供されたコードの値は、`Unknown`は、画像の種類が不明であることを示し、Aspose.PDF はファイル拡張子に基づいて画像の種類を判断しようとします。

#### Q: この方法を使用して、複数の画像を 1 つのページに追加できますか?

 A: はい、複数の画像を作成することで、1 つのページに複数の画像を追加できます。`Aspose.Pdf.Image`インスタンスを作成し、ページの段落コレクションに追加します。必要に応じて画像の位置やレイアウトを調整してください。

#### Q: ページ上に追加された画像の配置と配置を制御するにはどうすればよいですか?

 A: 追加した画像の配置と配置は、次のようなプロパティを使用して画像の座標とレイアウトを調整することで制御できます。`img.Left`, `img.Top`、および段落書式設定プロパティ。

####  Q: を使用してページのプロパティを設定する目的は何ですか?`page.PageInfo.Width` and `page.PageInfo.Height`?

A: ページのプロパティを設定すると、ページ自体のサイズを定義できます。これにより、ページの寸法が、追加された画像やページ上にあるその他のコンテンツに確実に対応できるようになります。

#### Q: 同じ PDF ドキュメント内の異なる画像に異なるサイズを設定できますか?

 A: はい、別々に作成することで、異なる画像に異なるサイズを設定できます。`Aspose.Pdf.Image`インスタンスと調整`FixWidth`, `FixHeight`、および各画像の配置プロパティ。

#### Q: この方法を自分のプロジェクトに統合して PDF ファイルの画像サイズを設定するにはどうすればよいですか?

A: このメソッドをプロジェクトに統合するには、説明されている手順に従い、必要に応じてコードを変更します。この方法を使用すると、アプリケーションの要件に基づいて特定のサイズの画像を PDF ドキュメントに追加できます。