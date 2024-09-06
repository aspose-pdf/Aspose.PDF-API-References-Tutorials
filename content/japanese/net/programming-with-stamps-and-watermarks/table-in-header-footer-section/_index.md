---
title: ヘッダー フッター セクションの表
linktitle: ヘッダー フッター セクションの表
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ドキュメントのヘッダー/フッター セクションにテーブルを追加する方法を学習します。
type: docs
weight: 170
url: /ja/net/programming-with-stamps-and-watermarks/table-in-header-footer-section/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントのヘッダーまたはフッター セクションにテーブルを追加する方法を段階的に説明します。提供されている C# ソース コードでは、空の PDF ドキュメントを作成し、ページを追加し、ヘッダー セクションを構成し、テーブルを作成し、テーブルに行とセルを追加し、最後に PDF ドキュメントを保存する方法が示されています。

## ステップ1: 環境の設定

始める前に、次のものがあることを確認してください。

- インストールされた .NET 開発環境。
- .NET 用の Aspose.PDF ライブラリがダウンロードされ、プロジェクトで参照されます。

## ステップ2: PDFドキュメントとページの作成

最初のステップは、`Document`クラスを作成して、ドキュメントにページを追加します。方法は次のとおりです。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Documentオブジェクトをインスタンス化する
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// PDF文書にページを作成する
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

「YOUR DOCUMENTS DIRECTORY」を、PDF ドキュメントを保存するディレクトリへの実際のパスに置き換えてください。

## ステップ3: ヘッダーセクションの構成

次に、PDFドキュメントのヘッダーセクションを構成するために、`HeaderFooter`クラス。方法は次のとおりです。

```csharp
// PDFファイルのヘッダーセクションを作成する
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

//ページのヘッダーセクションを定義する
page. Header = header;

//ヘッダーセクションの上余白を設定する
header. Margin. Top = 20;
```

## ステップ4: テーブルの作成

次は、`Table`クラスを作成し、見出しセクションの段落コレクションに追加します。方法は次のとおりです。

```csharp
//テーブルオブジェクトをインスタンス化する
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

//ヘッダーセクションの段落コレクションに表を追加します
header.Paragraphs.Add(tab1);

//表の列の幅を定義する
tab1.ColumnWidths = "60,300";
```

上記のコードは、指定された幅の 2 つの列を持つテーブルを作成します。

## ステップ5: 表に行とセルを追加する

次に、テーブルに行とセルを追加します。`Row`クラスと`Cell`クラス。方法は次のとおりです。

```csharp
//表に行を作成し、セルを追加する
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in header section");
row1.BackgroundColor = Color.Gray;

//最初の行の最初のセルを結合する
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

//表に別の行を作成し、画像を含むセルを追加します
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

## ステップ6: PDFドキュメントを保存する

テーブルをヘッダー セクションに追加したら、PDF ドキュメントを保存できます。手順は次のとおりです。

```csharp
//PDFファイルを保存する
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");
```

「YOUR DOCUMENTS DIRECTORY」を、PDF ドキュメントを保存するディレクトリへの実際のパスに置き換えてください。

### Aspose.PDF for .NET を使用したヘッダー フッター セクションの表のサンプル ソース コード 
```csharp

//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//空のコンストラクタを呼び出してDocumentインスタンスをインスタンス化する
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

//PDF文書にページを作成する
Aspose.Pdf.Page page = pdfDocument.Pages.Add();

//PDFファイルのヘッダーセクションを作成する
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

//PDFファイルの奇数ヘッダーを設定する
page.Header = header;

//ヘッダーセクションの上余白を設定する
header.Margin.Top = 20;

//テーブルオブジェクトをインスタンス化する
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

//希望するセクションの段落コレクションに表を追加します
header.Paragraphs.Add(tab1);

//BorderInfo オブジェクトを使用してデフォルトのセル境界線を設定する
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

//テーブルの列幅を設定する
tab1.ColumnWidths = "60 300";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";

//表に行を作成し、行にセルを作成します
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in Header Section");
row1.BackgroundColor = Color.Gray;

