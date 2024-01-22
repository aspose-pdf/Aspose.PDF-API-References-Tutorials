---
title: PDF ファイルにタイムスタンプを使用してデジタル署名する
linktitle: PDF ファイルにタイムスタンプを使用してデジタル署名する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイルにタイムスタンプ付きのデジタル署名を実行する方法を学びます。
type: docs
weight: 50
url: /ja/net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---
このチュートリアルでは、Aspose.PDF for .NET を使用してタイムスタンプ付きで PDF ファイルにデジタル署名するプロセスを説明します。タイムスタンプ付きデジタル署名は、タイムスタンプ付きの電子指紋を追加することにより、文書の信頼性と完全性を保証します。

## ステップ 1: 前提条件

始める前に、次の前提条件を満たしていることを確認してください。

- C# プログラミング言語の基本的な知識
- マシンに Visual Studio をインストールする
- .NET 用の Aspose.PDF ライブラリがインストールされている

## ステップ 2: 環境セットアップ

開始するには、次の手順に従って開発環境をセットアップします。

1. Visual Studio を開き、新しい C# プロジェクトを作成します。
2. 必要な名前空間をコード ファイルにインポートします。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
```

## ステップ 3: タイムスタンプ付きのデジタル署名

最初のステップは、PDF ファイルにタイムスタンプを使用してデジタル署名を実行することです。提供されたコードは、Aspose.PDF for .NET を使用してこの署名を実現する方法を示しています。

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

このコードは PDF ファイルをロードし、PFX ファイル (秘密キー) と指定されたタイムスタンプ パラメーターを使用してタイムスタンプ付きのデジタル署名を作成します。署名は PDF ファイルに追加され、「」というサフィックスを付けて保存されます。_外"。

### Aspose.PDF for .NET を使用したタイムスタンプ付きデジタル署名のサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
	using (PdfFileSignature signature = new PdfFileSignature(document))
	{
		PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
		TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password"); //ユーザー/パスワードは省略可能
		pkcs.TimestampSettings = timestampSettings;
		System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
		// つの署名タイプのいずれかを作成します
		signature.Sign(1, "Signature Reason", "Contact", "Location", true, rect, pkcs);
		//出力された PDF ファイルを保存する
		signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
	}
}
```

## 結論

おめでとうございます！ Aspose.PDF for .NET を使用して、PDF ファイルにタイムスタンプ付きのデジタル署名を正常に実行できました。このチュートリアルでは、署名の作成から更新された PDF ファイルの保存までの段階的なプロセスを説明しました。この機能を使用して、タイムスタンプ付きのデジタル署名を PDF ファイルに追加できるようになりました。

### PDF ファイルにタイムスタンプを使用してデジタル署名するための FAQ

#### Q: タイムスタンプを使用してデジタル署名する目的は何ですか?

A: タイムスタンプを使用してデジタル署名すると、タイムスタンプ付きの電子指紋が PDF ファイルに追加され、特定の時点での文書の信頼性と完全性が保証されます。

#### Q: このチュートリアルを開始するにはどのような前提条件が必要ですか?

A: 始める前に、C# プログラミング言語の基本を理解していること、Visual Studio がインストールされていること、および .NET 用の Aspose.PDF ライブラリがインストールされていることを確認してください。

#### Q: 開発環境をセットアップするにはどうすればよいですか?

A: Visual Studio での新しい C# プロジェクトの作成や必要な名前空間のインポートなど、提供された手順に従って開発環境をセットアップします。

#### Q: タイムスタンプ付きのデジタル署名を PDF に追加するにはどうすればよいですか?

A: 提供されているサンプル コードは、PDF ファイルをロードし、PFX ファイル (秘密キー) と指定されたタイムスタンプ設定を使用してタイムスタンプ付きのデジタル署名を作成し、PDF ファイルに署名を追加し、更新されたファイルを保存する方法を示しています。

#### Q: PFX ファイルとは何ですか? なぜこのファイルが例で使用されているのですか?

A: PFX (Personal Exchange Format) ファイルには、秘密キーと証明書が含まれています。ここでは、デジタル署名の暗号化機能を提供するために使用されます。プレースホルダーを PFX ファイルとパスワードに置き換えてください。

#### Q: TimestampSettings とは何ですか?

A: TimestampSettings は、電子タイムスタンプを署名に追加するために使用されるタイムスタンプ サーバーの設定を定義します。これには、タイムスタンプ サーバーの URL とオプションのユーザー資格情報が含まれます。

#### Q: 例にあるもの以外のタイムスタンプ サーバーを使用できますか?
 A: はい、互換性のあるタイムスタンプ サーバーであればどれでも使用できます。 URL を置き換え、必要に応じて、適切なユーザー認証情報を`TimestampSettings`物体。

#### Q: 署名四角形を指定する目的は何ですか?

A: 署名の四角形は、PDF ページ上のデジタル署名の外観の位置と寸法を定義します。これらの値を調整して、必要に応じて署名を配置します。

#### Q: 署名中にタイムスタンプ サーバーが利用できない場合はどうなりますか?

A: 署名中にタイムスタンプ サーバーが利用できない場合、プロセスが失敗するか、時間がかかる可能性があります。タイムスタンプ サーバーが信頼でき、アクセス可能であることを確認してください。

#### Q: 署名された PDF にタイムスタンプが存在することを確認するにはどうすればよいですか?

 A: 提供されているサンプル コードを使用して、署名された PDF を調べることができます。の`TimestampSettings`署名中に使用した情報は、署名の詳細で利用できるはずです。

#### Q: タイムスタンプ付きのデジタル署名には法的拘束力がありますか?

A: タイムスタンプ付きのデジタル署名は多くの法域で法的価値を有しており、多くの場合、単純なデジタル署名よりも信頼性が高いと考えられています。特定の規制については、管轄区域の法律専門家に相談してください。

#### Q: タイムスタンプ付きの複数のデジタル署名を PDF に追加できますか?

A: はい、署名作成プロセスを複数回呼び出すことで、タイムスタンプ付きの複数のデジタル署名を PDF ファイルに追加できます。各署名には独自のタイムスタンプがあります。