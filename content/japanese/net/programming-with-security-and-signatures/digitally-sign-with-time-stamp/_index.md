---
title: PDF ファイルにタイムスタンプを付けてデジタル署名する
linktitle: PDF ファイルにタイムスタンプを付けてデジタル署名する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイルにタイムスタンプ付きのデジタル署名を実行する方法を学習します。
type: docs
weight: 50
url: /ja/net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---
このチュートリアルでは、Aspose.PDF for .NET を使用してタイムスタンプ付きの PDF ファイルにデジタル署名するプロセスについて説明します。タイムスタンプ付きのデジタル署名は、タイムスタンプ付きの電子指紋を追加することで、ドキュメントの信頼性と整合性を保証します。

## ステップ1: 前提条件

始める前に、次の前提条件を満たしていることを確認してください。

- C#プログラミング言語の基礎知識
- マシンに Visual Studio をインストールする
- .NET 用の Aspose.PDF ライブラリがインストールされている

## ステップ2: 環境設定

開始するには、次の手順に従って開発環境をセットアップします。

1. Visual Studio を開き、新しい C# プロジェクトを作成します。
2. 必要な名前空間をコード ファイルにインポートします。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
```

## ステップ3: タイムスタンプ付きデジタル署名

最初のステップは、PDF ファイルにタイムスタンプ付きのデジタル署名を実行することです。提供されているコードは、Aspose.PDF for .NET を使用してこの署名を実現する方法を示しています。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
         TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password");
         pkcs. TimestampSettings = timestampSettings;
         System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
         signature.Sign(1, "Reason for signing", "Contact", "Location", true, rect, pkcs);
         signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
     }
}
```

このコードは PDF ファイルを読み込み、PFX ファイル (秘密鍵) と指定されたタイムスタンプ パラメータを使用してタイムスタンプ付きのデジタル署名を作成します。署名は PDF ファイルに追加され、接尾辞 " を付けて保存されます。_外"。

### Aspose.PDF for .NET を使用してタイムスタンプでデジタル署名するためのサンプル ソース コード 
```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
	using (PdfFileSignature signature = new PdfFileSignature(document))
	{
		PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
		TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password"); //ユーザー名/パスワードは省略可能
		pkcs.TimestampSettings = timestampSettings;
		System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
		//3種類の署名タイプのいずれかを作成する
		signature.Sign(1, "Signature Reason", "Contact", "Location", true, rect, pkcs);
		//出力PDFファイルを保存する
		signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
	}
}
```

## 結論

おめでとうございます! Aspose.PDF for .NET を使用して、PDF ファイルにタイムスタンプ付きのデジタル署名を正常に実行しました。このチュートリアルでは、署名の作成から更新された PDF ファイルの保存までのプロセスをステップごとに説明しました。この機能を使用して、タイムスタンプ付きのデジタル署名を PDF ファイルに追加できるようになりました。

### PDF ファイルにタイムスタンプを付けてデジタル署名するための FAQ

#### Q: タイムスタンプを使用してデジタル署名する目的は何ですか?

A: タイムスタンプを使用してデジタル署名すると、タイムスタンプ付きの電子指紋が PDF ファイルに追加され、特定の時点での文書の信頼性と整合性が保証されます。

#### Q: このチュートリアルを開始するにはどのような前提条件が必要ですか?

A: 始める前に、C# プログラミング言語の基本を理解していること、Visual Studio がインストールされていること、.NET 用の Aspose.PDF ライブラリがインストールされていることを確認してください。

#### Q: 開発環境をどのように設定すればよいですか?

A: Visual Studio で新しい C# プロジェクトを作成し、必要な名前空間をインポートするなど、提供されている手順に従って開発環境をセットアップしてください。

#### Q: PDF にタイムスタンプ付きのデジタル署名を追加するにはどうすればよいですか?

A: 提供されているサンプル コードは、PDF ファイルを読み込み、PFX ファイル (秘密キー) と指定されたタイムスタンプ設定を使用してタイムスタンプ付きのデジタル署名を作成し、PDF ファイルに署名を追加し、更新されたファイルを保存する方法を示しています。

#### Q: PFX ファイルとは何ですか? また、この例ではなぜ PFX ファイルを使用しているのですか?

A: PFX (Personal Exchange Format) ファイルには、秘密キーと証明書が含まれています。ここでは、デジタル署名の暗号化機能を提供するために使用されます。プレースホルダーを PFX ファイルとパスワードに置き換えてください。

#### Q: TimestampSettings とは何ですか?

A: TimestampSettings は、署名に電子タイムスタンプを追加するために使用されるタイムスタンプ サーバーの設定を定義します。これには、タイムスタンプ サーバーの URL とオプションのユーザー資格情報が含まれます。

#### Q: 例にあるタイムスタンプ サーバー以外のタイムスタンプ サーバーを使用できますか?
 A: はい、互換性のあるタイムスタンプサーバーであればどれでも使用できます。URLを置き換え、必要に応じて適切なユーザー認証情報を入力してください。`TimestampSettings`物体。

#### Q: 署名長方形を指定する目的は何ですか?

A: 署名の四角形は、PDF ページ上のデジタル署名の位置と寸法を定義します。これらの値を調整して、署名を希望どおりに配置します。

#### Q: 署名中にタイムスタンプ サーバーが利用できない場合はどうなりますか?

A: 署名中にタイムスタンプ サーバーが利用できない場合、プロセスが失敗したり、時間がかかることがあります。タイムスタンプ サーバーが信頼性が高く、アクセス可能であることを確認してください。

#### Q: 署名された PDF にタイムスタンプが存在するかどうかを確認するにはどうすればよいですか?

 A: 提供されているサンプルコードを使用して署名されたPDFを調べることができます。`TimestampSettings`署名時に使用したパスワードは署名の詳細で確認できるはずです。

#### Q: タイムスタンプ付きのデジタル署名には法的拘束力がありますか?

A: タイムスタンプ付きのデジタル署名は多くの法域で法的価値を持ち、単純なデジタル署名よりも信頼性が高いとみなされることがよくあります。具体的な規制については、管轄地域の法律専門家にご相談ください。

#### Q: PDF にタイムスタンプ付きのデジタル署名を複数追加できますか?

A: はい、署名作成プロセスを複数回呼び出すことで、タイムスタンプ付きの複数のデジタル署名を PDF ファイルに追加できます。各署名には独自のタイムスタンプが付きます。