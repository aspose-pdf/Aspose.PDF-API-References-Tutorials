---
title: PDF ファイルのテキストにツールチップを追加
linktitle: PDF ファイルのテキストにツールチップを追加
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイル内のテキストにツールヒントを追加する方法を学びます。
type: docs
weight: 90
url: /ja/net/programming-with-text/add-tooltip-to-text/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイル内のテキストにツールチップを追加するプロセスを説明します。提供されている C# ソース コードは、必要な手順を示しています。

## 要件
始める前に、以下のものがあることを確認してください。

- マシンにインストールされている Visual Studio またはその他の C# コンパイラー。
- .NET ライブラリ用の Aspose.PDF。 Aspose の公式 Web サイトからダウンロードするか、NuGet などのパッケージ マネージャーを使用してインストールできます。

## ステップ 1: プロジェクトをセットアップする
1. 好みの開発環境で新しい C# プロジェクトを作成します。
2. Aspose.PDF for .NET ライブラリへの参照を追加します。

## ステップ 2: 必要な名前空間をインポートする
ツールチップをテキストに追加するコード ファイルで、ファイルの先頭に次の using ディレクティブを追加します。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

## ステップ 3: ドキュメント ディレクトリを設定する
コード内で、次の行を見つけます。`string dataDir = "YOUR DOCUMENT DIRECTORY";`そして交換してください`"YOUR DOCUMENT DIRECTORY"`ドキュメントが保存されているディレクトリへのパスを置き換えます。

## ステップ 4: テキストを含むサンプルドキュメントを作成する
新しいを作成します`Document`オブジェクトを作成し、テキスト断片を含むページを追加します。提供されたコードでは、2 つのテキスト フラグメントがそれぞれのツールチップ テキストとともにドキュメントに追加されます。

```csharp
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
```

## ステップ 5: 文書を開いてテキストの断片を見つける
作成したドキュメントをロードします。`Document`コンストラクターを使用して、ツールチップが必要なテキストの断片を見つけます。`TextFragmentAbsorber`.

```csharp
Document document = new Document(outputFile);
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
```

## ステップ 6: テキストフラグメントにツールチップを追加する
抽出されたテキストの断片をループし、その位置に非表示のボタンを作成します。目的のツールチップ テキストを`AlternateName`の財産`ButtonField`。ボタンフィールドをドキュメントのフォームに追加します。

```csharp
foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Tooltip for text.";
     document.Form.Add(field);
}
```

## ステップ 7: 長いツールチップを含む追加のテキスト断片についても繰り返します。
長いツールチップを含むテキスト断片に対して手順 5 と 6 を繰り返します。検索条件とツールヒントのテキストを適宜変更します。

```csharp
absorb = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorb);
textFragments = absorb.TextFragments;

foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Long tooltip text goes here...";
     document.Form.Add(field);
}
```

## ステップ 8: 変更したドキュメントを保存する
変更した PDF ドキュメントを保存するには、`Save`の方法`Document`物体。

```csharp
document. Save(outputFile);
```

### Aspose.PDF for .NET を使用してツールチップをテキストに追加するサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "Tooltip_out.pdf";
//テキストを含むサンプルドキュメントを作成する
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
//テキストを含む文書を開く
Document document = new Document(outputFile);
//TextAbsorber オブジェクトを作成して、正規表現に一致するすべてのフレーズを検索します
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
//文書ページの吸収材を受け入れる
document.Pages.Accept(absorber);
//抽出されたテキスト断片を取得する
TextFragmentCollection textFragments = absorber.TextFragments;
//フラグメントをループする
foreach (TextFragment fragment in textFragments)
{
	//テキストフラグメントの位置に非表示のボタンを作成します
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	//AlternateName の値は、ビューア アプリケーションによってツールヒントとして表示されます
	field.AlternateName = "Tooltip for text.";
	//ボタンフィールドをドキュメントに追加する
	document.Form.Add(field);
}
//次は非常に長いツールチップのサンプルです
absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorber);
textFragments = absorber.TextFragments;
foreach (TextFragment fragment in textFragments)
{
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	//非常に長いテキストを設定する
	field.AlternateName = "Lorem ipsum dolor sit amet, consectetur adipiscing elit," +
							" sed do eiusmod tempor incididunt ut labore et dolore magna" +
							" aliqua. Ut enim ad minim veniam, quis nostrud exercitation" +
							" ullamco laboris nisi ut aliquip ex ea commodo consequat." +
							" Duis aute irure dolor in reprehenderit in voluptate velit" +
							" esse cillum dolore eu fugiat nulla pariatur. Excepteur sint" +
							" occaecat cupidatat non proident, sunt in culpa qui officia" +
							" deserunt mollit anim id est laborum.";
	document.Form.Add(field);
}
//文書の保存
document.Save(outputFile);
```

## 結論
Aspose.PDF for .NET を使用して PDF ドキュメント内のテキストにツールヒントを正常に追加しました。作成された PDF ファイルは、指定した出力ファイル パスに表示されます。

## よくある質問

#### Q: このチュートリアルの焦点は何ですか?

A: このチュートリアルでは、Aspose.PDF for .NET ライブラリを使用して PDF ファイル内のテキストにツールヒントを追加することに重点を置いています。提供されている C# ソース コードは、これを実現するために必要な手順を示しています。

#### Q: このチュートリアルではどの名前空間をインポートする必要がありますか?

A: ツールチップをテキストに追加するコード ファイルで、ファイルの先頭に次の名前空間をインポートします。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

#### Q: ドキュメント ディレクトリを指定するにはどうすればよいですか?

 A: コード内で次の行を見つけます。`string dataDir = "YOUR DOCUMENT DIRECTORY";`そして交換してください`"YOUR DOCUMENT DIRECTORY"`ドキュメントディレクトリへの実際のパスを置き換えます。

#### Q: テキストを含むサンプルドキュメントを作成するにはどうすればよいですか?

 A: ステップ 4 では、新しいファイルを作成します。`Document`オブジェクトを作成し、テキスト断片を含むページを追加します。提供されたコードは、それぞれのツールヒント テキストを含む 2 つのテキスト フラグメントを追加します。

#### Q: 文書を開いてテキストの断片を見つけるにはどうすればよいですか?

 A: ステップ 5 では、作成したドキュメントを`Document`コンストラクターを使用し、ツールチップを必要とするテキストの断片を見つけます。`TextFragmentAbsorber`.

#### Q: テキストフラグメントにツールチップを追加するにはどうすればよいですか?

 A: ステップ 6 では、抽出されたテキストの断片をループし、その位置に非表示のボタンを作成します。ツールヒントのテキストは、`AlternateName`の財産`ButtonField`、ドキュメントのフォームに追加されます。

#### Q: 長いツールチップを含む追加のテキスト断片に対してこのプロセスを繰り返すにはどうすればよいですか?

A: 長いツールチップを含むテキスト断片の場合は、手順 5 と 6 を繰り返します。それに応じて、検索条件とツールチップ テキストを変更します。

#### Q: 変更したドキュメントを保存するにはどうすればよいですか?

 A: ステップ 8 では、変更した PDF ドキュメントを保存します。`Save`の方法`Document`物体。

#### Q: このチュートリアルの主なポイントは何ですか?

A: このチュートリアルに従うことで、Aspose.PDF for .NET を使用してテキストにツールチップを追加して PDF ドキュメントを強化する方法を学習しました。これにより、読者が PDF コンテンツを操作するときに貴重な追加情報が提供されます。