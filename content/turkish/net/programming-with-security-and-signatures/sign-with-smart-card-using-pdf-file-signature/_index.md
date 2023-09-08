---
title: PDF Dosya İmzasını Kullanarak Akıllı Kartla İmzalayın
linktitle: PDF Dosya İmzasını Kullanarak Akıllı Kartla İmzalayın
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak PDF dosyalarınızı akıllı kartla güvenli bir şekilde imzalayın.
type: docs
weight: 110
url: /tr/net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---
Akıllı kartla dijital imzalama, PDF dosyalarını imzalamanın güvenli bir yoludur. Aspose.PDF for .NET ile aşağıdaki kaynak kodunu takip ederek akıllı kart kullanarak bir PDF dosyasını kolayca imzalayabilirsiniz:

## 1. Adım: Gerekli kitaplıkları içe aktarın

Başlamadan önce C# projeniz için gerekli kütüphaneleri içe aktarmanız gerekir. Gerekli ithalat direktifleri şunlardır:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## 2. Adım: Belgeler klasörünün yolunu ayarlayın

 Bu adımda imzalamak istediğiniz PDF dosyasının bulunduğu klasörün yolunu belirtmeniz gerekiyor. Yer değiştirmek`"YOUR DOCUMENTS DIRECTORY"`belgeler klasörünüzün gerçek yolunu içeren aşağıdaki kodda:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 3. Adım: PDF belgesini yükleyin

Şimdi aşağıdaki kodu kullanarak imzalanacak PDF belgesini yükleyeceğiz:

```csharp
Document doc = new Document(dataDir + "blank.pdf");
```

## Adım 4: İmzayı akıllı kartla gerçekleştirin

 Bu adımda akıllı kart ile imza işlemini gerçekleştireceğiz.`PdfFileSignature` gelen sınıf`Facades`kütüphane. Windows sertifika deposundan akıllı kart sertifikasını seçiyoruz ve gerekli imzalama bilgilerini belirliyoruz. İşte ilgili kod:

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature())
{
     pdfSign.BindPdf(doc);

     // Mağazadaki sertifikayı seçin
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

 Son olarak, imzalanan PDF dosyasının imzasını kullanarak doğrularız.`PdfFileSignature` sınıf. İmza isimlerini alıp tek tek kontrol ediyoruz. Bir imzanın doğrulaması başarısız olursa bir istisna oluşturulur. İşte ilgili kod:

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
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
	pdfSign.BindPdf(doc);
	// Windows sertifika deposunda sertifika seçimiyle imzalayın
	System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
	store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
	// Sertifikayı mağazada manuel olarak seçtiniz
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

Tebrikler! Artık Aspose.PDF for .NET kullanarak bir PDF dosyasını akıllı kartla imzalamak için adım adım bir kılavuza sahipsiniz. PDF belgelerinize güvenli dijital imzalar eklemek için bu kodu kullanabilirsiniz.

Gelişmiş dijital imza ve sertifika yönetimi özellikleri hakkında daha fazla bilgi için resmi Aspose.PDF belgelerine göz atmayı unutmayın.

### SSS'ler

#### S: PDF dosyalarını neden akıllı kartla imzalamayı düşünmeliyim?

C: PDF dosyalarının akıllı kartla imzalanması, belgenin orijinalliğini ve bütünlüğünü sağlayarak güvenliği artırır. Akıllı kart tabanlı imzalar daha yüksek düzeyde güven ve uyumluluk sağlar.

#### S: Akıllı kart tabanlı dijital imzalama nasıl çalışır?

C: Akıllı kart tabanlı dijital imzalama, benzersiz bir dijital imza oluşturmak için akıllı kartta saklanan bir şifreleme anahtarının kullanılmasını içerir. Bu imza, PDF dosyasına eklenerek alıcıların belgenin kökenini ve bütünlüğünü doğrulamasına olanak tanır.

#### S: Aspose.PDF for .NET'in akıllı kart tabanlı imzalamadaki rolü nedir?

C: Aspose.PDF for .NET, PDF dosyalarının akıllı kart tabanlı dijital imzalanmasını kolaylaştırmak için kapsamlı bir araç ve kitaplık seti sağlar. Süreci basitleştirir ve güvenli belge imzalamayı sağlar.

#### S: İmzalamak için belirli bir akıllı kart sertifikasını seçebilir miyim?

C: Evet, imzalamak için Windows sertifika deposundan belirli bir akıllı kart sertifikasını seçebilirsiniz. Aspose.PDF for .NET, sertifika seçimini uygulamanıza sorunsuz bir şekilde entegre etmenize olanak tanır.

#### S: Sağlanan kaynak kodu akıllı kart tabanlı imzalamayı nasıl işliyor?

C: Kaynak kodu, bir PDF belgesinin nasıl ciltleneceğini, akıllı kart sertifikasının nasıl seçileceğini, imzalama bilgilerinin nasıl belirleneceğini ve dijital imzanın nasıl oluşturulacağını gösterir. Ayrıca imzanın geçerliliğinin nasıl doğrulanacağını da gösterir.

#### S: Tek bir PDF dosyasında akıllı kartlar kullanarak birden fazla imza uygulayabilir miyim?

C: Kesinlikle, tek bir PDF dosyasına birden fazla akıllı kart tabanlı imza uygulayabilirsiniz. Her imza benzersizdir ve belgenin genel güvenliğine katkıda bulunur.

#### S: Doğrulama adımı sırasında bir imza doğrulamada başarısız olursa ne olur?

C: Bir imzanın doğrulaması başarısız olursa imzanın geçerli olmadığını belirten bir istisna oluşturulur. Bu, yalnızca geçerli ve güvenilir imzaların kabul edilmesini sağlar.

#### S: Akıllı kart tabanlı imzalama her tür PDF belgesiyle uyumlu mudur?

C: Evet, akıllı kart tabanlı imzalama her tür PDF belgesiyle uyumludur. Dijital imzaları formlar, raporlar ve daha fazlası dahil olmak üzere çeşitli PDF dosyalarına uygulayabilirsiniz.

#### S: Gelişmiş dijital imza ve sertifika yönetimi hakkında nasıl daha fazla bilgi edinebilirim?

C: Gelişmiş dijital imza özelliklerine, sertifika yönetimine ve belge güvenliğini sağlamaya yönelik en iyi uygulamalara ilişkin ayrıntılı bilgiler için resmi Aspose.PDF belgelerini inceleyin.

#### S: Akıllı kart tabanlı imzalamayı uygulamak için nereden daha fazla yardım veya destek bulabilirim?

C: Daha fazla rehberlik ve destek için Aspose.PDF topluluk forumlarına ulaşın veya akıllı kart tabanlı imzalama hakkında kapsamlı bilgi için belgelere bakın.