---
title: テキストボックス
linktitle: テキストボックス
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ドキュメントにテキスト フィールドを作成する方法を学習します。
type: docs
weight: 290
url: /ja/net/programming-with-forms/text-box/
---
このガイドでは、.NET 用の Aspose.PDF ライブラリを使用して PDF ドキュメントにテキスト フィールドを作成する方法を段階的に説明します。ドキュメントを開き、テキスト フィールドを作成し、そのプロパティをカスタマイズし、編集した PDF を保存する方法を説明します。

## ステップ1: ドキュメントディレクトリの構成

最初のステップは、作業したいPDFファイルが保存されているドキュメントディレクトリを設定することです。`dataDir`ディレクトリ パスを指定する変数。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

必ず交換してください`"YOUR DOCUMENTS DIRECTORY"`ドキュメント ディレクトリへの実際のパスを入力します。

## ステップ2: PDF文書を開く

このステップでは、`Document` Aspose.PDF のクラス。

```csharp
Document pdfDocument = new Document(dataDir + "TextField.pdf");
```

指定されたドキュメント ディレクトリに PDF ファイルが存在することを確認します。

## ステップ3: テキストフィールドの作成

テキストフィールドを作成するには、`TextBoxField`クラス。位置座標とフィールドサイズは、`Rectangle`クラス。

```csharp
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField. PartialName = "textbox1";
textBoxField.Value = "Text Field";
```

必要に応じて、座標、サイズ、部分的な名前、テキスト フィールドの値をカスタマイズします。

## ステップ4: テキストフィールドのプロパティをカスタマイズする

このステップでは、境界線や色などのテキスト フィールドのプロパティをカスタマイズします。

```csharp
Border border = new Border(textBoxField);
border. width = 5;
border. Dash = new Dash(1, 1);
textBoxField. Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```

好みに応じてテキスト フィールドのプロパティをカスタマイズします。

## ステップ5: ドキュメントにフィールドを追加する

テキスト フィールドを作成して構成したので、それを PDF ドキュメントに追加できます。

```csharp
pdfDocument.Form.Add(textBoxField, 1);
```

## ステップ6: 変更したPDFを保存する

最後に、変更したPDFを`Save`方法の`Document`クラス。

```csharp
dataDir = dataDir + "TextBox_out.pdf";
pdfDocument.Save(dataDir);
```

編集した PDF の完全なパスとファイル名を必ず指定してください。

### Aspose.PDF for .NET を使用したテキスト ボックスのサンプル ソース コード 
```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ドキュメントを開く
Document pdfDocument = new Document(dataDir + "TextField.pdf");
//フィールドを作成する
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField.PartialName = "textbox1";
textBoxField.Value = "Text Box";
//TextBoxField.Border = 新しいBorder(
Border border = new Border(textBoxField);
border.Width = 5;
border.Dash = new Dash(1, 1);
textBoxField.Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
//ドキュメントにフィールドを追加する
pdfDocument.Form.Add(textBoxField, 1);
dataDir = dataDir + "TextBox_out.pdf";
//変更したPDFを保存
pdfDocument.Save(dataDir);
Console.WriteLine("\nTextbox field added successfully.\nFile saved at " + dataDir);
```

## 結論

このガイドでは、Aspose.PDF ライブラリ for .NET を使用して PDF ドキュメントにテキスト フィールドを作成する方法を学習しました。説明されている手順に従うことで、テキスト フィールドのプロパティをカスタマイズし、必要に応じてドキュメントに追加できます。Aspose.PDF for .NET の機能をさらに詳しく調べて、PDF ファイルの操作の可能性を広げてください。

### よくある質問

#### Q: Aspose.PDF for .NET を使用して、単一の PDF ドキュメント内に複数のテキスト フィールドを作成できますか?

A: はい、Aspose.PDF for .NET を使用して、1 つの PDF ドキュメントに複数のテキスト フィールドを作成できます。ドキュメント内の目的の場所ごとに、テキスト フィールドの作成とカスタマイズのプロセスを繰り返すだけです。

#### Q: フォントサイズや色など、テキストフィールドの外観をカスタマイズするにはどうすればよいですか?

A: テキスト フィールドの外観は、フォント サイズ、フォント スタイル、色、境界線のスタイル、背景色などのプロパティを調整することでカスタマイズできます。提供されているサンプル ソース コードでは、境界線の幅、境界線の破線パターン、テキストの色がカスタマイズされています。

#### Q: 作成されたテキスト フィールドからユーザーが入力したテキストを抽出することは可能ですか?

A: はい、作成されたテキスト フィールドからユーザーが入力したテキストを抽出できます。ユーザーが PDF ドキュメントのテキスト フィールドに入力した後、Aspose.PDF for .NET を使用してプログラムでフィールド値を取得できます。

#### Q: 新しい PDF ドキュメントを作成せずに、既存の PDF ドキュメントにテキスト フィールドを追加できますか?

A: はい、新しい PDF ドキュメントを作成せずに、既存の PDF ドキュメントにテキスト フィールドを追加できます。Aspose.PDF for .NET には、テキスト フィールド、チェックボックス、その他のフォーム要素の追加など、既存の PDF ドキュメントを変更する機能が用意されています。

#### Q: Aspose.PDF for .NET は、チェックボックスやラジオ ボタンなど、他の種類のフォーム フィールドをサポートしていますか?

A: はい、Aspose.PDF for .NET は、チェックボックス、ラジオ ボタン、ドロップダウン リストなど、さまざまな種類のフォーム フィールドをサポートしています。ライブラリを使用して、PDF ドキュメント内のさまざまな種類のフォーム要素を操作できます。