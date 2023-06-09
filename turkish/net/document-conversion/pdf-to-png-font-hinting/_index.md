---
title: PDF'den PNG'ye Yazı Tipi İpucu
linktitle: PDF'den PNG'ye Yazı Tipi İpucu
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak yazı tipi ipuçlarıyla PDF'yi PNG'ye dönüştürmek için adım adım kılavuz.
type: docs
weight: 160
url: /tr/net/document-conversion/pdf-to-png-font-hinting/
---

Bu eğitimde, Aspose.PDF for .NET kullanarak yazı tipi ipuçlarını etkinleştirirken bir PDF'yi PNG'ye dönüştürme sürecinde size yol göstereceğiz. Yazı tipi ipucu, küçük yazı tiplerinin okunabilirliğini artıran bir tekniktir. Aşağıdaki adımları izleyerek, PDF'nin her sayfasını yazı tipi ipucu içeren bir PNG görüntüsüne dönüştürebileceksiniz.

## Önkoşullar
Başlamadan önce, aşağıdaki ön koşulları karşıladığınızdan emin olun:

- C# programlama dili hakkında temel bilgi.
- Sisteminizde kurulu .NET için Aspose.PDF kitaplığı.
- Visual Studio gibi bir geliştirme ortamı.

## 1. Adım: Kaynak PDF belgesini açma
Bu adımda, Aspose.PDF for .NET kullanarak kaynak PDF dosyasını açacağız. Aşağıdaki kodu izleyin:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// belgeyi aç
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 değiştirdiğinizden emin olun`"YOUR DOCUMENTS DIRECTORY"` PDF dosyanızın bulunduğu gerçek dizinle.

## 2. Adım: Yazı tipi ipuçlarını etkinleştirin
PDF dosyasını açtıktan sonra, rendering seçeneklerini kullanarak font ipucunu etkinleştireceğiz. Aşağıdaki kodu kullanın:

```csharp
// Yazı tipi ipuçlarını etkinleştirmek için oluşturma seçenekleri oluşturun
RenderingOptions opts = new RenderingOptions();
opts. UseFontHinting = true;
```

## 3. Adım: PNG görüntülerine dönüştürün
Şimdi PDF'nin her sayfasını yazı tipi ipuçlarıyla bir PNG görüntüsüne dönüştüreceğiz. Aşağıdaki kodu kullanın:

```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
     using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".png", FileMode.Create))
     {
         // Belirtilen niteliklere sahip bir PNGDevice nesnesi oluşturun
         // Genişlik, Yükseklik, Çözünürlük, Kalite
         // Kalite [0-100], 100 maksimumdur
         // Çözünürlük nesnesi oluşturma
         Resolution resolution = new Resolution(300);
         PngDevice pngDevice = new PngDevice(resolution);
         // Önceden tanımlanmış oluşturma seçeneklerini ayarlayın
         pngDevice.RenderingOptions = opts;

         // Belirli bir sayfayı dönüştürün ve görüntüyü akışa kaydedin
         pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);

         // akışı kapat
         imageStream.Close();
     }
}
```

Yukarıdaki kod, PDF'nin her sayfasını yazı tipi ipucu içeren bir PNG görüntüsüne dönüştürür ve her görüntüyü ayrı bir PNG dosyası olarak kaydeder.

### Aspose.PDF for .NET kullanarak PDF'den PNGFont'a Hinting için örnek kaynak kodu

```csharp
try
{
	
	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Belgeyi aç
	Document pdfDocument = new Document(dataDir + "input.pdf");
	// Yazı tipi ipuçlarını etkinleştirmek için Aspose.Pdf.RenderingOptions oluşturun
	RenderingOptions opts = new RenderingOptions();
	opts.UseFontHinting = true;
	
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
			// Önceden tanımlanmış oluşturma seçeneklerini ayarlayın
			pngDevice.RenderingOptions = opts;

			// Belirli bir sayfayı dönüştürün ve görüntüyü akışa kaydedin
			pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);

			// Akışı kapat
			imageStream.Close();
		}
	}
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Çözüm
Bu eğitimde, Aspose.PDF for .NET kullanarak yazı tipi ipuçlarıyla PDF'yi PNG'ye dönüştürme sürecini adım adım ele aldık. Yukarıda özetlenen talimatları izleyerek, artık PDF'nin her sayfasını yazı tipi ipucu içeren bir PNG görüntüsüne dönüştürebilmelisiniz. Bu özellik, PNG görüntülerine dönüştürürken küçük yazı tiplerinin okunabilirliğini korumak istediğinizde kullanışlıdır.