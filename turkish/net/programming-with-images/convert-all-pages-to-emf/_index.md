---
title: Tüm Sayfaları EMF'ye Dönüştür
linktitle: Tüm Sayfaları EMF'ye Dönüştür
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile bir PDF belgesinin tüm sayfalarını kolayca EMF dosyalarına dönüştürün.
type: docs
weight: 50
url: /tr/net/programming-with-images/convert-all-pages-to-emf/
---

Bu kılavuz, Aspose.PDF for .NET kullanarak bir PDF belgesinin tüm sayfalarının EMF (Enhanced Metafile) dosyalarına nasıl dönüştürüleceğini adım adım gösterecek. Ortamınızı zaten kurduğunuzdan emin olun ve aşağıdaki adımları izleyin:

## 1. Adım: Belge dizinini tanımlayın

 Başlamadan önce, belgeler için doğru dizini ayarladığınızdan emin olun. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` PDF belgenizin bulunduğu dizinin yolunu içeren kodda.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Belgeyi açın

 Bu adımda, PDF belgesini kullanarak açacağız.`Document` Aspose.PDF sınıfı. Kullan`Document` yapıcı ve yolu PDF belgesine iletin.

```csharp
Document pdfDocument = new Document(dataDir + "ConvertAllPagesToEMF.pdf");
```

## 3. Adım: Her sayfayı EMF'ye dönüştürün

 Bu adımda, PDF belgesinin her sayfasını inceleyeceğiz ve bunları ayrı EMF dosyalarına dönüştüreceğiz. bir kullanacağız`for`tüm sayfaları yinelemek için döngü.

```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
     // EMF görüntüsünü kaydetmek için bir akış oluşturun
     using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".emf", FileMode.Create))
     {
         // Çözünürlük nesnesi oluşturma
         Resolution resolution = new Resolution(300);
        
         // Belirtilen özniteliklere sahip bir EMF cihazı oluşturun
         // Genişlik, Yükseklik, Çözünürlük
         EmfDevice emfDevice = new EmfDevice(500, 700, resolution);
        
         // Belirli bir sayfayı dönüştürün ve görüntüyü akışa kaydedin
         emfDevice.Process(pdfDocument.Pages[pageCount], imageStream);
        
         // akışı kapat
         imageStream.Close();
     }
}
```

### Aspose.PDF for .NET kullanarak Tüm Sayfaları EMF'ye Dönüştürmek için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir+ "ConvertAllPagesToEMF.pdf");
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
	using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".emf", FileMode.Create))
	{
		// Çözünürlük nesnesi oluştur
		Resolution resolution = new Resolution(300);
		// Belirtilen özniteliklerle PNG cihazı oluştur
		// Genişlik, Yükseklik, Çözünürlük
		EmfDevice emfDevice = new EmfDevice(500, 700, resolution);
		// Belirli bir sayfayı dönüştürün ve görüntüyü akışa kaydedin
		emfDevice.Process(pdfDocument.Pages[pageCount], imageStream);
		// Akışı kapat
		imageStream.Close();
	}
}
System.Console.WriteLine("PDF pages are converted to EMF successfully!");
```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesinin tüm sayfalarını başarıyla EMF dosyalarına dönüştürdünüz. Bireysel EMF dosyaları belirtilen dizine kaydedilir. Artık bu EMF dosyalarını projelerinizde veya uygulamalarınızda kullanabilirsiniz.