---
title: WebページをPDFに変換
linktitle: WebページをPDFに変換
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して Web ページを PDF に変換するためのステップバイステップ ガイド。
type: docs
weight: 320
url: /ja/net/document-conversion/web-page-to-pdf/
---
このチュートリアルでは、Aspose.PDF for .NET ライブラリを使用して Web ページを PDF に変換する方法を段階的に説明します。提供されている C# ソース コードについて説明し、それを独自のプロジェクトに実装する方法を示します。このチュートリアルを終えると、Web ページを PDF ドキュメントに簡単に変換できるようになります。

## 導入
Web ページを PDF 形式に変換することは、多くのアプリケーションで共通の要件です。 Web コンテンツを PDF に変換すると、元の Web ページのレイアウト、書式設定、画像を簡単に保存できます。 Aspose.PDF for .NET は、この変換を効率的かつ正確に実行できる強力なライブラリです。

## 要件
始める前に、次の前提条件が満たされていることを確認してください。
- マシンにインストールされている Visual Studio
- Aspose.PDF for .NET ライブラリ (Aspose の公式 Web サイトからダウンロードできます)
- C# プログラミングの基本的な知識


## ステップ 1: ドキュメント ディレクトリを定義する
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
交換する`"YOUR DOCUMENT DIRECTORY"`生成された PDF ファイルを保存するパスを指定します。

## ステップ 2: Web リクエストを作成する
```csharp
WebRequest request = WebRequest.Create("https://en.wikipedia.org/wiki/Main_Page");
request.Credentials = CredentialCache.DefaultCredentials;
```
Web リクエスト オブジェクトを作成し、変換する Web ページの URL を指定します。 URL を任意の Web ページに置き換えることができます。

## ステップ 3: Web 応答を取得する
```csharp
HttpWebResponse response = (HttpWebResponse)request.GetResponse();
```
Web リクエストを送信し、サーバーから応答を取得します。

## ステップ 4: Web コンテンツを読む
```csharp
Stream dataStream = response. GetResponseStream();
StreamReader reader = new StreamReader(dataStream);
string responseFromServer = reader.ReadToEnd();
reader. Close();
dataStream.Close();
response. Close();
```
を使用して Web ページのコンテンツを読み取ります。`StreamReader`そしてそれを`responseFromServer`変数。

## ステップ 5: HTML を PDF に変換する
```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));
HtmlLoadOptions options = new HtmlLoadOptions("https://en.wikipedia.org/wiki/");
Document pdfDocument = new Document(stream, options);
options.PageInfo.IsLandscape = true;
pdfDocument.Save(dataDir + "WebPageToPDF_out.pdf");
```
を作成します`MemoryStream` Web ページのコンテンツをロードするオブジェクト。次に、のインスタンスを作成します`HtmlLoadOptions`Web ページのベース URL を渡します。次に、`Document`ロードされたストリームと HTML ロード オプションを使用してオブジェクトを読み込みます。をセットする`IsLandscape`財産を`true`PDF を横向きにしたい場合。最後に、PDF ドキュメントを指定したディレクトリに保存します

.

## ステップ 6: 例外を処理する
```csharp
catch (Exception ex)
{
Console.WriteLine(ex.Message);
}
```
変換プロセス中に発生する可能性のある例外をキャッチし、エラー メッセージを表示します。

### Aspose.PDF for .NET を使用した Web ページから PDF へのソース コードの例

```csharp
try
{
	
	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// URL のリクエストを作成します。
	WebRequest request = WebRequest.Create("https://En.wikipedia.org/wiki/Main_Page");
	//サーバーで必要な場合は、資格情報を設定します。
	request.Credentials = CredentialCache.DefaultCredentials;
	//リクエストがタイムアウトになるまでのタイムアウト (ミリ秒単位)
	//リクエストタイムアウト = 100;

	//応答を取得します。
	HttpWebResponse response = (HttpWebResponse)request.GetResponse();

	//サーバーから返されたコンテンツを含むストリームを取得します。
	Stream dataStream = response.GetResponseStream();
	//簡単にアクセスできるように、StreamReader を使用してストリームを開きます。
	StreamReader reader = new StreamReader(dataStream);
	//内容を読んでください。
	string responseFromServer = reader.ReadToEnd();
	reader.Close();
	dataStream.Close();
	response.Close();

	MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));
	HtmlLoadOptions options = new HtmlLoadOptions("https:// En.wikipedia.org/wiki/");


	// HTMLファイルの読み込み
	Document pdfDocument = new Document(stream, options);

	options.PageInfo.IsLandscape = true;

	//出力を PDF 形式で保存
	pdfDocument.Save(dataDir + "WebPageToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 結論
このチュートリアルでは、Aspose.PDF for .NET ライブラリを使用して Web ページを PDF に変換する方法を学習しました。提供された C# ソース コードを説明するステップバイステップ ガイドを確認しました。これらの手順に従うことで、Web ページから PDF への変換機能を独自の .NET アプリケーションに簡単に統合できます。

### よくある質問

#### Q: Aspose.PDF for .NET とは何ですか?

A: Aspose.PDF for .NET は、開発者が C# アプリケーションで PDF ドキュメントを操作できるようにする強力なライブラリです。 WebページをPDFに変換するなど、さまざまな機能を提供します。

#### Q: Web ページを PDF に変換したいのはなぜですか?

A: Web ページを PDF に変換すると、元の Web コンテンツのレイアウト、書式設定、画像を保持するのに役立ちます。 Web ページのスナップショットを作成して、オフラインで表示したり、他のユーザーと共有したりできます。

#### Q: このチュートリアルの前提条件は何ですか?

A: このチュートリアルに従うには、マシンに Visual Studio がインストールされていること、.NET ライブラリ用の Aspose.PDF、および C# プログラミングの基本を理解している必要があります。

#### Q: Web ページを PDF に変換できますか?

A: はい、コード内に Web ページの URL を指定することで、任意の Web ページを PDF に変換できます。 Aspose.PDF for .NET は Web コンテンツを取得し、PDF 形式に変換します。

#### Q: ページの向きなど、PDF 出力をカスタマイズするにはどうすればよいですか?

 A: 次のようなオプションを使用して PDF 出力をカスタマイズできます。`IsLandscape`ページの向きを設定します。提供されたコードでは、`options.PageInfo.IsLandscape = true` PDF を横向きで作成するために使用されます。