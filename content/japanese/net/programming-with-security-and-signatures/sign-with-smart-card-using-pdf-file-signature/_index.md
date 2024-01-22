---
title: PDF ファイル署名を使用したスマート カードによる署名
linktitle: PDF ファイル署名を使用したスマート カードによる署名
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して、スマート カードを使用して PDF ファイルに安全に署名します。
type: docs
weight: 110
url: /ja/net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---
スマート カードを使用したデジタル署名は、PDF ファイルに署名する安全な方法です。 Aspose.PDF for .NET を使用すると、次のソース コードに従って、スマート カードを使用して PDF ファイルに簡単に署名できます。

## ステップ 1: 必要なライブラリをインポートする

始める前に、C# プロジェクトに必要なライブラリをインポートする必要があります。必要なインポート ディレクティブは次のとおりです。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## ステップ 2: ドキュメントフォルダーへのパスを設定する

この手順では、署名する PDF ファイルが含まれるフォルダーへのパスを指定する必要があります。交換する`"YOUR DOCUMENTS DIRECTORY"`次のコードでは、ドキュメント フォルダーへの実際のパスを指定します。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ 3: PDF ドキュメントをロードする

ここで、次のコードを使用して、署名する PDF ドキュメントを読み込みます。

```csharp
Document doc = new Document(dataDir + "blank.pdf");
```

## ステップ 4: スマート カードを使用して署名を実行する

このステップでは、スマート カードを使用して署名を実行します。`PdfFileSignature`からのクラス`Facades`図書館。 Windows 証明書ストアからスマート カード証明書を選択し、必要な署名情報を指定します。対応するコードは次のとおりです。

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature())
{
     pdfSign.BindPdf(doc);

     //ストアで証明書を選択します
     X509Store store = new X509Store(StoreLocation.CurrentUser);
     store.Open(OpenFlags.ReadOnly);
     X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
     ExternalSignature externalSignature = new ExternalSignature(sel[0]);

     pdfSign.SignatureAppearance = dataDir + "demo.png";
     pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
     pdfSign.Save(dataDir + "externalSignature2.pdf");
}
```

## ステップ 5: 署名を検証する

最後に、署名された PDF ファイルの署名を次のコマンドを使用して検証します。`PdfFileSignature`クラス。署名名を取得し、1 つずつ確認します。署名の検証に失敗した場合、例外がスローされます。対応するコードは次のとおりです。

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

### Aspose.PDF for .NET を使用した PDF ファイル署名を使用したスマート カードによる署名のサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
	pdfSign.BindPdf(doc);
	//Windows 証明書ストアで選択した証明書を使用して署名します
	System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
	store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
	//ストアで証明書を手動で選択しました
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

おめでとうございます！これで、Aspose.PDF for .NET を使用してスマート カードで PDF ファイルに署名するためのステップバイステップ ガイドが完成しました。このコードを使用して、PDF ドキュメントに安全なデジタル署名を追加できます。

高度なデジタル署名および証明書管理機能の詳細については、公式の Aspose.PDF ドキュメントを必ずご確認ください。

### よくある質問

#### Q: スマート カードを使用して PDF ファイルに署名することを検討する必要があるのはなぜですか?

A: スマート カードを使用して PDF ファイルに署名すると、ドキュメントの信頼性と完全性が保証され、セキュリティが強化されます。スマート カード ベースの署名により、より高いレベルの信頼とコンプライアンスが提供されます。

#### Q: スマート カード ベースのデジタル署名はどのように機能しますか?

A: スマート カード ベースのデジタル署名では、スマート カードに保存されている暗号キーを使用して一意のデジタル署名を作成します。この署名は PDF ファイルに添付され、受信者が文書の出所と完全性を確認できるようになります。

#### Q: スマート カード ベースの署名における Aspose.PDF for .NET の役割は何ですか?

A: Aspose.PDF for .NET は、PDF ファイルのスマート カード ベースのデジタル署名を容易にするツールとライブラリの包括的なセットを提供します。これによりプロセスが簡素化され、安全な文書署名が保証されます。

#### Q: 署名用に特定のスマート カード証明書を選択できますか?

A: はい、Windows 証明書ストアから特定のスマート カード証明書を選択して署名できます。 Aspose.PDF for .NET を使用すると、証明書の選択をアプリケーションにシームレスに統合できます。

#### Q: 提供されたソース コードはスマート カード ベースの署名をどのように処理しますか?

A: ソース コードは、PDF ドキュメントをバインドし、スマート カード証明書を選択し、署名情報を指定し、デジタル署名を作成する方法を示しています。署名の有効性を確認する方法も示します。

#### Q: 単一の PDF ファイルにスマート カードを使用して複数の署名を適用できますか?

A: もちろん、複数のスマート カード ベースの署名を 1 つの PDF ファイルに適用できます。各署名は一意であり、ドキュメント全体のセキュリティに貢献します。

#### Q: 検証ステップ中に署名の検証に失敗した場合はどうなりますか?

A: 署名の検証に失敗した場合は、署名が無効であることを示す例外がスローされます。これにより、有効で信頼できる署名のみが受け入れられるようになります。

#### Q: スマート カード ベースの署名は、あらゆる種類の PDF ドキュメントと互換性がありますか?

A: はい、スマート カード ベースの署名は、あらゆる種類の PDF ドキュメントと互換性があります。フォーム、レポートなど、さまざまなタイプの PDF ファイルにデジタル署名を適用できます。

#### Q: 高度なデジタル署名と証明書の管理について詳しく知るにはどうすればよいですか?

A: 高度なデジタル署名機能、証明書管理、ドキュメントのセキュリティを確保するためのベスト プラクティスについて詳しくは、Aspose.PDF の公式ドキュメントを参照してください。

#### Q: スマート カード ベースの署名の実装に関するさらなる支援やサポートはどこで入手できますか?

A: 追加のガイダンスとサポートが必要な場合は、Aspose.PDF コミュニティ フォーラムに問い合わせるか、スマート カード ベースの署名に関する包括的な情報についてのドキュメントを参照してください。