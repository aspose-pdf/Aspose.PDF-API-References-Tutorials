---
title: ドキュメントの作成
linktitle: ドキュメントの作成
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用すると、ラジオ ボタン付きのドキュメントを簡単に作成できます。
type: docs
weight: 40
url: /ja/net/programming-with-forms/create-doc/
---
このチュートリアルでは、Aspose.PDF for .NET を使用してラジオ ボタンのあるドキュメントを作成する方法を説明します。このプロセスをガイドするために、C# ソース コードをステップごとに説明します。

##ステップ 1: 準備

まず、必要なライブラリをインポートし、ドキュメント ディレクトリへのパスを設定していることを確認します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: 新しいドキュメントを作成する

PDF ドキュメントを保持する新しい Document オブジェクトを作成します。

```csharp
Document doc = new Document();
```

## ステップ 3: ページを追加する

ドキュメントに新しいページを追加します。

```csharp
Page page = doc.Pages.Add();
```

## ステップ 4: ラジオボタンフィールドを追加する

ラジオ ボタン フィールドを作成し、その位置とサイズを設定します。

```csharp
RadioButtonField field = new RadioButtonField(page);
field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
field. PartialName = "NewField";
```

## ステップ 5: ラジオ ボタン オプションを追加する

ラジオボタンフィールドに必要なオプションを追加します。必要に応じて、各オプションの座標とサイズを設定できます。

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField();
opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
opt1.OptionName = "Item1";
opt1.Border = new Border(opt1);
opt1.Border.Width = 1;
opt1.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt2 = new RadioButtonOptionField();
opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
opt2.OptionName = "Item2";
opt2.Border = new Border(opt2);
opt2.Border.Width = 1;
opt2.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt3 = new RadioButtonOptionField();
opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
opt3.OptionName = "Item3";
opt3.Border = new Border(opt3);
opt3.Border.Width = 1;
opt3.Characteristics.Border = System.Drawing.Color.Black;

field. Add(opt1);
field. Add(opt2);
field. Add(opt3);
```

## ステップ 6: ラジオボタンフィールドをフォームに追加する

ラジオ ボタン フィールドを Document Form Fields コレクションに追加します。

```csharp
doc.Form.Add(field);
```

## ステップ 7: ドキュメントを保存する

PDF ドキュメントを保存します。

```csharp
dataDir = dataDir + "CreateDoc_out.pdf";
doc.Save(dataDir);
```

### Aspose.PDF for .NET を使用してドキュメントを作成するためのサンプル ソース コード 
```csharp
try
{
	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//新しいドキュメントを作成する
	Document doc = new Document();
	Page page = doc.Pages.Add();
	//ラジオボタンフィールドを追加
	RadioButtonField field = new RadioButtonField(page);
	field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
	field.PartialName = "NewField";
	//ラジオボタンのオプションを追加します。これらのオプションは次の場所にあることに注意してください。
	//水平でも垂直でもない。
	//任意の座標 (およびサイズ) を設定してみることができます。
	RadioButtonOptionField opt1 = new RadioButtonOptionField();
	opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
	opt1.OptionName = "Item1";
	opt1.Border = new Border(opt1);
	opt1.Border.Width = 1;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt2 = new RadioButtonOptionField();
	opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
	opt2.OptionName = "Item2";
	opt2.Border = new Border(opt2);
	opt2.Border.Width = 1;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt3 = new RadioButtonOptionField();
	opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
	opt3.OptionName = "Item3";
	opt3.Border = new Border(opt3);
	opt3.Border.Width = 1;
	opt3.Characteristics.Border = System.Drawing.Color.Black;
	field.Add(opt1);
	field.Add(opt2);
	field.Add(opt3);
	doc.Form.Add(field);
	dataDir = dataDir + "CreateDoc_out.pdf";
	// PDF ドキュメントを保存する
	doc.Save(dataDir);
	Console.WriteLine("\nNew doc with 3 items radio button created successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用してラジオ ボタンのあるドキュメントを作成する方法を学びました。次の手順に従うと、Aspose.PDF を使用して PDF ドキュメントにラジオ ボタンを簡単に追加できます。

### よくある質問

#### Q: Aspose.PDF for .NET を使用してドキュメント内のラジオ ボタンの外観をカスタマイズできますか?

A: はい、Aspose.PDF for .NET を使用してドキュメント内のラジオ ボタンの外観をカスタマイズできます。サイズ、色、境界線のスタイルなどのプロパティを設定して、ラジオ ボタンの外観をカスタマイズできます。

#### Q: 相互に排他的なオプションを持つラジオ ボタン グループを追加するにはどうすればよいですか?

A: 相互に排他的なオプションを作成するには、同じ名前の複数のラジオ ボタン フィールドを追加できます。これにより、1 つのオプションが選択されると、同じ名前の他のオプションが自動的に選択解除されます。

#### Q: ラジオ ボタンにデフォルトで選択されているオプションを設定することはできますか?

A: はい、Aspose.PDF for .NET を使用して、ラジオ ボタンにデフォルトで選択されたオプションを設定できます。使用できます`Selected`の財産`RadioButtonOptionField`オブジェクトを使用して、オプションをデフォルトで選択済みとしてマークします。

#### Q: ラジオ ボタンにイベント ハンドラーを追加できますか?

 A: はい、Aspose.PDF for .NET を使用してイベント ハンドラーをラジオ ボタンに追加できます。次のような JavaScript アクションを関連付けることができます。`OnValueChanged`、ユーザーがオプションを選択したときに特定のアクションを実行するラジオ ボタンに追加します。

#### Q: ユーザーが選択した後、ラジオ ボタン グループから選択したオプションを取得するにはどうすればよいですか?

 A: Aspose.PDF for .NET を使用して、ラジオ ボタン グループから選択したオプションを取得できます。ユーザーが選択を行った後、`Selected`の財産`RadioButtonOptionField`オブジェクトを使用して、どのオプションが選択されているかを確認します。