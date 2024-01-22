---
title: PDF ドキュメントの角の丸い表
linktitle: PDF ドキュメントの角の丸い表
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ドキュメントに角の丸い表を作成する方法を学びます。
type: docs
weight: 190
url: /ja/net/programming-with-tables/rounded-corner-table/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントに角の丸い表を作成する方法を段階的に説明します。提供されている C# ソース コードについて説明し、実装方法を示します。

## ステップ 1: テーブルの作成
まず、次のコードを使用してテーブルを作成します。

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## ステップ 2: 角丸スタイルの設定
次に、テーブルの角の丸いスタイルを設定します。

```csharp
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
```

## ステップ 3: テーブルの境界線の設定
テーブルに丸い角の境界線を付けるには、BorderInfo オブジェクトを作成し、適切なパラメーターを使用して構成する必要があります。

```csharp
// GraphInfo オブジェクトを作成して境界線の色を設定します
GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;

//空の BorderInfo オブジェクトを作成する
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);

//丸い境界線の半径を 15 に設定します。
bInfo.RoundedBorderRadius = 15;

//表に枠線情報を適用する
tab1.Border = bInfo;
```

### Aspose.PDF for .NET を使用した角丸テーブルのソース コード例

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;
//空の BorderInfo オブジェクトを作成する
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);
//境界線を丸い半径が 15 の丸い境界線に設定します。
bInfo.RoundedBorderRadius = 15;
//テーブルのコーナー スタイルを Round に設定します。
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
//テーブルの境界線情報を設定する
tab1.Border = bInfo;
```

## 結論
おめでとうございます！ Aspose.PDF for .NET を使用して PDF ドキュメント内に角の丸い表を作成する方法を学習しました。このステップバイステップのガイドでは、丸い角のスタイルと表の境界線を設定する方法を説明しました。この知識を自分のプロジェクトに適用できるようになりました。

### PDFドキュメントの角丸表に関するFAQ

#### Q: テーブルの丸い角の半径をカスタマイズできますか?

A: はい、テーブルの丸い角の半径をカスタマイズするには、`bInfo.RoundedBorderRadius`提供された C# ソース コードのプロパティ。目的の半径値 (ポイント単位) を設定するだけで、目的の丸い角の外観を実現できます。

#### Q: テーブル内の個々のセルに丸い角を適用できますか?

A: いいえ、角丸スタイルはテーブル全体に全体として適用されます。 Aspose.PDF for .NET は現在、テーブル内の個々のセルに角丸を適用するための組み込みサポートを提供していません。

#### Q: 角丸の枠線の色を変更できますか?

 A: はい、角の丸い境界線の色は、`graph.Color` C# ソース コードのプロパティ。希望の色を指定するだけです。`Aspose.Pdf.Color.Red`またはその他の有効な色表現。

#### Q: 同じ PDF ドキュメント内の異なるテーブルに異なるコーナー スタイル (例: 正方形と丸い) を適用することはできますか?

A: はい、同じ PDF ドキュメント内の異なるテーブルに異なるコーナー スタイルを適用することができます。複数のテーブルを作成し、要件に基づいてテーブルのコーナー スタイルを個別に構成できます。

#### Q: 角丸枠の太さを調整できますか?

 A: はい、角の丸い境界線の太さは、`BorderInfo` C# ソース コード内のオブジェクトのプロパティ。たとえば、次のように設定できます。`bInfo.Width`境界線の太さを調整するプロパティ。