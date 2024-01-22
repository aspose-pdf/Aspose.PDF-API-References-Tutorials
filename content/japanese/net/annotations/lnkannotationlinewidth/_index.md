---
title: lnk 注釈の線幅
linktitle: lnk 注釈の線幅
second_title: Aspose.PDF for .NET API リファレンス
description: この記事では、Aspose.PDF for .NET を使用して lnk 注釈の線幅を設定するためのステップバイステップのガイドを提供します。
type: docs
weight: 110
url: /ja/net/annotations/lnkannotationlinewidth/
---
Aspose.PDF は、.NET アプリケーションで PDF ファイルを操作するための強力で広く使用されているツールです。ページに注釈を追加する機能など、PDF ファイルを作成、編集、操作するためのさまざまな機能が提供されます。このチュートリアルでは、Aspose.PDF for .NET を使用してリンク注釈の線幅を設定する方法を説明します。

これらの前提条件を満たしたら、Visual Studio で新しいコンソール アプリケーション プロジェクトを作成します。次に、ソリューション エクスプローラーでプロジェクトを右クリックし、[NuGet パッケージの管理] を選択して、NuGet パッケージ マネージャーで「Aspose.PDF」を検索して、Aspose.PDF for .NET ライブラリへの参照を追加します。

PDF ドキュメントに lnk 注釈を追加するには、次の手順に従います。

## ステップ 1: 新規作成`Document` object.
```csharp
Document doc = new Document();
```
## ステップ 2: ドキュメントに新しいページを追加します。
```csharp
doc.Pages.Add();
```
## ステップ 3: リストを作成する`Point` arrays that represent the ink gesture for the annotation.
```csharp
IList<Point[]> inkList = new List<Point[]>();
```
## ステップ 4: 新規作成`LineInfo` object that defines the properties of the ink gesture.
```csharp
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
```
## ステップ 5: 新規作成`Aspose.Pdf.Point` array that represents the gesture from the `LineInfo` object.
```csharp
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
    gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}
```
## ステップ 6: インク ジェスチャのリストにジェスチャを追加します。
```csharp
inkList.Add(gesture);
```
## ステップ 7: 新規作成`InkAnnotation` object that represents the link annotation.
```csharp
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
```
## ステップ 8: 注釈の件名とタイトルを設定します。
```csharp
a1.Subject = "Test";
a1.Title = "Title";
```
## ステップ 9: 注釈の色を設定します。
```csharp
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```
## ステップ 10: 新しいファイルを作成する`Border` object that defines the properties of the annotation's border.
```csharp
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
```
## ステップ 11: ページに注釈を追加します。
```csharp
doc.Pages[1].Annotations.Add(a1);
```
## ステップ 12: ドキュメントをファイルに保存します。
```csharp
//出力ファイルを保存する
doc.Save(dataDir);


```
### この例は、Aspose.PDF for .NET を使用した lnk 注釈の線幅を示しています。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
IList<Point[]> inkList = new List<Point[]>();
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}

inkList.Add(gesture);
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
a1.Subject = "Test";
a1.Title = "Title";
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
doc.Pages[1].Annotations.Add(a1);

dataDir = dataDir + "lnkAnnotationLineWidth_out.pdf";
//出力ファイルを保存する
doc.Save(dataDir);
```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメント内のリンク注釈の線幅を設定する方法を学びました。 Aspose.PDF for .NET は、リンク注釈を作成およびカスタマイズする機能など、PDF ドキュメントを操作するための幅広いツールと機能を提供します。ステップバイステップのガイドに従い、提供されている C# ソース コードを使用することで、開発者は PDF ドキュメントにインタラクティブなリンクを簡単に追加でき、アプリケーションのユーザー エクスペリエンスとインタラクティブ性を強化できます。 Aspose.PDF for .NET は、.NET 開発者が PDF ファイルを効率的かつ効果的に操作できるようにする多用途ライブラリです。

### よくある質問

#### Q: PDF ドキュメントのリンク注釈とは何ですか?

A: PDF ドキュメント内のリンク注釈は、同じドキュメント内の別の場所、外部 Web サイト、または別の PDF ドキュメントにユーザーを誘導するハイパーリンクまたはアクションを作成できる対話型要素です。

#### Q: Aspose.PDF for .NET を使用してリンク注釈の線幅を設定するにはどうすればよいですか?

A: Aspose.PDF for .NET を使用してリンク注釈の線幅を設定するには、`InkAnnotation`オブジェクトを選択し、線幅プロパティを指定します。

#### Q: Aspose.PDF for .NET のリンク注釈のどのプロパティをカスタマイズできますか?

A: Aspose.PDF for .NET では、リンク注釈の位置、サイズ、色、境界線のプロパティ (幅、スタイル、破線パターン、効果)、件名、タイトル、表示/非表示など、リンク注釈のさまざまなプロパティをカスタマイズできます。

#### Q: 複数のインク ジェスチャを含むリンク アノテーションを作成できますか?

 A: はい、複数のインク ジェスチャを追加することで、複数のインク ジェスチャを含むリンク アノテーションを作成できます。`Point`配列を`InkAnnotation`物体。

#### Q: PDF ドキュメントの特定のページにリンク注釈を追加するにはどうすればよいですか?

 A: PDF ドキュメントの特定のページにリンク注釈を追加するには、PDF ドキュメントの作成時にページ番号を指定する必要があります。`InkAnnotation`物体。例えば、`new InkAnnotation(doc.Pages[1], ...)`最初のページにリンク注釈を追加します。