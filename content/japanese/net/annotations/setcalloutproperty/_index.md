---
title: PDF ファイルの吹き出しプロパティを設定する
linktitle: PDF ファイルの吹き出しプロパティを設定する
second_title: Aspose.PDF for .NET API リファレンス
description: この詳細なステップバイステップのチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイルにコールアウト プロパティを設定する方法を学習します。
type: docs
weight: 130
url: /ja/net/annotations/setcalloutproperty/
---
## 導入

プロフェッショナルで視覚的に魅力的な PDF ドキュメントを作成するには、特定のコンテンツに注目を集める注釈の追加が必要になることがよくあります。そのような注釈の 1 つが吹き出しです。吹き出しは、漫画で見られる吹き出しのようなものです。吹き出しは、PDF 内のテキストを明確化したり強調したりするのに役立ちます。Aspose.PDF for .NET を使用すると、ドキュメントにそのような注釈を簡単に追加できます。このチュートリアルでは、この強力なライブラリを使用して PDF ファイルに吹き出しプロパティを設定する方法について説明します。熟練した開発者でも、初心者でも、このガイドを読み終える頃には、PDF ファイルで吹き出しを操作する方法を明確に理解できるようになります。

## 前提条件

コードに進む前に、始めるために必要な基本事項について説明しましょう。

1.  Aspose.PDF for .NET: Aspose.PDF for .NETライブラリがインストールされていることを確認してください。ダウンロードはこちらからできます。[ここ](https://releases.aspose.com/pdf/net/).
2. IDE: Visual Studio などの開発環境。
3. .NET Framework: マシンに .NET がインストールされていることを確認します。
4. 一時ライセンス: Aspose.PDFの機能を制限なく試してみたい場合は、[一時ライセンス](https://purchase.aspose.com/temporary-license/).

## パッケージのインポート

コードの記述を開始する前に、PDF ファイルと注釈を操作するために必要なパッケージをインポートする必要があります。

```csharp
using Aspose.Pdf.Annotations;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

これらのインポートにより、PDF ドキュメントを操作し、吹き出しなどの注釈を作成するために必要なすべてのクラスとメソッドが提供されます。

## ステップ1: PDFドキュメントを初期化する

最初のステップは、吹き出し注釈を追加する新しい PDF ドキュメントを初期化することです。これは、要素を追加し始めることができる空白のキャンバスを設定することと考えてください。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//新しいPDF文書を初期化する
Document doc = new Document();
```
ここでは、新しい`Document`PDFファイルとして機能するオブジェクトです。`dataDir`変数は、完了後に PDF ファイルを保存するディレクトリに設定されます。

## ステップ2: ドキュメントに新しいページを追加する

PDF ドキュメントには複数のページを含めることができます。この手順では、ドキュメントに新しいページを追加します。このページに、吹き出し注釈を配置します。

```csharp
//ドキュメントに新しいページを追加する
Page page = doc.Pages.Add();
```
の`Pages.Add()`メソッドは、新しいページを追加するために使用されます`doc`オブジェクトに保存されます。新しいページは`page`変数は後で注釈を追加するときに使用します。

## ステップ3: デフォルトの外観を定義する

注釈には、吹き出しと同様に、カスタマイズ可能な外観があります。この手順では、吹き出し内のテキストの外観を定義します。

```csharp
//注釈のデフォルトの外観を定義する
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
```
私たちは`DefaultAppearance`テキストの色とフォント サイズを定義するオブジェクト。ここでは、テキストは赤になり、フォント サイズは 10 に設定されています。この外観は吹き出し注釈に適用されます。

## ステップ4: フリーテキスト注釈を作成する

次に、実際の注釈を作成します。フリーテキスト注釈を使用すると、特定のテキストとスタイルを使用して吹き出しを追加できます。

```csharp
//吹き出し付きのFreeTextAnnotationを作成する
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
```
私たちは`FreeTextAnnotation`オブジェクトを特定の座標に関連付け、ページ上の位置を定義します。`Intent`に設定されています`FreeTextCallout`は、これが吹き出し注釈であることを示します。`EndingStyle`に設定されています`OpenArrow`つまり、吹き出し線は開いた矢印で終わります。

## ステップ5: 吹き出し線のポイントを定義する

吹き出し注釈には、関心領域を指す線があります。ここでは、この線を構成するポイントを定義します。

```csharp
//吹き出し線のポイントを定義する
fta.Callout = new Point[]
{
    new Point(428.25, 651.75), 
    new Point(462.75, 681.375), 
    new Point(474, 681.375)
};
```
の`Callout`プロパティは配列です`Point`オブジェクトはそれぞれページ上の座標を表します。これらのポイントは吹き出し線のパスを定義し、古典的な吹き出しの外観を与えます。

## ステップ6: ページに注釈を追加する

注釈を作成して構成したら、次のステップはそれをページに追加することです。

```csharp
//ページに注釈を追加する
page.Annotations.Add(fta);
```
の`Annotations.Add()`メソッドは、前に作成したページに注釈を配置するために使用されます。この手順により、PDF ページにコールアウトが効果的に「描画」されます。

## ステップ7: リッチテキストコンテンツを設定する

吹き出し注釈にはリッチ テキストを含めることができ、吹き出し内にフォーマットされたコンテンツを表示できます。サンプル テキストを追加してみましょう。

```csharp
//注釈のリッチテキストを設定する
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"color:#FF0000;font-weight:normal;font-style:normal;font-stretch:normal\"><p dir=\"ltr\"><span style=\"font-size:9.0pt;font-family:Helvetica\">これはサンプルです</span></p></body>";
```
の`RichText`プロパティは HTML コンテンツで設定されます。これにより、フォント サイズ、色、スタイルを指定するなど、コールアウト内で詳細な書式設定が可能になります。

## ステップ8: PDFドキュメントを保存する

最後に、すべてを設定したら、ドキュメントを保存する必要があります。この手順で、コールアウト注釈付きの PDF の作成が完了します。

```csharp
//文書を保存する
doc.Save(dataDir + "SetCalloutProperty.pdf");
```
の`Save()`メソッドは、ドキュメントを指定されたディレクトリに「SetCalloutProperty.pdf」というファイル名で保存します。この手順で PDF 作成プロセスは完了です。

## 結論

これで完了です。Aspose.PDF for .NET を使用して、吹き出し注釈付きの PDF ドキュメントを作成しました。この注釈は、ドキュメントの特定の部分を強調表示したり説明したりするのに非常に便利です。Aspose.PDF は、PDF の操作を簡単かつ柔軟にする強力な API を提供します。注釈の追加、ドキュメントの変換、複雑な PDF タスクの処理など、Aspose.PDF が対応します。

## よくある質問

### コールアウトの外観をさらにカスタマイズできますか?

もちろんです! 線の色、太さ、テキストのフォント ファミリやスタイルなど、さまざまな側面をカスタマイズできます。

### 1 ページに複数のコールアウトを追加することは可能ですか?

はい、注釈ごとに手順を繰り返すことで、必要な数の吹き出しを追加できます。

### 吹き出しの位置を変更するにはどうすればよいですか?

座標を変更するだけで、`Rectangle`そして`Callout`注釈の位置を変更するプロパティ。

### Aspose.PDF を使用して他の種類の注釈を追加できますか?

はい、Aspose.PDF は、ハイライト、スタンプ、ファイル添付など、さまざまな注釈タイプをサポートしています。

### リッチテキストコンテンツは HTML に限定されますか?

の`RichText`プロパティは HTML のサブセットをサポートしており、スタイル設定されたテキストと基本的な書式設定を含めることができます。