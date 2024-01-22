---
title: 水平方向と垂直方向のラジオ ボタン
linktitle: 水平方向と垂直方向のラジオ ボタン
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用すると、PDF ドキュメントに水平および垂直のラジオ ボタンを簡単に作成できます。
type: docs
weight: 180
url: /ja/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメント内に水平および垂直に配置されたラジオ ボタンを作成する方法を説明します。このプロセスをガイドするために、C# ソース コードをステップごとに説明します。

## ステップ 1: 準備

必要なライブラリをインポートし、ドキュメント ディレクトリへのパスを設定していることを確認してください。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ 2: ドキュメントをロードする

既存の PDF ドキュメントをロードします。

```csharp
FormEditor formEditor = new FormEditor();
formEditor.BindPdf(dataDir + "input.pdf");
```

## ステップ 3: ラジオ ボタン オプションをカスタマイズする

次のプロパティを設定して、ラジオ ボタン オプションをカスタマイズします。

```csharp
formEditor. RadioGap = 4; // 2 つのラジオ ボタン オプション間の距離
formEditor. RadioHoriz = true; //ラジオボタンの横レイアウト
formEditor.RadioButtonItemSize = 20; //ラジオボタンのサイズ
formEditor.Facade.BorderWidth = 1; //ラジオボタンの枠線の幅
formEditor.Facade.BorderColor = System.Drawing.Color.Black; //ラジオボタンの枠線の色
```

## ステップ 4: 水平方向のラジオ ボタンを追加する

オプションとフィールドの位置を指定して、水平方向に配置されたラジオ ボタンを追加します。

```csharp
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
```

## ステップ 5: 縦方向のラジオ ボタンを追加する

フィールドのオプションと位置を指定して、垂直方向に配置されたラジオ ボタンを追加します。

```csharp
formEditor. RadioHoriz = false; //ラジオボタンの縦方向のレイアウト
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
```

## ステップ 6: ドキュメントを保存する

変更した PDF ドキュメントを保存します。

```csharp
dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
formEditor.Save(dataDir);
```

### Aspose.PDF for .NET を使用した水平方向および垂直方向のラジオ ボタンのサンプル ソース コード 
```csharp
try
{
	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//以前に保存したドキュメントをロードします
	FormEditor formEditor = new FormEditor();
	formEditor.BindPdf(dataDir + "input.pdf");
	//RadioGap は、2 つのラジオ ボタン オプション間の距離です。
	formEditor.RadioGap = 4;
	//水平ラジオボタンを追加
	formEditor.RadioHoriz = true;
	//RadioButtonItemSize ラジオ ボタン項目のサイズの場合。
	formEditor.RadioButtonItemSize = 20;
	formEditor.Facade.BorderWidth = 1;
	formEditor.Facade.BorderColor = System.Drawing.Color.Black;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
	//縦に配置された他のラジオボタンを追加します
	formEditor.RadioHoriz = false;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
	dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
	// PDF ドキュメントを保存する
	formEditor.Save(dataDir);
	Console.WriteLine("\nHorizontally and vertically laid out radio buttons successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメント内に水平および垂直に配置されたラジオ ボタンを作成する方法を学びました。これらの手順に従うことで、ラジオ ボタンのレイアウトを簡単にカスタマイズし、Aspose.PDF を使用して PDF ドキュメントにラジオ ボタンを追加できます。

### よくある質問

#### Q: PDF ドキュメント内で水平および垂直に配置されたラジオ ボタンとは何ですか?

A: PDF ドキュメント内で水平および垂直に配置されたラジオ ボタンは、ラジオ ボタン オプションのレイアウトの方向を指します。水平レイアウトでは、ラジオ ボタンのオプションが横に並べて配置され、ユーザーは左から右に選択できるようになります。一方、垂直レイアウトでは、ラジオ ボタンのオプションが互いに積み重ねられ、ユーザーは上から下に選択できるようになります。

#### Q: Aspose.PDF for .NET のラジオ ボタン オプションの外観をカスタマイズするにはどうすればよいですか?

A: いくつかのプロパティを調整することで、Aspose.PDF for .NET のラジオ ボタン オプションの外観をカスタマイズできます。 API には、2 つのラジオ ボタン オプション間の距離を設定するオプションが用意されています (`RadioGap`)、レイアウトの向き (`RadioHoriz`)、ラジオボタン項目のサイズ(`RadioButtonItemSize`)、ラジオ ボタンの境界線の幅と色など。

#### Q: 同じ PDF ドキュメントに水平ラジオ ボタンと垂直ラジオ ボタンの両方を追加できますか?

A: はい、Aspose.PDF for .NET を使用して、水平ラジオ ボタンと垂直ラジオ ボタンの両方を同じ PDF ドキュメントに追加できます。チュートリアルで提供されるサンプル ソース コードは、最初に水平に配置されたラジオ ボタンを追加し、次に垂直に配置された別のラジオ ボタンのセットを同じ PDF ドキュメントに追加する方法を示しています。

#### Q: ラジオ ボタンのグループごとに異なるラジオ ボタン オプションを設定できますか?

 A: はい、ラジオ ボタンのグループごとに異なるラジオ ボタン オプションを設定できます。各グループには固有の`RadioButtonField`オブジェクトと、`RadioButtonOptionField`各グループ内のオブジェクトは、同じページとオプションの一意の名前を共有する必要があります。これにより、各グループ内のラジオ ボタンが正しく機能し、選択が相互に排他的になることが保証されます。

#### Q: ラジオ ボタンのレイアウトと外観の設定は、すべての PDF ビューアとアプリケーションでサポートされていますか?

A: はい、ラジオ ボタンのレイアウトと外観の設定は、標準に準拠したすべての PDF ビューアとアプリケーションでサポートされています。 PDF 仕様では、ラジオ ボタンとそのさまざまな属性が定義されており、ラジオ ボタンが PDF 形式で広く認識されるようになります。ただし、さまざまなプラットフォーム間で一貫したレンダリングを確保するには、さまざまな PDF ビューアでラジオ ボタンの外観と動作をテストすることが不可欠です。