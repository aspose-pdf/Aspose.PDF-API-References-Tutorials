---
title: 単語の取り消し線
linktitle: 単語の取り消し線
second_title: Aspose.PDF for .NET API リファレンス
description: この記事では、Aspose.PDF for .NET の単語の取り消し線機能を使用するためのステップバイステップのガイドと説明を提供します。
type: docs
weight: 150
url: /ja/net/annotations/strikeoutwords/
---
Aspose.PDF for .NET は、PDF ファイルを作成、変更、変換するためのさまざまな機能を提供する PDF ドキュメント操作および処理ライブラリです。 Aspose.PDF が提供する便利な機能の 1 つは、C# ソース コードを使用して PDF ドキュメント内の単語や語句を取り消す機能です。この記事では、Aspose.PDF for .NET を使用して単語を取り消す方法について段階的なガイドを提供します。

## ステップ 1: PDF ドキュメントをロードする
最初のステップは、変更する PDF ドキュメントをロードすることです。このチュートリアルでは、「YOUR DOCUMENT DIRECTORY」フォルダーから「input.pdf」という名前の PDF ドキュメントを読み込みます。 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "input.pdf");
```

## ステップ 2: テキストの断片を検索する
PDF 文書内の特定の単語や語句を取り消すには、まずそれらを検索する必要があります。 Aspose.PDF は、PDF ドキュメント内の特定のテキスト フラグメントを検索するために使用できる TextFragmentAbsorber クラスを提供します。

```csharp
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
```

上記のコードでは、PDF ドキュメント内のテキスト フラグメント「Estoque」を検索しています。これを変更して、取り消し線を付けたい他の単語や語句を検索することができます。

## ステップ 3: テキストの断片を取り消し線で削除する
テキストの断片を見つけたら、次のステップはそれらに取り消し線を引くことです。 Aspose.PDF は、テキスト フラグメントに取り消し線の注釈を作成するために使用できる StrikeOutAnnotation クラスを提供します。 

```csharp
Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle((float)textFragment.Position.XIndent, (float)textFragment.Position.YIndent, (float)textFragment.Position.XIndent + (float)textFragment.Rectangle.Width, (float)textFragment.Position.YIndent + (float)textFragment.Rectangle.Height);

StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
strikeOut.Opacity = .80f;
strikeOut.Border = new Border(strikeOut);
strikeOut.Color = Aspose.Pdf.Color.Red;
textFragment.Page.Annotations.Add(strikeOut);
```

上記のコードでは、見つかったテキスト断片ごとに取り消し線の注釈を作成しています。取り消し線の注釈の不透明度、境界線、色も設定します。

## ステップ 4: 変更した PDF ドキュメントを保存する
テキストの断片を削除した後、変更したドキュメントを保存します。

```csharp
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

### Aspose.PDF for .NET を使用した取り消し線のソース コードの例


```csharp

//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//開いた文書
Document document = new Document(dataDir + "input.pdf");

//特定のテキストフラグメントを検索する TextFragment Absorber インスタンスを作成する
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
//PDF ドキュメントのページを反復処理する
for (int i = 1; i <= document.Pages.Count; i++)
{
	//PDF ドキュメントの最初のページを取得する
	Page page = document.Pages[1];
	page.Accept(textFragmentAbsorber);
}

//吸収されたテキストのコレクションを作成する
Aspose.Pdf.Text.TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

//上記のコレクションを反復処理する
for (int j = 1; j <= textFragmentCollection.Count; j++)
{
	Aspose.Pdf.Text.TextFragment textFragment = textFragmentCollection[j];

	//TextFragment オブジェクトの長方形の寸法を取得する
	Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle(
				(float)textFragment.Position.XIndent,
				(float)textFragment.Position.YIndent,
				(float)textFragment.Position.XIndent +
				(float)textFragment.Rectangle.Width,
				(float)textFragment.Position.YIndent +
				(float)textFragment.Rectangle.Height);

	//StrikeOut Annotation インスタンスをインスタンス化する
	StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
	//注釈の不透明度を設定する
	strikeOut.Opacity = .80f;
	//注釈インスタンスの境界線を設定します
	strikeOut.Border = new Border(strikeOut);
	//注釈の色を設定する
	strikeOut.Color = Aspose.Pdf.Color.Red;
	//TextFragment の注釈コレクションに注釈を追加します
	textFragment.Page.Annotations.Add(strikeOut);
}
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメント内の特定の単語を取り消す方法を学習しました。ステップバイステップのガイドに従い、提供されている C# ソース コードを使用すると、PDF ドキュメントを簡単にロードし、特定のテキストの断片を検索し、取り消し線の注釈を作成してそれらの単語を視覚的にマークしたり取り消し線を引いたりすることができます。 Aspose.PDF for .NET は、PDF ドキュメントをプログラムで操作するためのシンプルかつ効果的な方法を提供し、.NET アプリケーションで PDF ファイルを扱う開発者にとって貴重なツールとなります。

### よくある質問

#### Q: Aspose.PDF for .NET とは何ですか?

A: Aspose.PDF for .NET は、開発者が .NET アプリケーションでプログラムによって PDF ドキュメントを作成、編集、操作できるようにする強力なライブラリです。テキスト抽出、注釈処理、フォーム入力など、PDF ファイルを操作するための幅広い機能を提供します。

#### Q: Aspose.PDF for .NET を使用して PDF ドキュメント内の特定の単語を取り消すことはできますか?

A: はい。Aspose.PDF for .NET は、PDF ドキュメント内の特定のテキスト断片を検索し、それらの単語を視覚的にマークして取り消し線を引く注釈を作成する機能を提供します。

#### Q: PDF 文書内で取り消し線を引くテキストを指定するにはどうすればよいですか?

 A: 取り消し線を引くテキストを指定するには、`TextFragmentAbsorber` Aspose.PDF for .NET によって提供されるクラス。希望の基準に基づいて PDF ドキュメント内の特定のテキスト断片を検索できます。

#### Q: 取り消し線の注釈の外観をカスタマイズできますか?

A: はい、取り消し線注釈のさまざまなプロパティ (不透明度、境界線のスタイル、色など) をカスタマイズできます。これにより、取り消し線の注釈の外観を特定の要件に合わせて調整できます。