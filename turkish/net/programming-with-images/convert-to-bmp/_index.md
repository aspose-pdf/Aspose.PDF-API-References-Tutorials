---
title: BMP'ye Dönüştür
linktitle: BMP'ye Dönüştür
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF'yi kolayca bireysel BMP görüntülerine dönüştürün.
type: docs
weight: 90
url: /tr/net/programming-with-images/convert-to-bmp/
---

Bu kılavuz, Aspose.PDF for .NET kullanarak bir PDF dosyasını bireysel BMP görüntülerine nasıl dönüştüreceğinizi adım adım gösterecek. Ortamınızı zaten kurduğunuzdan emin olun ve aşağıdaki adımları izleyin:

## 1. Adım: Belge dizinini tanımlayın

 Başlamadan önce, belgeler için doğru dizini ayarladığınızdan emin olun. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` PDF belgenizin bulunduğu dizinin yolunu içeren kodda.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Belgeyi açın

 Bu adımda, PDF belgesini kullanarak açacağız.`Document` Aspose.PDF sınıfı. Kullan`Document` yapıcı ve yolu PDF belgesine iletin.

```csharp
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
```

## 3. Adım: Her sayfayı BMP'ye dönüştürün

 Bu adımda, PDF belgesinin her sayfasını inceleyeceğiz ve bunları ayrı BMP görüntülerine dönüştüreceğiz. bir kullanacağız`for`tüm sayfaları yinelemek için döngü.

```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
     // BMP görüntüsünü kaydetmek için bir akış oluşturun
     using (FileStream imageStream = new FileStream("image" + pageCount + "_out" + ".bmp", FileMode.Create))
     {
         // Çözünürlük nesnesi oluşturma
         Resolution resolution = new Resolution(300);
        
         // Belirtilen niteliklere sahip bir BMP cihazı oluşturun
         //Genişlik, Yükseklik, Çözünürlük, Sayfa Boyutu
         BmpDevice bmpDevice = new BmpDevice(resolution);
        
         // Belirli bir sayfayı dönüştürün ve görüntüyü akışa kaydedin
         bmpDevice.Process(pdfDocument.Pages[pageCount], imageStream);
        
         // akışı kapat
         imageStream.Close();
     }
}
```

### Aspose.PDF for .NET kullanarak BMP'ye Dönüştürmek için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
	using (FileStream imageStream = new FileStream("image" + pageCount + "_out" + ".bmp", FileMode.Create))
	{
		// Çözünürlük nesnesi oluştur
		Resolution resolution = new Resolution(300);
		// Belirtilen özniteliklere sahip BMP cihazı oluşturun
		// Genişlik, Yükseklik, Çözünürlük, Sayfa Boyutu
		BmpDevice bmpDevice = new BmpDevice(resolution);
		// Belirli bir sayfayı dönüştürün ve görüntüyü akışa kaydedin
		bmpDevice.Process(pdfDocument.Pages[pageCount], imageStream);
		// Akışı kapat
		imageStream.Close();
	}
} 
Console.WriteLine("\nPDF file converted to bmp successfully!"); 
```

## Çözüm

Tebrikler! Aspose.PDF for .NET'i kullanarak bir PDF dosyasını bağımsız BMP görüntülerine başarıyla dönüştürdünüz. BMP görüntüleri belirtilen dizine kaydedilir. Artık bu görselleri projelerinizde veya uygulamalarınızda kullanabilirsiniz.