---
title: PDF Dosyasında Köprü Hedeflerini Alın
linktitle: PDF Dosyasında Köprü Hedeflerini Alın
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak PDF dosyasındaki köprü hedeflerini nasıl çıkaracağınızı öğrenin.
type: docs
weight: 60
url: /tr/net/programming-with-links-and-actions/get-hyperlink-destinations/
---
Aspose.PDF for .NET, C# programlama dilini kullanarak PDF dosyasındaki bilgileri düzenlemek ve çıkarmak için kullanılan güçlü bir kütüphanedir. Bu eğitimde Aspose.PDF for .NET kullanarak bir PDF dosyasından köprü hedeflerini çıkarmaya odaklanacağız.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Visual Studio gibi entegre bir geliştirme ortamı (IDE).
- .NET için Aspose.PDF kütüphanesi makinenizde yüklü.

## 1. Adım: Geliştirme ortamını ayarlama

Kod yazmaya başlamadan önce favori IDE'nizde yeni bir C# projesi oluşturarak geliştirme ortamınızı ayarlamanız gerekir.

## Adım 2: Aspose.PDF referanslarını içe aktarın

Aspose.PDF for .NET'i kullanmak için projenize uygun referansları eklemeniz gerekir. Gerekli referansları içe aktarmak için aşağıdaki adımları izleyin:

1. Projenizde "Referanslar"a sağ tıklayın ve "Referans Ekle"yi seçin.
2. "Referans Ekle" penceresinde Aspose.PDF for .NET'in DLL dosyalarını bulun ve seçin.
3. Referansları projenize aktarmak için "Tamam"ı tıklayın.

## Adım 3: PDF Dosyasını Yükleme

Köprü hedeflerini ayıklamadan önce PDF dosyasını uygulamanıza yüklemelisiniz. PDF dosyasını yüklemek için aşağıdaki kodu kullanın:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// PDF dosyasını yükleyin
Document document = new Document(dataDir + "input.pdf");
```

Belge dizininizin ve işlemek istediğiniz PDF dosyasının doğru yolunu belirttiğinizden emin olun.

## Adım 4: Belgenin sayfalarında gezinme

Artık PDF dosyası yüklendiğine göre belgenin tüm sayfalarını gözden geçirmeniz gerekiyor. Bu, şunları elde etmenizi sağlayacaktır:

her sayfada bulunan köprü açıklamaları. Belgenin sayfaları arasında yineleme yapmak için aşağıdaki kodu kullanın:

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     // Belirli bir sayfanın bağlantı açıklamalarını alın
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     // Tüm bağlantıları saklamak için bir liste oluşturun
     IList<Annotation> list = selector. Selected;
     // Listedeki her öğe arasında dolaşın
     foreach(LinkAnnotation a in list)
     {
         // Hedef URL'yi yazdır
         Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
     }
}
```

Bu kod, belgenin her sayfasında döngü yapar ve her sayfada bulunan köprü açıklamalarını seçer. Daha sonra bu ek açıklamaları bir listede saklar ve her bağlantı için hedef URL'yi yazdırır.

## Adım 5: Köprü Hedeflerini Alma

Son adım, köprü hedeflerini köprü ek açıklamalarından çıkarmaktır. Aşağıdaki kod bunu nasıl yapacağınızı gösterir:

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

Bu kodda, her bir köprü hedefini bağlantı açıklamalarından alıyoruz ve hedefi bir değişkende saklıyoruz. Daha sonra bu hedefi uygulamanızda dilediğiniz gibi kullanabilirsiniz.

### Aspose.PDF for .NET kullanarak Köprü Hedefleri Alma için örnek kaynak kodu 
```csharp
try
{
	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// PDF dosyasını yükleyin
	Document document = new Document(dataDir + "input.pdf");
	// PDF'nin tüm sayfasını dolaşın
	foreach (Aspose.Pdf.Page page in document.Pages)
	{
		// Belirli bir sayfadan bağlantı açıklamalarını alın
		AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
		page.Accept(selector);
		// Tüm bağlantıları tutan bir liste oluşturun
		IList<Annotation> list = selector.Selected;
		// Liste içindeki bireysel öğeyi yineleyin
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

### PDF dosyasında köprü hedeflerini almaya ilişkin SSS

#### S: PDF dosyasındaki köprü hedefi nedir?

C: PDF dosyasındaki köprü hedefi, köprünün işaret ettiği belirli bir konum veya hedeftir. Bu bir URL, aynı belge içindeki bir sayfa veya harici bir belge olabilir.

#### S: Köprü hedeflerini ayıklamak PDF belge analizime nasıl fayda sağlayabilir?

C: Köprü hedeflerini çıkarmak, bir PDF belgesinde köprülerin işaret ettiği tüm hedefleri tanımlamanıza ve kataloglamanıza olanak tanır. Bu bilgiler içerik doğrulama, bağlantı doğrulama ve veri analizi için yararlı olabilir.

#### S: Aspose.PDF for .NET, köprü hedeflerinin çıkarılmasına nasıl yardımcı olur?

C: Aspose.PDF for .NET, köprü hedeflerini kolaylıkla çıkarmak için güçlü API'ler sağlar. Bu öğretici, C# kullanarak köprü hedeflerinin nasıl çıkarılacağını adım adım gösterir.

#### S: Köprü hedeflerini belirli kriterlere göre seçerek çıkarabilir miyim?

C: Evet, PDF belgesinin sayfalarını yineleyerek ve kriterlerinize göre istenen köprü ek açıklamalarını filtreleyerek köprü hedeflerini seçerek çıkarabilirsiniz.

#### S: Parola korumalı PDF belgelerinden köprü hedeflerini çıkarmak mümkün müdür?

C: Aspose.PDF for .NET, belgeyi açarken gerekli kimlik doğrulama bilgilerini sağladığınız sürece parola korumalı PDF belgelerinden köprü hedeflerini çıkarabilir.

#### S: Çıkarılan köprü hedeflerini uygulamamda nasıl kullanabilirim?

C: Köprü hedeflerini çıkardıktan sonra bunları, bağlantı URL'lerini doğrulamak, raporlar oluşturmak veya özel gezinmeyi uygulamak gibi çeşitli eylemleri gerçekleştirmek için kullanabilirsiniz.

#### S: Köprü hedeflerini çıkarırken herhangi bir sınırlama var mı?

C: Köprü hedefinin çıkarılması güçlü olsa da, PDF belgesinin yapısını dikkate almak önemlidir. Karmaşık grafiklere veya multimedya içeriğine gömülü köprüler ek işlem gerektirebilir.

#### S: Bağlantı türleri veya koordinatlar gibi köprülerin diğer özelliklerini çıkarabilir miyim?

C: Eğitim, köprü hedeflerini çıkarmaya odaklanıyor. Ancak bağlantı türleri ve koordinatların çıkarılması da dahil olmak üzere gelişmiş özellikleri keşfetmek için resmi Aspose.PDF belgelerine başvurabilirsiniz.