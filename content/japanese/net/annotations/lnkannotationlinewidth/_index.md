---
title: lnk 注釈線幅
linktitle: lnk 注釈線幅
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF のインク注釈の線幅を設定する方法を学びます。この詳細なチュートリアルでは、各手順をガイドし、高品質の出力を保証します。
type: docs
weight: 110
url: /ja/net/annotations/lnkannotationlinewidth/
---
## 導入

PDF ドキュメントを操作する場合、注釈を追加すると、情報を強調表示したり、ファイルにインタラクティブな要素を追加したりするのに非常に役立ちます。そのような注釈の 1 つがインク注釈で、これを使用すると PDF に自由形式の線を描くことができます。しかし、これらの線の外観、特に線の幅をカスタマイズする必要がある場合はどうすればよいでしょうか。このチュートリアルでは、Aspose.PDF for .NET を使用してインク注釈の線の幅を設定する手順を説明します。

## 前提条件

コードに進む前に、このチュートリアルをスムーズに実行できるようにすべて設定されていることを確認しましょう。

1.  Aspose.PDF for .NET: Aspose.PDF for .NETライブラリがインストールされていることを確認してください。[ダウンロードページ](https://releases.aspose.com/pdf/net/)または、Visual Studio の NuGet パッケージ マネージャー経由でインストールします。
2. 開発環境: このチュートリアルでは、Visual Studio などの .NET 開発環境で作業していることを前提としています。
3. C# の基礎知識: C# の基礎的な理解は、コーディング手順を理解するのに役立ちます。
4. PDF ドキュメント: 既存の PDF ドキュメントを使用するか、このチュートリアル用に新しい PDF ドキュメントを作成します。

## 必要な名前空間のインポート

コーディングを始める前に、プロジェクトに必要な名前空間をインポートしてください。

```csharp
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using System;
using System.Collections;
using System.Collections.Generic;
```

これらの名前空間は、PDF ドキュメントの操作、注釈の操作、グラフィカル要素の処理に必要なクラスとメソッドを提供します。

前提条件が整ったので、インク注釈の線幅を設定するプロセスを明確で管理しやすいステップに分解してみましょう。

## ステップ1: PDFドキュメントを初期化する

まず、PDF ドキュメントを作成するか開く必要があります。このチュートリアルでは、最初から新しい PDF ドキュメントを作成します。

```csharp
// PDFドキュメントを初期化する
string dataDir = "YOUR DOCUMENT DIRECTORY"; //ドキュメントディレクトリを指定する
Document doc = new Document();
doc.Pages.Add(); //ドキュメントに空白ページを追加する
```

ここでは、新しい`Document`オブジェクトは PDF ファイルを表します。次に、このドキュメントに作業用の空白ページを追加します。

## ステップ2: インク注釈を作成する

次に、インク注釈自体を作成します。これには、インク ストロークを構成するポイントの定義が含まれます。

```csharp
//インク注釈を作成する
IList<Point[]> inkList = new List<Point[]>();
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = Color.Red;
lineInfo.LineWidth = 2;
```

このステップでは、`LineInfo`オブジェクトは、インクストロークの座標、可視性、色、初期の線幅を保持します。`VerticeCoordinate`配列には、ストローク内の各ポイントの X 座標と Y 座標が含まれます。

## ステップ3: 座標をポイントに変換する

ここで、これらの座標をインク注釈で使用できるポイントに変換する必要があります。

```csharp
//座標をポイントに変換する
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
    gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}

inkList.Add(gesture);
```

このループは座標配列を処理し、各座標のペアを`Point`オブジェクトは、その後、`inkList`.

## ステップ4: PDFページにインク注釈を追加する

ポイントの準備ができたら、インク注釈を作成して PDF ページに追加できます。

```csharp
// PDFページにインク注釈を追加する
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
a1.Subject = "Test";
a1.Title = "Title";
a1.Color = Aspose.Pdf.Color.FromRgb(Color.Green);
```

このステップでは、`InkAnnotation`オブジェクトを作成し、ページ、境界の四角形、ポイントのリストを指定します。注釈の件名、タイトル、色も設定します。

## ステップ5: 注釈の境界線をカスタマイズする

注釈の外観をさらにカスタマイズするには、境界線のプロパティを変更します。

```csharp
//注釈の境界線をカスタマイズする
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
doc.Pages[1].Annotations.Add(a1);
```

ここでは、`Border`注釈のオブジェクトを作成し、幅、効果、破線パターン、スタイルを設定します。この手順により、注釈が PDF ページ上で視覚的に目立つようになります。

## ステップ6: PDFドキュメントを保存する

最後に、必要な変更をすべて行ったら、ドキュメントを保存します。

```csharp
// PDF文書を保存する
dataDir = dataDir + "lnkAnnotationLineWidth_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nInk annotation line width setup successfully.\nFile saved at " + dataDir);
```

このコードは、インク注釈付きの修正されたPDF文書を指定されたディレクトリに保存します。`Console.WriteLine`ステートメントは、コードが正常に実行されたことを確認します。

## 結論

おめでとうございます! Aspose.PDF for .NET を使用して、PDF ドキュメントにインク注釈を作成し、カスタマイズすることができました。このチュートリアルでは、ドキュメントの初期化から最終ファイルの保存まで、プロセス全体を説明しました。この知識があれば、Aspose.PDF for .NET の幅広い機能をさらに探求し、同様の手法を他の種類の注釈や PDF 操作に適用することができます。

## よくある質問

### インク注釈の異なる部分に異なる色を使用できますか?  
はい、複数作成できます`InkAnnotation`オブジェクトを異なる色で分割し、PDF の同じページまたは別のページに追加します。

### 線の幅を動的に変更するにはどうすればよいですか?  
調整することができます`LineWidth`の財産`LineInfo`座標をポイントに変換する前にオブジェクトを作成します。

### インク注釈を透明にすることは可能ですか?  
はい、変更できます`Opacity`の財産`InkAnnotation`オブジェクトを透明にします。

### 同じページに複数のインク注釈を追加できますか?  
もちろんです! このプロセスを繰り返すことで、1 ページに好きなだけインク注釈を追加できます。

### PDF からインク注釈を削除するにはどうすればよいですか?  
注釈を削除するには、`doc.Pages[1].Annotations.Delete(a1)`方法、ここで`a1`注釈オブジェクトです。