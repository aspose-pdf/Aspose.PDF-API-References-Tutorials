---
title: ページ上に XForm を描画する
linktitle: ページ上に XForm を描画する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ページ上に XForm フォームを描画するためのステップバイステップ ガイド。ページ上にフォームを追加して配置します。
type: docs
weight: 10
url: /ja/net/programming-with-operators/draw-xform-on-page/
---
このチュートリアルでは、Aspose.PDF for .NET を使用してページ上に XForm を描画する方法について段階的なガイドを提供します。 Aspose.PDF は、PDF ドキュメントをプログラムで作成、操作、変換できる強力なライブラリです。 Aspose.PDF が提供する演算子を使用すると、既存の PDF ページに XForm フォームを追加して配置できます。

## 前提条件

始める前に、次の前提条件が満たされていることを確認してください。

1. Visual Studio には .NET Framework がインストールされています。
2. .NET 用の Aspose.PDF ライブラリ。

## ステップ 1: プロジェクトのセットアップ

まず、Visual Studio で新しいプロジェクトを作成し、Aspose.PDF for .NET ライブラリへの参照を追加します。 Aspose 公式 Web サイトからライブラリをダウンロードして、マシンにインストールできます。

## ステップ 2: 必要な名前空間をインポートする

C# コード ファイルで、Aspose.PDF が提供するクラスとメソッドにアクセスするために必要な名前空間をインポートします。

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

## ステップ 3: ファイルパスの設定

背景画像、入力 PDF ファイル、出力 PDF ファイルのファイル パスを定義します。

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string imageFile = dataDir + "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
```

必ずマシン上の実際のファイル パスを指定してください。

## ステップ 4: 入力 PDF ファイルをロードする

次のコードを使用して、入力 PDF ファイルをロードします。

```csharp
using (Document doc = new Document(inFile))
{
OperatorCollection pageContents = doc.Pages[1].Contents;
//次のコードでは、GSave/GRestore 演算子を使用しています。
//このコードでは、ContatenateMatrix 演算子を使用して XForm を配置します。
//このコードでは、Do 演算子を使用してページ上に XForm を描画します。
// GSave/GRestore オペレーターは既存のコンテンツをラップします
//これは、既存のコンテンツの最後で初期グラフィックス状態を取得するために行われます。
//そうしないと、既存の演算子のチェーンの最後に不要な変換が残る可能性があります。
pageContents. Insert(1, new GSave());
pageContents. Add(new GRestore());
//新しいコマンドの後にグラフィックス状態を適切にリセットするための GSave オペレーターを追加しました
pageContents. Add(new GSave());

//Xフォームを作成する
XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
doc.Pages[1].Resources.Forms.Add(form);
form.Contents.Add(new GSave());
//画像の幅と高さを設定する
form.Contents.Add(new ConcatenateMatrix(200, 0, 0, 200, 0, 0));
//画像をストリームにロードします
Stream imageStream = new FileStream(imageFile, FileMode.Open);
//画像を XForm リソースの画像コレクションに追加します
form.Resources.Images.Add(imageStream);
XImage ximage = form.Resources.Images[form.Resources.Images.Count];
//Do 演算子の使用: この演算子は画像を描画します
form.Contents.Add(new Do(ximage.Name));
form.Contents.Add(new GRestore());

pageContents. Add(new GSave());
//XForm を座標 x=100 および y=500 に配置します。
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 500));
// Do 演算子を使用して XForm を描画する
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

pageContents. Add(new GSave());
//XForm を座標 x=100 および y=300 に配置します。
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 300));
// Do 演算子を使用して XForm を描画する
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

// GSave 後に GRestore を使用してグラフィックス状態を復元する
pageContents. Add(new GRestore());
doc.Save(outFile);
}
```

必ず実際のファイル パスを指定し、必要に応じてページ番号と XForm の位置を調整してください。

### Aspose.PDF for .NET を使用した Draw XForm On Page のサンプル ソース コード
 
```csharp

