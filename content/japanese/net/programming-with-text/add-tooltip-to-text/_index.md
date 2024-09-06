---
title: PDF ファイル内のテキストにツールヒントを追加する
linktitle: PDF ファイル内のテキストにツールヒントを追加する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイル内のテキストにツールヒントを追加する方法を学習します。
type: docs
weight: 90
url: /ja/net/programming-with-text/add-tooltip-to-text/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイル内のテキストにツールヒントを追加するプロセスについて説明します。提供されている C# ソース コードは、必要な手順を示しています。

## 要件
始める前に、次のものがあることを確認してください。

- マシンにインストールされている Visual Studio またはその他の C# コンパイラ。
- Aspose.PDF for .NET ライブラリ。公式 Aspose Web サイトからダウンロードするか、NuGet などのパッケージ マネージャーを使用してインストールできます。

## ステップ1: プロジェクトを設定する
1. 好みの開発環境で新しい C# プロジェクトを作成します。
2. Aspose.PDF for .NET ライブラリへの参照を追加します。

## ステップ2: 必要な名前空間をインポートする
テキストにツールヒントを追加するコード ファイルで、ファイルの先頭に次の using ディレクティブを追加します。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

## ステップ3: ドキュメントディレクトリを設定する
コード内で、次の行を見つけます。`string dataDir = "YOUR DOCUMENT DIRECTORY";`置き換えて`"YOUR DOCUMENT DIRECTORY"`ドキュメントが保存されているディレクトリへのパスを指定します。

## ステップ4: テキストを含むサンプルドキュメントを作成する
新規作成`Document`オブジェクトを作成し、テキスト フラグメントを含むページを追加します。提供されたコードでは、2 つのテキスト フラグメントがそれぞれのツールヒント テキストとともにドキュメントに追加されます。

```csharp
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
```

## ステップ5: 文書を開いてテキストの断片を見つける
作成したドキュメントを`Document`コンストラクタを使用してツールチップが必要なテキストフラグメントを見つけます`TextFragmentAbsorber`.

```csharp
Document document = new Document(outputFile);
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
```

## ステップ6: テキストフラグメントにツールチップを追加する
抽出されたテキストフラグメントをループし、その位置に非表示のボタンを作成します。目的のツールヒントテキストを`AlternateName`の財産`ButtonField`ドキュメントのフォームにボタン フィールドを追加します。

```csharp
foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Tooltip for text.";
     document.Form.Add(field);
}
```

## ステップ7: 長いツールチップを含む追加のテキストフラグメントについて繰り返します
長いツールチップを含むテキスト フラグメントに対して手順 5 と 6 を繰り返します。それに応じて検索条件とツールチップ テキストを変更します。

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

## ステップ8: 変更したドキュメントを保存する
変更したPDF文書を`Save`方法の`Document`物体。

```csharp
document. Save(outputFile);
```

### Aspose.PDF for .NET を使用してテキストにツールヒントを追加するためのサンプル ソース コード 
```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "Tooltip_out.pdf";
//テキストを含むサンプルドキュメントを作成する
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
//テキストを含む文書を開く
Document document = new Document(outputFile);
//正規表現に一致するすべてのフレーズを見つけるためにTextAbsorberオブジェクトを作成します。
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
//文書ページの吸収剤を受け入れる
document.Pages.Accept(absorber);
//抽出されたテキストフラグメントを取得する
TextFragmentCollection textFragments = absorber.TextFragments;
//フラグメントをループする
foreach (TextFragment fragment in textFragments)
{
	//テキストフラグメントの位置に非表示のボタンを作成する
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	//AlternateName 値はビューアアプリケーションによってツールチップとして表示されます。
	field.AlternateName = "Tooltip for text.";
	//ドキュメントにボタンフィールドを追加する
	document.Form.Add(field);
}
//次は、非常に長いツールチップのサンプルです
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
//ドキュメントを保存
document.Save(outputFile);
```

## 結論
Aspose.PDF for .NET を使用して、PDF ドキュメント内のテキストにツールヒントを正常に追加しました。結果の PDF ファイルは、指定した出力ファイル パスにあります。

## よくある質問

#### Q: このチュートリアルの焦点は何ですか?

A: このチュートリアルでは、Aspose.PDF for .NET ライブラリを使用して PDF ファイル内のテキストにツールヒントを追加することに焦点を当てています。提供されている C# ソース コードは、これを実現するために必要な手順を示しています。

#### Q: このチュートリアルではどの名前空間をインポートする必要がありますか?

A: テキストにツールヒントを追加するコード ファイルで、ファイルの先頭に次の名前空間をインポートします。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

#### Q: ドキュメントディレクトリを指定するにはどうすればよいですか?

 A: コード内で次の行を見つけてください`string dataDir = "YOUR DOCUMENT DIRECTORY";`置き換えて`"YOUR DOCUMENT DIRECTORY"`ドキュメント ディレクトリへの実際のパスを入力します。

#### Q: テキストを含むサンプルドキュメントを作成するにはどうすればよいですか?

 A: ステップ4では、新しい`Document`オブジェクトを作成し、テキスト フラグメントを含むページを追加します。提供されているコードは、それぞれのツールヒント テキストを含む 2 つのテキスト フラグメントを追加します。

#### Q: ドキュメントを開いてテキストの断片を見つけるにはどうすればよいですか?

 A: ステップ5では、作成したドキュメントを`Document`コンストラクタを使用してツールチップを必要とするテキストフラグメントを見つけます`TextFragmentAbsorber`.

#### Q: テキストフラグメントにツールチップを追加するにはどうすればよいですか?

 A: ステップ6では、抽出されたテキストフラグメントをループし、その位置に非表示のボタンを作成します。ツールチップテキストは、`AlternateName`の財産`ButtonField`ドキュメントのフォームに追加されます。

#### Q: 長いツールチップを含む追加のテキストフラグメントに対してこのプロセスを繰り返すにはどうすればよいでしょうか?

A: 長いツールチップを含むテキスト フラグメントの場合は、手順 5 と 6 を繰り返します。それに応じて検索条件とツールチップ テキストを変更します。

#### Q: 変更したドキュメントを保存するにはどうすればよいですか?

 A: ステップ8では、変更したPDF文書を`Save`方法の`Document`物体。

#### Q: このチュートリアルから得られる主な教訓は何ですか?

A: このチュートリアルでは、Aspose.PDF for .NET を使用してテキストにツールヒントを追加し、PDF ドキュメントを強化する方法を学習しました。これにより、読者が PDF コンテンツを操作するときに貴重な追加情報を提供できます。