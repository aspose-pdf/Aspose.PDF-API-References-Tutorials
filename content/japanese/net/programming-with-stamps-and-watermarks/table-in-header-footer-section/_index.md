---
title: ヘッダー フッター セクションのテーブル
linktitle: ヘッダー フッター セクションのテーブル
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ドキュメントのヘッダー/フッター セクションに表を追加する方法を学びます。
type: docs
weight: 170
url: /ja/net/programming-with-stamps-and-watermarks/table-in-header-footer-section/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントのヘッダーまたはフッター セクションに表を追加する方法を段階的に説明します。提供されている C# ソース コードは、空の PDF ドキュメントの作成、ページの追加、ヘッダー セクションの構成、テーブルの作成、テーブルへの行とセルの追加、そして最後に PDF ドキュメントの保存方法を示しています。

## ステップ 1: 環境をセットアップする

始める前に、以下のものがあることを確認してください。

- インストールされた .NET 開発環境。
- .NET 用の Aspose.PDF ライブラリがダウンロードされ、プロジェクトで参照されます。

## ステップ 2: PDF ドキュメントとページを作成する

最初のステップは、のインスタンスを作成することです。`Document`クラスを作成し、ドキュメントにページを追加します。その方法は次のとおりです。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Document オブジェクトをインスタンス化する
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// PDF ドキュメント内にページを作成する
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

「YOUR DOCUMENTS DIRECTORY」を、PDF ドキュメントを保存するディレクトリへの実際のパスに必ず置き換えてください。

## ステップ 3: ヘッダー セクションの構成

ここで、のインスタンスを作成して、PDF ドキュメントのヘッダー セクションを構成します。`HeaderFooter`クラス。その方法は次のとおりです。

```csharp
// PDFファイルのヘッダーセクションを作成します。
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

//ページのヘッダー セクションを定義する
page. Header = header;

//ヘッダーセクションの上マージンを設定します
header. Margin. Top = 20;
```

## ステップ 4: テーブルの作成

次に、次を使用してテーブルを作成します。`Table`クラスを作成し、それを見出しセクションの段落コレクションに追加します。その方法は次のとおりです。

```csharp
// Table オブジェクトをインスタンス化する
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

//ヘッダーセクションの段落コレクションに表を追加します。
header.Paragraphs.Add(tab1);

//テーブルの列の幅を定義します
tab1.ColumnWidths = "60,300";
```

上記のコードは、指定された幅の 2 つの列を持つテーブルを作成します。

## ステップ 5: テーブルに行とセルを追加する

ここで、次のコマンドを使用してテーブルに行とセルを追加します。`Row`クラスと`Cell`クラス。その方法は次のとおりです。

```csharp
//テーブルに行を作成し、セルを追加します
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in header section");
row1.BackgroundColor = Color.Gray;

//最初の行の最初のセルを結合します
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

//テーブルに別の行を作成し、画像を含むセルを追加します
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.BackgroundColor = Color.White;
Aspose.Pdf.Cell cell2 = row2.Cells.Add();
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";
img. FixWidth = 60;
cell2.Paragraphs.Add(img);
row2.Cells.Add("The logo is beautiful!");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
```

## ステップ 6: PDF ドキュメントを保存する

表をヘッダー セクションに追加したら、PDF ドキュメントを保存できます。その方法は次のとおりです。

```csharp
//PDF ファイルを保存する
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");
```

「YOUR DOCUMENTS DIRECTORY」を、PDF ドキュメントを保存するディレクトリへの実際のパスに必ず置き換えてください。