//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string imageFile = dataDir+ "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
using (Document doc = new Document(inFile))
{
	OperatorCollection pageContents = doc.Pages[1].Contents;
	//サンプルは次のことを示しています
	//GSave/GRestore オペレーターの使用法
	//xForm を配置するための ContatenateMatrix 演算子の使用法
	//演算子を使用してページ上に xForm を描画します
	//GSave/GRestore 演算子のペアで既存のコンテンツをラップする
	//これは、既存のコンテンツの初期グラフィックス状態を取得することです。
	//そうしないと、既存の演算子チェーンの最後に望ましくない変換が残る可能性があります。
	pageContents.Insert(1, new Aspose.Pdf.Operators.GSave());
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	//新しいコマンドの後にグラフィックス状態を適切にクリアするために、グラフィックス状態保存オペレーターを追加しました。
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	#region create xForm
	// xFormの作成
	XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
	doc.Pages[1].Resources.Forms.Add(form);
	form.Contents.Add(new Aspose.Pdf.Operators.GSave());
	//画像の幅と高さを定義する
	form.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(200, 0, 0, 200, 0, 0));
	//画像をストリームにロードする
	Stream imageStream = new FileStream(imageFile, FileMode.Open);
	//XForm リソースの Images コレクションに画像を追加します。
	form.Resources.Images.Add(imageStream);
	XImage ximage = form.Resources.Images[form.Resources.Images.Count];
	//Do 演算子の使用: この演算子は画像を描画します
	form.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
	form.Contents.Add(new Aspose.Pdf.Operators.GRestore());
	#endregion
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	//フォームを x=100 y=500 座標に配置します
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 500));
	//Do 演算子を使用してフォームを描画する
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	//フォームを x=100 y=300 座標に配置します
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 300));
	//Do 演算子を使用してフォームを描画する
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	//GSave 後に GRestore を使用してグラフィックス状態を復元する
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	doc.Save(outFile);                
}

```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ページ上に XForm フォームを描画する方法を学習しました。説明されている手順に従うことで、既存のページに XForm フォームを追加して配置できるようになり、PDF ドキュメントの柔軟性がさらに高まります。

### ページ上に XForm を描画するための FAQ

#### Q: Aspose.PDF の XForm とは何ですか?

A: XForm は、PDF ドキュメント内の再利用可能なグラフィカル オブジェクトです。これにより、異なるページで何度も再利用できる複雑なグラフィック、画像、またはテキストを定義して描画できます。

#### Q: Aspose.PDF に必要な名前空間をインポートするにはどうすればよいですか?

 A: C# コード ファイルでは、`using` Aspose.PDF によって提供されるクラスとメソッドにアクセスするために必要な名前空間をインポートするディレクティブ:
```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

#### Q: GSave および GRestore オペレーターの目的は何ですか?

 A:`GSave`そして`GRestore`Aspose.PDF の演算子は、グラフィックス状態の保存と復元に使用されます。これらは、コンテンツの 1 つのセクションに適用された変換と設定が後続のセクションに影響を与えないようにするのに役立ちます。

#### Q: Aspose.PDF を使用して XForm を定義するにはどうすればよいですか?

 A: XForm を作成するには、`XForm.CreateNewForm`メソッドを作成し、`Resources.Forms`特定のページのコレクション。その後、XForm にコンテンツを追加できます。`Contents`財産。

#### Q: XForm 内に画像を描画するにはどうすればよいですか?

 A: 画像をストリームにロードし、`Resources.Images` XForm のコレクション。使用`Do`XForm 内の演算子`Contents`イメージを描くために。

#### Q: PDF ページ上に XForm を配置するにはどうすればよいですか?

 A: ページ上に XForm を配置するには、`ConcatenateMatrix`ページ内の演算子`Contents`。マトリックスのパラメータを調整して、XForm の移動 (位置) とスケーリングを指定します。

#### Q: 同じページに複数の XForms を描画できますか?

 A: はい、`ConcatenateMatrix`パラメータを使用して、各 XForm を異なる座標に配置します。

#### Q: XForm の作成後に内容を変更できますか?

 A: はい、作成後に XForm に演算子を追加することで、XForm の内容を変更できます。`Contents`財産。

#### Q: GSave 演算子と GRestore 演算子を省略するとどうなりますか?

A: GSave 演算子と GRestore 演算子を省略すると、後続のコンテンツに不要な変換や設定が適用される可能性があります。これらを使用すると、きれいなグラフィック状態を維持するのに役立ちます。

#### Q: PDF ドキュメントの異なるページにわたって XForms を再利用できますか?

 A: はい、同じ XForm を`Resources.Forms`さまざまなページのコレクション。

#### Q: 作成できる XForms の数に制限はありますか?

A: 作成できる XForms の数に厳密な制限はありませんが、XForms が多すぎるとパフォーマンスとメモリ使用量に影響を与える可能性があることに注意してください。慎重に使用してください。

#### Q: XForm を回転したり、他の変換を適用したりできますか?

 A: はい、使用できます。`ConcatenateMatrix`演算子を使用して、回転、スケーリング、移動などの変換を XForm に適用します。
