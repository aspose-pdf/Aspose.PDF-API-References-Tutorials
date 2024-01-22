---
title: 署名フィールドを使用したスマート カードによる署名
linktitle: 署名フィールドを使用したスマート カードによる署名
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して、スマート カードを使用して PDF ファイルに安全に署名します。
type: docs
weight: 120
url: /ja/net/programming-with-security-and-signatures/sign-with-smart-card-using-signature-field/
---
スマート カードを使用したデジタル署名は、PDF ファイルに署名する安全な方法です。 Aspose.PDF for .NET を使用すると、次のソース コードに従って、署名フィールドとスマート カードを使用して PDF ファイルに簡単に署名できます。

## ステップ 1: 必要なライブラリをインポートする

始める前に、C# プロジェクトに必要なライブラリをインポートする必要があります。必要なインポート ディレクティブは次のとおりです。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## ステップ 2: ドキュメントフォルダーへのパスを設定する

この手順では、署名する PDF ファイルが含まれるフォルダーへのパスを指定する必要があります。交換する`"YOUR DOCUMENTS DIRECTORY"`次のコードでは、ドキュメント フォルダーへの実際のパスを指定します。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ 3: PDF ドキュメントをコピーして開きます

次に、次のコードを使用して、署名する PDF ドキュメントをコピーして開きます。

```csharp
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);

using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
     using (Document doc = new Document(fs))
     {
         //署名フィールドを作成する
         SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));

         //ストアで証明書を選択します
         X509Store store = new X509Store(StoreLocation.CurrentUser);
         store.Open(OpenFlags.ReadOnly);
         X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
        
         //必要な情報を含む外部署名を作成する
         ExternalSignature externalSignature = new ExternalSignature(sel[0])
         {
             Authority = "Me",
             Reason = "Reason",
             ContactInfo = "Contact"
         };

         field1.PartialName = "sig1";
         doc.Form.Add(field1, 1);
         field1.Sign(externalSignature);
         doc.Save();
     }
}
```

## ステップ 4: 署名を検証する

最後に、署名された PDF ファイルの署名を次のコマンドを使用して検証します。`PdfFileSignature`クラス。署名名を取得し、1 つずつ確認します。署名の検証に失敗した場合、例外がスローされます。対応するコードは次のとおりです。

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature1.pdf")))
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

### Aspose.PDF for .NET を使用した署名フィールドを使用したスマート カードによる署名のサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);
using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
	using (Document doc = new Document(fs))
	{
		SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));
		//Windows 証明書ストアで選択した証明書を使用して署名します
		System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
		store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
		//ストアで証明書を手動で選択しました
		System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel = System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
		Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0])
		{
			Authority = "Me",
			Reason = "Reason",
			ContactInfo = "Contact"
		};
		field1.PartialName = "sig1";
		doc.Form.Add(field1, 1);
		field1.Sign(externalSignature);
		doc.Save();
	}
}
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature1.pdf")))
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

おめでとうございます！ Aspose.PDF for .NET の署名フィールドを使用して、スマート カードで PDF ファイルに署名するためのステップバイステップ ガイドが完成しました。このコードを使用して、PDF ドキュメントに安全なデジタル署名を追加できます。

高度なデジタル署名および証明書管理機能の詳細については、公式の Aspose.PDF ドキュメントを必ずご確認ください。

### よくある質問

#### Q: スマート カードによるデジタル署名に署名フィールドを使用する利点は何ですか?

A: スマート カードによるデジタル署名に署名フィールドを使用すると、PDF 内に署名が適用される指定された領域が提供されます。これにより、文書の明瞭さが向上し、署名の信頼性が保証されます。

#### Q: Aspose.PDF for .NET ライブラリは、署名フィールドを使用したスマート カード ベースのデジタル署名をどのように促進しますか?

A: Aspose.PDF for .NET は、署名フィールドの作成、スマート カード証明書の選択、PDF ドキュメント内の特定の領域へのデジタル署名の適用のプロセスを簡素化します。

#### Q: スマート カード ベースの署名では、特定の証明書を選択することが重要なのはなぜですか?

A: 特定の証明書を選択すると、署名者を一意に識別し、署名の整合性を確保できます。これは、信頼とデジタル署名標準への準拠を確立するのに役立ちます。

#### Q: 提供されたソース コードは、署名フィールドを使用したスマート カード ベースの署名プロセスをどのように処理しますか?

A: ソース コードは、署名フィールドを作成し、スマート カード証明書を選択し、特定の署名情報を使用してデジタル署名を適用する方法を示しています。署名の有効性を確認する方法も示します。

#### Q: 署名フィールドの外観をカスタマイズできますか?

A: はい、ドキュメントのレイアウトに合わせて、署名フィールドのサイズ、位置、視覚的表現などの外観をカスタマイズできます。

#### Q: 検証ステップ中に署名の検証に失敗した場合はどうなりますか?

A: 署名の検証に失敗した場合は、署名が無効であることを示す例外がスローされます。これにより、有効で信頼できる署名のみが受け入れられるようになります。

#### Q: 複数の署名フィールドとスマート カード ベースの署名を 1 つの PDF ドキュメントに適用できますか?

A: もちろん、複数の署名フィールドとスマート カード ベースの署名を同じ PDF ドキュメントの異なる領域に適用して、複数のセキュリティ層を提供することができます。

#### Q: 署名フィールドを使用すると、ドキュメント署名プロセス全体がどのように強化されますか?

A: 署名フィールドを使用すると、署名者が指定された領域に署名するよう誘導されるため、文書の署名プロセスが合理化され、署名プロセスがより組織化され、使いやすくなります。

#### Q: スマート カード ベースの署名で署名フィールドを使用する場合に制限はありますか?

A: スマート カード ベースの署名で署名フィールドを使用することに固有の制限はありません。ただし、選択した署名フィールドの場所によって重要な文書の内容が隠されないようにすることが重要です。

#### Q: 署名フィールドを使用したスマート カード ベースの署名の実装に関するさらなる支援やサポートはどこで入手できますか?

A: 追加のガイダンスとサポートについては、Aspose.PDF の公式ドキュメントとコミュニティ フォーラムを参照してください。これらのフォーラムでは、安全なデジタル署名を実装するための貴重な洞察とソリューションが提供されています。