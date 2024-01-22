---
title: ラジオボタンのキャプションを設定する
linktitle: ラジオボタンのキャプションを設定する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF フォームのラジオ ボタンのキャプションを設定する方法を学習します。
type: docs
weight: 280
url: /ja/net/programming-with-forms/set-radio-button-caption/
---
このガイドでは、.NET 用の Aspose.PDF ライブラリを使用して PDF フォームのラジオ ボタンのキャプションを定義する方法を段階的に説明します。ラジオ ボタン フィールドにアクセスし、新しいラジオ ボタン オプションを作成し、ボタンのキャプションをカスタマイズする方法を示します。

## ステップ 1: ドキュメント ディレクトリの構成

最初のステップは、作業対象の PDF フォームが配置されるドキュメント ディレクトリを構成することです。使用できます`dataDir`ディレクトリパスを指定する変数。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

必ず交換してください`"YOUR DOCUMENTS DIRECTORY"`ドキュメントディレクトリへの実際のパスを含めます。

## ステップ 2: ソース PDF フォームをロードする

このステップでは、`Aspose.Pdf.Facades.Form` Aspose.PDF のクラス。

```csharp
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
```

フォームを含む PDF ファイルが指定されたドキュメント ディレクトリに存在することを確認してください。

## ステップ 3: ラジオボタンのキャプションを編集する

フォームフィールド名をループして、ラジオボタンフィールドを検索します。一致するフィールドが見つかった場合は、カスタム キャプションを含む新しいラジオ ボタン オプションを作成し、既存のフィールドに追加します。

```csharp
foreach(var item in form1.FieldNames)
{
if (item.Contains("radio1"))
{
Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
fieldoption.OptionName = "Yes";
fieldoption.PartialName = "Yesname";
var updatedFragment = new Aspose.Pdf.Text.TextFragment("test123");
updatedFragment.TextState.Font = FontRepository.FindFont("Arial");
updatedFragment.TextState.FontSize = 10;
updatedFragment.TextState.LineSpacing = 6.32f;
// TextParagraph オブジェクトを作成する
TextParagraph par = new TextParagraph();
//段落位置を設定する
par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
//ワードラップモードを指定する
by.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
//新しい TextFragment を段落に追加します
par.AppendLine(updatedFragment);
//TextBuilder を使用して TextParagraph を追加する
TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
textBuilder.AppendParagraph(par);
field0.DeleteOption("item1");
}
}
```

必要に応じて、キャプションのラジオ ボタンやその他の設定をカスタマイズします。

## ステップ 4: 結果の PDF を保存する

ラジオ ボタンのキャプションの変更が完了したので、結果の PDF を次のコマンドを使用して保存できます。`Save`の方法`Document`クラス。

```csharp
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

生成される PDF の絶対パスとファイル名を必ず指定してください。

### Aspose.PDF for .NET を使用したラジオ ボタン キャプションの設定のサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ソース PDF フォームをロードする
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
Document PDF_Template_PDF_HTML = new Document(dataDir + "RadioButtonField.pdf");
foreach (var item in form1.FieldNames)
{
	Console.WriteLine(item.ToString());
	Dictionary<string, string> radioOptions = form1.GetButtonOptionValues(item);
	if (item.Contains("radio1"))
	{
		Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
		Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
		fieldoption.OptionName = "Yes";
		fieldoption.PartialName = "Yesname";
		var updatedFragment = new Aspose.Pdf.Text.TextFragment("test123");
		updatedFragment.TextState.Font = FontRepository.FindFont("Arial");
		updatedFragment.TextState.FontSize = 10;
		updatedFragment.TextState.LineSpacing = 6.32f;
		//TextParagraph オブジェクトを作成する
		TextParagraph par = new TextParagraph();
		//段落位置を設定する
		par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
		//ワードラップモードを指定する
		par.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
		//新しい TextFragment を段落に追加します
		par.AppendLine(updatedFragment);
		//TextBuilder を使用して TextParagraph を追加する
		TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
		textBuilder.AppendParagraph(par);
		field0.DeleteOption("item1");
	}
}
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

## 結論

このガイドでは、.NET 用の Aspose.PDF ライブラリを使用して、PDF フォームのラジオ ボタンのキャプションを設定する方法を学習しました。説明されている手順に従うことで、ラジオ ボタンのオプションをカスタマイズし、必要に応じてキャプションを変更できます。 PDF ファイルの操作の可能性を広げるために、Aspose.PDF for .NET の機能を自由にさらに探索してください。

### よくある質問

#### Q: Aspose.PDF for .NET を使用して PDF フォームのラジオ ボタンのキャプションを設定できますか?

A: はい、Aspose.PDF for .NET を使用して、PDF フォームのラジオ ボタンのキャプションを設定できます。提供されているサンプル ソース コードは、ラジオ ボタン フィールドにアクセスし、カスタム キャプションを持つ新しいラジオ ボタン オプションを作成し、既存のフィールドを更新する方法を示しています。

#### Q: フォント サイズや色など、ラジオ ボタンのキャプションの外観をカスタマイズするにはどうすればよいですか?

 A: ラジオ ボタンのキャプションの外観をカスタマイズするには、`TextFragment`キャプションに使用されます。たとえば、フォント、フォント サイズ、色、行間隔、その他のテキスト書式設定オプションを設定できます。

#### Q: 異なるキャプションを持つ複数のラジオ ボタン オプションを 1 つのラジオ ボタン グループに追加することはできますか?

A: はい、異なるキャプションを持つ複数のラジオ ボタン オプションを 1 つのラジオ ボタン グループに追加できます。各オプションは異なる選択肢を表し、ユーザーはグループからオプションを 1 つだけ選択できます。

#### Q: Aspose.PDF for .NET を使用して PDF ドキュメント内の他のフォーム フィールドを変更できますか?

A: はい。Aspose.PDF for .NET は、テキスト フィールド、チェックボックス、ドロップダウン リストなど、PDF ドキュメント内のさまざまなフォーム フィールドを操作するための包括的な機能セットを提供します。このライブラリを使用すると、値の設定、外観の変更、フォーム フィールドへの対話機能の追加ができます。

#### Q: Aspose.PDF for .NET は、スキャンされたドキュメントなど、他のソースから生成された PDF の操作をサポートしていますか?

A: はい、Aspose.PDF for .NET は、スキャンされたドキュメントを含むさまざまなソースから生成された PDF の操作をサポートしています。このライブラリは、スキャンされた PDF からテキストを抽出し、プログラムでコンテンツを操作するための OCR (光学文字認識) 機能を提供します。