---
title: PDF ドキュメントの角丸テーブル
linktitle: PDF ドキュメントの角丸テーブル
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ドキュメントに角の丸い表を作成する方法を学習します。
type: docs
weight: 190
url: /ja/net/programming-with-tables/rounded-corner-table/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントに角丸のテーブルを作成する方法を段階的に説明します。提供されている C# ソース コードについて説明し、実装方法を示します。

## ステップ1: テーブルの作成
まず、次のコードを使用してテーブルを作成します。

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## ステップ2: 丸い角のスタイルの設定
次に、テーブルの角丸スタイルを設定します。

```csharp
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
```

## ステップ3: 表の境界線の設定
テーブルに丸い角の境界線を付けるには、BorderInfo オブジェクトを作成し、適切なパラメータで設定する必要があります。

```csharp
//境界線の色を設定するためのGraphInfoオブジェクトを作成する
GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;

//空のBorderInfoオブジェクトを作成する
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);

//丸い境界線の半径を15に設定します
bInfo.RoundedBorderRadius = 15;

//テーブルに境界線情報を適用する
tab1.Border = bInfo;
```

### Aspose.PDF for .NET を使用した角丸表のサンプル ソース コード

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;
//空のBorderInfoオブジェクトを作成する
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);
//境界線を丸い境界線に設定します。丸みの半径は15です。
bInfo.RoundedBorderRadius = 15;
//テーブルのコーナースタイルを丸型に設定します。
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
//表の境界線情報を設定する
tab1.Border = bInfo;
```

## 結論
おめでとうございます。Aspose.PDF for .NET を使用して PDF ドキュメントに角丸の表を作成する方法を学習しました。このステップ バイ ステップ ガイドでは、角丸のスタイルと表の境界線を設定する方法を説明しました。これで、この知識を自分のプロジェクトに適用できます。

### 角丸テーブルに関するよくある質問（PDF ドキュメント）

#### Q: テーブルの丸い角の半径をカスタマイズできますか?

A: はい、テーブルの角丸の半径は、`bInfo.RoundedBorderRadius`提供されている C# ソース コードのプロパティ。希望する丸い角の外観を実現するには、必要な半径値 (ポイント単位) を設定するだけです。

#### Q: 表内の個々のセルに丸い角を適用できますか?

A: いいえ、丸い角のスタイルはテーブル全体に適用されます。Aspose.PDF for .NET には現在、テーブル内の個々のセルに丸い角を適用するための組み込みサポートは提供されていません。

#### Q: 角丸の境界線の色を変更できますか?

 A: はい、角丸の境界線の色は、`graph.Color` C#ソースコードでプロパティを設定します。希望する色を指定するだけです。`Aspose.Pdf.Color.Red`またはその他の有効な色表現。

#### Q: 同じ PDF ドキュメント内の異なる表に異なる角のスタイル (四角形や丸みなど) を適用することは可能ですか?

A: はい、同じ PDF ドキュメント内の異なる表に異なるコーナー スタイルを適用できます。複数の表を作成し、要件に応じてコーナー スタイルを個別に設定できます。

#### Q: 角丸の枠線の太さを調整できますか?

 A: はい、角丸の枠線の太さは、`BorderInfo` C#ソースコード内のオブジェクトのプロパティを設定します。たとえば、`bInfo.Width`境界線の太さを調整するプロパティ。