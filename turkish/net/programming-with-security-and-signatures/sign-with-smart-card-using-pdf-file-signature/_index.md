---
title: PDF Dosya İmzasını Kullanarak Akıllı Kartla İmzalayın
linktitle: PDF Dosya İmzasını Kullanarak Akıllı Kartla İmzalayın
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyalarınızı bir akıllı kartla güvenli bir şekilde imzalayın.
type: docs
weight: 110
url: /tr/net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---
Akıllı kartla dijital imzalama, PDF dosyalarını imzalamanın güvenli bir yoludur. Aspose.PDF for .NET ile, aşağıdaki kaynak kodunu takip ederek akıllı kart kullanarak bir PDF dosyasını kolayca imzalayabilirsiniz:

## 1. Adım: Gerekli kitaplıkları içe aktarın

Başlamadan önce, C# projeniz için gerekli kitaplıkları içe aktarmanız gerekir. İşte gerekli ithalat direktifleri:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## 2. Adım: Belgeler klasörünün yolunu ayarlayın

 Bu adımda, imzalamak istediğiniz PDF dosyasını içeren klasörün yolunu belirtmeniz gerekir. Yer değiştirmek`"YOUR DOCUMENTS DIRECTORY"`belgeler klasörünüzün gerçek yolu ile aşağıdaki kodda:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 3. Adım: PDF belgesini yükleyin

Şimdi imzalanacak PDF belgesini aşağıdaki kodu kullanarak yükleyeceğiz:

```csharp
Document doc = new Document(dataDir + "blank.pdf");
```

## 4. Adım: İmzayı akıllı kartla gerçekleştirin

 Bu adımda, kullanarak akıllı kart ile imzayı gerçekleştireceğiz.`PdfFileSignature` gelen sınıf`Facades`kütüphane. Windows sertifika deposundan akıllı kart sertifikasını seçiyoruz ve gerekli imzalama bilgilerini belirtiyoruz. İşte ilgili kod:

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

## 5. Adım: İmzayı Doğrulayın

 Son olarak, imzalanan PDF dosyasının imzasını kullanarak doğrularız.`PdfFileSignature` sınıf. İmza isimlerini alıp tek tek kontrol ediyoruz. Bir imza doğrulamada başarısız olursa, bir istisna atılır. İşte ilgili kod:

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

### Aspose.PDF for .NET kullanarak Pdf Dosya İmzası Kullanarak Akıllı Kartla İmzala için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
	pdfSign.BindPdf(doc);
	// Windows sertifika deposunda sertifika seçimi ile imzalayın
	System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
	store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
	// Mağazada sertifikayı manuel olarak seçti
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

Tebrikler! Artık bir PDF dosyasını Aspose.PDF for .NET kullanarak akıllı kartla imzalamak için adım adım bir kılavuza sahipsiniz. PDF belgelerinize güvenli dijital imzalar eklemek için bu kodu kullanabilirsiniz.

Gelişmiş dijital imza ve sertifika yönetimi özellikleri hakkında daha fazla bilgi için resmi Aspose.PDF belgelerine baktığınızdan emin olun.

### SSS

#### S: Neden PDF dosyalarını akıllı kartla imzalamayı düşünmeliyim?

C: PDF dosyalarını akıllı kartla imzalamak, belgenin gerçekliğini ve bütünlüğünü sağlayarak güvenliği artırır. Akıllı kart tabanlı imzalar, daha yüksek düzeyde güven ve uyumluluk sağlar.

#### S: Akıllı kart tabanlı dijital imzalama nasıl çalışır?

C: Akıllı kart tabanlı dijital imzalama, benzersiz bir dijital imza oluşturmak için bir akıllı kartta saklanan bir kriptografik anahtarın kullanılmasını içerir. Bu imza, PDF dosyasına eklenir ve alıcıların belgenin kaynağını ve bütünlüğünü doğrulamasına olanak tanır.

#### S: Akıllı kart tabanlı imzalamada Aspose.PDF for .NET'in rolü nedir?

Y: Aspose.PDF for .NET, PDF dosyalarının akıllı kart tabanlı dijital olarak imzalanmasını kolaylaştırmak için kapsamlı bir araç ve kitaplık seti sağlar. Süreci basitleştirir ve güvenli belge imzalama sağlar.

#### S: İmzalamak için belirli bir akıllı kart sertifikası seçebilir miyim?

Y: Evet, imzalamak için Windows sertifika deposundan belirli bir akıllı kart sertifikası seçebilirsiniz. Aspose.PDF for .NET, sertifika seçimini uygulamanıza sorunsuz bir şekilde entegre etmenize olanak tanır.

#### S: Sağlanan kaynak kodu, akıllı kart tabanlı imzalamayı nasıl işler?

C: Kaynak kodu, bir PDF belgesinin nasıl ciltleneceğini, bir akıllı kart sertifikasının nasıl seçileceğini, imza bilgilerinin nasıl belirleneceğini ve bir dijital imzanın nasıl oluşturulacağını gösterir. Ayrıca imzanın geçerliliğinin nasıl doğrulanacağını da gösterir.

#### S: Akıllı kartları kullanarak tek bir PDF dosyasında birden fazla imza uygulayabilir miyim?

C: Kesinlikle, tek bir PDF dosyasına birden fazla akıllı kart tabanlı imza uygulayabilirsiniz. Her imza benzersizdir ve belgenin genel güvenliğine katkıda bulunur.

#### S: Doğrulama adımı sırasında bir imza doğrulamayı geçemezse ne olur?

C: Bir imza doğrulamada başarısız olursa, imzanın geçerli olmadığını belirten bir istisna atılır. Bu, yalnızca geçerli ve güvenilir imzaların kabul edilmesini sağlar.

#### S: Akıllı kart tabanlı imzalama, tüm PDF belgeleriyle uyumlu mu?

Y: Evet, akıllı kart tabanlı imzalama, her tür PDF belgesiyle uyumludur. Dijital imzaları formlar, raporlar ve daha fazlası dahil olmak üzere çeşitli PDF dosyası türlerine uygulayabilirsiniz.

#### S: Gelişmiş dijital imza ve sertifika yönetimi hakkında nasıl daha fazla bilgi edinebilirim?

A: Gelişmiş dijital imza özellikleri, sertifika yönetimi ve belge güvenliğini sağlamaya yönelik en iyi uygulamalar hakkında ayrıntılı bilgiler için resmi Aspose.PDF belgelerini keşfedin.

#### S: Akıllı kart tabanlı imzalamayı uygulamak için daha fazla yardım veya desteği nereden bulabilirim?

Y: Ek rehberlik ve destek için Aspose.PDF topluluk forumlarına ulaşın veya akıllı kart tabanlı imzalama hakkında kapsamlı bilgi için belgelere bakın.