---
title: HTMLからPDFへの変換中に資格情報を提供する
linktitle: HTMLからPDFへの変換中に資格情報を提供する
second_title: Aspose.PDF for .NET API リファレンス
description: このステップバイステップ ガイドでは、Aspose.PDF for .NET を使用して HTML を PDF に変換する方法を説明します。ドキュメント生成を効率化したい開発者に最適です。
type: docs
weight: 240
url: /ja/net/document-conversion/provide-credentials-during-html-to-pdf/
---
## 導入

ソフトウェア開発の世界では、HTML を PDF に変換することは一般的な要件です。レポート、請求書、またはその他のドキュメントを生成する場合でも、このタスクを処理するための信頼性の高いライブラリがあれば、多くの時間と労力を節約できます。開発者が PDF ドキュメントを簡単に作成、操作、変換できるようにする強力なライブラリ、Aspose.PDF for .NET の登場です。このチュートリアルでは、安全なアクセスのための資格情報を提供しながら、Aspose.PDF を使用して HTML を PDF に変換するプロセスについて説明します。では、コーディングの帽子をかぶって、さっそく始めましょう。

## 前提条件

始める前に、いくつか準備しておくべきことがあります。

1. Visual Studio: マシンに Visual Studio がインストールされていることを確認してください。これが開発環境になります。
2.  Aspose.PDF for .NET: ライブラリは以下からダウンロードできます。[Webサイト](https://releases.aspose.com/pdf/net/)まずは試してみたいという方は、[無料トライアル](https://releases.aspose.com/).
3. C# の基礎知識: C# プログラミングに精通していると、例をよりよく理解するのに役立ちます。
4. インターネット アクセス: URL から HTML コンテンツを取得するため、インターネット接続が有効であることを確認してください。

## パッケージのインポート

Aspose.PDF を使い始めるには、必要なパッケージをプロジェクトにインポートする必要があります。手順は次のとおりです。

1. Visual Studio プロジェクトを開きます。
2. ソリューション エクスプローラーでプロジェクトを右クリックし、[NuGet パッケージの管理] を選択します。
3. 「Aspose.PDF」を検索し、最新バージョンをインストールしてください。

```csharp
using System.IO;
using Aspose.Pdf;
using System;
using System.Net;
```
これですべての設定が完了したので、資格情報を使用して HTML を PDF に変換するプロセスを管理しやすいステップに分解してみましょう。

## ステップ1: ドキュメントディレクトリを設定する

HTML を PDF に変換する前に、出力 PDF を保存する場所を指定する必要があります。これは、ドキュメント ディレクトリへのパスを定義することによって行われます。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

交換する`"YOUR DOCUMENT DIRECTORY"` PDF ファイルを保存する実際のパスを入力します。デスクトップ上のフォルダーでも、システム上の他の場所でもかまいません。

## ステップ2: Webリクエストを作成する

次に、特定のURLからHTMLコンテンツを取得するためのリクエストを作成する必要があります。ここで、`WebRequest`クラス。

```csharp
WebRequest request = WebRequest.Create("http://My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
```

ここでは、変換する HTML を含む URL へのリクエストを作成しています。使用する URL に必ず置き換えてください。

## ステップ 3: 資格情報を設定する (必要な場合)

サーバーがコンテンツにアクセスするために認証情報を必要とする場合は、それを設定する必要があります。これは、`CredentialCache.DefaultCredentials`.

```csharp
request.Credentials = CredentialCache.DefaultCredentials;
```

この行は、リクエストが現在のユーザーのデフォルトの資格情報を使用することを保証します。特定の資格情報を提供する必要がある場合は、新しい`NetworkCredential`物体。

## ステップ4: 応答を取得する

リクエストの設定が完了したので、サーバーからの応答を取得します。

```csharp
HttpWebResponse response = (HttpWebResponse)request.GetResponse();
```

この行はリクエストを送信し、サーバーが応答するのを待ちます。すべてがうまくいけば、必要な HTML コンテンツが受信されます。

## ステップ5: レスポンスストリームを読み取る

レスポンスを受け取ったら、サーバーから返されたコンテンツを読み取る必要があります。これは、`StreamReader`.

```csharp
Stream dataStream = response.GetResponseStream();
StreamReader reader = new StreamReader(dataStream);
string responseFromServer = reader.ReadToEnd();
reader.Close();
dataStream.Close();
response.Close();
```

ここでは、レスポンスストリームのコンテンツ全体を文字列変数に読み込みます。`responseFromServer`リソースを解放するために、リーダーとストリームを閉じることを忘れないでください。

## ステップ6: HTMLをPDFに変換する

次は面白い部分です。Aspose.PDF を使用して HTML コンテンツを PDF ドキュメントに変換します。

```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));
HtmlLoadOptions options = new HtmlLoadOptions("http://My.signchart.com/");
options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

Document pdfDocument = new Document(stream, options);
```

このステップでは、`MemoryStream` HTMLコンテンツから設定`HtmlLoadOptions`これにより、HTML が参照する可能性のある外部リソース (画像やスタイルシートなど) のベース URL を指定できます。

## ステップ7: PDFドキュメントを保存する

最後に、生成された PDF ドキュメントを指定されたディレクトリに保存する必要があります。

```csharp
pdfDocument.Save(dataDir + "ProvideCredentialsDuringHTMLToPDF_out.pdf");
```

この行はPDFファイルを次の名前で保存します`ProvideCredentialsDuringHTMLToPDF_out.pdf`先ほど指定したディレクトリにあります。

## 結論

これで完了です。安全なアクセスのための資格情報を提供しながら、Aspose.PDF for .NET を使用して HTML を PDF に正常に変換できました。この強力なライブラリを使用すると、PDF ドキュメントを簡単に処理でき、わずか数行のコードで HTML コンテンツからプロフェッショナルな外観の PDF を生成できます。 

## よくある質問

### Aspose.PDF for .NET とは何ですか?
Aspose.PDF for .NET は、開発者が .NET アプリケーションで PDF ドキュメントを作成、操作、変換できるようにするライブラリです。

### Aspose.PDF をインストールするにはどうすればよいですか?
 Aspose.PDFはVisual StudioのNuGetパッケージマネージャーからインストールするか、[Webサイト](https://releases.aspose.com/pdf/net/).

### Aspose.PDF を無料で使用できますか?
はい、Aspose では、購入前にライブラリを評価できる無料試用版を提供しています。

### Aspose.PDF で作成できるドキュメントの種類は何ですか?
Aspose.PDF を使用すると、レポート、請求書、フォームなど、さまざまなドキュメントを作成できます。

### Aspose.PDF のサポートはどこで受けられますか?
サポートを見つけたり質問したりできます[Aspose サポート フォーラム](https://forum.aspose.com/c/pdf/10).