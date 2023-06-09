---
title: Tüm Sayfaları PNG'ye Dönüştür
linktitle: Tüm Sayfaları PNG'ye Dönüştür
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile bir PDF belgesinin tüm sayfalarını kolayca PNG dosyalarına dönüştürün.
type: docs
weight: 60
url: /tr/net/programming-with-images/convert-all-pages-to-png/
---

Bu kılavuz, Aspose.PDF for .NET kullanarak bir PDF belgesinin tüm sayfalarının PNG dosyalarına nasıl dönüştürüleceğini adım adım gösterecek. Ortamınızı zaten kurduğunuzdan emin olun ve aşağıdaki adımları izleyin:

## 1. Adım: Belge dizinini tanımlayın

 Başlamadan önce, belgeler için doğru dizini ayarladığınızdan emin olun. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` PDF belgenizin bulunduğu dizinin yolunu içeren kodda.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Belgeyi açın

 Bu adımda, PDF belgesini kullanarak açacağız.`Document` Aspose.PDF sınıfı. Kullan`Document` yapıcı ve yolu PDF belgesine iletin.

```csharp
Document pdfDocument = new Document(dataDir + "ConvertAllPagesToPNG.pdf");
```

## 3. Adım: Her sayfayı PNG'ye dönüştürün

 Bu adımda, PDF belgesinin her sayfasını inceleyeceğiz ve bunları ayrı ayrı PNG dosyalarına dönüştüreceğiz. bir kullanacağız`for`tüm sayfaları yinelemek için döngü.

```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
     //PNG görüntüsünü kaydetmek için bir akış oluşturun
     using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".png", FileMode.Create))
     {
         // Belirtilen niteliklere sahip bir PNG cihazı oluşturun
         // Genişlik, Yükseklik, Çözünürlük, Kalite
         // Kalite [0-100], 100 maksimumdur
         Resolution resolution = new Resolution(300);
         PngDevice pngDevice = new PngDevice(resolution);
        
         // Belirli bir sayfayı dönüştürün ve görüntüyü akışa kaydedin
         pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);
        
         // akışı kapat
         imageStream.Close();
     }
}
```

### Aspose.PDF for .NET kullanarak Tüm Sayfaları PNG'ye Dönüştürmek için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "ConvertAllPagesToPNG.pdf");
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
	using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".png", FileMode.Create))
	{
		// Belirtilen özniteliklerle PNG cihazı oluştur
		// Genişlik, Yükseklik, Çözünürlük, Kalite
		// Kalite [0-100], 100 Maksimum
		// Çözünürlük nesnesi oluştur
		Resolution resolution = new Resolution(300);
		PngDevice pngDevice = new PngDevice(resolution);
		// Belirli bir sayfayı dönüştürün ve görüntüyü akışa kaydedin
		pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);
		// Akışı kapat
		imageStream.Close();
	}
}
System.Console.WriteLine("PDF pages are converted to PNG successfully!");
```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesinin tüm sayfalarını başarıyla PNG dosyalarına dönüştürdünüz. Bireysel PNG dosyaları belirtilen dizine kaydedilir. Artık bu PNG dosyalarını projelerinizde veya uygulamalarınızda kullanabilirsiniz.