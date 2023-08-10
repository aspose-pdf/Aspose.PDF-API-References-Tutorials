---
title: İmza Alanını Kullanarak Akıllı Kartla İmzalayın
linktitle: İmza Alanını Kullanarak Akıllı Kartla İmzalayın
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyalarınızı bir akıllı kartla güvenli bir şekilde imzalayın.
type: docs
weight: 120
url: /tr/net/programming-with-security-and-signatures/sign-with-smart-card-using-signature-field/
---
Akıllı kartla dijital imzalama, PDF dosyalarını imzalamanın güvenli bir yoludur. Aspose.PDF for .NET ile, aşağıdaki kaynak kodunu takip ederek bir imza alanı ve akıllı kart kullanarak bir PDF dosyasını kolayca imzalayabilirsiniz:

## 1. Adım: Gerekli kitaplıkları içe aktarın

Başlamadan önce, C# projeniz için gerekli kitaplıkları içe aktarmanız gerekir. İşte gerekli ithalat direktifleri:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## 2. Adım: Belgeler klasörünün yolunu ayarlayın

 Bu adımda, imzalamak istediğiniz PDF dosyasını içeren klasörün yolunu belirtmeniz gerekir. Yer değiştirmek`"YOUR DOCUMENTS DIRECTORY"`belgeler klasörünüzün gerçek yolu ile aşağıdaki kodda:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 3. Adım: PDF belgesini kopyalayın ve açın

Şimdi aşağıdaki kodu kullanarak imzalanacak PDF belgesini kopyalayıp açacağız:

```csharp
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);

using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
     using (Document doc = new Document(fs))
     {
         // Bir imza alanı oluşturun
         SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));

         // Mağazada sertifikayı seçin
         X509Store store = new X509Store(StoreLocation.CurrentUser);
         store.Open(OpenFlags.ReadOnly);
         X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
        
         // Gerekli bilgilerle harici bir imza oluşturun
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

 Son olarak, imzalanan PDF dosyasının imzasını kullanarak doğrularız.`PdfFileSignature` sınıf. İmza isimlerini alıp tek tek kontrol ediyoruz. Bir imza doğrulamada başarısız olursa, bir istisna atılır. İşte ilgili kod:

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

### Aspose.PDF for .NET kullanarak İmza Alanı Kullanarak Akıllı Kartla İmzala için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);
using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
	using (Document doc = new Document(fs))
	{
		SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));
		// Windows sertifika deposunda sertifika seçimi ile imzalayın
		System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
		store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
		// Mağazada sertifikayı manuel olarak seçti
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

Tebrikler! Artık bir PDF dosyasını Aspose.PDF for .NET ile bir imza alanı kullanarak akıllı kartla imzalamak için adım adım bir kılavuza sahipsiniz. PDF belgelerinize güvenli dijital imzalar eklemek için bu kodu kullanabilirsiniz.

Gelişmiş dijital imza ve sertifika yönetimi özellikleri hakkında daha fazla bilgi için resmi Aspose.PDF belgelerine baktığınızdan emin olun.

### SSS

#### S: Akıllı kartla dijital imzalama için imza alanı kullanmanın faydası nedir?

C: Akıllı kartla dijital imzalama için bir imza alanı kullanmak, PDF içinde imzanın uygulandığı belirlenmiş bir alan sağlar. Bu, belge netliğini artırır ve imzanın gerçekliğini garanti eder.

#### S: Aspose.PDF for .NET kitaplığı, bir imza alanıyla akıllı kart tabanlı dijital imzalamayı nasıl kolaylaştırır?

Y: Aspose.PDF for .NET, imza alanı oluşturma, akıllı kart sertifikası seçme ve PDF belgesindeki belirli bir alana dijital imza uygulama sürecini basitleştirir.

#### S: Akıllı kart tabanlı imzalama için belirli bir sertifika seçmek neden önemlidir?

Y: Belirli bir sertifika seçmek, imzalayanı benzersiz bir şekilde tanımlamanıza ve imzanın bütünlüğünü sağlamanıza olanak tanır. Bu, dijital imzalama standartlarıyla güven ve uyum sağlamaya yardımcı olur.

#### S: Sağlanan kaynak kodu, bir imza alanıyla akıllı kart tabanlı imzalama sürecini nasıl ele alıyor?

C: Kaynak kodu, bir imza alanının nasıl oluşturulacağını, bir akıllı kart sertifikasının nasıl seçileceğini ve belirli imzalama bilgileriyle bir dijital imzanın nasıl uygulanacağını gösterir. Ayrıca imzanın geçerliliğinin nasıl doğrulanacağını da gösterir.

#### S: İmza alanının görünümünü özelleştirebilir miyim?

C: Evet, belgenizin düzeniyle hizalamak için imza alanının boyutunu, konumunu ve görsel sunumunu özelleştirebilirsiniz.

#### S: Doğrulama adımı sırasında bir imza doğrulamayı geçemezse ne olur?

C: Bir imza doğrulamada başarısız olursa, imzanın geçerli olmadığını belirten bir istisna atılır. Bu, yalnızca geçerli ve güvenilir imzaların kabul edilmesini sağlar.

#### S: Tek bir PDF belgesine birden çok imza alanı ve akıllı kart tabanlı imza uygulayabilir miyim?

C: Kesinlikle, aynı PDF belgesinin farklı alanlarına birden çok imza alanı ve akıllı kart tabanlı imza uygulayarak birden çok güvenlik katmanı sağlayabilirsiniz.

#### S: Bir imza alanı kullanmak genel belge imzalama sürecini nasıl geliştirir?

Y: Bir imza alanı kullanmak, imzalayana imzasını belirlenmiş bir alana atması için rehberlik ederek belge imzalama sürecini kolaylaştırır ve imzalama sürecini daha organize ve kullanıcı dostu hale getirir.

#### S: Akıllı kart tabanlı imzalama ile imza alanlarını kullanmanın herhangi bir sınırlaması var mı?

C: Akıllı kart tabanlı imzalama ile imza alanlarını kullanmanın doğasında var olan sınırlamalar yoktur. Ancak, seçilen imza alanı konumunun önemli belge içeriğini engellememesini sağlamak önemlidir.

#### S: İmza alanıyla akıllı kart tabanlı imzalamayı uygulamaya yönelik daha fazla yardım veya desteği nereden bulabilirim?

C: Ek rehberlik ve destek için, güvenli dijital imzaların uygulanmasına yönelik değerli bilgiler ve çözümler sunan resmi Aspose.PDF belgelerine ve topluluk forumlarına başvurabilirsiniz.