//最初の行の行スパン値を2に設定します
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

//表に行を作成し、行にセルを作成します
Aspose.Pdf.Row row2 = tab1.Rows.Add();

//行2の背景色を設定する
row2.BackgroundColor = Color.White;

//画像を保持するセルを追加します
Aspose.Pdf.Cell cell2 = row2.Cells.Add();

//画像の幅を60に設定します
img.FixWidth = 60;

//表のセルに画像を追加する
cell2.Paragraphs.Add(img);
row2.Cells.Add("Logo is looking fine !");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

//テキストの垂直方向の配置を中央揃えに設定します
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;

//PDFファイルを保存する
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");

```

## 結論

おめでとうございます! Aspose.PDF for .NET を使用して、PDF ドキュメントのヘッダーまたはフッター セクションにテーブルを追加する方法を学習しました。テーブルを追加して PDF ドキュメントに追加情報を表示することで、ヘッダーとフッターをカスタマイズできるようになりました。

### ヘッダー フッター セクションのテーブルに関する FAQ

#### Q: PDF ドキュメントのヘッダーまたはフッター セクションに表を追加する目的は何ですか?

A: PDF ドキュメントのヘッダーまたはフッター セクションにテーブルを追加すると、タイトル、サブタイトル、ロゴ、またはドキュメントの各ページに一貫して表示したいその他のコンテンツなど、構造化され整理された情報を表示できます。

#### Q: 提供されている C# ソース コードでは、どのようにして PDF ドキュメントのヘッダーまたはフッター セクションにテーブルを追加するのですか?

A: このコードは、空の PDF ドキュメントを作成し、ページを追加し、ヘッダー セクションを構成し、行とセルを含むテーブルを作成し、最後に PDF ドキュメントを保存するプロセスを示しています。結果は、PDF ドキュメントのヘッダー セクションに表示されるテーブルです。

#### Q: 境界線、背景色、テキスト スタイルなど、テーブル セルの外観をカスタマイズできますか?

A: はい、セルの境界線、背景色、テキスト スタイル、フォント、フォント サイズなどのプロパティを設定することで、テーブル セルの外観をカスタマイズできます。

#### Q: PDF ドキュメントのヘッダー セクションにテーブルはどのように追加されますか?

A: コードは、ヘッダー セクションの段落コレクションにテーブルを追加し、各ページのヘッダーにテーブルが表示されるようにします。

#### Q: 必要に応じて表に行やセルを追加できますか?

 A: もちろん、テーブルに行やセルを追加するには、`Rows.Add()`そして`Cells.Add()`メソッド。これにより、テーブルの内容を必要に応じて構造化できます。

#### Q: 表の列の幅を調整することは可能ですか?
 A: はい、表の列の幅は、`ColumnWidths`プロパティ。これにより、テーブルのレイアウトを制御できます。

#### Q: テーブル内の複数の列または行にまたがってセルを拡張するにはどうすればよいですか?
 A: 複数の列にまたがるセルを作成するには、`ColSpan`対応するセルのプロパティを使用します。同様に、`RowSpan`複数の行にまたがるセルを作成するプロパティ。

#### Q: PDF ドキュメントのヘッダーセクションとフッターセクションの両方に表を追加するとどうなりますか?

 A: ヘッダーとフッターのセクションの両方で同様のアプローチを取ることができます。`HeaderFooter`フッターのインスタンスを作成し、設定して、その段落コレクションにテーブルを追加します。

#### Q: 表のセル内で画像を使用できますか? また、どのように実現できますか?

 A: はい、表のセル内に画像を追加できます。コード例では、セルに画像を追加する方法を示しています。`Image`オブジェクトを作成し、そのファイル パスとサイズを設定して、セルの段落に追加します。

#### Q: PDF ドキュメントのすべてのページで表が一貫して表示されるようにするにはどうすればよいですか?

 A: ヘッダーまたはフッターセクションにテーブルを追加する場合は、`HeaderFooter`たとえば、Aspose.PDF では、テーブルが各ページに一貫して表示され、均一なレイアウトが提供されます。