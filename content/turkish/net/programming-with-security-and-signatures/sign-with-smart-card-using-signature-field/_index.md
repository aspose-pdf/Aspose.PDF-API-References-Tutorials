---
title: İmza Alanını Kullanarak Akıllı Kartla İmzalama
linktitle: İmza Alanını Kullanarak Akıllı Kartla İmzalama
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak PDF dosyalarınızı akıllı kartla güvenli bir şekilde imzalayın.
type: docs
weight: 120
url: /tr/net/programming-with-security-and-signatures/sign-with-smart-card-using-signature-field/
---
Akıllı kartla dijital imzalama, PDF dosyalarını imzalamanın güvenli bir yoludur. Aspose.PDF for .NET ile aşağıdaki kaynak kodunu takip ederek bir imza alanı ve akıllı kart kullanarak bir PDF dosyasını kolayca imzalayabilirsiniz:

## 1. Adım: Gerekli kitaplıkları içe aktarın

Başlamadan önce C# projeniz için gerekli kütüphaneleri içe aktarmanız gerekir. Gerekli ithalat direktifleri şunlardır:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## 2. Adım: Belgeler klasörünün yolunu ayarlayın

 Bu adımda imzalamak istediğiniz PDF dosyasının bulunduğu klasörün yolunu belirtmeniz gerekiyor. Yer değiştirmek`"YOUR DOCUMENTS DIRECTORY"`belgeler klasörünüzün gerçek yolunu içeren aşağıdaki kodda:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 3. Adım: PDF belgesini kopyalayıp açın

Şimdi aşağıdaki kodu kullanarak imzalanacak PDF belgesini kopyalayıp açacağız:

```csharp
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);

using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
     using (Document doc = new Document(fs))
     {
         // İmza alanı oluşturma
         SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));

         // Mağazadaki sertifikayı seçin
         X509Store store = new X509Store(StoreLocation.CurrentUser);
         store.Open(OpenFlags.ReadOnly);
         X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
        
         // Gerekli bilgileri içeren harici bir imza oluşturun
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

## 4. Adım: İmzayı Doğrulayın

 Son olarak, imzalanan PDF dosyasının imzasını kullanarak doğrularız.`PdfFileSignature` sınıf. İmza isimlerini alıp tek tek kontrol ediyoruz. Bir imzanın doğrulaması başarısız olursa bir istisna oluşturulur. İşte ilgili kod:

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

### Aspose.PDF for .NET kullanarak İmza Alanını Kullanarak Akıllı Kartla İmzalama için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);
using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
	using (Document doc = new Document(fs))
	{
		SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));
		// Windows sertifika deposunda sertifika seçimiyle imzalayın
		System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
		store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
		// Sertifikayı mağazada manuel olarak seçtiniz
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

## Çözüm

Tebrikler! Artık Aspose.PDF for .NET'te bir imza alanını kullanarak bir PDF dosyasını akıllı kartla imzalamak için adım adım bir kılavuza sahipsiniz. PDF belgelerinize güvenli dijital imzalar eklemek için bu kodu kullanabilirsiniz.

Gelişmiş dijital imza ve sertifika yönetimi özellikleri hakkında daha fazla bilgi için resmi Aspose.PDF belgelerine göz atmayı unutmayın.

### SSS'ler

#### S: Akıllı kartla dijital imzalama için imza alanı kullanmanın faydası nedir?

C: Akıllı kartla dijital imzalama için bir imza alanının kullanılması, PDF içinde imzanın uygulandığı belirlenmiş bir alan sağlar. Bu, belgenin netliğini artırır ve imzanın orijinalliğini garanti eder.

#### S: Aspose.PDF for .NET kütüphanesi, imza alanıyla akıllı kart tabanlı dijital imzalamayı nasıl kolaylaştırıyor?

C: Aspose.PDF for .NET, imza alanı oluşturma, akıllı kart sertifikası seçme ve PDF belgesindeki belirli bir alana dijital imza uygulama sürecini basitleştirir.

#### S: Akıllı kart tabanlı imzalama için belirli bir sertifikanın seçilmesi neden önemlidir?

C: Belirli bir sertifikayı seçmek, imzalayanı benzersiz bir şekilde tanımlamanıza ve imzanın bütünlüğünü sağlamanıza olanak tanır. Bu, güven oluşturulmasına ve dijital imzalama standartlarına uyum sağlanmasına yardımcı olur.

#### S: Sağlanan kaynak kodu, imza alanıyla akıllı kart tabanlı imzalama işlemini nasıl gerçekleştiriyor?

C: Kaynak kodu, imza alanının nasıl oluşturulacağını, akıllı kart sertifikasının nasıl seçileceğini ve belirli imzalama bilgileriyle dijital imzanın nasıl uygulanacağını gösterir. Ayrıca imzanın geçerliliğinin nasıl doğrulanacağını da gösterir.

#### S: İmza alanının görünümünü özelleştirebilir miyim?

C: Evet, imza alanının boyutunu, konumunu ve görsel temsilini belgenizin düzeniyle hizalanacak şekilde görünümünü özelleştirebilirsiniz.

#### S: Doğrulama adımı sırasında bir imzanın doğrulaması başarısız olursa ne olur?

C: Bir imzanın doğrulaması başarısız olursa imzanın geçerli olmadığını belirten bir istisna oluşturulur. Bu, yalnızca geçerli ve güvenilir imzaların kabul edilmesini sağlar.

#### S: Tek bir PDF belgesine birden fazla imza alanı ve akıllı kart tabanlı imza uygulayabilir miyim?

C: Kesinlikle, aynı PDF belgesinin farklı alanlarına birden fazla imza alanı ve akıllı kart tabanlı imza uygulayabilir, böylece birden fazla güvenlik katmanı sağlayabilirsiniz.

#### S: İmza alanı kullanmak genel belge imzalama sürecini nasıl geliştirir?

C: İmza alanı kullanmak, imzalayana imzasını belirlenmiş bir alana yerleştirme konusunda rehberlik ederek, imzalama sürecini daha düzenli ve kullanıcı dostu hale getirerek belge imzalama sürecini kolaylaştırır.

#### S: İmza alanlarını akıllı kart tabanlı imzalamayla kullanma konusunda herhangi bir sınırlama var mı?

C: İmza alanlarının akıllı kart tabanlı imzalamayla kullanılmasına ilişkin herhangi bir doğal sınırlama yoktur. Ancak seçilen imza alanı konumunun önemli belge içeriğini engellemediğinden emin olmak önemlidir.

#### S: İmza alanıyla akıllı kart tabanlı imzalamayı uygulamak için nereden daha fazla yardım veya destek bulabilirim?

C: Daha fazla rehberlik ve destek için, güvenli dijital imzaların uygulanmasına yönelik değerli bilgiler ve çözümler sunan resmi Aspose.PDF belgelerine ve topluluk forumlarına başvurabilirsiniz.