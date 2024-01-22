---
title: テキストボックス
linktitle: テキストボックス
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ドキュメントにテキスト フィールドを作成する方法を学びます。
type: docs
weight: 290
url: /ja/net/programming-with-forms/text-box/
---
このガイドでは、.NET 用の Aspose.PDF ライブラリを使用して PDF ドキュメント内にテキスト フィールドを作成する方法を段階的に説明します。ドキュメントを開き、テキストフィールドを作成し、そのプロパティをカスタマイズし、編集した PDF を保存する方法を説明します。

## ステップ 1: ドキュメント ディレクトリの構成

最初のステップは、作業する PDF ファイルが配置されるドキュメント ディレクトリを構成することです。使用できます`dataDir`ディレクトリパスを指定する変数。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

必ず交換してください`"YOUR DOCUMENTS DIRECTORY"`ドキュメントディレクトリへの実際のパスを含めます。

## ステップ 2: PDF ドキュメントを開く

このステップでは、`Document` Aspose.PDF のクラス。

```csharp
Document pdfDocument = new Document(dataDir + "TextField.pdf");
```

PDF ファイルが指定されたドキュメント ディレクトリに存在することを確認してください。

## ステップ 3: テキストフィールドの作成

を使用してテキストフィールドを作成します`TextBoxField`クラス。位置座標とフィールド サイズを指定するには、`Rectangle`クラス。

```csharp
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField. PartialName = "textbox1";
textBoxField.Value = "Text Field";
```

必要に応じて、座標、サイズ、名前の一部、テキスト フィールドの値をカスタマイズします。

## ステップ 4: テキストフィールドのプロパティをカスタマイズする

このステップでは、境界線や色などのテキスト フィールドのプロパティをカスタマイズします。

```csharp
Border border = new Border(textBoxField);
border. width = 5;
border. Dash = new Dash(1, 1);
textBoxField. Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```

好みに応じてテキスト フィールドのプロパティをカスタマイズします。

## ステップ 5: ドキュメントにフィールドを追加する

テキストフィールドを作成して設定したので、それを PDF ドキュメントに追加できます。

```csharp
pdfDocument.Form.Add(textBoxField, 1);
```

## ステップ 6: 変更した PDF を保存する

最後に、次のコマンドを使用して、変更した PDF を保存できます。`Save`の方法`Document`クラス。

```csharp
dataDir = dataDir + "TextBox_out.pdf";
pdfDocument.Save(dataDir);
```

編集した PDF の絶対パスとファイル名を必ず指定してください。

### Aspose.PDF for .NET を使用したテキスト ボックスのサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開いた文書
Document pdfDocument = new Document(dataDir + "TextField.pdf");
//フィールドを作成する
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField.PartialName = "textbox1";
textBoxField.Value = "Text Box";
//TextBoxField.Border = 新しい境界線(
Border border = new Border(textBoxField);
border.Width = 5;
border.Dash = new Dash(1, 1);
textBoxField.Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
//ドキュメントにフィールドを追加する
pdfDocument.Form.Add(textBoxField, 1);
dataDir = dataDir + "TextBox_out.pdf";
//変更した PDF を保存する
pdfDocument.Save(dataDir);
Console.WriteLine("\nTextbox field added successfully.\nFile saved at " + dataDir);
```

## 結論

このガイドでは、.NET 用の Aspose.PDF ライブラリを使用して PDF ドキュメント内にテキスト フィールドを作成する方法を学習しました。説明されている手順に従うことで、テキスト フィールドのプロパティをカスタマイズし、必要に応じてドキュメントに追加できます。 PDF ファイルの操作の可能性を広げるために、Aspose.PDF for .NET の機能を自由にさらに探索してください。

### よくある質問

#### Q: Aspose.PDF for .NET を使用して、単一の PDF ドキュメント内に複数のテキスト フィールドを作成できますか?

A: はい、Aspose.PDF for .NET を使用して、単一の PDF ドキュメント内に複数のテキスト フィールドを作成できます。文書内の目的の場所ごとにテキスト フィールドを作成してカスタマイズするプロセスを繰り返すだけです。

#### Q: フォント サイズや色など、テキスト フィールドの外観をカスタマイズするにはどうすればよいですか?

A: フォント サイズ、フォント スタイル、色、境界線のスタイル、背景色などのプロパティを調整することで、テキスト フィールドの外観をカスタマイズできます。提供されているサンプル ソース コードでは、境界線の幅、境界線の破線パターン、および文字の色がカスタマイズされています。

#### Q: 作成したテキストフィールドからユーザーが入力したテキストを抽出することはできますか?

A: はい、作成されたテキスト フィールドからユーザーが入力したテキストを抽出できます。ユーザーが PDF ドキュメントのテキスト フィールドに入力した後、Aspose.PDF for .NET を使用してプログラムでフィールド値を取得できます。

#### Q: 新しい PDF ドキュメントを作成せずに、既存の PDF ドキュメントにテキスト フィールドを追加できますか?

A: はい、新しい PDF ドキュメントを作成しなくても、既存の PDF ドキュメントにテキスト フィールドを追加できます。 Aspose.PDF for .NET は、テキスト フィールド、チェックボックス、その他のフォーム要素の追加など、既存の PDF ドキュメントを変更する機能を提供します。

#### Q: Aspose.PDF for .NET は、チェックボックスやラジオ ボタンなど、他のタイプのフォーム フィールドをサポートしていますか?

A: はい、Aspose.PDF for .NET は、チェックボックス、ラジオ ボタン、ドロップダウン リストなどを含む、さまざまなタイプのフォーム フィールドをサポートしています。このライブラリを使用すると、PDF ドキュメント内のさまざまなタイプのフォーム要素を操作できます。