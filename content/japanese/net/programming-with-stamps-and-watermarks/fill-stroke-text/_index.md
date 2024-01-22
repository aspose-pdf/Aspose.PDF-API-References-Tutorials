---
title: PDF ファイルのストロークテキストを塗りつぶす
linktitle: PDF ファイルのストロークテキストを塗りつぶす
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイル内のテキストを簡単に入力およびアウトライン化する方法を学びます。
type: docs
weight: 90
url: /ja/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイル内のテキストを塗りつぶし、アウトラインを作成する方法を段階的に説明します。提供されている C# ソース コードを使用して、PDF ファイル内のテキストに塗りつぶしと輪郭の色を適用する方法を示します。

## ステップ 1: 環境をセットアップする

始める前に、以下のものがあることを確認してください。

- インストールされた .NET 開発環境。
- .NET 用の Aspose.PDF ライブラリがダウンロードされ、プロジェクトで参照されます。

## ステップ 2: TextState オブジェクトの作成

最初のステップは、高度なプロパティを渡す TextState オブジェクトを作成することです。その方法は次のとおりです。

```csharp
// TextState オブジェクトを作成して高度なプロパティを転送する
TextState ts = new TextState();

//輪郭の色を設定する
ts.StrokingColor = Color.Gray;

//テキストレンダリングモードを定義する
ts.RenderingMode = TextRenderingMode.StrokeText;
```

上記のコードは、新しい TextState オブジェクトを作成し、アウトラインの色とテキストのレンダリング方法を設定します。

## ステップ 3: PDF ドキュメントをロードする

TextState オブジェクトの準備ができたので、テキストの塗りつぶしとアウトラインを適用する PDF ドキュメントをロードできます。その方法は次のとおりです。

```csharp
// PDF ドキュメントを入力としてロードします
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
```

上記のコードは、Aspose.PDF.Facades ライブラリの PdfFileStamp クラスを使用して既存の PDF ドキュメントを読み込みます。

## ステップ 4: テキストに塗りつぶしとストロークを追加する

PDF ドキュメントがロードされたので、テキストに塗りつぶしとアウトラインを追加できます。その方法は次のとおりです。

```csharp
//定義されたテキストとプロパティを使用してスタンプ (Stamp) を作成します
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

//TextState オブジェクトをバインドする
stamp.BindTextState(ts);

//原点 X、Y を設定する
stamp.SetOrigin(100, 100);
stamp. Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp. IsBackground = false;

//書類にスタンプを追加する
fileStamp.AddStamp(stamp);
```

上記のコードは、指定されたテキストと定義された Fill および Stroke プロパティを使用してスタンプを作成します。

## ステップ 5: 出力ドキュメントを保存する

テキストスタンプを追加したら、変更した PDF ドキュメントを保存できます。その方法は次のとおりです。

```csharp
//変更したドキュメントを保存する
fileStamp.Save(dataDir + "output_out.pdf");
fileStamp.Close();
```

上記のコードは、編集した PDF ドキュメントを指定されたディレクトリに保存します。

### Aspose.PDF for .NET を使用した塗りつぶしストローク テキストのサンプル ソース コード 
```csharp

//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

// TextState オブジェクトを作成して高度なプロパティを転送する
TextState ts = new TextState();

//ストロークの色を設定する
ts.StrokingColor = Color.Gray;

//テキストレンダリングモードを設定する
ts.RenderingMode = TextRenderingMode.StrokeText;

//入力 PDF ドキュメントをロードする
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

//バインド TextState
stamp.BindTextState(ts);

// X、Y原点の設定
stamp.SetOrigin(100, 100);
stamp.Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp.IsBackground = false;

//スタンプを追加する
fileStamp.AddStamp(stamp);
fileStamp.Save(dataDir + "ouput_out.pdf");
fileStamp.Close();

```

## 結論

おめでとうございます！ Aspose.PDF for .NET を使用して PDF ドキュメントにテキストを入力し、アウトラインを作成する方法を学習しました。この知識を応用して、PDF ドキュメントの塗りつぶしと輪郭の色をカスタマイズできるようになりました。

