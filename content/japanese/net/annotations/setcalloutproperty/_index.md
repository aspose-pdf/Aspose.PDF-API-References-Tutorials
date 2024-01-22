---
title: PDF ファイルに吹き出しプロパティを設定する
linktitle: PDF ファイルに吹き出しプロパティを設定する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイルの吹き出しプロパティを設定する方法を学びます。吹き出し線、テキストの色、終了スタイルを使用して注釈をカスタマイズします。
type: docs
weight: 130
url: /ja/net/annotations/setcalloutproperty/
---
 Aspose.PDF for .NET は、C# で PDF ドキュメントを作成、操作、変換するための強力なライブラリです。このライブラリが提供する機能の 1 つは、PDF ドキュメント内のフリー テキスト注釈の吹き出しプロパティを設定する機能です。これは、`FreeTextAnnotation`クラスを使用すると、吹き出し付きの注釈を作成できます。

このチュートリアルでは、C# で Aspose.PDF for .NET を使用してフリー テキスト注釈の吹き出しプロパティを設定するプロセスを説明します。以下の手順に従って開始してください。

## Aspose.PDF for .NET をインストールする

まだ行っていない場合は、次のことを行う必要があります[ダウンロード](https://releases.aspose.com/pdf/net/)Aspose リリースまたは NuGet パッケージ マネージャー経由で Aspose.PDF for .NET をインストールします。

## ステップ 1: 新しい PDF ドキュメントを作成する

を使用して新しい PDF ドキュメントを作成します。`Document`Aspose.PDF for .NET によって提供されるクラス。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## ステップ 2: ドキュメントに新しいページを追加する

を使用してドキュメントに新しいページを追加します。`Pages`のコレクション`Document`クラス。

```csharp
Page page = doc.Pages.Add();
```

## ステップ 3: デフォルトの外観を設定する

新しい注釈を作成して、フリー テキスト注釈のデフォルトの外観を設定します。`DefaultAppearance`オブジェクトとそのプロパティの設定`TextColor`そして`FontSize`.

```csharp
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
```

## ステップ 4: 吹き出し付きのフリーテキスト注釈を作成する

を使用して、吹き出し付きの新しいフリーテキスト注釈を作成します。`FreeTextAnnotation`クラス。をセットする`Intent`財産を`FreeTextIntent.FreeTextCallout`これが吹き出し注釈であることを指定します。をセットする`EndingStyle`財産を`LineEnding.OpenArrow`吹き出しの端の矢印のスタイルを指定します。をセットする`Callout`プロパティを配列に変換`Point`吹き出し線を描画する必要があるページ上の点を表すオブジェクト。

```csharp
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
fta.Callout = new Point[]
{
    new Point(428.25,651.75), new Point(462.75,681.375), new Point(474,681.375)
};
```

## ステップ 5: フリーテキストの注釈をページに追加する

を使用して、フリーテキストの注釈をページに追加します。`Annotations`のコレクション`Page`クラス。

```csharp
page.Annotations.Add(fta);
```

## ステップ 6: 注釈にテキストを追加する

注釈にテキストを追加するには、`RichText`プロパティをフォーマットされた XML の文字列に変換します。このチュートリアルでは、テキストの色を赤、フォント サイズを 9 に設定します。

```csharp
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"color:#FF
```

## ステップ 7: ドキュメントを保存する

次に、次のコードを使用してドキュメントを保存します。

```csharp
doc.Save(dataDir + "SetCalloutProperty.pdf")
```

### Aspose.PDF for .NET を使用した Set Callout Property のソース コード例

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
Page page = doc.Pages.Add();
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
fta.Callout = new Point[]
{
	new Point(428.25,651.75), new Point(462.75,681.375), new Point(474,681.375)
};
page.Annotations.Add(fta);
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"color:#FF0000;font-weight:normal;font-style:normal;font-stretch:normal\"><p dir=\"ltr\"> <span style=\"font-size:9.0pt;font-family:Helvetica\">これはサンプルです</span></p></body>";
doc.Save(dataDir + "SetCalloutProperty.pdf");
```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメント内のフリー テキスト注釈の吹き出しプロパティを設定する方法を検討しました。吹き出し注釈は、文書内の特定の領域に関連する追加情報や説明を提供するのに役立ちます。 Aspose.PDF for .NET は、吹き出しなどの注釈の作成やカスタマイズなど、PDF ファイルを操作するための幅広い機能を提供します。ステップバイステップのガイドに従い、提供されている C# ソース コードを使用することで、開発者は PDF ドキュメントに吹き出し注釈を簡単に実装でき、ドキュメントの使いやすさと明瞭さが向上します。 Aspose.PDF for .NET は、.NET アプリケーションでの PDF 操作のための多用途で信頼性の高いライブラリであり、さまざまな PDF 関連タスクを効率的に処理するための強力なツールを提供します。

### PDF ファイルのコールアウトプロパティの設定に関する FAQ

#### Q: PDF ドキュメントの吹き出し注釈とは何ですか?

A: PDF ドキュメントの吹き出し注釈は、ドキュメント内の特定の領域を指す引出線を持つテキスト ボックスを作成できる注釈の一種です。通常、文書内の特定のセクションまたは要素に関連する追加情報またはコメントを提供するために使用されます。

#### Q: Aspose.PDF for .NET を使用してコールアウト注釈の外観をカスタマイズできますか?

A: はい、色、フォント サイズ、テキストの配置、線のスタイル、矢印のスタイルなど、吹き出し注釈のさまざまなプロパティをカスタマイズできます。

#### Q: 吹き出しの注釈にテキストを追加するにはどうすればよいですか?

 A: 吹き出しの注釈にテキストを追加するには、`RichText`の財産`FreeTextAnnotation`物体。の`RichText`プロパティは、吹き出し注釈に表示されるテキストを表す、フォーマットされた XML の文字列を受け取ります。

#### Q: Aspose.PDF for .NET を使用して PDF ドキュメントに複数の吹き出し注釈を追加できますか?

 A: はい、PDF ドキュメント内に複数の吹き出し注釈を作成するには、`FreeTextAnnotation`オブジェクトを作成し、ドキュメント内の別のページまたは場所に追加します。