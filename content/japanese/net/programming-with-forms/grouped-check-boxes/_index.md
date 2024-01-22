---
title: PDF ドキュメント内のグループ化されたチェック ボックス
linktitle: PDF ドキュメント内のグループ化されたチェック ボックス
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用すると、PDF ドキュメント内にグループ化されたチェックボックスを簡単に作成できます。
type: docs
weight: 170
url: /ja/net/programming-with-forms/grouped-check-boxes/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメント内にグループ化されたチェックボックスを作成する方法を説明します。このプロセスをガイドするために、C# ソース コードをステップごとに説明します。

## ステップ 1: 準備

必要なライブラリをインポートし、ドキュメント ディレクトリへのパスを設定していることを確認してください。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ 2: ドキュメント オブジェクトをインスタンス化する

Document オブジェクトをインスタンス化します。

```csharp
Document pdfDocument = new Document();
```

## ステップ 3: PDF ドキュメントにページを追加する

PDF ドキュメントにページを追加します。

```csharp
Page page = pdfDocument.Pages.Add();
```

## ステップ 4: RadioButtonField オブジェクトをインスタンス化する

ページ番号を引数として RadioButtonField オブジェクトをインスタンス化します。

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## ステップ 5: ラジオ ボタン オプションを追加する

RadioButtonOptionField オブジェクトを使用してラジオ ボタン オプションを追加し、Rectangle オブジェクトを使用してその位置を指定します。

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
opt1.OptionName = "Test1";
opt2.OptionName = "Test2";
radio.Add(opt1);
radio.Add(opt2);
```

## ステップ 6: ラジオ ボタン オプションをカスタマイズする

ラジオ ボタンのオプションをカスタマイズするには、スタイル、境界線、外観を設定します。

```csharp
opt1.Style = BoxStyle.Square;
opt2.Style = BoxStyle.Square;
opt1.Border = new Border(opt1);
opt1.Border.Style = BorderStyle.Solid;
opt1.Border.Width = 1;
opt2.Border = new Border(opt2);
opt2.Border.Width = 1;
opt2.Border.Style = BorderStyle.Solid;
```

## ステップ 7: フォームにラジオ ボタンを追加する

ラジオ ボタンをドキュメント フォーム オブジェクトに追加します。

```csharp
pdfDocument.Form.Add(radio);
```

## ステップ 8: ドキュメントを保存する

PDF ドキュメントを保存します。

```csharp
dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
pdfDocument.Save(dataDir);
```

### Aspose.PDF for .NET を使用したグループ化チェック ボックスのサンプル ソース コード 
```csharp
try
{
	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//Documentオブジェクトをインスタンス化する
	Document pdfDocument = new Document();
	//PDF ファイルにページを追加する
	Page page = pdfDocument.Pages.Add();
	//ページ番号を引数として RadioButtonField オブジェクトをインスタンス化します。
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	//最初のラジオ ボタン オプションを追加し、Rectangle オブジェクトを使用してその原点も指定します
	RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
	RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
	opt1.OptionName = "Test1";
	opt2.OptionName = "Test2";
	radio.Add(opt1);
	radio.Add(opt2);
	opt1.Style = BoxStyle.Square;
	opt2.Style = BoxStyle.Square;
	opt1.Style = BoxStyle.Cross;
	opt2.Style = BoxStyle.Cross;
	opt1.Border = new Border(opt1);
	opt1.Border.Style = BorderStyle.Solid;
	opt1.Border.Width = 1;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	opt2.Border = new Border(opt2);
	opt2.Border.Width = 1;
	opt2.Border.Style = BorderStyle.Solid;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	//Documentオブジェクトのフォームオブジェクトにラジオボタンを追加
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
	// PDF ドキュメントを保存する
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nGrouped checkboxes added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメント内にグループ化されたチェックボックスを作成する方法を学びました。これらの手順に従うことで、カスタム ラジオ ボタン オプションを簡単に追加し、Aspose.PDF を使用して PDF ドキュメントにバンドルすることができます。

### よくある質問

#### Q: PDF ドキュメント内のグループ化されたチェックボックスとは何ですか?

A: PDF ドキュメント内のグループ化されたチェックボックスは、グループ化された一連のラジオ ボタン オプションを指します。ラジオ ボタンを使用すると、ユーザーは相互に排他的な選択肢のグループから 1 つのオプションだけを選択できます。 1 つのラジオ ボタンを選択すると、同じグループ内の他のラジオ ボタンは自動的に選択解除されます。このグループ化動作は、ユーザーに複数のオプションを提示しながら、ユーザーの選択を 1 つの選択肢のみに制限したい場合に便利です。

#### Q: Aspose.PDF for .NET でグループ化されたチェックボックスの外観をカスタマイズできますか?

A: はい、Aspose.PDF for .NET でグループ化されたチェックボックスの外観をカスタマイズできます。 API には、ラジオ ボタン オプションのスタイル、境界線、外観を設定するためのさまざまなオプションが用意されています。各オプションの位置を定義し、さまざまなボックス スタイル (正方形、円、十字など) から選択し、境界線のプロパティを調整して目的の視覚的表現を実現できます。

#### Q: グループ化されたチェックボックスを PDF ドキュメントの特定のページに追加するにはどうすればよいですか?

A: グループ化されたチェックボックスを PDF ドキュメントの特定のページに追加するには、`RadioButtonField`引数として目的のページ番号を持つオブジェクト。次に、作成します`RadioButtonOptionField`各ラジオ ボタン オプションを表すオブジェクトを作成し、`Rectangle`物体。最後に、これらのオプションを`RadioButtonField`を追加する前に、必要に応じて外観をカスタマイズします。`RadioButtonField`書類フォームへ。

#### Q: 複数のチェックボックスのグループを 1 つの PDF ドキュメントに追加できますか?

 A: はい、複数のチェックボックスのグループを 1 つの PDF ドキュメントに追加できます。各グループには固有の`RadioButtonField`オブジェクトと、`RadioButtonOptionField`各グループ内のオブジェクトは、同じページとオプションの一意の名前を共有する必要があります。これにより、各グループ内のラジオ ボタンが正しく機能し、選択が相互に排他的になることが保証されます。

#### Q: グループ化されたチェックボックスは、すべての PDF ビューアおよびアプリケーションでサポートされていますか?

A: はい、グループ化されたチェックボックスは、標準に準拠したすべての PDF ビューアとアプリケーションでサポートされています。 PDF 仕様では、ラジオ ボタンとそのグループ化動作が定義されており、PDF 形式でラジオ ボタンが広く認識されるようになります。ただし、さまざまなプラットフォーム間で一貫した動作を保証するには、さまざまな PDF ビューアで機能をテストすることが不可欠です。