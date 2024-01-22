---
title: ヘッダー フッターの置換可能な記号
linktitle: ヘッダー フッターの置換可能な記号
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して、PDF ドキュメントのヘッダーとフッターで置換可能なシンボルを使用する方法を学びます。
type: docs
weight: 320
url: /ja/net/programming-with-text/replaceable-symbols-in-header-footer/
---
このチュートリアルでは、.NET 用の Aspose.PDF ライブラリを使用して、PDF ドキュメントのヘッダーとフッターで置換可能なシンボルを使用する方法を説明します。 PDF の作成、余白の設定、置換可能な記号を含むヘッダーとフッターの追加、提供された C# ソース コードを使用した PDF の保存という手順を段階的に説明します。

## 前提条件

始める前に、以下のものがあることを確認してください。

- Aspose.PDF for .NET ライブラリがインストールされています。
- C# プログラミングの基本的な理解。

## ステップ 1: ドキュメント ディレクトリを設定する

まず、生成された PDF ファイルを保存するディレクトリへのパスを設定する必要があります。交換する`"YOUR DOCUMENT DIRECTORY"`の中に`dataDir`変数を目的のディレクトリへのパスに置き換えます。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: PDF ドキュメントとページを作成する

次に、新しい PDF ドキュメントを作成し、`Document`クラスと`Page` Aspose.PDF ライブラリのクラス。

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## ステップ 3: 余白を設定する

ページの余白を設定するには、`MarginInfo`クラス。要件に応じてマージン値を調整します。

```csharp
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

## ステップ 4: 置換可能なシンボルを含むヘッダーを追加する

私たちは`HeaderFooter`ページのオブジェクトを追加し、`TextFragment`置換可能なシンボルを追加します。

```csharp
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;

TextFragment t1 = new TextFragment("report title");
//必要に応じてテキストのプロパティを設定します
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;

hfFirst.Paragraphs.Add(t1);

//TextFragments をさらに追加するか、必要に応じてカスタマイズします
```

## ステップ 5: 置換可能なシンボルを含むフッターを追加する

同様に、`HeaderFooter`ページフッターのオブジェクトを追加して追加します`TextFragment`置換可能なシンボルを持つオブジェクト。

```csharp
HeaderFooter hfFoot = new HeaderFooter();
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;

TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");

//TextFragments をさらに追加するか、必要に応じてカスタマイズします

hfFoot.Paragraphs.Add(tab2);
```

## ステップ 6: PDF ドキュメントを保存する

最後に、PDF ドキュメントを指定した出力ファイルに保存します。

```csharp
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols replaced successfully in the header and footer.\nFile saved at " + dataDir);
```

### Aspose.PDF for .NET を使用したヘッダー フッターの置換可能なシンボルのサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
//marginInfo インスタンスを sec1.PageInfo の Margin プロパティに割り当てます。
page.PageInfo.Margin = marginInfo;
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;
//ヘッダーとして表示するコンテンツを保存するテキスト段落をインスタンス化します。
TextFragment t1 = new TextFragment("report title");
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;
hfFirst.Paragraphs.Add(t1);
TextFragment t2 = new TextFragment("Report_Name");
t2.TextState.Font = FontRepository.FindFont("Arial");
t2.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t2.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t2.TextState.LineSpacing = 5f;
t2.TextState.FontSize = 12;
hfFirst.Paragraphs.Add(t2);
//セクションの HeaderFooter オブジェクトを作成する
HeaderFooter hfFoot = new HeaderFooter();
//HeaderFooter オブジェクトを奇数および偶数のフッターに設定します
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;
//現在のページ番号または総ページ数を含むテキスト段落を追加します
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");
//テーブルオブジェクトをインスタンス化する
Table tab2 = new Table();
//目的のセクションの段落コレクションに表を追加します
hfFoot.Paragraphs.Add(tab2);
//テーブルの列幅で設定します
tab2.ColumnWidths = "165 172 165";
//テーブルに行を作成し、その行にセルを作成します。
Row row3 = tab2.Rows.Add();
row3.Cells.Add();
row3.Cells.Add();
row3.Cells.Add();
//テキストの垂直方向の配置を中央揃えに設定します
row3.Cells[0].Alignment = Aspose.Pdf.HorizontalAlignment.Left;
row3.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
row3.Cells[2].Alignment = Aspose.Pdf.HorizontalAlignment.Right;
row3.Cells[0].Paragraphs.Add(t3);
row3.Cells[1].Paragraphs.Add(t4);
row3.Cells[2].Paragraphs.Add(t5);
//Sec1.Paragraphs.Add(New Text("Aspose.Total for Java は、Aspose が提供するすべての Java コンポーネントをコンパイルしたものです。各コンポーネントの最新バージョンが含まれていることを確認するために、#$NL" + "毎日コンパイルされます#$NL " + "Aspose.Total for Java を使用すると、開発者は幅広いアプリケーションを作成できます。 #$NL #$NL #$NP" + "Aspose.Total for Java は、すべての Java コンポーネントをコンパイルしたものですAspose によって提供されています。#$NL" + "毎日コンパイルされ、各 Java コンポーネントの最新バージョンが含まれていることを確認します。#$NL " + "Aspose.Total for Java を使用すると、開発者は幅広いコンポーネントを作成できます。 #$NL #$NL #$NP" + "Aspose.Total for Java は、Aspose が提供するすべての Java コンポーネントをコンパイルしたものです。#$NL" + "毎日、最も多くのアプリケーションが含まれるようにコンパイルされます。各 Java コンポーネントの最新バージョン。 #$NL " + "Aspose.Total for Java 開発者を使用すると、幅広いアプリケーションを作成できます。 #$NL #$NL"))
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
table.DefaultCellPadding = new MarginInfo();
table.DefaultCellPadding.Top = 10;
table.DefaultCellPadding.Bottom = 10;
//目的のセクションの段落コレクションに表を追加します
page.Paragraphs.Add(table);
//BorderInfo オブジェクトを使用してデフォルトのセル境界線を設定する
table.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1f);
//別のカスタマイズされた BorderInfo オブジェクトを使用してテーブルの境界線を設定する
table.Border = new BorderInfo(BorderSide.All, 1f);
table.RepeatingRowsCount = 1;
//テーブルに行を作成し、その行にセルを作成します。
Row row1 = table.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");
const string CRLF = "\r\n";
for (int i = 0; i <= 10; i++)
{
	Row row = table.Rows.Add();
	row.IsRowBroken = true;
	for (int c = 0; c <= 2; c++)
	{
		Cell c1;
		if (c == 2)
			c1 = row.Cells.Add("Aspose.Total for Java is a compilation of every Java component offered by Aspose. It is compiled on a" + CRLF + "daily basis to ensure it contains the most up to date versions of each of our Java components. " + CRLF + "daily basis to ensure it contains the most up to date versions of each of our Java components. " + CRLF + "Using Aspose.Total for Java developers can create a wide range of applications.");
		else
			c1 = row.Cells.Add("item1" + c);
		c1.Margin = new MarginInfo();
		c1.Margin.Left = 30;
		c1.Margin.Top = 10;
		c1.Margin.Bottom = 10;
	}
}
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nSymbols replaced successfully in header and footer.\nFile saved at " + dataDir);
```

