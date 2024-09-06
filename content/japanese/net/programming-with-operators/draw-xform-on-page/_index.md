---
title: ページにXFormを描画
linktitle: ページにXFormを描画
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ページに XForm フォームを描画するためのステップ バイ ステップ ガイド。ページにフォームを追加して配置します。
type: docs
weight: 10
url: /ja/net/programming-with-operators/draw-xform-on-page/
---
このチュートリアルでは、Aspose.PDF for .NET を使用してページに XForm を描画する方法について、ステップ バイ ステップで説明します。Aspose.PDF は、PDF ドキュメントをプログラムで作成、操作、変換できる強力なライブラリです。Aspose.PDF が提供する演算子を使用して、既存の PDF ページに XForm フォームを追加して配置できます。

## 前提条件

始める前に、次の前提条件が満たされていることを確認してください。

1. .NET フレームワークとともにインストールされた Visual Studio。
2. .NET 用の Aspose.PDF ライブラリ。

## ステップ1: プロジェクトのセットアップ

まず、Visual Studio で新しいプロジェクトを作成し、Aspose.PDF for .NET ライブラリへの参照を追加します。ライブラリは Aspose の公式 Web サイトからダウンロードして、マシンにインストールできます。

## ステップ2: 必要な名前空間をインポートする

C# コード ファイルで、Aspose.PDF によって提供されるクラスとメソッドにアクセスするために必要な名前空間をインポートします。

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

## ステップ3: ファイルパスの設定

背景画像、入力 PDF ファイル、出力 PDF ファイルのファイル パスを定義します。

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string imageFile = dataDir + "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
```

必ずマシン上の実際のファイル パスを指定してください。

## ステップ4: 入力PDFファイルの読み込み

入力 PDF ファイルを読み込むには、次のコードを使用します。

```csharp
using (Document doc = new Document(inFile))
{
OperatorCollection pageContents = doc.Pages[1].Contents;
//次のコードはGSave/GRestore演算子を使用しています
//このコードはContatenateMatrix演算子を使用してXFormを配置します。
//このコードはDo演算子を使用してページにXFormを描画します。
// GSave/GRestore演算子は既存のコンテンツをラップします
//これは、既存のコンテンツの最後にある初期のグラフィック状態を取得するために行われます。
//そうしないと、既存の演算子のチェーンの最後に不要な変換が残ってしまう可能性があります。
pageContents. Insert(1, new GSave());
pageContents. Add(new GRestore());
//新しいコマンドの後にグラフィックスの状態を適切にリセットするための GSave 演算子を追加します。
pageContents. Add(new GSave());

// XFormを作成する
XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
doc.Pages[1].Resources.Forms.Add(form);
form.Contents.Add(new GSave());
//画像の幅と高さを設定する
form.Contents.Add(new ConcatenateMatrix(200, 0, 0, 200, 0, 0));
//画像をストリームに読み込む
Stream imageStream = new FileStream(imageFile, FileMode.Open);
//XFormリソース画像コレクションに画像を追加する
form.Resources.Images.Add(imageStream);
XImage ximage = form.Resources.Images[form.Resources.Images.Count];
//Do演算子の使用：この演算子は画像を描画します
form.Contents.Add(new Do(ximage.Name));
form.Contents.Add(new GRestore());

pageContents. Add(new GSave());
//XFormをx=100、y=500の座標に配置します。
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 500));
// Do演算子でXFormを描画する
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

pageContents. Add(new GSave());
//XFormをx=100、y=300の座標に配置します。
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 300));
// Do演算子でXFormを描画する
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

// GSave 後に GRestore でグラフィック状態を復元する
pageContents. Add(new GRestore());
doc.Save(outFile);
}
```

必ず実際のファイル パスを指定し、必要に応じてページ番号と XForm の位置を調整してください。

### Aspose.PDF for .NET を使用してページ上に XForm を描画するためのサンプル ソース コード
 
```csharp

