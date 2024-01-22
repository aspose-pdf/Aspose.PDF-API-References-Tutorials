---
title: PDF ファイルのデジタル サインイン
linktitle: PDF ファイルのデジタル サインイン
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイルにデジタル署名する方法を学びます。
type: docs
weight: 40
url: /ja/net/programming-with-security-and-signatures/digitally-sign/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイルにデジタル署名するプロセスを説明します。デジタル署名は、一意の電子指紋を追加することにより、文書の信頼性と完全性を保証します。

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
using System.Collections.Generic;
```

## ステップ 3: デジタル署名

最初のステップは、PDF ファイルにデジタル署名することです。提供されたコードは、Aspose.PDF for .NET を使用してデジタル署名を作成する方法を示しています。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pbxFile = "";
string inFile = dataDir + @"DigitallySign.pdf";
string outFile = dataDir + @"DigitallySign_out.pdf";
using (Document document = new Document(inFile))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         PKCS7 pkcs = new PKCS7(pbxFile, "WebSales");
         DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
         System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
         signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
         signature.Certify(1, "Reason for signing", "Contact", "Location", true, rect, docMdpSignature);
         signature.Save(outFile);
     }
}
```

このコードは、PDF ファイルをロードし、指定された外観でデジタル署名を作成し、署名を追加して PDF ファイルを保存します。

## ステップ 4: 署名の検証

デジタル署名を追加した後、PDF ファイルに有効な署名が含まれているかどうかを確認できます。

```csharp
using(Document document = new Document(outFile))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         IList<string> sigNames = signature. GetSignNames();
         if (sigNames.Count > 0)
         {
             if (signature.VerifySigned(sigNames[0] as string))
             {
                 if (signature.IsCertified)
                 {
                     if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms)
                     {
                         //何かをしてください
                     }
                 }
             }
         }
     }
}
```

このコードは、PDF ファイルの最初の署名を検証し、署名が認証され、特定のアクセス許可がある場合は追加のアクションを実行します。

### Aspose.PDF for .NET を使用したデジタル署名のサンプル ソース コード 
```csharp
try
{
	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENTS DIRECTORY";
	string pbxFile = "";
	string inFile = dataDir + @"DigitallySign.pdf";
	string outFile = dataDir + @"DigitallySign_out.pdf";
	using (Document document = new Document(inFile))
	{
		using (PdfFileSignature signature = new PdfFileSignature(document))
		{
			PKCS7 pkcs = new PKCS7(pbxFile, "WebSales"); //PKCS7/PKCS7Detached オブジェクトを使用する
			DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
			System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
			//署名の外観を設定する
			signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
			// つの署名タイプのいずれかを作成します
			signature.Certify(1, "Signature Reason", "Contact", "Location", true, rect, docMdpSignature);
			//出力された PDF ファイルを保存する
			signature.Save(outFile);
		}
	}
	using (Document document = new Document(outFile))
	{
		using (PdfFileSignature signature = new PdfFileSignature(document))
		{
			IList<string> sigNames = signature.GetSignNames();
			if (sigNames.Count > 0) //署名はありますか？
			{
				if (signature.VerifySigned(sigNames[0] as string)) //最初のものを確認してください
				{
					if (signature.IsCertified) //認証済み？
					{
						if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms) //アクセス許可を取得する
						{
							//何かをしてください
						}
					}
				}
			}
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 結論

おめでとうございます！ Aspose.PDF for .NET を使用して PDF ファイルにデジタル署名を実行することができました。このチュートリアルでは、デジタル署名の追加からその有効性の検証までの段階的なプロセスを説明しました。この機能を使用して、デジタル署名で PDF ファイルを保護できるようになりました。

### よくある質問

#### Q: このチュートリアルの目的は何ですか?

A: このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイルにデジタル署名するプロセスを説明します。デジタル署名は電子指紋を追加して、文書の信頼性と完全性を保証します。

#### Q: 開始する前にどのような前提条件が必要ですか?

A: 始める前に、C# プログラミング言語の基本を理解していること、Visual Studio がインストールされていること、および .NET 用の Aspose.PDF ライブラリがインストールされていることを確認してください。

#### Q: 開発環境はどのようにセットアップすればよいですか?

A: Visual Studio での新しい C# プロジェクトの作成や必要な名前空間のインポートなど、提供された手順に従って開発環境をセットアップします。

#### Q: PDF ファイルにデジタル署名を追加するにはどうすればよいですか?

 A: 提供されているサンプル コードは、PDF ファイルの読み込み、デジタル署名の作成、外観の指定、署名された PDF ファイルの保存方法を示しています。デジタル署名は、`Certify`の方法`PdfFileSignature`物体。

#### Q: デジタル署名の有効性を確認するにはどうすればよいですか?

A: デジタル署名を追加した後、サンプル コードを使用して署名の有効性を確認できます。署名が認証されており、特定のアクセス許可があるかどうかを確認します。

####  Q: とは何ですか?`PKCS7` object represent?

 A:`PKCS7`オブジェクトは、デジタル署名の暗号化機能を提供するために使用されます。提供されたサンプル コードでデジタル署名を作成するために使用されます。

#### Q: デジタル署名の外観をカスタマイズできますか?

 A: はい、画像へのパスを指定することで、デジタル署名の外観をカスタマイズできます。`SignatureAppearance`の財産`PdfFileSignature`物体。

#### Q: 署名が無効な場合はどうなりますか?

A: 署名が有効でない場合、検証プロセスは失敗し、検証コード ブロック内の対応するアクションは実行されません。

#### Q: デジタル署名のセキュリティを確保するにはどうすればよいですか?

A: デジタル署名は設計上安全であり、暗号化技術を使用して信頼性と完全性を保証します。秘密キーを安全に保管し、デジタル署名の処理に関するベスト プラクティスに従ってください。

#### Q: PDF に複数のデジタル署名を追加できますか?

 A: はい、次のコマンドを使用して PDF ファイルに複数のデジタル署名を追加できます。`PdfFileSignature`オブジェクトの`Sign`または`Certify`方法。各署名は独自の外観と構成を持ちます。