## 結論

このチュートリアルでは、.NET 用の Aspose.PDF ライブラリを使用して、PDF ドキュメントのヘッダーとフッターで置換可能なシンボルを使用する方法を学習しました。ステップバイステップのガイドに従って、提供されている C# コードを実行することで、PDF の作成、余白の設定、置換可能な記号を含むヘッダーとフッターの追加、PDF の保存を行うことができます。

### よくある質問

#### Q: 「ヘッダー フッターの置換可能なシンボル」チュートリアルの目的は何ですか?

A: 「ヘッダー フッターの置換可能なシンボル」チュートリアルは、.NET 用の Aspose.PDF ライブラリを使用して PDF ドキュメントのヘッダーとフッターに置換可能なシンボルを追加するプロセスをガイドすることを目的としています。置換可能なシンボルを使用すると、PDF の生成時に特定のプレースホルダーを実際の値に動的に置き換えることができます。

#### Q: PDF ヘッダーとフッターのコンテキストで置き換え可能なシンボルとは何ですか?

A: 置換可能なシンボルは、PDF ドキュメントのヘッダーとフッターに挿入できるプレースホルダーです。これらのシンボルは、ページ番号、日付、カスタム情報など、実行時に入力できる値の動的なプレースホルダーとして機能します。

#### Q: PDF のヘッダーとフッターで置換可能なシンボルを使用する必要があるのはなぜですか?

A: ヘッダーとフッターの置換可能な記号は、ページ番号、日付、ドキュメントの生成時に変更される可能性のあるその他の可変データなどの動的な情報を PDF ドキュメントに含める場合に便利です。

#### Q: PDF ページの余白を設定するにはどうすればよいですか?

 A: PDF ページの余白は、`MarginInfo`クラスに割り当てて、`Margin`の財産`PageInfo`ページの。必要に応じてマージンの値を調整します。

#### Q: ヘッダーとフッターに置換可能な記号を追加するにはどうすればよいですか?

 A: 置換可能なシンボルを追加するには、`HeaderFooter`ページのヘッダーとフッターのオブジェクト。次に、追加できます`TextFragment`置換可能なシンボルを含む、目的のテキストを含むオブジェクトを`Paragraphs`のコレクション`HeaderFooter`物体。

#### Q: 置換可能なシンボルの外観をカスタマイズできますか?

A: はい、置換可能なシンボルのプロパティを変更することで、その外観をカスタマイズできます。`TextFragment`シンボルを含むオブジェクト。フォント、フォント サイズ、色、配置、行間隔などのプロパティを設定できます。

#### Q: どのような置換可能なシンボルを使用できますか?

A: 次のようなさまざまな置換可能なシンボルを使用できます。

- `$p`: 現在のページ番号。
- `$P`: 総ページ数。
- `$d`： 現在の日付。
- `$t`： 現在の時刻。
- ユーザーが定義するカスタム プレースホルダー。

#### Q: 置換可能なシンボルの周りに他のテキストや書式設定を含めることはできますか?

 A: はい、他のテキストや書式設定を、`TextFragment`オブジェクト。これにより、動的コンテンツと静的コンテンツを組み込んだ、より複雑なヘッダーとフッターを作成できます。

#### Q: 生成された PDF ドキュメントを保存するにはどうすればよいですか?

 A: 生成された PDF ドキュメントを保存するには、`Save`の方法`Document`クラス。必要な出力ファイルのパスと名前を引数として指定します。

#### Q: このチュートリアルには有効な Aspose ライセンスが必要ですか?

A: はい、このチュートリアルのコードを正常に実行するには、有効な Aspose ライセンスが必要です。 Aspose Web サイトから完全ライセンスまたは 30 日間の一時ライセンスを取得できます。