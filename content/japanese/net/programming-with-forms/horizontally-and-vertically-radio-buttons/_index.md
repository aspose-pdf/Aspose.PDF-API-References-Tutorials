---
title: 水平方向と垂直方向のラジオボタン
linktitle: 水平方向と垂直方向のラジオボタン
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用すると、PDF ドキュメントに水平および垂直のラジオ ボタンを簡単に作成できます。
type: docs
weight: 180
url: /ja/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して、PDF ドキュメントに水平および垂直に配置されたラジオ ボタンを作成する方法を説明します。このプロセスをガイドするために、C# ソース コードを段階的に説明します。

## ステップ1: 準備

必要なライブラリがインポートされ、ドキュメント ディレクトリへのパスが設定されていることを確認してください。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ2: ドキュメントを読み込む

既存の PDF ドキュメントを読み込みます:

```csharp
FormEditor formEditor = new FormEditor();
formEditor.BindPdf(dataDir + "input.pdf");
```

## ステップ3: ラジオボタンのオプションをカスタマイズする

次のプロパティを設定してラジオ ボタンのオプションをカスタマイズします。

```csharp
formEditor. RadioGap = 4; // 2つのラジオボタンオプション間の距離
formEditor. RadioHoriz = true; //ラジオボタンの水平レイアウト
formEditor.RadioButtonItemSize = 20; //ラジオボタンのサイズ
formEditor.Facade.BorderWidth = 1; //ラジオボタンの境界線の幅
formEditor.Facade.BorderColor = System.Drawing.Color.Black; //ラジオボタンの境界線の色
```

## ステップ4: 水平ラジオボタンを追加する

オプションとフィールドの位置を指定して、水平に配置されたラジオ ボタンを追加します。

```csharp
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
```

## ステップ5: 垂直ラジオボタンを追加する

オプションとフィールドの位置を指定して、垂直に配置されたラジオ ボタンを追加します。

```csharp
formEditor. RadioHoriz = false; //ラジオボタンの垂直レイアウト
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
```

## ステップ6: ドキュメントを保存する

変更した PDF ドキュメントを保存します。

```csharp
dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
formEditor.Save(dataDir);
```

### Aspose.PDF for .NET を使用した水平および垂直ラジオ ボタンのサンプル ソース コード 
```csharp
try
{
	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//以前に保存したドキュメントを読み込む
	FormEditor formEditor = new FormEditor();
	formEditor.BindPdf(dataDir + "input.pdf");
	//RadioGap は、2 つのラジオ ボタン オプション間の距離です。
	formEditor.RadioGap = 4;
	//水平ラジオボタンを追加
	formEditor.RadioHoriz = true;
	//ラジオ ボタン項目のサイズの場合は RadioButtonItemSize。
	formEditor.RadioButtonItemSize = 20;
	formEditor.Facade.BorderWidth = 1;
	formEditor.Facade.BorderColor = System.Drawing.Color.Black;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
	//縦に並んだ他のラジオボタンを追加する
	formEditor.RadioHoriz = false;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
	dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
	// PDF文書を保存する
	formEditor.Save(dataDir);
	Console.WriteLine("\nHorizontally and vertically laid out radio buttons successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して、PDF ドキュメントに水平および垂直に配置されたラジオ ボタンを作成する方法を学習しました。これらの手順に従うことで、ラジオ ボタンのレイアウトを簡単にカスタマイズし、Aspose.PDF を使用して PDF ドキュメントに追加できます。

### よくある質問

#### Q: PDF ドキュメント内の水平方向と垂直方向に配置されたラジオ ボタンとは何ですか?

A: PDF ドキュメント内の水平および垂直に配置されたラジオ ボタンは、ラジオ ボタン オプションのレイアウト方向を示します。水平レイアウトでは、ラジオ ボタン オプションが横に並んで配置されるため、ユーザーは左から右に選択できます。一方、垂直レイアウトでは、ラジオ ボタン オプションが上下に積み重ねられるため、ユーザーは上から下に選択できます。

#### Q: Aspose.PDF for .NET でラジオ ボタン オプションの外観をカスタマイズするにはどうすればよいですか?

A: Aspose.PDF for .NET では、いくつかのプロパティを調整することでラジオ ボタン オプションの外観をカスタマイズできます。API には、2 つのラジオ ボタン オプション間の距離を設定するオプションが用意されています (`RadioGap`）、レイアウトの向き（`RadioHoriz`）、ラジオボタン項目のサイズ（`RadioButtonItemSize`）、ラジオボタンの境界線の幅や色などを設定できます。

#### Q: 同じ PDF ドキュメントに水平ラジオ ボタンと垂直ラジオ ボタンの両方を追加できますか?

A: はい、Aspose.PDF for .NET を使用して、同じ PDF ドキュメントに水平ラジオ ボタンと垂直ラジオ ボタンの両方を追加できます。チュートリアルで提供されるサンプル ソース コードは、最初に水平に配置されたラジオ ボタンを追加し、次に同じ PDF ドキュメントに垂直に配置された別のラジオ ボタンのセットを追加する方法を示しています。

#### Q: ラジオ ボタンのグループごとに異なるラジオ ボタン オプションを設定できますか?

 A: はい、ラジオボタンのグループごとに異なるラジオボタンオプションを設定できます。各グループには固有の`RadioButtonField`オブジェクト、および`RadioButtonOptionField`各グループ内のオブジェクトは同じページを共有し、オプションに一意の名前を使用する必要があります。これにより、各グループ内のラジオ ボタンが正しく機能し、選択が相互に排他的になります。

#### Q: ラジオ ボタンのレイアウトと外観の設定は、すべての PDF ビューアとアプリケーションでサポートされていますか?

A: はい、ラジオ ボタンのレイアウトと外観設定は、標準に準拠したすべての PDF ビューアとアプリケーションでサポートされています。PDF 仕様ではラジオ ボタンとそのさまざまな属性が定義されており、PDF 形式では普遍的に認識されます。ただし、さまざまなプラットフォーム間で一貫したレンダリングを保証するには、さまざまな PDF ビューアでラジオ ボタンの外観と動作をテストすることが重要です。