---
title: İmza Alanını Kullanarak Akıllı Kartla İmzalayın
linktitle: İmza Alanını Kullanarak Akıllı Kartla İmzalayın
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyalarınızı akıllı kartla güvenli bir şekilde imzalayın.
type: docs
weight: 120
url: /tr/net/programming-with-security-and-signatures/sign-with-smart-card-using-signature-field/
---
Akıllı kartla dijital imzalama, PDF dosyalarını imzalamanın güvenli bir yoludur. Aspose.PDF for .NET ile, aşağıdaki kaynak kodunu izleyerek bir imza alanı ve akıllı kart kullanarak bir PDF dosyasını kolayca imzalayabilirsiniz:

## Adım 1: Gerekli kitaplıkları içe aktarın

Başlamadan önce, C# projeniz için gerekli kütüphaneleri içe aktarmanız gerekir. İşte gerekli içe aktarma yönergeleri:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## Adım 2: Belgeler klasörüne giden yolu ayarlayın

 Bu adımda, imzalamak istediğiniz PDF dosyasını içeren klasörün yolunu belirtmeniz gerekir. Değiştir`"YOUR DOCUMENTS DIRECTORY"` Aşağıdaki kodda belgeler klasörünüzün gerçek yolunu bulabilirsiniz:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Adım 3: PDF belgesini kopyalayın ve açın

Şimdi imzalanacak PDF belgesini aşağıdaki kodu kullanarak kopyalayıp açacağız:

```csharp
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);

using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
     using (Document doc = new Document(fs))
     {
         // İmza alanı oluştur
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

## Adım 4: İmzayı Doğrulayın

 Son olarak, imzalanmış PDF dosyasının imzasını kullanarak doğrularız.`PdfFileSignature` sınıf. İmza adlarını alırız ve bunları tek tek kontrol ederiz. Bir imza doğrulamada başarısız olursa, bir istisna atılır. İşte karşılık gelen kod:

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

### Aspose.PDF for .NET kullanarak Akıllı Kartla İmza Alanı Kullanarak İmzalama için örnek kaynak kodu 
```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);
using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
	using (Document doc = new Document(fs))
	{
		SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));
		// Windows sertifika deposunda sertifika seçimiyle imzala
		System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
		store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
		// Mağazada sertifikayı manuel olarak seçtim
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

Tebrikler! Artık Aspose.PDF for .NET ile bir imza alanı kullanarak bir PDF dosyasını akıllı kartla imzalamak için adım adım bir kılavuzunuz var. Bu kodu kullanarak PDF belgelerinize güvenli dijital imzalar ekleyebilirsiniz.

Gelişmiş dijital imza ve sertifika yönetimi özellikleri hakkında daha fazla bilgi edinmek için resmi Aspose.PDF belgelerine göz atmayı unutmayın.

### SSS

#### S: Akıllı kartla dijital imzalama için imza alanı kullanmanın faydası nedir?

A: Akıllı kartla dijital imzalama için bir imza alanı kullanmak, PDF içinde imzanın uygulandığı belirlenmiş bir alan sağlar. Bu, belgenin netliğini artırır ve imzanın gerçekliğini garanti eder.

#### S: Aspose.PDF for .NET kütüphanesi, imza alanıyla akıllı kart tabanlı dijital imzalamayı nasıl kolaylaştırır?

A: Aspose.PDF for .NET, imza alanı oluşturma, akıllı kart sertifikası seçme ve PDF belgesindeki belirli bir alana dijital imza uygulama sürecini basitleştirir.

#### S: Akıllı kart tabanlı imzalama için belirli bir sertifikanın seçilmesi neden önemlidir?

A: Belirli bir sertifika seçmek, imzalayanı benzersiz bir şekilde tanımlamanıza ve imzanın bütünlüğünü sağlamanıza olanak tanır. Bu, dijital imzalama standartlarına güven ve uyum sağlamaya yardımcı olur.

#### S: Sağlanan kaynak kodu, imza alanı olan akıllı kart tabanlı imzalama sürecini nasıl işliyor?

A: Kaynak kodu, bir imza alanının nasıl oluşturulacağını, bir akıllı kart sertifikasının nasıl seçileceğini ve belirli imzalama bilgileriyle dijital bir imzanın nasıl uygulanacağını gösterir. Ayrıca imzanın geçerliliğinin nasıl doğrulanacağını da gösterir.

#### S: İmza alanının görünümünü özelleştirebilir miyim?

C: Evet, imza alanının görünümünü (boyutu, konumu ve görsel temsili gibi) belgenizin düzeniyle uyumlu olacak şekilde özelleştirebilirsiniz.

#### S: Doğrulama adımı sırasında bir imzanın doğrulanması başarısız olursa ne olur?

A: Bir imza doğrulamayı geçemezse, imzanın geçerli olmadığını belirten bir istisna atılır. Bu, yalnızca geçerli ve güvenilir imzaların kabul edilmesini sağlar.

#### S: Tek bir PDF belgesine birden fazla imza alanı ve akıllı kart tabanlı imza uygulayabilir miyim?

C: Kesinlikle, aynı PDF belgesinin farklı alanlarına birden fazla imza alanı ve akıllı kart tabanlı imzalar uygulayabilir, böylece birden fazla güvenlik katmanı sağlayabilirsiniz.

#### S: İmza alanının kullanılması genel belge imzalama sürecini nasıl iyileştirir?

A: İmza alanı kullanmak, imzalayanın imzasını belirlenmiş bir alana koymasını sağlayarak belge imzalama sürecini kolaylaştırır, imzalama sürecini daha düzenli ve kullanıcı dostu hale getirir.

#### S: Akıllı kart tabanlı imzalamada imza alanlarının kullanımında herhangi bir sınırlama var mı?

A: Akıllı kart tabanlı imzalama ile imza alanlarını kullanmanın doğasında hiçbir sınırlama yoktur. Ancak, seçilen imza alanı konumunun önemli belge içeriğini gizlemediğinden emin olmak önemlidir.

#### S: Akıllı kart tabanlı imzalamayı imza alanıyla uygulama konusunda daha fazla yardım veya desteği nerede bulabilirim?

C: Ek rehberlik ve destek için, güvenli dijital imzaların uygulanmasına yönelik değerli içgörüler ve çözümler sunan resmi Aspose.PDF belgelerine ve topluluk forumlarına başvurabilirsiniz.