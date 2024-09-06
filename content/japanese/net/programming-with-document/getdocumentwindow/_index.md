---
title: ドキュメントウィンドウを取得
linktitle: ドキュメントウィンドウを取得
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET の GetDocumentWindow 機能を使用して、PDF ドキュメントのウィンドウ プロパティに関する情報を取得する方法を学習します。
type: docs
weight: 170
url: /ja/net/programming-with-document/getdocumentwindow/
---
Aspose.PDF for .NET は、開発者が .NET アプリケーションで PDF ファイルを作成、編集、変換できるようにする強力な PDF 操作ライブラリです。このライブラリが提供する機能の 1 つは、ドキュメントのウィンドウ プロパティに関する情報を取得する機能です。このチュートリアルでは、`GetDocumentWindow` Aspose.PDF for .NET の機能を使用して、PDF ドキュメントのウィンドウ プロパティに関する情報を取得します。

## ステップ 1: Aspose.PDF for .NET をインストールする

.NETアプリケーションでAspose.PDF for .NETを使用するには、まずライブラリをインストールする必要があります。ライブラリの最新バージョンは、[Aspose.PDF for .NET ダウンロード ページ](https://releases.aspose.com/pdf/net).

ライブラリをダウンロードしたら、ZIP ファイルの内容をコンピューターのフォルダーに解凍します。次に、.NET プロジェクトに Aspose.PDF for .NET DLL への参照を追加する必要があります。

## ステップ2: PDFドキュメントを読み込む

 Aspose.PDF for .NETをインストールし、.NETプロジェクトにDLLへの参照を追加したら、`GetDocumentWindow`PDF ドキュメントのウィンドウ プロパティに関する情報を取得する機能。

この機能を使用するための最初のステップは、情報を取得する PDF ドキュメントを読み込むことです。これを行うには、次のコードを使用します。

```csharp
// PDF文書へのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

// PDF文書を開く
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

上記のコードでは、`"YOUR DOCUMENT DIRECTORY"` PDF文書があるディレクトリへのパスを入力します。このコードはPDF文書を`Document`オブジェクトを使用して、ドキュメントのウィンドウ プロパティに関する情報を取得できます。

## ステップ3: ドキュメントのウィンドウプロパティを取得する

PDF ドキュメントのウィンドウ プロパティに関する情報を取得するには、次のコードを使用できます。

```csharp
//ドキュメントのウィンドウプロパティを取得する
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);
Console.WriteLine("Direction : {0}", pdfDocument.Direction);
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

上記のコードでは、各行で PDF ドキュメントの異なるウィンドウ プロパティを取得し、コンソールに出力します。このコードをカスタマイズして、必要なプロパティのみを取得できます。

### Aspose.PDF for .NET を使用して PDF ファイルのドキュメント ウィンドウを取得するためのサンプル ソース コード 

以下はPDF文書のウィンドウプロパティを取得するための完全なソースコードです。`GetDocumentWindow` Aspose.PDF for .NET の機能:

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//ドキュメントを開く
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");

//さまざまなドキュメントプロパティを取得する
//ドキュメントのウィンドウの位置 - デフォルト: false
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);

//主な読み順。ページの位置を決定します。
//並べて表示する場合 - デフォルト: L2R
Console.WriteLine("Direction : {0}", pdfDocument.Direction);

//ウィンドウのタイトルバーにドキュメントのタイトルを表示するかどうか
//false の場合、タイトルバーに PDF ファイル名が表示されます - デフォルト: false
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);

//ドキュメントのウィンドウをサイズに合わせて変更するかどうか
//最初に表示されるページ - デフォルト: false
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);

//ビューアアプリケーションのメニューバーを非表示にするかどうか - デフォルト: false
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);

//ビューアアプリケーションのツールバーを非表示にするかどうか - デフォルト: false
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);

//スクロールバーなどのUI要素を非表示にするかどうか
//ページの内容のみを表示したままにします - デフォルト: false
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);

//ドキュメントのページ モード。フルスクリーン モードを終了したときにドキュメントを表示する方法。
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);

//ページレイアウト（単一ページ、1列）
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);

//ドキュメントを開いたときにどのように表示されるか
//つまり、サムネイルを表示、全画面表示、添付ファイルパネルを表示
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントのウィンドウ プロパティに関する情報を取得する方法を学習しました。PDF ドキュメントを読み込み、そのウィンドウ プロパティにアクセスすることで、ビューアー アプリケーションで開いたときにドキュメントがどのように表示されるかに関する情報を収集できます。Aspose.PDF for .NET は、PDF ファイルをプログラムで操作するための強力な機能セットを提供するため、.NET アプリケーションで PDF を操作するための貴重なツールとなります。

### よくある質問

#### Q: PDF ドキュメントのウィンドウ プロパティを取得する目的は何ですか?

A: PDF ドキュメントのウィンドウ プロパティを取得すると、ビューア アプリケーションで開いたときに PDF ドキュメントがどのように表示されるかに関する情報を収集できます。これらのプロパティは、ウィンドウの位置、表示モード、UI 要素の表示など、さまざまな側面を制御します。

#### Q: .NET プロジェクトに Aspose.PDF for .NET をインストールするにはどうすればよいですか?

 A: Aspose.PDF for .NETをインストールするには、以下のサイトからライブラリをダウンロードする必要があります。[Aspose.PDF for .NET ダウンロード ページ](https://releases.aspose.com/pdf/net)ダウンロード後、ZIP ファイルの内容を抽出し、.NET プロジェクトに Aspose.PDF for .NET DLL への参照を追加します。

#### Q: 特定のウィンドウ プロパティのみを取得するようにコードをカスタマイズできますか?

A: はい、不要な行をコメント アウトすることで、特定のウィンドウ プロパティを取得するようにコードをカスタマイズできます。コード内の各行は特定のウィンドウ プロパティに対応しているため、要件に応じてプロパティを含めたり除外したりできます。

#### Q: Aspose.PDF for .NET を使用して取得できるウィンドウ プロパティの種類は何ですか?

A: Aspose.PDF for .NET を使用すると、ウィンドウの中央配置、ページ レイアウトの設定、ツール バーやメニュー バーの表示の制御など、PDF ドキュメントのさまざまなウィンドウ プロパティを取得できます。