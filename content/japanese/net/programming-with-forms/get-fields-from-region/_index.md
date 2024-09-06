---
title: PDF ファイルの領域からフィールドを取得する
linktitle: PDF ファイルの領域からフィールドを取得する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用すると、PDF ファイル内の特定の領域からフィールドを簡単に取得できます。
type: docs
weight: 130
url: /ja/net/programming-with-forms/get-fields-from-region/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイル内の特定の領域のフィールドを取得する方法を説明します。このプロセスをガイドするために、C# ソース コードを段階的に説明します。

## ステップ1: 準備

必要なライブラリがインポートされ、ドキュメント ディレクトリへのパスが設定されていることを確認してください。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ2: PDFファイルを開く

PDF ファイルを開きます:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
```

## ステップ3: 領域を囲む長方形オブジェクトを作成する

フィールドを取得する領域を囲む長方形オブジェクトを作成します。

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
```

## ステップ4: PDFフォームを入手する

ドキュメントの PDF 形式を取得します。

```csharp
Aspose.Pdf.Forms.Form form = doc.Form;
```

## ステップ5: 長方形領域内のフィールドを取得する

指定された長方形領域内にあるフィールドを取得します。

```csharp
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
```

## ステップ6: フィールド名と値を表示する

結果のフィールドを反復処理し、その名前と値を表示します。

```csharp
foreach (Field field in fields)
{
Console.Out.WriteLine("Field name: " + field.FullName + "-" + "Field value: " + field.Value);
}
```

### Aspose.PDF for .NET を使用して領域からフィールドを取得するためのサンプル ソース コード 
```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//PDFファイルを開く
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
//その領域のフィールドを取得するための長方形オブジェクトを作成します
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
//PDFフォームを入手する
Aspose.Pdf.Forms.Form form = doc.Form;
//長方形の領域内のフィールドを取得する
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
//フィールド名と値を表示する
foreach (Field field in fields)
{
	//すべての配置の画像配置プロパティを表示する
	Console.Out.WriteLine("Field Name: " + field.FullName + "-" + "Field Value: " + field.Value);
}
```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメント内の特定の領域のフィールドを取得する方法を学習しました。これらの手順に従うと、Aspose.PDF を使用して PDF ドキュメントの特定の長方形領域にあるフィールドを簡単に抽出できます。

### よくある質問

#### Q: このメソッドを使用して、PDF ドキュメント内の長方形以外の領域からフィールドを取得できますか?

 A: いいえ、提供された方法は`GetFieldsInRect`PDF ドキュメント内の長方形の領域内にあるフィールドを取得するために特別に設計されています。長方形以外の領域からフィールドを抽出する必要がある場合は、フィールドの座標や名前などの他の基準に基づいてフィールドを識別して抽出するカスタム ロジックを実装する必要があります。

#### Q: 別の領域からフィールドを取得するために、四角形のサイズや位置を変更するにはどうすればよいですか?

 A: 別の地域のフィールドを取得するには、`Aspose.Pdf.Rectangle`境界矩形を定義するために使用されるオブジェクトのパラメータ。`Rectangle`コンストラクタは 4 つのパラメータを取ります。`x`, `y`, `width` 、 そして`height`は、四角形の左上隅の座標と寸法を表します。これらのパラメータを調整すると、フィールドが抽出される領域が変更されます。

#### Q: 指定された長方形領域内にフィールドがない場合はどうなりますか?

 A: 指定された長方形領域内にフィールドがない場合、`GetFieldsInRect`メソッドは空の配列を返します。配列の長さをチェックして、領域内にフィールドがあるかどうかを判断できます。

#### Q: PDF ドキュメント内の重複領域からフィールドを取得できますか?

 A: はい、PDF文書内の重複領域からフィールドを取得するには、複数の`Aspose.Pdf.Rectangle`オブジェクトと呼び出し`GetFieldsInRect`それぞれのメソッドを使用します。重複する領域は個別に処理され、領域ごとに個別のフィールド配列が返されます。

#### Q: PDF ドキュメント内の特定のページまたは複数のページからフィールドを取得することは可能ですか?

A: はい、PDF文書内の特定のページまたは複数のページからフィールドを取得できます。これを実現するには、PDF文書を読み込み、`doc.Pages`コレクションを適用し、`GetFieldsInRect`各ページの特定の領域にメソッドを適用します。