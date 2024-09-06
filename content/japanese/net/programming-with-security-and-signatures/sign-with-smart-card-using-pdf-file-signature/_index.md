---
title: PDF ファイル署名を使用してスマート カードで署名する
linktitle: PDF ファイル署名を使用してスマート カードで署名する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して、スマート カードで PDF ファイルに安全に署名します。
type: docs
weight: 110
url: /ja/net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---
スマート カードを使用したデジタル署名は、PDF ファイルに署名するための安全な方法です。Aspose.PDF for .NET を使用すると、次のソース コードに従って、スマート カードを使用して PDF ファイルに簡単に署名できます。

## ステップ1: 必要なライブラリをインポートする

始める前に、C# プロジェクトに必要なライブラリをインポートする必要があります。必要なインポート ディレクティブは次のとおりです。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## ステップ2: ドキュメントフォルダへのパスを設定する

この手順では、署名するPDFファイルを含むフォルダへのパスを指定する必要があります。`"YOUR DOCUMENTS DIRECTORY"`次のコードでは、ドキュメント フォルダーへの実際のパスを指定します。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ3: PDF文書を読み込む

ここで、次のコードを使用して署名する PDF ドキュメントを読み込みます。

```csharp
Document doc = new Document(dataDir + "blank.pdf");
```

## ステップ4: スマートカードで署名を実行する

このステップでは、スマートカードを使用して署名を実行します。`PdfFileSignature`クラスから`Facades`ライブラリ。Windows 証明書ストアからスマート カード証明書を選択し、必要な署名情報を指定します。対応するコードは次のとおりです。

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature())
{
     pdfSign.BindPdf(doc);

     //ストアで証明書を選択する
     X509Store store = new X509Store(StoreLocation.CurrentUser);
     store.Open(OpenFlags.ReadOnly);
     X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
     ExternalSignature externalSignature = new ExternalSignature(sel[0]);

     pdfSign.SignatureAppearance = dataDir + "demo.png";
     pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
     pdfSign.Save(dataDir + "externalSignature2.pdf");
}
```

## ステップ5: 署名を確認する

最後に、署名されたPDFファイルの署名を検証します。`PdfFileSignature`クラス。署名名を取得して、1 つずつチェックします。署名の検証に失敗した場合は、例外がスローされます。対応するコードは次のとおりです。

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
{
     IList<string> sigNames = pdfSign. GetSignNames();
     for (int index = 0; index <= sigNames.Count - 1; index++)
     {
         if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
         {
             throw new ApplicationException("Unverified");
         }
     }
}
```

### Aspose.PDF for .NET を使用した PDF ファイル署名によるスマート カード署名のサンプル ソース コード 
```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
	pdfSign.BindPdf(doc);
	//Windows 証明書ストアで証明書を選択して署名する
	System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
	store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
	//ストアで証明書を手動で選択
	System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel = System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
	Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0]);
	pdfSign.SignatureAppearance = dataDir + "demo.png";
	pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
	pdfSign.Save(dataDir + "externalSignature2.pdf");
}
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
{
	IList<string> sigNames = pdfSign.GetSignNames();
	for (int index = 0; index <= sigNames.Count - 1; index++)
	{
		if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
		{
			throw new ApplicationException("Not verified");
		}
	}
}
```

## 結論

おめでとうございます! Aspose.PDF for .NET を使用してスマート カードで PDF ファイルに署名するためのステップ バイ ステップ ガイドが完成しました。このコードを使用して、PDF ドキュメントに安全なデジタル署名を追加できます。

高度なデジタル署名および証明書管理機能の詳細については、Aspose.PDF の公式ドキュメントを必ず確認してください。

### よくある質問

#### Q: スマート カードを使用して PDF ファイルに署名することを検討する必要があるのはなぜですか?

A: スマート カードを使用して PDF ファイルに署名すると、ドキュメントの信頼性と整合性が確保され、セキュリティが強化されます。スマート カード ベースの署名により、より高いレベルの信頼性とコンプライアンスが実現します。

#### Q: スマート カード ベースのデジタル署名はどのように機能しますか?

A: スマート カード ベースのデジタル署名では、スマート カードに保存されている暗号化キーを使用して一意のデジタル署名を作成します。この署名は PDF ファイルに添付され、受信者はドキュメントの出所と整合性を検証できます。

#### Q: スマート カード ベースの署名における Aspose.PDF for .NET の役割は何ですか?

A: Aspose.PDF for .NET は、PDF ファイルのスマート カード ベースのデジタル署名を容易にする包括的なツールとライブラリのセットを提供します。これによりプロセスが簡素化され、ドキュメントの署名が安全に行われます。

#### Q: 署名に特定のスマート カード証明書を選択できますか?

A: はい、Windows 証明書ストアから特定のスマート カード証明書を選択して署名することができます。Aspose.PDF for .NET を使用すると、証明書の選択をアプリケーションにシームレスに統合できます。

#### Q: 提供されたソース コードはスマート カード ベースの署名をどのように処理しますか?

A: ソース コードは、PDF ドキュメントをバインドし、スマート カード証明書を選択し、署名情報を指定して、デジタル署名を作成する方法を示しています。また、署名の有効性を検証する方法も示しています。

#### Q: 1 つの PDF ファイルにスマート カードを使用して複数の署名を適用できますか?

A: もちろんです。1 つの PDF ファイルに複数のスマート カード ベースの署名を適用できます。各署名は一意であり、ドキュメント全体のセキュリティに貢献します。

#### Q: 検証手順中に署名の検証に失敗した場合はどうなりますか?

A: 署名の検証に失敗した場合、署名が有効でないことを示す例外がスローされます。これにより、有効で信頼できる署名のみが受け入れられるようになります。

#### Q: スマート カード ベースの署名は、すべての種類の PDF ドキュメントと互換性がありますか?

A: はい、スマート カード ベースの署名は、すべての種類の PDF ドキュメントと互換性があります。フォーム、レポートなど、さまざまな種類の PDF ファイルにデジタル署名を適用できます。

#### Q: 高度なデジタル署名と証明書の管理について詳しく知るにはどうすればよいですか?

A: 高度なデジタル署名機能、証明書管理、ドキュメントのセキュリティを確保するためのベスト プラクティスの詳細については、Aspose.PDF の公式ドキュメントを参照してください。

#### Q: スマート カード ベースの署名の実装に関する詳細な支援やサポートはどこで受けられますか?

A: 追加のガイダンスとサポートについては、Aspose.PDF コミュニティ フォーラムにアクセスするか、スマート カード ベースの署名に関する包括的な情報が記載されたドキュメントを参照してください。