---
title: PDF ファイルのページ番号スタンプ
linktitle: PDF ファイルのページ番号スタンプ
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイルにページ番号スタンプを追加する方法を学びます。
type: docs
weight: 160
url: /ja/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイルにページ番号スタンプを追加する方法を段階的に説明します。提供されている C# ソース コードを使用して、既存の PDF ドキュメントを開き、ページ番号スタンプを作成し、そのプロパティを設定して、PDF ファイル内の特定のページに追加します。

## ステップ 1: 環境をセットアップする

始める前に、以下のものがあることを確認してください。

- インストールされた .NET 開発環境。
- .NET 用の Aspose.PDF ライブラリがダウンロードされ、プロジェクトで参照されます。

## ステップ 2: 既存の PDF ドキュメントをロードする

最初のステップは、既存の PDF ドキュメントをプロジェクトにロードすることです。その方法は次のとおりです。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//既存の PDF ドキュメントを開く
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

「YOUR DOCUMENTS DIRECTORY」を、PDF ドキュメントが配置されているディレクトリへの実際のパスに必ず置き換えてください。

## ステップ 3: ページ番号スタンプの作成と構成

PDF ドキュメントがロードされたので、ページ番号付けバッファーを作成し、必要に応じて構成できます。その方法は次のとおりです。

```csharp
//ページ番号バッファを作成する
PageNumberStamp pageNumberStamp = new PageNumberStamp();

//バッファがバックグラウンドにあるかどうかを定義します
pageNumberStamp.Background = false;

//ページ番号付けバッファの形式
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;

//ページ番号付けバッファの下マージン
pageNumberStamp.BottomMargin = 10;

//ページ番号付けバッファの水平方向の配置
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;

//ページ番号付けの開始番号
pageNumberStamp.StartingNumber = 1;

//ページ番号バッファテキストのプロパティを設定する
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

上記のコードは、ページ番号の形式、下マージン、水平方向の配置、開始番号、テキストのプロパティなどのプロパティを備えたページ番号スタンプを作成します。

## ステップ 4: 特定のページにページ番号スタンプを追加する

ページ番号スタンプを設定したら、PDF ドキュメントの特定のページにページ番号スタンプを追加できます。その方法は次のとおりです。

```csharp
//特定のページにページ番号バッファを追加する
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

上記のコードは、PDF ドキュメントの最初のページにページ番号スタンプを追加します。必要に応じてページ番号を変更できます。

## ステップ 5: 変更した PDF ドキュメントを保存する

ページ番号スタンプを PDF ドキュメントに追加したら、変更した PDF ドキュメントを保存できます。その方法は次のとおりです。

```csharp
//変更した PDF ドキュメントを保存する
pdfDocument.Save(dataDir + "PageNumberStamp_out.pdf");
```

「YOUR DOCUMENTS DIRECTORY」を、編集した PDF ドキュメントを保存するディレクトリへの実際のパスに必ず置き換えてください。

### Aspose.PDF for .NET を使用したページ番号スタンプのサンプル ソース コード 
```csharp

//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//開いた文書
Document pdfDocument = new Document(dataDir+ "PageNumberStamp.pdf");

//ページ番号スタンプを作成する
PageNumberStamp pageNumberStamp = new PageNumberStamp();

//スタンプが背景かどうか
pageNumberStamp.Background = false;
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;
pageNumberStamp.BottomMargin = 10;
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;
pageNumberStamp.StartingNumber = 1;

//テキストのプロパティを設定する
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

おめでとうございます！ Aspose.PDF for .NET を使用して PDF ドキュメントにページ番号スタンプを追加する方法を学習しました。明確で有益なページ番号を追加して、PDF ドキュメントをカスタマイズできるようになりました。

### PDF ファイルのページ番号スタンプに関する FAQ

#### Q: ページ番号スタンプとは何ですか? PDF ファイルにページ番号を追加するためにどのように使用されますか?

A: ページ番号スタンプは、PDF ドキュメントの特定のページに動的なページ番号を追加できる Aspose.PDF の機能です。このチュートリアルでは、PageNumberStamp オブジェクトを作成し、そのプロパティを構成し、それを指定されたページに追加することでこれを実現します。

#### Q: 提供されている C# ソース コードはどのようにして PDF ファイルにページ番号スタンプを追加するのですか?

A: このコードは、既存の PDF ドキュメントをロードし、PageNumberStamp を作成し、さまざまなプロパティ (形式、フォント、配置など) を設定して、特定のページにスタンプを追加する方法を示しています。スタンプは総ページ数を自動的に計算し、正しいページ番号を挿入します。

#### Q: フォント スタイル、色、サイズなど、ページ番号の外観をカスタマイズできますか?

A: もちろん、フォント、フォント サイズ、フォント スタイル (太字、斜体など)、テキストの色などのプロパティを調整することで、ページ番号スタンプの外観をカスタマイズできます。

#### Q: PDF ドキュメント内の複数のページにページ番号スタンプを追加することはできますか?

A: はい、複数の PageNumberStamp オブジェクトを作成し、それぞれを目的のページに追加することで、複数のページにページ番号スタンプを追加できます。

#### Q: ページ番号スタンプをページのコンテンツの一部として表示するか、背景要素として表示するかを選択できますか?

 A: はい、ページ番号スタンプをページのコンテンツの一部として表示するか、背景要素として表示するかを制御できます。`Background` PageNumberStamp のプロパティ。

#### Q: 総ページ数を含むページ番号の形式を指定するにはどうすればよいですか?

 A: コードでは、`Format`PageNumberStamp のプロパティを使用して、ページ番号の形式を指定します。マクロ「# of」は、総ページ数を表すために使用されます。

#### Q: 複数のページに同じページ番号スタンプを追加するとどうなりますか?

A: 同じ PageNumberStamp インスタンスを複数のページに追加すると、各ページに正しいページ番号が表示されます。スタンプはページ番号と総ページ数を自動調整します。

#### Q: PDF ドキュメントのヘッダーまたはフッター セクションにページ番号スタンプを追加できますか?

A: PageNumberStamp は通常、ページのコンテンツに直接追加されますが、FloatingBox またはその他の技術を使用してヘッダー セクションやフッター セクションに配置することもできます。

#### Q: ページ上のページ番号スタンプの位置を指定するにはどうすればよいですか?

 A:`BottomMargin`そして`HorizontalAlignment` PageNumberStamp のプロパティを使用すると、ページ内のスタンプの位置を制御できます。

#### Q: ページ番号を 1 ではなく別の番号から開始したい場合はどうすればよいですか?

 A: 設定できます。`StartingNumber`PageNumberStamp のプロパティを使用して開始ページ番号を指定します。