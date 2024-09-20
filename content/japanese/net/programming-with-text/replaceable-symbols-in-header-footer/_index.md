---
title: ヘッダー フッター内の置換可能なシンボル
linktitle: ヘッダー フッター内の置換可能なシンボル
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して、PDF ドキュメントのヘッダーとフッターで置き換え可能なシンボルを使用する方法を学習します。
type: docs
weight: 320
url: /ja/net/programming-with-text/replaceable-symbols-in-header-footer/
---
## 導入

PDF ファイルで作業する場合、ページ番号、レポート名、生成日などの動的コンテンツを使用してヘッダーとフッターをカスタマイズする必要がある場合があります。幸いなことに、Aspose.PDF for .NET はこのプロセスを簡素化し、ページ番号やレポート生成の詳細などのヘッダーとフッターのシンボルを自動的に更新する PDF を作成できます。この記事では、Aspose.PDF for .NET を使用して、シンプルであるだけでなく非常に効率的な方法でヘッダーとフッターのシンボルを置き換える手順を順を追って説明します。

## 前提条件

ステップバイステップガイドに進む前に、次のものを用意してください。

-  Aspose.PDF for .NET ライブラリ –[ダウンロード](https://releases.aspose.com/pdf/net/)または[無料トライアル](https://releases.aspose.com/).
- システムにインストールされている Visual Studio または任意の C# IDE。
- C# および .NET 開発に関する基本的な知識。
- 有効な[ライセンス](https://purchase.aspose.com/temporary-license/)Aspose.PDF の場合は、試用版を使用することもできます。

## パッケージのインポート

まず、Aspose.PDF for .NET の機能を有効にするために必要な名前空間をインポートする必要があります。必要なインポートは次のとおりです。

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

これらは、PDF の作成、テキストの操作、ヘッダー/フッターの管理を処理するために不可欠です。

サンプルコードをわかりやすいステップに分解してみましょう。

## ステップ1: ドキュメントとページを設定する

まず、ドキュメントを初期化し、ページを追加する必要があります。これにより、ヘッダーとフッターを追加するための基礎が設定されます。

```csharp
//ドキュメントディレクトリを設定する
string dataDir = "YOUR DOCUMENT DIRECTORY";

//ドキュメントオブジェクトを初期化する
Document doc = new Document();

//ドキュメントにページを追加する
Page page = doc.Pages.Add();
```

ここでは、`Document`クラスとページの追加`doc.Pages.Add()`このページには、ヘッダー、フッター、その他のコンテンツが保持されます。

## ステップ2: ページ余白を設定する

次に、コンテンツがページの端まで表示されないように、ページの余白を定義します。

```csharp
//余白を設定する
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

ここでは、上、下、左、右の余白を次のように定義しています。`MarginInfo`クラスを作成し、それをページに適用しました`page.PageInfo.Margin`.

## ステップ3: ヘッダーを作成して構成する

次に、ヘッダーを作成してページに追加します。ヘッダーにはレポートのタイトルと名前が含まれます。

```csharp
//ヘッダーを作成
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;

//ヘッダー余白を設定する
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;

//ヘッダーにタイトルを追加
TextFragment t1 = new TextFragment("report title");
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
hfFirst.Paragraphs.Add(t1);

//ヘッダーにレポート名を追加する
TextFragment t2 = new TextFragment("Report_Name");
t2.TextState.Font = FontRepository.FindFont("Arial");
t2.TextState.FontSize = 12;
t2.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
hfFirst.Paragraphs.Add(t2);
```

2つ追加しました`TextFragment`ヘッダーにオブジェクトを追加します。1つはレポートタイトル用、もう1つはレポート名用です。テキストは次のようにスタイル設定されています。`TextState`フォント、サイズ、配置などのプロパティ。

## ステップ4: フッターを作成して構成する

次に、ページ番号や生成日などの動的なコンテンツを保持するフッターを設定します。

```csharp
//フッターを作成
HeaderFooter hfFoot = new HeaderFooter();
page.Footer = hfFoot;

//フッターの余白を設定する
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;

//フッターコンテンツを追加する
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("Report Name");
TextFragment t5 = new TextFragment("Page $p of $P");
```

フッターには、生成日、レポート名、動的ページ番号のフラグメントが含まれています（`$p`そして`$P`それぞれ現在のページ番号と総ページ数を表します。

## ステップ5: フッターにテーブルを作成する

フッターにテーブルなどのより複雑な要素を追加して、データをより適切に整理することもできます。

```csharp
//フッター用のテーブルを作成する
Table tab2 = new Table();
hfFoot.Paragraphs.Add(tab2);
tab2.ColumnWidths = "165 172 165";

//表の行とセルを作成する
Row row3 = tab2.Rows.Add();
row3.Cells.Add();
row3.Cells.Add();
row3.Cells.Add();

//各セルの配置を設定する
row3.Cells[0].Alignment = Aspose.Pdf.HorizontalAlignment.Left;
row3.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
row3.Cells[2].Alignment = Aspose.Pdf.HorizontalAlignment.Right;

//表のセルにコンテンツを追加する
row3.Cells[0].Paragraphs.Add(t3);
row3.Cells[1].Paragraphs.Add(t4);
row3.Cells[2].Paragraphs.Add(t5);
```

このコード ブロックは、フッターに 3 列のテーブルを作成します。各列には、生成日、レポート名、ページ番号などのさまざまな情報が含まれます。

## ステップ6: ページにコンテンツを追加する

ヘッダーとフッターに加えて、PDF ページの本文にコンテンツを追加できます。ここでは、プレースホルダー テキストを含む表を追加します。

```csharp
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
page.Paragraphs.Add(table);

//表の内容を追加する
for (int i = 0; i <= 10; i++)
{
    Row row = table.Rows.Add();
    for (int c = 0; c <= 2; c++)
    {
        Cell cell = row.Cells.Add("Content " + c);
        cell.Margin = new MarginInfo { Left = 30, Top = 10, Bottom = 10 };
    }
}
```

このコードは、3 つの列を持つ単純なテーブルをページに追加します。特定のニーズに合わせて変更できます。

## ステップ7: PDFを保存する

すべての設定が完了したら、最後のステップとして PDF ドキュメントを目的の場所に保存します。

```csharp
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("Symbols replaced successfully in header and footer. File saved at " + dataDir);
```

ファイルパスを指定して、ドキュメントを保存します。`doc.Save()`これで完了です。カスタマイズされたヘッダーとフッターを含む PDF が正常に作成されました。

## 結論

Aspose.PDF for .NET を使用してヘッダーとフッターのシンボルを置き換えるのは、簡単なだけでなく、強力です。上記のステップバイステップのガイドに従うことで、ページ番号、レポート名、日付などの動的なコンテンツを使用して PDF を簡単にカスタマイズできます。この方法は非常に柔軟性が高く、テーブルを挿入したり、書式を調整したり、特定の要件に合わせてレイアウトを制御したりできます。

## よくある質問

### ヘッダーとフッターのフォントをカスタマイズできますか?  
はい、ヘッダーとフッターのテキストのフォント、サイズ、色、スタイルを完全にカスタマイズできます。

### ヘッダーとフッターに画像を追加するにはどうすればよいですか?  
使用できます`ImageStamp`ヘッダーとフッターに画像を挿入します。

### ヘッダーやフッターにハイパーリンクを追加することは可能ですか?  
はい、使えます`TextFragment`ハイパーリンクを設定することで`Hyperlink`財産。

### 奇数ページと偶数ページで異なるヘッダーを使用できますか?  
はい、Aspose.PDF では、奇数ページと偶数ページに異なるヘッダーとフッターを指定できます。

### ヘッダーとフッターの位置を調整するにはどうすればよいですか?  
余白と配置のプロパティを調整して、ヘッダーとフッターの位置を制御できます。