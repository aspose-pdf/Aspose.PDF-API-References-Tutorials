---
title: ラジオボタンのキャプションを設定する
linktitle: ラジオボタンのキャプションを設定する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF フォームのラジオ ボタンのキャプションを設定する方法を学習します。
type: docs
weight: 280
url: /ja/net/programming-with-forms/set-radio-button-caption/
---
このガイドでは、.NET 用の Aspose.PDF ライブラリを使用して PDF フォームのラジオ ボタンのキャプションを定義する方法を段階的に説明します。ラジオ ボタン フィールドにアクセスし、新しいラジオ ボタン オプションを作成し、ボタンのキャプションをカスタマイズする方法を説明します。

## ステップ1: ドキュメントディレクトリの構成

最初のステップは、作業したいPDFフォームが保存されているドキュメントディレクトリを設定することです。`dataDir`ディレクトリ パスを指定する変数。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

必ず交換してください`"YOUR DOCUMENTS DIRECTORY"`ドキュメント ディレクトリへの実際のパスを入力します。

## ステップ2: ソースPDFフォームの読み込み

このステップでは、ソースPDFフォームを読み込み、`Aspose.Pdf.Facades.Form` Aspose.PDF のクラス。

```csharp
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
```

フォームを含む PDF ファイルが指定されたドキュメント ディレクトリに存在することを確認します。

## ステップ3: ラジオボタンのキャプションを編集する

フォーム フィールド名をループしてラジオ ボタン フィールドを検索します。一致するフィールドが見つかった場合は、カスタム キャプション付きの新しいラジオ ボタン オプションを作成し、既存のフィールドに追加します。

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
// TextParagraphオブジェクトを作成する
TextParagraph par = new TextParagraph();
//段落の位置を設定する
par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
//単語の折り返しモードを指定する
by.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
//段落に新しいTextFragmentを追加します
par.AppendLine(updatedFragment);
//TextBuilderを使用してTextParagraphを追加する
TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
textBuilder.AppendParagraph(par);
field0.DeleteOption("item1");
}
}
```

必要に応じて、キャプションのラジオ ボタンやその他の設定をカスタマイズします。

## ステップ4: 結果のPDFを保存する

ラジオボタンのキャプションの変更が完了したら、結果のPDFを`Save`方法の`Document`クラス。

```csharp
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

結果の PDF の完全なパスとファイル名を必ず指定してください。

### Aspose.PDF for .NET を使用してラジオ ボタンのキャプションを設定するサンプル ソース コード 
```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ソースPDFフォームを読み込む
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
		//TextParagraphオブジェクトを作成する
		TextParagraph par = new TextParagraph();
		//段落の位置を設定する
		par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
		//単語の折り返しモードを指定する
		par.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
		//段落に新しい TextFragment を追加する
		par.AppendLine(updatedFragment);
		//TextBuilderを使用してTextParagraphを追加する
		TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
		textBuilder.AppendParagraph(par);
		field0.DeleteOption("item1");
	}
}
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

## 結論

このガイドでは、Aspose.PDF ライブラリ for .NET を使用して PDF フォームのラジオ ボタンのキャプションを設定する方法を学習しました。説明されている手順に従うことで、ラジオ ボタンのオプションをカスタマイズし、必要に応じてキャプションを変更できます。Aspose.PDF for .NET の機能をさらに詳しく調べて、PDF ファイルの操作の可能性を広げてください。

### よくある質問

#### Q: Aspose.PDF for .NET を使用して PDF フォームのラジオ ボタンのキャプションを設定できますか?

A: はい、Aspose.PDF for .NET を使用して PDF フォームのラジオ ボタンのキャプションを設定できます。提供されているサンプル ソース コードは、ラジオ ボタン フィールドにアクセスし、カスタム キャプションを使用して新しいラジオ ボタン オプションを作成し、既存のフィールドを更新する方法を示しています。

#### Q: ラジオ ボタンのキャプションの外観 (フォント サイズや色など) をカスタマイズするにはどうすればよいですか?

 A: ラジオボタンのキャプションの外観は、プロパティを調整することでカスタマイズできます。`TextFragment`キャプションに使用されます。たとえば、フォント、フォント サイズ、色、行間、その他のテキスト書式設定オプションを設定できます。

#### Q: 異なるキャプションを持つ複数のラジオ ボタン オプションを 1 つのラジオ ボタン グループに追加することは可能ですか?

A: はい、異なるキャプションを持つ複数のラジオ ボタン オプションを 1 つのラジオ ボタン グループに追加できます。各オプションは異なる選択肢を表し、ユーザーはグループから 1 つのオプションのみを選択できます。

#### Q: Aspose.PDF for .NET を使用して PDF ドキュメント内の他のフォーム フィールドを変更できますか?

A: はい、Aspose.PDF for .NET は、テキスト フィールド、チェックボックス、ドロップダウン リストなど、PDF ドキュメント内のさまざまなフォーム フィールドを操作するための包括的な機能セットを提供します。ライブラリを使用して、値の設定、外観の変更、フォーム フィールドへのインタラクションの追加を行うことができます。

#### Q: Aspose.PDF for .NET は、スキャンされたドキュメントなど、他のソースから生成された PDF の操作をサポートしていますか?

A: はい、Aspose.PDF for .NET は、スキャンされたドキュメントを含むさまざまなソースから生成された PDF の操作をサポートしています。ライブラリは、スキャンされた PDF からテキストを抽出し、そのコンテンツをプログラムで操作するための OCR (光学式文字認識) 機能を提供します。