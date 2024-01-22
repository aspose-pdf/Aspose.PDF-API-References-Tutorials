---
title: ラジオボタン
linktitle: ラジオボタン
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用すると、PDF ドキュメントにラジオ ボタンを簡単に追加できます。
type: docs
weight: 220
url: /ja/net/programming-with-forms/radio-button/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントにラジオ ボタンを追加する方法を説明します。このプロセスをガイドするために、C# ソース コードをステップごとに説明します。

## ステップ 1: 準備

必要なライブラリをインポートし、ドキュメント ディレクトリへのパスを設定していることを確認してください。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ 2: ドキュメント オブジェクトをインスタンス化する

Document オブジェクトをインスタンス化して、新しい PDF ドキュメントを作成します。

```csharp
Document pdfDocument = new Document();
```

## ステップ 3: ページを追加する

PDF ドキュメントにページを追加します。

```csharp
pdfDocument.Pages.Add();
```

## ステップ 4: RadioButtonField オブジェクトをインスタンス化する

ページ番号を引数として指定して RadioButtonField オブジェクトをインスタンス化します。

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## ステップ 5: ラジオ ボタン オプションを追加する

Rectangle オブジェクトで各オプションの座標を指定することにより、ラジオ ボタン オプションを RadioButtonField オブジェクトに追加します。

```csharp
radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
```

## ステップ 6: フォームにラジオ ボタンを追加する

ドキュメントの Form オブジェクトにラジオ ボタンを追加します。

```csharp
pdfDocument.Form.Add(radio);
```

## ステップ 7: PDF ドキュメントを保存する

作成した PDF ドキュメントを保存します。

```csharp
dataDir = dataDir + "RadioButton_out.pdf";
pdfDocument.Save(dataDir);
```

### Aspose.PDF for .NET を使用したラジオ ボタンのサンプル ソース コード 
```csharp
try
{
	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//Documentオブジェクトをインスタンス化する
	Document pdfDocument = new Document();
	//PDF ファイルにページを追加する
	pdfDocument.Pages.Add();
	//ページ番号を引数として RadioButtonField オブジェクトをインスタンス化します。
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	//最初のラジオ ボタン オプションを追加し、Rectangle オブジェクトを使用してその原点も指定します
	radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
	// 番目のラジオ ボタン オプションを追加
	radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
	//Documentオブジェクトのフォームオブジェクトにラジオボタンを追加
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "RadioButton_out.pdf";
	//PDF ファイルを保存する
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadio button field added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントにラジオ ボタンを追加する方法を学びました。これらの手順に従うことで、ラジオ ボタンを簡単に作成し、PDF ドキュメント内の特定のページに配置することができます。


### よくある質問

#### Q: ラジオ ボタンのサイズや色などの外観をカスタマイズできますか?

 A: はい、ラジオ ボタンの外観は、`Rectangle`オブジェクトの座標を使用して、そのサイズと位置を定義します。 Aspose.PDF for .NET を使用すると、ニーズに合わせてラジオ ボタンの外観を調整できます。

#### Q: 同じページに異なるグループを持つ複数のラジオ ボタンを追加できますか?

A: はい、同じページに異なるグループを持つ複数のラジオ ボタンを追加できます。ラジオ ボタンの各グループには一意の名前を付けることができ、各グループ内のオプションは一度に 1 つだけ選択できます。

#### Q: ラジオ ボタンのオプションにラベルまたはテキストの説明を追加するにはどうすればよいですか?

 A: ラジオ ボタン オプションにラベルまたはテキストの説明を追加するには、`TextStamp`Aspose.PDF for .NET のクラスを使用して、PDF ドキュメント上の特定の座標でテキストをオーバーレイします。

#### Q: Aspose.PDF for .NET は、.NET Framework のすべてのバージョンと互換性がありますか?

A: はい、Aspose.PDF for .NET は、.NET Core や .NET Standard を含む .NET Framework のすべてのバージョンと互換性があります。

#### Q: PDF ドキュメント内のラジオ ボタン オプションの選択をプログラムで制御できますか?

 A: はい、ラジオ ボタン オプションの選択をプログラムで制御できます。`IsSelected`の財産`RadioButtonOption`クラス。このプロパティを使用すると、特定のオプションを選択済みとして設定できます。