---
title: PDF ファイルの領域からフィールドを取得
linktitle: PDF ファイルの領域からフィールドを取得
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用すると、PDF ファイルの特定の領域からフィールドを簡単に取得できます。
type: docs
weight: 130
url: /ja/net/programming-with-forms/get-fields-from-region/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイル内の特定の領域のフィールドを取得する方法を説明します。このプロセスをガイドするために、C# ソース コードをステップごとに説明します。

## ステップ 1: 準備

必要なライブラリをインポートし、ドキュメント ディレクトリへのパスを設定していることを確認してください。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ 2: PDF ファイルを開く

PDF ファイルを開きます。

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
```

## ステップ 3: 領域を境界付ける長方形オブジェクトを作成する

フィールドを取得する領域を境界付ける長方形オブジェクトを作成します。

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
```

## ステップ 4: PDF フォームを入手する

ドキュメントの PDF 形式を取得します。

```csharp
Aspose.Pdf.Forms.Form form = doc.Form;
```

## ステップ 5: 長方形領域内のフィールドを取得する

指定された長方形領域にあるフィールドを取得します。

```csharp
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
```

## ステップ 6: フィールド名と値を表示する

結果のフィールドを反復処理して、その名前と値を表示します。

```csharp
foreach (Field field in fields)
{
Console.Out.WriteLine("Field name: " + field.FullName + "-" + "Field value: " + field.Value);
}
```

### Aspose.PDF for .NET を使用した領域からフィールドを取得するためのサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//PDFファイルを開く
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
//四角形オブジェクトを作成してその領域のフィールドを取得します
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
//PDFフォームを入手
Aspose.Pdf.Forms.Form form = doc.Form;
//長方形の領域内のフィールドを取得します
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
//表示フィールド名と値
foreach (Field field in fields)
{
	//すべての配置の画像配置プロパティを表示する
	Console.Out.WriteLine("Field Name: " + field.FullName + "-" + "Field Value: " + field.Value);
}
```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメント内の特定の領域のフィールドを取得する方法を学びました。これらの手順に従うと、Aspose.PDF を使用して PDF ドキュメントの特定の長方形領域にあるフィールドを簡単に抽出できます。

### よくある質問

#### Q: このメソッドを使用して、PDF ドキュメント内の非長方形領域からフィールドを取得できますか?

 A: いいえ、提供されている方法です`GetFieldsInRect`は、PDF ドキュメント内の長方形領域内にあるフィールドを取得するように特別に設計されています。非長方形領域からフィールドを抽出する必要がある場合は、フィールド座標や名前などの他の基準に基づいてフィールドを識別し、抽出するカスタム ロジックを実装する必要があります。

#### Q: 四角形のサイズや位置を変更して、別の領域からフィールドを取得するにはどうすればよいですか?

 A: 別のリージョンからフィールドを取得するには、`Aspose.Pdf.Rectangle`外接する四角形を定義するために使用されるオブジェクトのパラメータ。の`Rectangle`コンストラクターは 4 つのパラメーターを取ります。`x`, `y`, `width` 、 そして`height`、左上隅の座標と長方形の寸法を表します。これらのパラメータを調整すると、フィールドが抽出される領域が変更されます。

#### Q: 指定された長方形の領域内にフィールドがない場合はどうなりますか?

 A: 指定された長方形の領域内にフィールドがない場合、`GetFieldsInRect`メソッドは空の配列を返します。配列の長さをチェックして、領域内にフィールドがあるかどうかを判断できます。

#### Q: PDF ドキュメント内の重複する領域からフィールドを取得できますか?

 A: はい、複数のファイルを作成することで、PDF ドキュメント内の重複する領域からフィールドを取得できます。`Aspose.Pdf.Rectangle`オブジェクトと呼び出し`GetFieldsInRect`それぞれの方法です。重複する領域は個別に処理され、領域ごとに個別のフィールド配列を受け取ります。

#### Q: PDF ドキュメント内の特定のページまたは複数のページからフィールドを取得することはできますか?

A: はい、PDF ドキュメント内の特定のページまたは複数のページからフィールドを取得できます。これを実現するには、PDF ドキュメントをロードし、`doc.Pages`コレクションを作成してから、`GetFieldsInRect`各ページの特定の領域にメソッドを追加します。