### Aspose.PDF for .NET を使用したヘッダー フッター セクションのテーブルのサンプル ソース コード 
```csharp

//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//空のコンストラクターを呼び出して Document インスタンスをインスタンス化します。
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// PDFドキュメント内にページを作成する
Aspose.Pdf.Page page = pdfDocument.Pages.Add();

//PDFファイルのヘッダーセクションを作成する
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

//PDF ファイルの奇数ヘッダーを設定する
page.Header = header;

//ヘッダーセクションの上マージンを設定します
header.Margin.Top = 20;

//テーブルオブジェクトをインスタンス化する
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

//目的のセクションの段落コレクションに表を追加します
header.Paragraphs.Add(tab1);

//BorderInfo オブジェクトを使用してデフォルトのセル境界線を設定する
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

//テーブルの列幅で設定します
tab1.ColumnWidths = "60 300";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";

//テーブルに行を作成し、その行にセルを作成します。
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in Header Section");
row1.BackgroundColor = Color.Gray;

//最初の行の行スパン値を 2 に設定します。
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

//テーブルに行を作成し、その行にセルを作成します。
Aspose.Pdf.Row row2 = tab1.Rows.Add();

// Row2 の背景色を設定します。
row2.BackgroundColor = Color.White;

//画像を保持するセルを追加します
Aspose.Pdf.Cell cell2 = row2.Cells.Add();

//画像の幅を60に設定します
img.FixWidth = 60;

//表のセルに画像を追加します
cell2.Paragraphs.Add(img);
row2.Cells.Add("Logo is looking fine !");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

//テキストの垂直方向の配置を中央揃えに設定します
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;

//PDF ファイルを保存する
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");

```

## 結論

おめでとうございます！ Aspose.PDF for .NET を使用して、PDF ドキュメントのヘッダーまたはフッター セクションに表を追加する方法を学習しました。 PDF ドキュメントに追加情報を表示するテーブルを追加して、ヘッダーとフッターをカスタマイズできるようになりました。

### ヘッダー フッター セクションのテーブルに関する FAQ

#### Q: PDF ドキュメントのヘッダーまたはフッター セクションに表を追加する目的は何ですか?

A: PDF ドキュメントのヘッダーまたはフッター セクションに表を追加すると、タイトル、サブタイトル、ロゴ、ドキュメントの各ページに一貫して表示したいその他のコンテンツなど、構造化され整理された情報を表示できます。

#### Q: 提供されている C# ソース コードでは、PDF ドキュメントのヘッダーまたはフッター セクションにテーブルをどのように追加しますか?

A: このコードは、空の PDF ドキュメントの作成、ページの追加、ヘッダー セクションの構成、行とセルを含むテーブルの作成、そして最後に PDF ドキュメントの保存のプロセスを示しています。結果として、PDF ドキュメントのヘッダー セクションに表が表示されます。

#### Q: 表のセルの外観(境界線、背景色、テキストスタイルなど)をカスタマイズできますか?

A: はい、セルの境界線、背景色、テキスト スタイル、フォント、フォント サイズなどのプロパティを設定することで、表のセルの外観をカスタマイズできます。

#### Q: PDF ドキュメントのヘッダー セクションに表はどのように追加されますか?

A: コードはヘッダー セクションの段落コレクションに表を追加します。これにより、表が各ページのヘッダーに表示されるようになります。

#### Q: 必要に応じてテーブルに行やセルを追加できますか?

 A: もちろん、テーブルに行やセルを追加するには、`Rows.Add()`そして`Cells.Add()`方法。これにより、テーブルの内容を必要に応じて構成できます。

#### Q: 表の列の幅を調整することはできますか?
 A: はい、テーブルの列の幅は、`ColumnWidths`財産。これにより、テーブルのレイアウトを制御できるようになります。

#### Q: テーブル内の複数の列または行にセルをまたがるにはどうすればよいですか?
 A: セルを複数の列にまたがるには、`ColSpan`対応するセルのプロパティ。同様に、`RowSpan`セルを複数の行にまたがるプロパティ。

#### Q: PDF ドキュメントのヘッダー セクションとフッター セクションの両方に表を追加したい場合はどうなりますか?

A: ヘッダー セクションとフッター セクションの両方で同様のアプローチに従うことができます。単に作成するだけです`HeaderFooter`フッターのインスタンスを作成して構成し、その段落コレクションにテーブルを追加します。

#### Q: 表のセル内で画像を使用できますか?それはどのように実現されますか?

 A: はい、表のセル内に画像を追加できます。このコード例は、`Image`オブジェクトを作成し、そのファイル パスとサイズを設定して、セルの段落に追加します。

#### Q: PDF ドキュメント内のすべてのページで表が一貫して表示されるようにするにはどうすればよいですか?

 A: ヘッダーまたはフッター セクションにテーブルを追加する場合、`HeaderFooter`たとえば、Aspose.PDF は、テーブルが各ページに一貫して表示されるようにし、均一なレイアウトを提供します。