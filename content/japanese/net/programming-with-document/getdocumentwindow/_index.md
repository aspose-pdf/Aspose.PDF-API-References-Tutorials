---
title: ドキュメントの取得ウィンドウ
linktitle: ドキュメントの取得ウィンドウ
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET の GetDocumentWindow 機能を使用して、PDF ドキュメントのウィンドウ プロパティに関する情報を取得する方法を学習します。
type: docs
weight: 170
url: /ja/net/programming-with-document/getdocumentwindow/
---
 Aspose.PDF for .NET は、開発者が .NET アプリケーションで PDF ファイルを作成、編集、変換できるようにする強力な PDF 操作ライブラリです。このライブラリが提供する機能の 1 つは、ドキュメントのウィンドウ プロパティに関する情報を取得する機能です。このチュートリアルでは、`GetDocumentWindow` Aspose.PDF for .NET の機能を使用して、PDF ドキュメントのウィンドウ プロパティに関する情報を取得します。

## ステップ 1: Aspose.PDF for .NET をインストールする

 .NET アプリケーションで Aspose.PDF for .NET を使用するには、まずライブラリをインストールする必要があります。ライブラリの最新バージョンは、次の場所からダウンロードできます。[Aspose.PDF for .NET ダウンロード ページ](https://releases.aspose.com/pdf/net).

ライブラリをダウンロードしたら、ZIP ファイルの内容をコンピュータ上のフォルダに抽出します。次に、.NET プロジェクトに Aspose.PDF for .NET DLL への参照を追加する必要があります。

## ステップ 2: PDF ドキュメントをロードする

Aspose.PDF for .NET をインストールし、.NET プロジェクトに DLL への参照を追加すると、`GetDocumentWindow` PDF ドキュメントのウィンドウ プロパティに関する情報を取得する機能。

この機能を使用する最初のステップは、情報を取得する PDF ドキュメントをロードすることです。これを行うには、次のコードを使用できます。

```csharp
// PDF ドキュメントへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

//PDF ドキュメントを開く
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

上記のコードでは、次のように置き換えます。`"YOUR DOCUMENT DIRECTORY"` PDF ドキュメントが置かれているディレクトリへのパスを置き換えます。このコードは PDF ドキュメントを`Document`オブジェクトを使用して、ドキュメントのウィンドウ プロパティに関する情報を取得できます。

## ステップ 3: ドキュメントのウィンドウ プロパティを取得する

PDF ドキュメントのウィンドウ プロパティに関する情報を取得するには、次のコードを使用できます。

```csharp
//ドキュメントのウィンドウプロパティを取得します。
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

上記のコードでは、各行が PDF ドキュメントの異なるウィンドウ プロパティを取得し、コンソールに出力します。このコードをカスタマイズして、関心のあるプロパティのみを取得することができます。

### Aspose.PDF for .NET を使用した PDF ファイルのドキュメント ウィンドウの取得ソース コードの例 

以下は、PDF ドキュメントのウィンドウ プロパティを取得するための完全なソース コードです。`GetDocumentWindow` Aspose.PDF for .NET の機能:

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//開いた文書
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");

//さまざまなドキュメントのプロパティを取得する
//ドキュメントのウィンドウの位置 - デフォルト: false
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);

//主な読む順序。ページの位置を決定します
//並べて表示する場合 - デフォルト：L2R
Console.WriteLine("Direction : {0}", pdfDocument.Direction);

//ウィンドウのタイトルバーにドキュメントのタイトルを表示するかどうか
//false の場合、タイトル バーに PDF ファイル名が表示されます - デフォルト: false
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);

//ドキュメントのサイズに合わせてウィンドウのサイズを変更するかどうか
//最初に表示されるページ - デフォルト: false
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);

//ビューアアプリケーションのメニューバーを非表示にするかどうか - デフォルト: false
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);

//ビューアアプリケーションのツールバーを非表示にするかどうか - デフォルト: false
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);

//スクロールバーなどのUI要素を非表示にするかどうか
//ページのコンテンツのみを表示したままにします - デフォルト: false
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);

//ドキュメントのページ モード。全画面モードの終了時にドキュメントを表示する方法。
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);

//ページ レイアウト、つまり 1 ページ、1 列
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);

//ドキュメントを開いたときにどのように表示されるべきか
//例: サムネイルの表示、全画面表示、添付パネルの表示
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントのウィンドウ プロパティに関する情報を取得する方法を学習しました。 PDF ドキュメントをロードし、そのウィンドウ プロパティにアクセスすると、ビューア アプリケーションで開いたときにドキュメントがどのように表示されるべきかに関する情報を収集できます。 Aspose.PDF for .NET は、PDF ファイルをプログラムで操作するための強力な機能セットを提供し、.NET アプリケーションで PDF を操作するための貴重なツールとなります。

### よくある質問

#### Q: PDF ドキュメントのウィンドウ プロパティを取得する目的は何ですか?

A: PDF ドキュメントのウィンドウ プロパティを取得すると、PDF ドキュメントがビューア アプリケーションで開かれたときにどのように表示されるべきかに関する情報を収集できます。これらのプロパティは、ウィンドウの位置、表示モード、UI 要素の可視性などのさまざまな側面を制御します。

#### Q: Aspose.PDF for .NET を .NET プロジェクトにインストールするにはどうすればよいですか?

 A: Aspose.PDF for .NET をインストールするには、次の場所からライブラリをダウンロードする必要があります。[Aspose.PDF for .NET ダウンロード ページ](https://releases.aspose.com/pdf/net)。ダウンロード後、ZIP ファイルの内容を抽出し、.NET プロジェクト内の Aspose.PDF for .NET DLL への参照を追加します。

#### Q: 特定のウィンドウ プロパティのみを取得するようにコードをカスタマイズできますか?

A: はい、必要のない行をコメント アウトすることで、コードをカスタマイズして特定のウィンドウ プロパティを取得できます。コードの各行は特定のウィンドウ プロパティに対応するため、要件に基づいてプロパティを含めたり除外したりできます。

#### Q: Aspose.PDF for .NET を使用して取得できるウィンドウ プロパティの種類は何ですか?

A: Aspose.PDF for .NET を使用すると、ウィンドウの中央揃え、ページ レイアウトの設定、ツールバーやメニュー バーの表示の制御など、PDF ドキュメントのさまざまなウィンドウ プロパティを取得できます。