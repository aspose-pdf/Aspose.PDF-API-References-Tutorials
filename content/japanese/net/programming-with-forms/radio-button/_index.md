---
title: ラジオボタン
linktitle: ラジオボタン
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用すると、PDF ドキュメントにラジオ ボタンを簡単に追加できます。
type: docs
weight: 220
url: /ja/net/programming-with-forms/radio-button/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントにラジオ ボタンを追加する方法を説明します。このプロセスをガイドするために、C# ソース コードを段階的に説明します。

## ステップ1: 準備

必要なライブラリがインポートされ、ドキュメント ディレクトリへのパスが設定されていることを確認してください。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ2: ドキュメントオブジェクトのインスタンスを作成する

Document オブジェクトをインスタンス化して新しい PDF ドキュメントを作成します。

```csharp
Document pdfDocument = new Document();
```

## ステップ3: ページを追加する

PDF ドキュメントにページを追加します。

```csharp
pdfDocument.Pages.Add();
```

## ステップ4: RadioButtonFieldオブジェクトのインスタンスを作成する

ページ番号を引数として指定して RadioButtonField オブジェクトをインスタンス化します。

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## ステップ5: ラジオボタンオプションを追加する

各オプションの座標を Rectangle オブジェクトで指定して、ラジオ ボタン オプションを RadioButtonField オブジェクトに追加します。

```csharp
radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
```

## ステップ6: フォームにラジオボタンを追加する

ドキュメントのフォーム オブジェクトにラジオ ボタンを追加します。

```csharp
pdfDocument.Form.Add(radio);
```

## ステップ7: PDFドキュメントを保存する

作成した PDF ドキュメントを保存します。

```csharp
dataDir = dataDir + "RadioButton_out.pdf";
pdfDocument.Save(dataDir);
```

### Aspose.PDF for .NET を使用したラジオ ボタンのサンプル ソース コード 
```csharp
try
{
	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Documentオブジェクトをインスタンス化する
	Document pdfDocument = new Document();
	//PDFファイルにページを追加する
	pdfDocument.Pages.Add();
	//ページ番号を引数としてRadioButtonFieldオブジェクトをインスタンス化する
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	//最初のラジオボタンオプションを追加し、Rectangleオブジェクトを使用してその原点も指定します。
	radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
	//2番目のラジオボタンオプションを追加する
	radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
	// Document オブジェクトのフォーム オブジェクトにラジオ ボタンを追加します。
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "RadioButton_out.pdf";
	//PDFファイルを保存する
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadio button field added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントにラジオ ボタンを追加する方法を学習しました。これらの手順に従うことで、ラジオ ボタンを簡単に作成し、PDF ドキュメントの特定のページに配置できます。


### よくある質問

#### Q: ラジオ ボタンのサイズや色などの外観をカスタマイズできますか?

 A: はい、ラジオボタンの外観は、`Rectangle`オブジェクトの座標を使用して、サイズと位置を定義します。Aspose.PDF for .NET を使用すると、ラジオ ボタンの外観をニーズに合わせて調整できます。

#### Q: 同じページに異なるグループのラジオ ボタンを複数追加できますか?

A: はい、同じページに異なるグループのラジオ ボタンを複数追加できます。ラジオ ボタンの各グループには一意の名前を付けることができ、各グループ内で一度に選択できるオプションは 1 つだけです。

#### Q: ラジオ ボタン オプションにラベルまたはテキストの説明を追加するにはどうすればよいですか?

 A: ラジオボタンのオプションにラベルやテキストの説明を追加するには、`TextStamp`Aspose.PDF for .NET のクラスを使用して、PDF ドキュメント上の特定の座標にテキストをオーバーレイします。

#### Q: Aspose.PDF for .NET は、すべてのバージョンの .NET Framework と互換性がありますか?

A: はい、Aspose.PDF for .NET は、.NET Core および .NET Standard を含むすべてのバージョンの .NET Framework と互換性があります。

#### Q: PDF ドキュメント内のラジオ ボタン オプションの選択をプログラムで制御できますか?

 A: はい、ラジオボタンオプションの選択をプログラムで制御できます。`IsSelected`の財産`RadioButtonOption`クラス。このプロパティを使用すると、特定のオプションを選択済みとして設定できます。