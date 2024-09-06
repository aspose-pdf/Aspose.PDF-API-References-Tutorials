---
title: PDFフォームフィールド座標を取得する
linktitle: PDFフォームフィールド座標を取得する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用すると、PDF ドキュメント内の PDF フォーム フィールドの座標を簡単に取得できます。
type: docs
weight: 120
url: /ja/net/programming-with-forms/get-coordinates/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF フォーム フィールドの座標を取得する方法を説明します。このプロセスをガイドするために、C# ソース コードを段階的に説明します。

## ステップ1: 準備

必要なライブラリがインポートされ、ドキュメント ディレクトリへのパスが設定されていることを確認してください。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ2: 出力ドキュメントを読み込む

出力 PDF ドキュメントを読み込みます。

```csharp
Document doc1 = new Document(dataDir + "input.pdf");
```

## ステップ3: 追加されたフィールドを見つける

追加されたフォーム フィールドを見つけます (この例では、「Item1」、「Item2」、および「Item3」フィールドを使用しています)。

```csharp
RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
```

## ステップ4: 各フィールドのサブアイテムの位置を表示する

各フィールドのオプションを切り替えて、各サブ項目の座標を表示します。

```csharp
foreach(RadioButtonOptionField option in field0)
{
Console.WriteLine(option.Rect);
}
foreach(RadioButtonOptionField option in field1)
{
Console.WriteLine(option.Rect);
}
foreach(RadioButtonOptionField option in field2)
{
Console.WriteLine(option.Rect);
}
```

### Aspose.PDF for .NET を使用して座標を取得するためのサンプル ソース コード 
```csharp
try
{
	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//出力ドキュメントを読み込む
	Document doc1 = new Document( dataDir + "input.pdf");
	//追加されたフィールドを見つける
	RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
	RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
	RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
	//そして、それぞれのサブ項目の位置を表示します。
	foreach (RadioButtonOptionField option in field0)
	{
		Console.WriteLine(option.Rect);
	}
	foreach (RadioButtonOptionField option in field1)
	{
		Console.WriteLine(option.Rect);
	}
	foreach (RadioButtonOptionField option in field2)
	{
		Console.WriteLine(option.Rect);
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用してフォーム フィールドの座標を取得する方法を学習しました。これらの手順に従うと、Aspose.PDF を使用して PDF ドキュメント内のフォーム フィールドのサブ要素の座標を簡単に取得できます。

### よくある質問

#### Q: このメソッドを使用して、Aspose.PDF for .NET の任意のタイプのフォーム フィールドの座標を取得できますか?

A: はい、この方法を使用して、Aspose.PDF for .NET のさまざまな種類のフォーム フィールドの座標を取得できます。提供されている C# ソース コードは、RadioButton フィールドの座標を取得する方法を示していますが、TextBox、CheckBox、ListBox などの他のフォーム フィールドの種類にも同じアプローチを適用できます。

#### Q: フォーム フィールドの座標を変更または調整するにはどうすればよいですか?

A: フォームフィールドの座標はPDF文書の座標系に基づいており、原点（0,0）はページの左下隅にあります。フォームフィールドの座標を変更または調整するには、`Rect` RadioButtonOptionField など、それぞれのフォーム フィールドまたはそのサブ項目のプロパティ。

#### Q: PDF ドキュメントにプログラムで追加されたフォーム フィールドの座標を取得できますか?

A: はい、PDF ドキュメントにプログラムで追加されたフォーム フィールドの座標を取得できます。Aspose.PDF for .NET を使用すると、フォーム フィールドを動的に追加できます。追加したら、このチュートリアルで説明した方法を使用して、その座標を取得できます。

#### Q: フォーム フィールドの座標を取得する目的は何ですか?

A: フォーム フィールドの座標を取得すると、PDF ドキュメント内のフォーム フィールドに対して特定のレイアウト関連の操作や検証を実行する必要がある場合に役立ちます。これにより、座標に基づいてフォーム フィールドを正確に配置および整列できるため、ドキュメント内でフォーム フィールドが正しく表示され、シームレスなユーザー エクスペリエンスが実現します。

#### Q: フォーム フィールドの座標はポイントで表されますか、それとも別の単位で表されますか?

A: Aspose.PDF for .NET のフォーム フィールドの座標はポイントで表されます。1 ポイントは 1/72 インチに相当し、PDF 形式の標準的な測定単位となります。