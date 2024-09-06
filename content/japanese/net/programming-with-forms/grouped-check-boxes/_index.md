---
title: PDF ドキュメント内のグループ化されたチェックボックス
linktitle: PDF ドキュメント内のグループ化されたチェックボックス
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用すると、PDF ドキュメントにグループ化されたチェックボックスを簡単に作成できます。
type: docs
weight: 170
url: /ja/net/programming-with-forms/grouped-check-boxes/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントにグループ化されたチェックボックスを作成する方法を説明します。このプロセスをガイドするために、C# ソース コードを段階的に説明します。

## ステップ1: 準備

必要なライブラリがインポートされ、ドキュメント ディレクトリへのパスが設定されていることを確認してください。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ2: ドキュメントオブジェクトのインスタンスを作成する

Document オブジェクトをインスタンス化します。

```csharp
Document pdfDocument = new Document();
```

## ステップ3: PDF文書にページを追加する

PDF ドキュメントにページを追加します。

```csharp
Page page = pdfDocument.Pages.Add();
```

## ステップ4: RadioButtonFieldオブジェクトのインスタンスを作成する

ページ番号を引数として RadioButtonField オブジェクトをインスタンス化します。

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## ステップ5: ラジオボタンオプションを追加する

RadioButtonOptionField オブジェクトを使用してラジオ ボタン オプションを追加し、Rectangle オブジェクトを使用してその位置を指定します。

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
opt1.OptionName = "Test1";
opt2.OptionName = "Test2";
radio.Add(opt1);
radio.Add(opt2);
```

## ステップ6: ラジオボタンのオプションをカスタマイズする

スタイル、境界線、外観を設定してラジオ ボタン オプションをカスタマイズします。

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

## ステップ7: フォームにラジオボタンを追加する

ドキュメント フォーム オブジェクトにラジオ ボタンを追加します。

```csharp
pdfDocument.Form.Add(radio);
```

## ステップ8: ドキュメントを保存する

PDF ドキュメントを保存します。

```csharp
dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
pdfDocument.Save(dataDir);
```

### Aspose.PDF for .NET を使用したグループ化されたチェックボックスのサンプル ソース コード 
```csharp
try
{
	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Documentオブジェクトをインスタンス化する
	Document pdfDocument = new Document();
	//PDFファイルにページを追加する
	Page page = pdfDocument.Pages.Add();
	//ページ番号を引数としてRadioButtonFieldオブジェクトをインスタンス化する
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	//最初のラジオボタンオプションを追加し、Rectangleオブジェクトを使用してその原点も指定します。
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
	// Document オブジェクトのフォーム オブジェクトにラジオ ボタンを追加します。
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
	// PDF文書を保存する
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nGrouped checkboxes added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントにグループ化されたチェックボックスを作成する方法を学習しました。これらの手順に従うことで、カスタム ラジオ ボタン オプションを簡単に追加し、Aspose.PDF を使用して PDF ドキュメントにバンドルすることができます。

### よくある質問

#### Q: PDF ドキュメント内のグループ化されたチェックボックスとは何ですか?

A: PDF ドキュメント内のグループ化されたチェックボックスは、グループ化されたラジオ ボタン オプションのセットを指します。ラジオ ボタンを使用すると、ユーザーは相互に排他的な選択肢のグループから 1 つのオプションのみを選択できます。1 つのラジオ ボタンが選択されると、同じグループ内の他のラジオ ボタンは自動的に選択解除されます。このグループ化の動作は、ユーザーに複数のオプションを提示しながら、選択を 1 つの選択肢のみに制限する場合に便利です。

#### Q: Aspose.PDF for .NET でグループ化されたチェックボックスの外観をカスタマイズできますか?

A: はい、Aspose.PDF for .NET ではグループ化されたチェックボックスの外観をカスタマイズできます。API には、ラジオ ボタン オプションのスタイル、境界線、外観を設定するためのさまざまなオプションが用意されています。各オプションの位置を定義し、さまざまなボックス スタイル (四角形、円、十字など) を選択し、境界線のプロパティを調整して、希望する視覚的表現を実現できます。

#### Q: PDF ドキュメントの特定のページにグループ化されたチェックボックスを追加するにはどうすればよいですか?

A: PDF文書の特定のページにグループ化されたチェックボックスを追加するには、`RadioButtonField`希望するページ番号を引数としてオブジェクトを作成します。次に、`RadioButtonOptionField`各ラジオボタンオプションを表すオブジェクトを作成し、その位置を`Rectangle`オブジェクト。最後に、これらのオプションを`RadioButtonField`必要に応じて外観をカスタマイズし、`RadioButtonField`ドキュメントフォームに。

#### Q: 1 つの PDF ドキュメントに複数のチェックボックス グループを追加できますか?

 A: はい、1つのPDF文書に複数のチェックボックスのグループを追加できます。各グループには固有のチェックボックスが必要です。`RadioButtonField`オブジェクト、および`RadioButtonOptionField`各グループ内のオブジェクトは同じページを共有し、オプションに一意の名前を使用する必要があります。これにより、各グループ内のラジオ ボタンが正しく機能し、選択が相互に排他的になります。

#### Q: グループ化されたチェックボックスはすべての PDF ビューアとアプリケーションでサポートされていますか?

A: はい、グループ化されたチェックボックスは、標準に準拠したすべての PDF ビューアとアプリケーションでサポートされています。PDF 仕様では、ラジオ ボタンとそのグループ化の動作が定義されており、PDF 形式では普遍的に認識されます。ただし、さまざまなプラットフォーム間で一貫した動作を保証するには、さまざまな PDF ビューアで機能をテストすることが重要です。