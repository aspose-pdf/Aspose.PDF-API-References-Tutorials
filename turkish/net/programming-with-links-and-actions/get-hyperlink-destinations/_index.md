---
title: PDF Dosyasında Köprü Hedeflerini Alın
linktitle: PDF Dosyasında Köprü Hedeflerini Alın
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyasındaki köprü hedeflerini nasıl çıkaracağınızı öğrenin.
type: docs
weight: 60
url: /tr/net/programming-with-links-and-actions/get-hyperlink-destinations/
---
Aspose.PDF for .NET, C# programlama dilini kullanarak PDF dosyasındaki bilgileri işlemek ve ayıklamak için güçlü bir kitaplıktır. Bu öğreticide, Aspose.PDF for .NET kullanarak bir PDF dosyasından köprü hedeflerini çıkarmaya odaklanacağız.

## Önkoşullar

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Visual Studio gibi entegre bir geliştirme ortamı (IDE).
- Makinenizde yüklü olan .NET için Aspose.PDF kitaplığı.

## 1. Adım: Geliştirme ortamını ayarlama

Kod yazmaya başlamadan önce, favori IDE'nizde yeni bir C# projesi oluşturarak geliştirme ortamınızı kurmanız gerekir.

## Adım 2: Aspose.PDF referanslarını içe aktarın

Aspose.PDF for .NET'i kullanmak için projenize uygun referansları eklemeniz gerekir. Gerekli referansları içe aktarmak için aşağıdaki adımları izleyin:

1. Projenizde "Referanslar"a sağ tıklayın ve "Referans Ekle"yi seçin.
2. "Referans Ekle" penceresinde, Aspose.PDF for .NET'in DLL dosyalarını bulun ve seçin.
3. Referansları projenize aktarmak için "Tamam"a tıklayın.

## 3. Adım: PDF Dosyasını Yükleme

Köprü hedeflerini ayıklayabilmeniz için önce PDF dosyasını uygulamanıza yüklemeniz gerekir. PDF dosyasını yüklemek için aşağıdaki kodu kullanın:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// PDF dosyasını yükleyin
Document document = new Document(dataDir + "input.pdf");
```

Belge dizininizin ve işlemek istediğiniz PDF dosyasının doğru yolunu belirttiğinizden emin olun.

## 4. Adım: Belgenin sayfalarında gezinme

Artık PDF dosyası yüklendiğine göre, belgenin tüm sayfalarını gözden geçirmeniz gerekiyor. Bu, almanızı sağlayacak

Her sayfada bulunan köprü açıklamaları. Belgenin sayfalarını yinelemek için aşağıdaki kodu kullanın:

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     // Belirli bir sayfanın bağlantı ek açıklamalarını alın
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     // Tüm bağlantıları saklamak için bir liste oluşturun
     IList<Annotation> list = selector. Selected;
     // Listedeki her öğe arasında döngü yapın
     foreach(LinkAnnotation a in list)
     {
         // Hedef URL'yi yazdır
         Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
     }
}
```

Bu kod, belgenin her sayfasında döngü halinde dolaşır ve her sayfada bulunan köprü ek açıklamalarını seçer. Daha sonra bu ek açıklamaları bir listede saklar ve her bağlantı için hedef URL'yi yazdırır.

## Adım 5: Köprü Hedeflerini Elde Etme

Son adım, köprü ek açıklamalarından köprü hedeflerini çıkarmaktır. Aşağıdaki kod bunu nasıl yapacağınızı gösterir:

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     IList<Annotation> list = selector. Selected;
     foreach(LinkAnnotation a in list)
     {
         string destination = (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI;
         // Hedefi istediğiniz gibi kullanın
     }
}
```

Bu kodda, her hiper bağlantı hedefini bağlantı ek açıklamalarından alır ve hedefi bir değişkende saklarız. Daha sonra bu destinasyonu uygulamanızda dilediğiniz gibi kullanabilirsiniz.

### Aspose.PDF for .NET kullanarak Köprü Hedeflerini Al için örnek kaynak kodu 
```csharp
try
{
	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// PDF dosyasını yükleyin
	Document document = new Document(dataDir + "input.pdf");
	// PDF'nin tüm sayfasında gezinin
	foreach (Aspose.Pdf.Page page in document.Pages)
	{
		// Bağlantı ek açıklamalarını belirli bir sayfadan alın
		AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
		page.Accept(selector);
		// Tüm bağlantıları tutan liste oluştur
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

### PDF dosyasında köprü hedefleri almayla ilgili SSS

#### S: PDF dosyasındaki köprü hedefi nedir?

Y: Bir PDF dosyasındaki köprü hedefi, köprünün işaret ettiği belirli bir konum veya hedeftir. Bir URL, aynı belgedeki bir sayfa veya harici bir belge olabilir.

#### S: Köprü hedeflerini ayıklamak, PDF belge analizime nasıl fayda sağlayabilir?

C: Köprü hedeflerini ayıklamak, bir PDF belgesinde köprülerin işaret ettiği tüm hedefleri tanımlamanıza ve kataloglamanıza olanak tanır. Bu bilgiler içerik doğrulama, bağlantı doğrulama ve veri analizi için yararlı olabilir.

#### S: Aspose.PDF for .NET, köprü hedeflerinin çıkarılmasına nasıl yardımcı olur?

Y: Aspose.PDF for .NET, hiper bağlantı hedeflerini kolaylıkla ayıklamak için güçlü API'ler sağlar. Bu öğretici, C# kullanarak köprü hedeflerinin nasıl ayıklanacağını adım adım gösterir.

#### S: Köprü hedeflerini belirli kriterlere göre seçerek çıkarabilir miyim?

C: Evet, PDF belgesinin sayfalarını yineleyerek ve kriterlerinize göre istenen köprü açıklamalarını filtreleyerek köprü hedeflerini seçerek çıkarabilirsiniz.

#### S: Parola korumalı PDF belgelerinden köprü hedefleri çıkarmak mümkün mü?

Y: Belgeyi açarken gerekli kimlik doğrulama bilgilerini sağladığınız sürece Aspose.PDF for .NET, parola korumalı PDF belgelerinden hiper bağlantı hedeflerini çıkarabilir.

#### S: Ayıklanan köprü hedeflerini uygulamamda nasıl kullanabilirim?

C: Köprü hedeflerini çıkardıktan sonra, bunları bağlantı URL'lerini doğrulamak, raporlar oluşturmak veya özel gezinme uygulamak gibi çeşitli eylemler gerçekleştirmek için kullanabilirsiniz.

#### S: Köprü hedeflerini çıkarırken herhangi bir sınırlama var mı?

Y: Köprü hedef ayıklaması güçlü olsa da, PDF belgesinin yapısını göz önünde bulundurmak önemlidir. Karmaşık grafiklere veya multimedya içeriğine gömülü köprüler, ek işlem gerektirebilir.

#### S: Köprülerin bağlantı türleri veya koordinatlar gibi diğer niteliklerini çıkarabilir miyim?

C: Öğretici, köprü hedeflerini çıkarmaya odaklanır. Ancak, bağlantı türleri ve koordinatların çıkarılması da dahil olmak üzere gelişmiş özellikleri keşfetmek için resmi Aspose.PDF belgelerine başvurabilirsiniz.