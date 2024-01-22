---
title: PDFドキュメントのラジオボタンを選択
linktitle: PDFドキュメントのラジオボタンを選択
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ドキュメント内のラジオ ボタンを選択する方法を学びます。
type: docs
weight: 250
url: /ja/net/programming-with-forms/select-radio-button/
---
ここでは、Aspose.PDF for .NET を使用してラジオ ボタンを選択する方法に関する詳細なチュートリアルを示します。次の手順を実行します：

## ステップ 1: まず、ファイルのパスを指定してドキュメントのディレクトリを定義します。`dataDir` variable.

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ 2: を使用して PDF ドキュメントを開きます。`Document` class and the document path.

```csharp
Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
```

## ステップ 3: ドキュメント フォームからラジオ ボタン フィールドを取得します。

```csharp
RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
```

## ステップ 4: グループから選択するラジオ ボタンのインデックスを指定します。

```csharp
radioField. Selected = 2;
```

## ステップ 5: 編集した PDF ファイルの出力パスを設定します。

```csharp
dataDir = dataDir + "SelectRadioButton_out.pdf";
```

## ステップ 6: 変更した PDF ファイルを保存します。

```csharp
pdfDocument.Save(dataDir);
```

## ステップ 7: 確認メッセージと保存されたファイルの場所が表示されます。

```csharp
Console.WriteLine("\nRadio button successfully selected in group.\nFile saved to location: " + dataDir);
```

### Aspose.PDF for .NET を使用したラジオ ボタンの選択のサンプル ソース コード 
```csharp
try
{
	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//開いた文書
	Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
	//フィールドを取得する
	RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
	//ラジオボタンのインデックスをグループから指定
	radioField.Selected = 2;
	dataDir = dataDir + "SelectRadioButton_out.pdf";
	//PDF ファイルを保存する
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadioButton from group selected successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用してラジオ ボタンを選択する方法を学びました。上記の手順に従って、Aspose.PDF for .NET を使用して PDF ドキュメント内のラジオ ボタンを操作および変更できます。


### よくある質問

#### Q: Aspose.PDF for .NET を使用してグループ内の複数のラジオ ボタンを選択できますか?

A: いいえ、グループ内のラジオ ボタンは相互に排他的になるように設計されています。グループ内で一度に選択できるラジオ ボタンは 1 つだけです。ラジオ ボタンを 1 つ選択すると、同じグループ内で以前に選択したラジオ ボタンが自動的に選択解除されます。

#### Q: Aspose.PDF for .NET を使用して、グループ内で選択されているラジオ ボタンを取得するにはどうすればよいですか?

 A: グループ内で選択したラジオ ボタンを取得するには、`Selected`の財産`RadioButtonField`クラス。グループ内で選択されたラジオ ボタンのインデックスを返します。

#### Q: PDF ドキュメント内で選択したラジオ ボタンの外観をカスタマイズできますか?

A: はい、Aspose.PDF for .NET を使用して、選択したラジオ ボタンの外観をカスタマイズできます。希望する外観に合わせて、色、サイズ、境界線のスタイル、その他の視覚的属性を変更できます。

#### Q: Aspose.PDF for .NET を使用して、プログラムで新しいラジオ ボタン グループを作成することはできますか?

A: はい、Aspose.PDF for .NET を使用して、プログラムで新しいラジオ ボタン グループを作成できます。ドキュメントのフォームに新しいラジオ ボタンを追加し、各ラジオ ボタンに同じグループ名を指定して新しいグループを作成できます。

#### Q: Aspose.PDF for .NET はインタラクティブ PDF フォームの操作をサポートしていますか?

A: はい、Aspose.PDF for .NET は、ラジオ ボタン、テキスト フィールド、チェックボックス、その他のフォーム要素を含む対話型 PDF フォームの操作を完全にサポートしています。ライブラリを使用すると、インタラクティブな PDF フォームを簡単に読み取り、変更、作成できます。