//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string imageFile = dataDir+ "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
using (Document doc = new Document(inFile))
{
	OperatorCollection pageContents = doc.Pages[1].Contents;
	//サンプルは
	//GSave/GRestore 演算子の使用法
	//ContatenateMatrix 演算子を使用して xForm を配置する
	//ページにxFormを描画するには演算子を使用します
	//既存のコンテンツをGSave/GRestore演算子ペアでラップする
	//これは、既存のコンテンツの初期のグラフィック状態を取得することです。
	//そうしないと、既存の演算子チェーンの最後に望ましくない変換が残る可能性があります。
	pageContents.Insert(1, new Aspose.Pdf.Operators.GSave());
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	//新しいコマンドの後にグラフィックス状態を適切にクリアするためのグラフィックス状態保存演算子を追加します。
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	#region create xForm
	// xForm を作成する
	XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
	doc.Pages[1].Resources.Forms.Add(form);
	form.Contents.Add(new Aspose.Pdf.Operators.GSave());
	//画像の幅と高さを定義する
	form.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(200, 0, 0, 200, 0, 0));
	//ストリームに画像を読み込む
	Stream imageStream = new FileStream(imageFile, FileMode.Open);
	//XFormリソースの画像コレクションに画像を追加する
	form.Resources.Images.Add(imageStream);
	XImage ximage = form.Resources.Images[form.Resources.Images.Count];
	//Do演算子の使用: この演算子は画像を描画します
	form.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
	form.Contents.Add(new Aspose.Pdf.Operators.GRestore());
	#endregion
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	//フォームをx=100 y=500の座標に配置します
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 500));
	//Do演算子でフォームを描画する
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	//フォームをx=100 y=300の座標に配置します
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 300));
	//Do演算子でフォームを描画する
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	//GSaveの後にGRestoreでグラフィックの状態を復元する
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	doc.Save(outFile);                
}

```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ページに XForm フォームを描画する方法を学習しました。説明されている手順に従うことで、既存のページに XForm フォームを追加して配置できるようになり、PDF ドキュメントの柔軟性が向上します。

### XFormの描画に関するFAQ

#### Q: Aspose.PDF の XForm とは何ですか?

A: XForm は、PDF ドキュメント内の再利用可能なグラフィック オブジェクトです。XForm を使用すると、異なるページで複数回再利用できる複雑なグラフィック、画像、またはテキストを定義して描画できます。

#### Q: Aspose.PDF に必要な名前空間をインポートするにはどうすればよいですか?

 A: C#コードファイルでは、`using` Aspose.PDF によって提供されるクラスとメソッドにアクセスするために必要な名前空間をインポートするディレクティブ:
```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

#### Q: GSave 演算子と GRestore 演算子の目的は何ですか?

 A:`GSave`そして`GRestore` Aspose.PDF の演算子は、グラフィックの状態を保存および復元するために使用されます。これにより、コンテンツの 1 つのセクションに適用された変換や設定が後続のセクションに影響しないようにすることができます。

#### Q: Aspose.PDF を使用して XForm を定義するにはどうすればよいですか?

 A: XFormを作成するには、`XForm.CreateNewForm`メソッドを追加して`Resources.Forms`特定のページのコレクションを作成します。その後、XFormsの`Contents`財産。

#### Q: XForm 内で画像を描画するにはどうすればよいですか?

A: 画像をストリームに読み込み、`Resources.Images` XFormのコレクション。`Do` XFormの`Contents`画像を描画します。

#### Q: PDF ページに XForm を配置するにはどうすればよいですか?

 A: XFormをページ上に配置するには、`ConcatenateMatrix`ページ内の`Contents`マトリックス パラメータを調整して、XForm の移動 (位置) とスケーリングを指定します。

#### Q: 同じページに複数の XForms を描画できますか?

 A: はい、複数のXFormsを同じページに描画することができます。`ConcatenateMatrix`各 XForm を異なる座標に配置するためのパラメータ。

#### Q: XForm を作成した後にその内容を変更できますか?

 A: はい、XFormsを作成した後で、追加の演算子を追加することでXFormsの内容を変更できます。`Contents`財産。

#### Q: GSave 演算子と GRestore 演算子を省略するとどうなりますか?

A: GSave 演算子と GRestore 演算子を省略すると、後続のコンテンツに不要な変換や設定が適用される可能性があります。これらを使用すると、クリーンなグラフィック状態を維持するのに役立ちます。

#### Q: PDF ドキュメントの異なるページで XForms を再利用できますか?

 A: はい、同じXFormを複数のページに追加することで、XFormsを複数のページで再利用できます。`Resources.Forms`さまざまなページのコレクション。

#### Q: 作成できる XForms の数に制限はありますか?

A: 作成できる XForms の数に厳密な制限はありませんが、XForms が多すぎるとパフォーマンスやメモリ使用量に影響する可能性があることに注意してください。慎重に使用してください。

#### Q: XForm を回転したり、その他の変換を適用したりできますか?

 A: はい、`ConcatenateMatrix`回転、拡大縮小、移動などの変換を XForm に適用する演算子。
