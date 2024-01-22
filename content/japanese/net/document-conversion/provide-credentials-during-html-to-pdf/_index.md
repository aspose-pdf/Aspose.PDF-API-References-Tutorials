---
title: HTML から PDF への変換中に資格情報を提供する
linktitle: HTML から PDF への変換中に資格情報を提供する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET で資格情報を提供して HTML を PDF に変換するためのステップバイステップ ガイド。
type: docs
weight: 240
url: /ja/net/document-conversion/provide-credentials-during-html-to-pdf/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して安全な URL にアクセスするときに資格情報を提供しながら、HTML ファイルを PDF に変換するプロセスを説明します。以下の手順に従うと、適切な認証情報を使用して HTML コンテンツを PDF に変換できるようになります。

## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。

- C# プログラミング言語の基本的な知識。
- .NET 用の Aspose.PDF ライブラリがシステムにインストールされています。
- Visual Studio などの開発環境。

## ステップ 1: 安全な HTML コンテンツを取得する
このステップでは、適切な資格情報を使用して URL から安全な HTML コンテンツを取得します。次のコードを使用します。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// URL のリクエストを作成します。
WebRequest request = WebRequest.Create("http://My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
//サーバーに必要な場合は、資格情報を設定します。
request.Credentials = CredentialCache.DefaultCredentials;
//応答を取得します。
HttpWebResponse response = (HttpWebResponse)request.GetResponse();

//サーバーから返されたコンテンツを含むストリームを取得します。
Stream dataStream = response. GetResponseStream();
//簡単にアクセスできるように、StreamReader を使用してストリームを開きます。
StreamReader reader = new StreamReader(dataStream);
//内容を読んでください。
string responseFromServer = reader.ReadToEnd();
reader. Close();
dataStream.Close();
response. Close();
```

必ず交換してください`"YOUR DOCUMENTS DIRECTORY"`結果の PDF ファイルを保存する実際のディレクトリに置き換えます。

## ステップ 2: 認証情報を指定して HTML を PDF に変換する
次に、取得した HTML コンテンツをロードし、適切な資格情報を提供しながら PDF 形式に変換します。次のコードを使用します。

```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));

HtmlLoadOptions options = new HtmlLoadOptions("http://My.signchart.com/");
options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

// HTMLファイルをロードする
Document pdfDocument = new Document(stream, options);
```

## ステップ 3: 結果の PDF ファイルを保存する
最後に、結果の PDF ファイルを保存します。次のコードを使用します。

```csharp
//結果の PDF ファイルを保存する
pdfDocument.Save(dataDir + "ProvideCredentialsDuringHTMLToPDF_out.pdf");
```

上記のコードは、結果の PDF ファイルを次のファイル名で保存します。`"ProvideCredentialsDuringHTMLToPDF_out.pdf"`.

### Aspose.PDF for .NET を使用した HTML から PDF への変換中に資格情報を提供するためのソース コードの例

```csharp
try
{
	
	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// URL のリクエストを作成します。
	WebRequest request = WebRequest.Create("http://My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
	//サーバーで必要な場合は、資格情報を設定します。
	request.Credentials = CredentialCache.DefaultCredentials;
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

	HtmlLoadOptions options = new HtmlLoadOptions("http:// My.signchart.com/");
	options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

	// HTMLファイルの読み込み
	Document pdfDocument = new Document(stream, options);
	//結果のファイルを保存する
	pdfDocument.Save("ProvideCredentialsDuringHTMLToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 結論
このチュートリアルでは、Aspose.PDF for .NET を使用して安全な URL にアクセスするときに資格情報を提供しながら、HTML ファイルを PDF に変換する段階的なプロセスについて説明しました。上記の手順に従うことで、正しい資格情報を指定しながら HTML コンテンツを PDF に正常に変換できます。

### よくある質問

#### Q: Aspose.PDF for .NET とは何ですか?

A: Aspose.PDF for .NET は、開発者が C# アプリケーションで PDF ドキュメントを操作できるようにする堅牢なライブラリです。 HTML から PDF への変換など、幅広い機能を提供します。

#### Q: URL から安全な HTML コンテンツを取得するにはどうすればよいですか?

 A: URL から安全な HTML コンテンツを取得するには、`WebRequest` C#のクラス。を使用して適切な資格情報を設定してください。`Credentials`財産。

#### Q: このチュートリアルの前提条件は何ですか?

A: チュートリアルに進む前に、次の前提条件を満たしていることを確認してください。

- C# プログラミング言語の基本的な知識。
- .NET 用の Aspose.PDF ライブラリがシステムにインストールされています。
- Visual Studio などの開発環境。

#### Q: Aspose.PDF for .NET は、HTML を PDF に変換する際に外部リソースをどのように処理しますか?

 A: Aspose.PDF for .NET は、`HtmlLoadOptions`HTML から PDF への変換中に外部リソースを処理するクラス。外部リソースの資格情報を設定するには、`ExternalResourcesCredentials`財産。

#### Q: 生成される PDF ファイルのファイル名をカスタマイズできますか?

 A: はい、PDF ドキュメントを保存するコードを変更することで、結果の PDF ファイルのファイル名をカスタマイズできます。必要なファイル名を変更するだけです。`pdfDocument.Save()`方法。