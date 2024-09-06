---
title: PDF ファイルにストロークテキストを記入する
linktitle: PDF ファイルにストロークテキストを記入する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイルにテキストを簡単に入力およびアウトラインする方法を学習します。
type: docs
weight: 90
url: /ja/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイル内のテキストを塗りつぶし、アウトライン化する方法を段階的に説明します。提供されている C# ソース コードを使用して、PDF ファイル内のテキストに塗りつぶしとアウトラインの色を適用する方法を説明します。

## ステップ1: 環境の設定

始める前に、次のものがあることを確認してください。

- インストールされた .NET 開発環境。
- .NET 用の Aspose.PDF ライブラリがダウンロードされ、プロジェクトで参照されます。

## ステップ2: TextStateオブジェクトの作成

最初のステップは、高度なプロパティを渡す TextState オブジェクトを作成することです。方法は次のとおりです。

```csharp
//高度なプロパティを転送するための TextState オブジェクトを作成する
TextState ts = new TextState();

//アウトラインの色を設定する
ts.StrokingColor = Color.Gray;

//テキストレンダリングモードを定義する
ts.RenderingMode = TextRenderingMode.StrokeText;
```

上記のコードは、新しい TextState オブジェクトを作成し、アウトラインの色とテキストのレンダリング方法を設定します。

## ステップ3: PDF文書の読み込み

TextState オブジェクトの準備ができたので、テキストの塗りつぶしとアウトラインを適用する PDF ドキュメントを読み込むことができます。手順は次のとおりです。

```csharp
// PDF文書を入力として読み込む
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
```

上記のコードは、Aspose.PDF.Facades ライブラリの PdfFileStamp クラスを使用して既存の PDF ドキュメントを読み込みます。

## ステップ4: テキストに塗りつぶしと線を追加する

PDF ドキュメントが読み込まれたので、テキストに塗りつぶしとアウトラインを追加できます。手順は次のとおりです。

```csharp
//定義されたテキストとプロパティを使用してスタンプ（スタンプ）を作成します
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

//TextStateオブジェクトをバインドする
stamp.BindTextState(ts);

//原点X、Yを設定
stamp.SetOrigin(100, 100);
stamp. Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp. IsBackground = false;

//文書にスタンプを追加する
fileStamp.AddStamp(stamp);
```

上記のコードは、指定されたテキストと定義された Fill および Stroke プロパティを使用してスタンプを作成します。

## ステップ5: 出力ドキュメントを保存する

テキスト スタンプを追加したら、変更した PDF ドキュメントを保存できます。手順は次のとおりです。

```csharp
//変更したドキュメントを保存する
fileStamp.Save(dataDir + "output_out.pdf");
fileStamp.Close();
```

上記のコードは、編集された PDF ドキュメントを指定されたディレクトリに保存します。

### Aspose.PDF for .NET を使用したストローク テキストの塗りつぶしのサンプル ソース コード 
```csharp

//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//高度なプロパティを転送するための TextState オブジェクトを作成する
TextState ts = new TextState();

//ストロークの色を設定する
ts.StrokingColor = Color.Gray;

//テキストレンダリングモードを設定する
ts.RenderingMode = TextRenderingMode.StrokeText;

//入力PDF文書を読み込む
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

//TextState をバインドする
stamp.BindTextState(ts);

//X、Y原点を設定
stamp.SetOrigin(100, 100);
stamp.Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp.IsBackground = false;

//スタンプを追加
fileStamp.AddStamp(stamp);
fileStamp.Save(dataDir + "ouput_out.pdf");
fileStamp.Close();

```

## 結論

おめでとうございます! Aspose.PDF for .NET を使用して PDF ドキュメント内のテキストを塗りつぶし、アウトライン化する方法を学びました。これで、この知識を適用して、PDF ドキュメント内の塗りつぶしとアウトラインの色をカスタマイズできます。

