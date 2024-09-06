---
title: PDF Dosyasında Köprü Bağlantısı Hedeflerini Alın
linktitle: PDF Dosyasında Köprü Bağlantısı Hedeflerini Alın
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyasındaki köprü hedeflerinin nasıl çıkarılacağını öğrenin.
type: docs
weight: 60
url: /tr/net/programming-with-links-and-actions/get-hyperlink-destinations/
---
Aspose.PDF for .NET, C# programlama dilini kullanarak PDF dosyasındaki bilgileri düzenlemek ve çıkarmak için güçlü bir kütüphanedir. Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF dosyasından köprü metni hedeflerini çıkarmaya odaklanacağız.

## Ön koşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Visual Studio gibi entegre bir geliştirme ortamı (IDE).
- Bilgisayarınızda .NET için Aspose.PDF kütüphanesi yüklü.

## Adım 1: Geliştirme ortamının kurulumu

Kod yazmaya başlamadan önce, favori IDE'nizde yeni bir C# projesi oluşturarak geliştirme ortamınızı ayarlamanız gerekir.

## Adım 2: Aspose.PDF referanslarını içe aktarın

Aspose.PDF for .NET'i kullanmak için projenize uygun referansları eklemeniz gerekir. Gerekli referansları içe aktarmak için aşağıdaki adımları izleyin:

1. Projenizde "Referanslar"a sağ tıklayın ve "Referans Ekle"yi seçin.
2. "Referans Ekle" penceresinde, Aspose.PDF for .NET'in DLL dosyalarını bulun ve seçin.
3. Referansları projenize aktarmak için "Tamam"a tıklayın.

## Adım 3: PDF Dosyasını Yükleme

Köprü metni hedeflerini çıkarabilmeniz için PDF dosyasını uygulamanıza yüklemeniz gerekir. PDF dosyasını yüklemek için aşağıdaki kodu kullanın:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// PDF dosyasını yükle
Document document = new Document(dataDir + "input.pdf");
```

Belge dizininize giden doğru yolu ve işlemek istediğiniz PDF dosyasını belirttiğinizden emin olun.

## Adım 4: Belgenin sayfalarında gezinme

Artık PDF dosyası yüklendiğine göre, belgenin tüm sayfalarını incelemeniz gerekir. Bu, şunları elde etmenizi sağlayacaktır:

Her sayfada bulunan köprü metni açıklamaları. Belgenin sayfaları arasında yineleme yapmak için aşağıdaki kodu kullanın:

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     // Belirli bir sayfanın bağlantı açıklamalarını alın
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     // Tüm bağlantıları depolamak için bir liste oluşturun
     IList<Annotation> list = selector. Selected;
     // Listedeki her bir öğeyi dolaş
     foreach(LinkAnnotation a in list)
     {
         // Hedef URL'yi yazdır
         Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
     }
}
```

Bu kod, belgenin her sayfasında döngüye girer ve her sayfada bulunan köprü metni açıklamalarını seçer. Daha sonra bu açıklamaları bir listede depolar ve her bağlantı için hedef URL'yi yazdırır.

## Adım 5: Köprü Bağlantısı Hedeflerinin Elde Edilmesi

Son adım, köprü metni açıklamalarından köprü metni hedeflerini çıkarmaktır. Aşağıdaki kod bunu nasıl yapacağınızı gösterir:

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     IList<Annotation> list = selector. Selected;
     foreach(LinkAnnotation a in list)
     {
         string destination = (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI;
         // Hedefi dilediğiniz gibi kullanın
     }
}
```

Bu kodda, her bir köprü metni hedefini bağlantı açıklamalarından alıyoruz ve hedefi bir değişkende saklıyoruz. Daha sonra bu hedefi uygulamanızda istediğiniz gibi kullanabilirsiniz.

### .NET için Aspose.PDF kullanarak Köprü Bağlantısı Hedeflerini Alma için örnek kaynak kodu 
```csharp
try
{
	// Belgeler dizinine giden yol.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// PDF dosyasını yükle
	Document document = new Document(dataDir + "input.pdf");
	// PDF'in tüm sayfalarını dolaş
	foreach (Aspose.Pdf.Page page in document.Pages)
	{
		// Belirli bir sayfadan bağlantı açıklamalarını al
		AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
		page.Accept(selector);
		// Tüm bağlantıları içeren listeyi oluştur
		IList<Annotation> list = selector.Selected;
		// Liste içindeki tekil öğeler arasında yineleme yap
		foreach (LinkAnnotation a in list)
		{
			// Hedef URL'yi yazdır
			Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

### PDF dosyasında köprü metni hedeflerini almak için SSS

#### S: PDF dosyasında köprü metni hedefi nedir?

A: Bir PDF dosyasındaki köprü metni hedefi, köprü metninin işaret ettiği belirli bir konum veya hedeftir. Bir URL, aynı belgedeki bir sayfa veya harici bir belge olabilir.

#### S: Köprü metni hedeflerini çıkarmak PDF belgemin analizine nasıl fayda sağlar?

A: Köprü metni hedeflerini çıkarmak, köprü metinlerinin bir PDF belgesi içinde işaret ettiği tüm hedefleri tanımlamanıza ve kataloglamanıza olanak tanır. Bu bilgiler içerik doğrulama, bağlantı doğrulama ve veri analizi için yararlı olabilir.

#### S: Aspose.PDF for .NET, köprü metin hedeflerinin çıkarılmasına nasıl yardımcı olur?

A: Aspose.PDF for .NET, köprü metni hedeflerini kolaylıkla çıkarmak için güçlü API'ler sağlar. Bu eğitim, köprü metni hedeflerinin C# kullanılarak nasıl adım adım çıkarılacağını gösterir.

#### S: Belirli kriterlere göre seçici bir şekilde hiper bağlantı hedeflerini çıkarabilir miyim?

C: Evet, PDF belgesinin sayfaları arasında gezinerek ve kriterlerinize göre istediğiniz köprü metni açıklamalarını filtreleyerek köprü metni hedeflerini seçici bir şekilde çıkarabilirsiniz.

#### S: Parola korumalı PDF belgelerinden köprü metin hedeflerini çıkarmak mümkün müdür?

C: Aspose.PDF for .NET, belgeyi açarken gerekli kimlik doğrulama bilgilerini sağladığınız sürece parola korumalı PDF belgelerinden köprü metni hedeflerini çıkarabilir.

#### S: Çıkarılan köprü metin hedeflerini uygulamamda nasıl kullanabilirim?

A: Köprü metni hedeflerini çıkardıktan sonra bunları kullanarak bağlantı URL'lerini doğrulama, raporlar oluşturma veya özel gezinme uygulama gibi çeşitli eylemler gerçekleştirebilirsiniz.

#### S: Köprü metni hedeflerini çıkarırken herhangi bir sınırlama var mı?

A: Köprü metni hedefi çıkarma güçlü olsa da, PDF belgesinin yapısını dikkate almak önemlidir. Karmaşık grafikler veya multimedya içeriklerine gömülü köprü metinleri ek işlem gerektirebilir.

#### S: Bağlantı türleri veya koordinatlar gibi hiper bağlantıların diğer niteliklerini çıkarabilir miyim?

A: Eğitim, köprü metni hedeflerini çıkarmaya odaklanıyor. Ancak, bağlantı türlerini ve koordinatları çıkarma gibi gelişmiş özellikleri keşfetmek için resmi Aspose.PDF belgelerine başvurabilirsiniz.