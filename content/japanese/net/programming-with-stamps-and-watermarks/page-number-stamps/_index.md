---
title: PDF ファイルのページ番号スタンプ
linktitle: PDF ファイルのページ番号スタンプ
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイルにページ番号スタンプを追加する方法を学習します。
type: docs
weight: 160
url: /ja/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイルにページ番号スタンプを追加する方法を段階的に説明します。提供されている C# ソース コードを使用して、既存の PDF ドキュメントを開き、ページ番号スタンプを作成し、そのプロパティを設定して、PDF ファイル内の特定のページに追加します。

## ステップ1: 環境の設定

始める前に、次のものがあることを確認してください。

- インストールされた .NET 開発環境。
- .NET 用の Aspose.PDF ライブラリがダウンロードされ、プロジェクトで参照されます。

## ステップ2: 既存のPDF文書を読み込む

最初のステップは、既存の PDF ドキュメントをプロジェクトに読み込むことです。手順は次のとおりです。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//既存のPDF文書を開く
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

「YOUR DOCUMENTS DIRECTORY」を、PDF ドキュメントが保存されているディレクトリへの実際のパスに置き換えてください。

## ステップ3: ページ番号スタンプの作成と設定

PDF ドキュメントが読み込まれたので、ページ番号バッファを作成し、必要に応じて設定することができます。手順は次のとおりです。

```csharp
//ページ番号バッファを作成する
PageNumberStamp pageNumberStamp = new PageNumberStamp();

//バッファがバックグラウンドにあるかどうかを定義します
pageNumberStamp.Background = false;

//ページ番号バッファのフォーマット
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;

//ページ番号バッファの下余白
pageNumberStamp.BottomMargin = 10;

//ページ番号バッファの水平方向の配置
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;

//ページ番号の開始番号
pageNumberStamp.StartingNumber = 1;

//ページ番号バッファのテキストプロパティを設定する
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

上記のコードは、ページ番号の形式、下余白、水平配置、開始番号、テキスト プロパティなどのプロパティを持つページ番号スタンプを作成します。

## ステップ4: 特定のページにページ番号スタンプを追加する

ページ番号スタンプが設定されると、それを PDF ドキュメントの特定のページに追加できます。手順は次のとおりです。

```csharp
//特定のページにページ番号バッファを追加する
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

上記のコードは、PDF ドキュメントの最初のページにページ番号スタンプを追加します。必要に応じてページ番号を変更できます。

## ステップ5: 変更したPDF文書を保存する

PDF ドキュメントにページ番号スタンプを追加したら、変更した PDF ドキュメントを保存できます。手順は次のとおりです。

```csharp
//変更したPDF文書を保存する
pdfDocument.Save(dataDir + "PageNumberStamp_out.pdf");
```

「YOUR DOCUMENTS DIRECTORY」を、編集した PDF ドキュメントを保存するディレクトリへの実際のパスに置き換えてください。

### Aspose.PDF for .NET を使用したページ番号スタンプのサンプル ソース コード 
```csharp

//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//ドキュメントを開く
Document pdfDocument = new Document(dataDir+ "PageNumberStamp.pdf");

//ページ番号スタンプを作成する
PageNumberStamp pageNumberStamp = new PageNumberStamp();

//スタンプが背景かどうか
pageNumberStamp.Background = false;
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;
pageNumberStamp.BottomMargin = 10;
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;
pageNumberStamp.StartingNumber = 1;

//テキストプロパティを設定する
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;

//特定のページにスタンプを追加する
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
dataDir = dataDir + "PageNumberStamp_out.pdf";

//出力ドキュメントを保存する
pdfDocument.Save(dataDir);
Console.WriteLine("\nPage number stamp added successfully.\nFile saved at " + dataDir);

```

## 結論

おめでとうございます! Aspose.PDF for .NET を使用して PDF ドキュメントにページ番号スタンプを追加する方法を学習しました。これで、明確でわかりやすいページ番号を追加して PDF ドキュメントをパーソナライズできます。

### PDF ファイルのページ番号スタンプに関する FAQ

#### Q: ページ番号スタンプとは何ですか? また、PDF ファイルにページ番号を追加するにはどのように使用しますか?

A: ページ番号スタンプは、PDF ドキュメントの特定のページに動的なページ番号を追加できる Aspose.PDF の機能です。このチュートリアルでは、PageNumberStamp オブジェクトを作成し、そのプロパティを構成して、指定したページに追加することでこれを実現します。

#### Q: 提供されている C# ソース コードはどのようにして PDF ファイルにページ番号スタンプを追加するのでしょうか?

A: このコードは、既存の PDF ドキュメントを読み込み、PageNumberStamp を作成し、さまざまなプロパティ (形式、フォント、配置など) を設定して、特定のページにスタンプを追加する方法を示しています。スタンプは合計ページ数を自動的に計算し、正しいページ番号を挿入します。

#### Q: ページ番号のフォントスタイル、色、サイズなどの外観をカスタマイズできますか?

A: はい、フォント、フォント サイズ、フォント スタイル (太字、斜体など)、テキストの色などのプロパティを調整することで、ページ番号スタンプの外観をカスタマイズできます。

#### Q: PDF ドキュメント内の複数のページにページ番号スタンプを追加することは可能ですか?

A: はい、複数の PageNumberStamp オブジェクトを作成し、それぞれを目的のページに追加することで、複数のページにページ番号スタンプを追加できます。

#### Q: ページ番号スタンプをページのコンテンツの一部として表示するか、背景要素として表示するかを選択できますか?

 A: はい、ページ番号スタンプをページコンテンツの一部として表示するか、背景要素として表示するかは、`Background` PageNumberStamp のプロパティ。

#### Q: 総ページ数を含むページ番号の形式を指定するにはどうすればよいですか?

 A: このコードは`Format`ページ番号の形式を指定するには、PageNumberStamp のプロパティを使用します。マクロ「# of」は、合計ページ数を表すために使用されます。

#### Q: 複数のページに同じページ番号スタンプを追加するとどうなりますか?

A: 同じ PageNumberStamp インスタンスを複数のページに追加すると、各ページに正しいページ番号が表示されます。スタンプはページ番号と合計ページ数を自動的に調整します。

#### Q: PDF ドキュメントのヘッダーまたはフッターセクションにページ番号スタンプを追加できますか?

A: PageNumberStamps は通常、ページのコンテンツに直接追加されますが、FloatingBox またはその他の手法を使用して、ヘッダーまたはフッター セクションに配置することもできます。

#### Q: ページ上のページ番号スタンプの位置を指定するにはどうすればよいですか?

 A:`BottomMargin`そして`HorizontalAlignment` PageNumberStamp のプロパティを使用すると、ページ内のスタンプの位置を制御できます。

#### Q: ページ番号を 1 以外の番号から開始したい場合はどうすればよいですか?

 A: 設定できます`StartingNumber`開始ページ番号を指定するための PageNumberStamp のプロパティ。