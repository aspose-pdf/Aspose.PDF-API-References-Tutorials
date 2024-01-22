---
title: PDFフォームフィールドの座標を取得する
linktitle: PDFフォームフィールドの座標を取得する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用すると、PDF ドキュメント内の PDF フォーム フィールドの座標を簡単に取得できます。
type: docs
weight: 120
url: /ja/net/programming-with-forms/get-coordinates/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF フォーム フィールドの座標を取得する方法を説明します。このプロセスをガイドするために、C# ソース コードをステップごとに説明します。

## ステップ 1: 準備

必要なライブラリをインポートし、ドキュメント ディレクトリへのパスを設定していることを確認してください。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: 出力ドキュメントをロードする

出力された PDF ドキュメントをロードします。

```csharp
Document doc1 = new Document(dataDir + "input.pdf");
```

## ステップ 3: 追加されたフィールドを検索する

追加されたフォーム フィールドを見つけます (この例では、「Item1」、「Item2」、および「Item3」フィールドを使用しています)。

```csharp
RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
```

## ステップ 4: 各フィールドのサブ項目の位置を表示する

各フィールドのオプションを循環して、各サブ項目の座標を表示します。

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

### Aspose.PDF for .NET を使用した座標の取得のサンプル ソース コード 
```csharp
try
{
	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//出力ドキュメントをロードする
	Document doc1 = new Document( dataDir + "input.pdf");
	//追加されたフィールドを検索する
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

このチュートリアルでは、Aspose.PDF for .NET を使用してフォーム フィールドの座標を取得する方法を学びました。これらの手順に従うと、Aspose.PDF を使用して PDF ドキュメント内のフォーム フィールドのサブ要素の座標を簡単に取得できます。

### よくある質問

#### Q: このメソッドを使用して、Aspose.PDF for .NET のあらゆる種類のフォーム フィールドの座標を取得できますか?

A: はい、このメソッドを使用して、Aspose.PDF for .NET のさまざまなタイプのフォーム フィールドの座標を取得できます。提供されている C# ソース コードは、RadioButton フィールドの座標を取得する方法を示していますが、TextBox、CheckBox、ListBox などの他のフォーム フィールド タイプにも同じアプローチを適用できます。

#### Q: フォームフィールドの座標を変更または調整するにはどうすればよいですか?

A: フォーム フィールドの座標は PDF ドキュメントの座標系に基づいており、原点 (0,0) はページの左下隅にあります。フォームフィールドの座標を変更または調整するには、`Rect`それぞれのフォーム フィールドまたはそのサブ項目 (RadioButtonOptionField など) のプロパティ。

#### Q: PDF ドキュメントにプログラムで追加されたフォーム フィールドの座標を取得できますか?

A: はい、PDF ドキュメントにプログラムで追加されたフォーム フィールドの座標を取得できます。 Aspose.PDF for .NET を使用すると、フォーム フィールドを動的に追加でき、追加したら、このチュートリアルで説明するアプローチを使用してその座標を取得できます。

#### Q: フォームフィールドの座標を取得する目的は何ですか?

A: フォーム フィールドの座標を取得すると、PDF ドキュメント内のフォーム フィールドで特定のレイアウト関連の操作や検証を実行する必要がある場合に役立ちます。これにより、座標に基づいてフォーム フィールドを正確に配置して整列できるため、ドキュメント内でフォーム フィールドが正しく表示され、シームレスなユーザー エクスペリエンスが提供されます。

#### Q: フォームフィールドの座標はポイントまたは別の単位で表されますか?

A: Aspose.PDF for .NET のフォーム フィールドの座標はポイントで表されます。 1 ポイントは 1/72 インチに相当し、PDF 形式の標準測定単位になります。