### PDF ファイル内のストローク テキストの塗りつぶしに関する FAQ

#### Q: PDF ドキュメントでテキストを塗りつぶしてアウトライン化するとはどういう意味ですか? また、いつこれを行う必要があるのでしょうか?

A: PDF ドキュメント内のテキストの塗りつぶしとアウトライン化には、テキスト文字の内部 (塗りつぶし) とテキストの周囲の境界線 (アウトライン) に色を適用することが含まれます。これを使用して、テキストの外観を向上させたり、強調したり、PDF 内の特定のコンテンツを強調表示したりできます。

#### Q: 提供されている C# ソース コードは、PDF ファイル内のテキストの塗りつぶしとアウトラインをどのように実現しますか?

 A: 提供されているソースコードは、`TextState`オブジェクトを使用して、アウトラインの色やレンダリング モードなどの高度なテキスト プロパティを定義します。次に、Aspose.PDF.Facades を使用して既存の PDF ドキュメントを読み込み、指定された塗りつぶしとストロークのプロパティを持つテキストを含むスタンプを作成し、そのスタンプをドキュメントに追加します。

####  Q: の目的は何ですか？`TextState` object in the code?

 A:`TextState`オブジェクトは、テキストのアウトライン (ストローク) の色やレンダリング モードなど、高度なテキスト プロパティを定義するために使用されます。これにより、ストロークと塗りつぶしの観点からテキストの表示方法をカスタマイズできます。

#### Q: 同じテキストの異なる部分に異なる塗りつぶし色とアウトライン色を適用できますか?

 A: はい、コードを変更して異なるものを作成できます。`TextState`異なる塗りつぶしとアウトラインの色を持つオブジェクトを作成し、テキストの特定の部分に個別の`Stamp`オブジェクト。

#### Q: PDF ドキュメントにすでに存在するテキストに塗りつぶしとアウトラインの色を適用できますか?

 A: はい、同様の原理で、適切なテキストオブジェクトを選択し、希望する色でスタンプとして追加することで、PDF文書内の既存のテキストに塗りつぶしとアウトラインの色を適用できます。`TextState`プロパティ。

#### Q: 塗りつぶされたテキストとアウトラインされたテキストの不透明度とブレンドを調整するにはどうすればよいですか?

 A: 提供されたコードを使用すると、スタンプの不透明度とブレンドプロパティを設定できます。`Opacity`そして`BlendingSpace`それぞれプロパティです。これらの値を調整することで、目的の視覚効果を実現できます。

#### Q: 同じ PDF ドキュメント内の複数のスタンプに異なる塗りつぶし色とアウトライン色を適用するにはどうすればよいですか?

 A: 複数作成できます`TextState`異なる塗りつぶしとアウトラインの色でオブジェクトを作成し、別の`Stamp`テキストセットごとに異なる色のオブジェクトを作成します。これらのスタンプを同じPDF文書に追加します。`PdfFileStamp`クラス。

#### Q: アウトラインおよび塗りつぶしテキストに Arial 以外のフォントを使用できますか?

 A: はい、フォント名パラメータを変更することでフォントを変更できます。`FormattedText`スタンプを作成するときにコンストラクターを使用します。システムで使用可能な任意のフォントを使用できます。

#### Q: アウトラインされたテキストと塗りつぶされたテキストの回転角度を変更するにはどうすればよいですか?

 A: 提供されたコードを使用すると、スタンプの回転角度を設定できます。`Rotation`プロパティ。このプロパティを調整して、テキストの希望する回転角度を指定できます。

#### Q: ページ上のアウトラインテキストと塗りつぶされたテキストの位置とサイズを制御するにはどうすればよいでしょうか?

 A:`SetOrigin`方法の`Stamp`オブジェクトを使用して、ページ上のスタンプの位置のX座標とY座標を設定します。また、フォントサイズを調整することもできます。`FormattedText`テキストのサイズを制御するコンストラクター。