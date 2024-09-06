---
title: PDF Dosya İmzası Kullanarak Akıllı Kartla İmzalayın
linktitle: PDF Dosya İmzası Kullanarak Akıllı Kartla İmzalayın
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyalarınızı akıllı kartla güvenli bir şekilde imzalayın.
type: docs
weight: 110
url: /tr/net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---
Akıllı kartla dijital imzalama, PDF dosyalarını imzalamanın güvenli bir yoludur. Aspose.PDF for .NET ile, aşağıdaki kaynak kodunu izleyerek bir PDF dosyasını akıllı kart kullanarak kolayca imzalayabilirsiniz:

## Adım 1: Gerekli kitaplıkları içe aktarın

Başlamadan önce, C# projeniz için gerekli kütüphaneleri içe aktarmanız gerekir. İşte gerekli içe aktarma yönergeleri:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## Adım 2: Belgeler klasörüne giden yolu ayarlayın

 Bu adımda, imzalamak istediğiniz PDF dosyasını içeren klasörün yolunu belirtmeniz gerekir. Değiştir`"YOUR DOCUMENTS DIRECTORY"` Aşağıdaki kodda belgeler klasörünüzün gerçek yolunu bulabilirsiniz:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Adım 3: PDF belgesini yükleyin

Şimdi imzalanacak PDF belgesini aşağıdaki kodu kullanarak yükleyeceğiz:

```csharp
Document doc = new Document(dataDir + "blank.pdf");
```

## Adım 4: Akıllı kartla imzayı gerçekleştirin

 Bu adımda akıllı kart ile imzayı gerçekleştireceğiz.`PdfFileSignature` sınıftan`Facades`kütüphane. Akıllı kart sertifikasını Windows sertifika deposundan seçiyoruz ve gerekli imzalama bilgilerini belirtiyoruz. İşte karşılık gelen kod:

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature())
{
     pdfSign.BindPdf(doc);

     // Mağazada sertifikayı seçin
     X509Store store = new X509Store(StoreLocation.CurrentUser);
     store.Open(OpenFlags.ReadOnly);
     X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
     ExternalSignature externalSignature = new ExternalSignature(sel[0]);

     pdfSign.SignatureAppearance = dataDir + "demo.png";
     pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
     pdfSign.Save(dataDir + "externalSignature2.pdf");
}
```

## Adım 5: İmzayı Doğrulayın

 Son olarak, imzalanmış PDF dosyasının imzasını kullanarak doğrularız.`PdfFileSignature` sınıf. İmza adlarını alırız ve bunları tek tek kontrol ederiz. Bir imza doğrulamada başarısız olursa, bir istisna atılır. İşte karşılık gelen kod:

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

### Aspose.PDF for .NET kullanarak Pdf Dosya İmzası Kullanarak Akıllı Kartla İmzalama için örnek kaynak kodu 
```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
	pdfSign.BindPdf(doc);
	// Windows sertifika deposunda sertifika seçimiyle imzala
	System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
	store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
	// Mağazada sertifikayı manuel olarak seçtim
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

## Çözüm

Tebrikler! Artık Aspose.PDF for .NET kullanarak bir PDF dosyasını akıllı kartla imzalamak için adım adım bir kılavuzunuz var. Bu kodu kullanarak PDF belgelerinize güvenli dijital imzalar ekleyebilirsiniz.

Gelişmiş dijital imza ve sertifika yönetimi özellikleri hakkında daha fazla bilgi edinmek için resmi Aspose.PDF belgelerine göz atmayı unutmayın.

### SSS

#### S: PDF dosyalarını akıllı kartla imzalamayı neden düşünmeliyim?

A: PDF dosyalarını akıllı kartla imzalamak, belgenin gerçekliğini ve bütünlüğünü garanti altına alarak güvenliği artırır. Akıllı kart tabanlı imzalar daha yüksek düzeyde güven ve uyumluluk sağlar.

#### S: Akıllı kart tabanlı dijital imzalama nasıl çalışır?

A: Akıllı kart tabanlı dijital imzalama, benzersiz bir dijital imza oluşturmak için akıllı kartta depolanan bir kriptografik anahtarın kullanılmasını içerir. Bu imza PDF dosyasına eklenir ve alıcıların belgenin kökenini ve bütünlüğünü doğrulamasını sağlar.

#### S: Akıllı kart tabanlı imzalamada Aspose.PDF for .NET'in rolü nedir?

A: Aspose.PDF for .NET, PDF dosyalarının akıllı kart tabanlı dijital imzalanmasını kolaylaştırmak için kapsamlı bir araç ve kitaplık seti sağlar. Süreci basitleştirir ve güvenli belge imzalamayı garanti eder.

#### S: İmzalama için belirli bir akıllı kart sertifikası seçebilir miyim?

C: Evet, imzalama için Windows sertifika deposundan belirli bir akıllı kart sertifikası seçebilirsiniz. Aspose.PDF for .NET, sertifika seçimini uygulamanıza sorunsuz bir şekilde entegre etmenizi sağlar.

#### S: Sağlanan kaynak kodu akıllı kart tabanlı imzalamayı nasıl işliyor?

A: Kaynak kodu bir PDF belgesinin nasıl bağlanacağını, akıllı kart sertifikasının nasıl seçileceğini, imzalama bilgilerinin nasıl belirtileceğini ve dijital imzanın nasıl oluşturulacağını gösterir. Ayrıca imzanın geçerliliğinin nasıl doğrulanacağını da gösterir.

#### S: Akıllı kartları kullanarak tek bir PDF dosyasında birden fazla imza uygulayabilir miyim?

A: Kesinlikle, tek bir PDF dosyasına birden fazla akıllı kart tabanlı imza uygulayabilirsiniz. Her imza benzersizdir ve belgenin genel güvenliğine katkıda bulunur.

#### S: Doğrulama adımı sırasında bir imzanın doğrulanması başarısız olursa ne olur?

A: Bir imza doğrulamayı geçemezse, imzanın geçerli olmadığını belirten bir istisna atılır. Bu, yalnızca geçerli ve güvenilir imzaların kabul edilmesini sağlar.

#### S: Akıllı kart tabanlı imzalama her türlü PDF belgesiyle uyumlu mudur?

C: Evet, akıllı kart tabanlı imzalama tüm PDF belge türleriyle uyumludur. Formlar, raporlar ve daha fazlası dahil olmak üzere çeşitli PDF dosyası türlerine dijital imzalar uygulayabilirsiniz.

#### S: Gelişmiş dijital imza ve sertifika yönetimi hakkında daha fazla bilgi nasıl edinebilirim?

A: Gelişmiş dijital imza özellikleri, sertifika yönetimi ve belge güvenliğinin sağlanmasına yönelik en iyi uygulamalar hakkında ayrıntılı bilgi edinmek için resmi Aspose.PDF belgelerini inceleyin.

#### S: Akıllı kart tabanlı imzalamayı uygulama konusunda daha fazla yardım veya desteği nereden bulabilirim?

C: Ek rehberlik ve destek için Aspose.PDF topluluk forumlarına ulaşın veya akıllı kart tabanlı imzalama hakkında kapsamlı bilgi için belgelere bakın.