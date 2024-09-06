---
title: PDF ファイルにデジタル署名する
linktitle: PDF ファイルにデジタル署名する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイルにデジタル署名する方法を学習します。
type: docs
weight: 40
url: /ja/net/programming-with-security-and-signatures/digitally-sign/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイルにデジタル署名するプロセスについて説明します。デジタル署名は、固有の電子指紋を追加することで、ドキュメントの信頼性と整合性を保証します。

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
using System.Collections.Generic;
```

## ステップ3: デジタル署名

最初のステップは、PDF ファイルにデジタル署名することです。提供されているコードは、Aspose.PDF for .NET を使用してデジタル署名を作成する方法を示しています。

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

このコードは、PDF ファイルを読み込み、指定された外観のデジタル署名を作成し、署名が追加された PDF ファイルを保存します。

## ステップ4: 署名の検証

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
                         //何かをする
                     }
                 }
             }
         }
     }
}
```

このコードは、PDF ファイルの最初の署名を検証し、署名が認証され、特定の権限がある場合は追加のアクションを実行します。

### Aspose.PDF for .NET を使用してデジタル署名するためのサンプル ソース コード 
```csharp
try
{
	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENTS DIRECTORY";
	string pbxFile = "";
	string inFile = dataDir + @"DigitallySign.pdf";
	string outFile = dataDir + @"DigitallySign_out.pdf";
	using (Document document = new Document(inFile))
	{
		using (PdfFileSignature signature = new PdfFileSignature(document))
		{
			PKCS7 pkcs = new PKCS7(pbxFile, "WebSales"); //PKCS7/PKCS7Detachedオブジェクトを使用する
			DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
			System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
			//署名の外観を設定する
			signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
			//3種類の署名タイプのいずれかを作成する
			signature.Certify(1, "Signature Reason", "Contact", "Location", true, rect, docMdpSignature);
			//出力PDFファイルを保存する
			signature.Save(outFile);
		}
	}
	using (Document document = new Document(outFile))
	{
		using (PdfFileSignature signature = new PdfFileSignature(document))
		{
			IList<string> sigNames = signature.GetSignNames();
			if (sigNames.Count > 0) //署名はありますか?
			{
				if (signature.VerifySigned(sigNames[0] as string)) //最初のものを確認する
				{
					if (signature.IsCertified) //認定済みですか?
					{
						if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms) //アクセス許可を取得する
						{
							//何かをする
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

おめでとうございます! Aspose.PDF for .NET を使用して PDF ファイルにデジタル署名を正常に実行できました。このチュートリアルでは、デジタル署名の追加からその有効性の検証まで、手順を追って説明しました。この機能を使用して、デジタル署名で PDF ファイルを保護できるようになりました。

### よくある質問

#### Q: このチュートリアルの目的は何ですか?

A: このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイルにデジタル署名するプロセスについて説明します。デジタル署名は、ドキュメントの信頼性と整合性を確保するために電子指紋を追加します。

#### Q: 始める前に必要な前提条件は何ですか?

A: 始める前に、C# プログラミング言語の基本を理解していること、Visual Studio がインストールされていること、.NET 用の Aspose.PDF ライブラリがインストールされていることを確認してください。

#### Q: 開発環境をどのように設定すればよいですか?

A: Visual Studio で新しい C# プロジェクトを作成し、必要な名前空間をインポートするなど、提供されている手順に従って開発環境をセットアップしてください。

#### Q: PDF ファイルにデジタル署名を追加するにはどうすればよいですか?

 A: 提供されているサンプルコードは、PDFファイルの読み込み、デジタル署名の作成、外観の指定、署名済みPDFファイルの保存方法を示しています。デジタル署名は、`Certify`方法の`PdfFileSignature`物体。

#### Q: デジタル署名の有効性を確認するにはどうすればよいですか?

A: デジタル署名を追加した後、サンプル コードを使用して署名の有効性を検証できます。署名が認証されているかどうか、および特定のアクセス権限があるかどうかを確認します。

####  Q:`PKCS7` object represent?

 A:`PKCS7`オブジェクトは、デジタル署名の暗号化機能を提供するために使用されます。提供されているサンプル コードでデジタル署名を作成するために使用されます。

#### Q: デジタル署名の外観をカスタマイズできますか?

 A: はい、画像へのパスを指定することにより、デジタル署名の外観をカスタマイズできます。`SignatureAppearance`の財産`PdfFileSignature`物体。

#### Q: 署名が有効でない場合はどうなりますか?

A: 署名が有効でない場合、検証プロセスは失敗し、検証コード ブロック内の対応するアクションは実行されません。

#### Q: デジタル署名のセキュリティを確保するにはどうすればよいですか?

A: デジタル署名は設計上安全であり、真正性と整合性を確保するために暗号化技術を使用しています。秘密鍵を安全に保ち、デジタル署名の取り扱いに関するベスト プラクティスに従ってください。

#### Q: PDF に複数のデジタル署名を追加できますか?

 A: はい、PDFファイルに複数のデジタル署名を追加することができます。`PdfFileSignature`オブジェクトの`Sign`または`Certify`メソッド。各署名には独自の外観と構成があります。