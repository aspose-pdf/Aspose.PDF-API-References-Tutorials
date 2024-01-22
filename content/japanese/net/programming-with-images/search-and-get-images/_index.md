---
title: PDF ファイル内の画像を検索して取得する
linktitle: PDF ファイル内の画像を検索して取得する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイル内の画像を検索して取得するためのステップバイステップ ガイド。
type: docs
weight: 260
url: /ja/net/programming-with-images/search-and-get-images/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイル内の画像を検索して取得する方法を説明します。この操作を簡単に実行するには、次の手順に従います。

## 前提条件

始める前に、以下のものがあることを確認してください。

- Visual Studio またはその他の開発環境がインストールされ、構成されている。
- C# プログラミング言語の基本的な知識。
- .NET 用の Aspose.PDF ライブラリがインストールされています。 Aspose公式Webサイトからダウンロードできます。

## ステップ 1: PDF ドキュメントをロードする

まず、次のコードを使用して PDF ドキュメントを読み込みます。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//文書を開く
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SearchAndGetImages.pdf");
```

PDF ドキュメントへの正しいパスを指定してください。

## ステップ 2: 画像の場所を検索する

PDF ドキュメント内の画像の場所を検索するには、次のコードを使用します。

```csharp
//画像の場所を検索する ImagePlacementAbsorber オブジェクトを作成します
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();

//文書のすべてのページに吸収体を受け入れます
doc.Pages.Accept(abs);
```

これにより、吸収体の画像の位置が収集されます。

## ステップ 3: 画像の場所を参照し、画像とそのプロパティを取得する

次に、収集された画像の場所を参照して、画像とそのプロパティを取得します。次のコードを使用します。

```csharp
foreach(ImagePlacement imagePlacement in abs.ImagePlacements)
{
     // ImagePlacement オブジェクトを使用して画像を取得する
     XImage image = imagePlacement.Image;

     //画像の場所のプロパティを表示する
     Console.Out.WriteLine("Image Width: " + imagePlacement.Rectangle.Width);
     Console.Out.WriteLine("Image Height: " + imagePlacement.Rectangle.Height);
     Console.Out.WriteLine("LLX of image: " + imagePlacement.Rectangle.LLX);
     Console.Out.WriteLine("LLY of image: " + imagePlacement.Rectangle.LLY);
     Console.Out.WriteLine("Horizontal image resolution: " + imagePlacement.Resolution.X);
     Console.Out.WriteLine("Vertical image resolution: " + imagePlacement.Resolution.Y);
}
```

これにより、すべての画像の場所が参照され、一致する画像が取得され、そのプロパティが表示されます。

### Aspose.PDF for .NET を使用した画像の検索と取得のサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開いた文書
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "SearchAndGetImages.pdf");
//画像配置検索を実行する ImagePlacementAbsorber オブジェクトを作成します
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
//すべてのページに吸収体を受け入れる
doc.Pages.Accept(abs);
//すべての ImagePlacement をループし、画像と ImagePlacement プロパティを取得します
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
	//ImagePlacement オブジェクトを使用して画像を取得する
	XImage image = imagePlacement.Image;
	//すべての配置の画像配置プロパティを表示する
	Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
	Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
	Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
	Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
	Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
	Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
}
```

## 結論

おめでとうございます！ Aspose.PDF for .NET を使用して PDF ドキュメント内の画像を正常に検索して取得しました。このメソッドを独自のプロジェクトに適用して、PDF ファイルから画像を抽出し、そのプロパティを取得できるようになりました。

### PDF ファイル内の画像の検索と取得に関する FAQ

#### Q: Aspose.PDF for .NET を使用して PDF ドキュメント内の画像を検索および取得する目的は何ですか?

A: PDF ドキュメント内の画像を検索して取得すると、PDF ファイル内の画像を検索して抽出できます。これは、コンテンツの分析、画像のプロパティの検証、画像のさらなる処理など、さまざまな目的に役立ちます。

#### Q: PDF ドキュメント内の画像を検索するプロセスはどのように機能しますか?

 A: このプロセスには、`ImagePlacementAbsorber`オブジェクトを使用して、PDF ドキュメントのすべてのページで画像配置の検索を実行します。アブソーバは、ドキュメント内の各画像の位置、サイズ、解像度に関する情報を収集します。

####  Q：その目的は何ですか？`ImagePlacement` object in the code?

 A:`ImagePlacement`オブジェクトは、PDF ドキュメント内の画像の配置を表します。画像の寸法、座標、解像度などの詳細にアクセスできるプロパティを提供します。

#### Q: 検索して取得した画像を特定の条件でフィルタリングすることはできますか?

A: 提供されたコードは、PDF ドキュメント内のすべての画像に関する情報を収集します。特定の基準 (画像の種類、サイズ、解像度など) に基づいて画像をフィルタリングする場合は、コードを変更して適切なフィルタリング条件を含める必要がある場合があります。

#### Q: 配置情報を取得した後、実際の画像コンテンツにアクセスするにはどうすればよいですか?

 A:`XImage`から取得したオブジェクト`ImagePlacement`オブジェクトは実際の画像コンテンツを表します。これをさらに加工することもできます`XImage`オブジェクトをファイルに保存したり、アプリケーションで表示したりすることができます。

#### Q: 取得した画像プロパティを使用して何ができますか?

A: 取得した画像の幅、高さ、座標、解像度などのプロパティはさまざまな用途に使用できます。プロパティを分析したり、ユーザーに表示したり、さらなる処理のための入力として使用したりできます。

#### Q: この方法を使用して PDF ドキュメント内の画像を変更または編集できますか?

A: 提供されているコードは、画像配置情報の検索と取得に重点を置いています。画像を変更または編集するには、Aspose.PDF ライブラリを使用して画像操作などの追加機能を統合する必要がある場合があります。

#### Q: このメソッドを自分のプロジェクトに統合するにはどうすればよいですか?

A: このメソッドをプロジェクトに統合するには、説明されている手順に従い、必要に応じてコードを変更します。取得した画像配置情報とプロパティは、アプリケーションの要件に応じて使用できます。

#### Q: Aspose.PDF for .NET は、PDF ドキュメント内の画像操作に関連する他の機能を提供しますか?

A: はい。Aspose.PDF for .NET は、画像の挿入、サイズ変更、回転、抽出など、PDF ドキュメント内の画像を操作するためのさまざまな機能を提供します。ライブラリのドキュメントと例を調べて、その全機能を確認できます。