### PDF ファイルの塗りつぶしストロークテキストに関する FAQ

#### Q: PDF ドキュメント内のテキストの塗りつぶしやアウトライン化とは何を意味しますか?また、どのような場合にそうする必要があるのですか?

A: PDF ドキュメント内のテキストの塗りつぶしとアウトラインには、テキスト文字の内部 (塗りつぶし) とテキストの周囲の境界線 (アウトライン) に色を適用することが含まれます。これを使用して、テキストの外観を向上させたり、強調を作成したり、PDF 内の特定のコンテンツを強調表示したりできます。

#### Q: 提供されている C# ソース コードは、PDF ファイル内のテキストの入力とアウトラインをどのように実行しますか?

 A: 提供されているソース コードは、`TextState`オブジェクトを使用して、アウトラインの色やレンダリング モードなどの高度なテキスト プロパティを定義します。次に、Aspose.PDF.Facades を使用して既存の PDF ドキュメントを読み込み、指定された塗りつぶしとストロークのプロパティを持つテキストを含むスタンプを作成し、そのスタンプをドキュメントに追加します。

####  Q：その目的は何ですか？`TextState` object in the code?

 A:`TextState`オブジェクトは、テキストのアウトライン (ストローク) の色やレンダリング モードなどの高度なテキスト プロパティを定義するために使用されます。ストロークと塗りつぶしに関してテキストの表示方法をカスタマイズできます。

#### Q: 同じテキストの異なる部分に異なる塗りつぶしと輪郭の色を適用できますか?

 A: はい、コードを変更して別のコードを作成できます。`TextState`個別の塗りつぶし色と輪郭色を持つオブジェクトを個別に使用してテキストの特定の部分に適用します。`Stamp`オブジェクト。

#### Q: PDF ドキュメント内に既に存在するテキストに塗りつぶしや輪郭の色を適用できますか?

 A: はい、同様の原則を使用して、適切なテキスト オブジェクトを選択し、目的のスタンプとして追加することで、PDF ドキュメント内の既存のテキストに塗りつぶしと輪郭の色を適用できます。`TextState`プロパティ。

#### Q: 塗りつぶしとアウトライン化されたテキストの不透明度とブレンドを調整するにはどうすればよいですか?

 A: 提供されているコードを使用すると、スタンプの不透明度とブレンドのプロパティを設定できます。`Opacity`そして`BlendingSpace`それぞれのプロパティ。これらの値を調整して、目的の視覚効果を実現できます。

#### Q: 同じ PDF ドキュメント内の複数のスタンプに異なる塗りつぶしと輪郭の色を適用するにはどうすればよいですか?

 A: 複数作成できます。`TextState`異なる塗りつぶし色と輪郭色を持つオブジェクトを作成し、別個に作成します。`Stamp`テキストのセットごとに異なる色を持つオブジェクト。これらのスタンプを同じ PDF ドキュメントに追加するには、`PdfFileStamp`クラス。

#### Q: アウトラインおよび塗りつぶしテキストに Arial 以外のフォントを使用できますか?

 A: はい、フォント名パラメータを変更することでフォントを変更できます。`FormattedText`スタンプ作成時のコンストラクター。システムで利用可能な任意のフォントを使用できます。

#### Q: アウトラインおよび塗りつぶされたテキストの回転角度を変更するにはどうすればよいですか?

 A: 付属のコードを使用すると、スタンプの回転角度を設定できます。`Rotation`財産。このプロパティを調整して、テキストに必要な回転角度を指定できます。

#### Q: ページ上のアウトラインと塗りつぶしのテキストの位置とサイズを制御するにはどうすればよいですか?

A: を使用できます。`SetOrigin`の方法`Stamp`オブジェクトを使用して、ページ上のスタンプの位置の X 座標と Y 座標を設定します。さらに、フォントサイズを調整することもできます。`FormattedText`テキストのサイズを制御するコンストラクター。