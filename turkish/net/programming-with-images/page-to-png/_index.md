---
title: Sayfadan PNG'ye
linktitle: Sayfadan PNG'ye
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir sayfayı PNG formatına dönüştürmek için adım adım kılavuz.
type: docs
weight: 220
url: /tr/net/programming-with-images/page-to-png/
---

Bu öğreticide, Aspose.PDF for .NET kullanarak bir sayfayı PNG formatına nasıl dönüştüreceğinizi anlatacağız. Bu işlemi kolayca gerçekleştirmek için aşağıdaki adımları izleyin.

## Önkoşullar

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Visual Studio veya kurulu ve yapılandırılmış başka bir geliştirme ortamı.
- C# programlama dili hakkında temel bilgi.
- Aspose.PDF kitaplığı for .NET kurulu. Aspose resmi sitesinden indirebilirsiniz.

## 1. Adım: PDF belgesini yükleme

Başlamak için, PDF belgesini yüklemek üzere aşağıdaki kodu kullanın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// belgeyi aç
Document pdfDocument = new Document(dataDir + "PageToPNG.pdf");
```

PDF belgenize giden doğru yolu sağladığınızdan emin olun.

## 2. Adım: Sayfayı PNG'ye dönüştürün

Ardından, PDF belgesinin belirli bir sayfasını PNG formatına dönüştüreceğiz. Aşağıdaki kodu kullanın:

```csharp
using (FileStream imageStream = new FileStream(dataDir + "aspose-logo.png", FileMode.Create))
{
// Çözünürlük nesnesi oluşturma
Resolution resolution = new Resolution(300);
// Belirtilen niteliklere (Genişlik, Yükseklik, Çözünürlük) sahip bir PNG aygıtı oluşturun
PngDevice pngDevice = new PngDevice(resolution);
// Belirli bir sayfayı dönüştürün ve görüntüyü akışa kaydedin
pngDevice.Process(pdfDocument.Pages[1], imageStream);
// akışı kapat
imageStream.Close();
}
```

Çıktı PNG görüntüsü için istenen yolu ve dosya adını sağladığınızdan emin olun.

### Aspose.PDF for .NET kullanan Page To PNG için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "PageToPNG.pdf");
using (FileStream imageStream = new FileStream(dataDir + "aspose-logo.png", FileMode.Create))
{
	// Çözünürlük nesnesi oluştur
	Resolution resolution = new Resolution(300);
	// Belirtilen niteliklere (Genişlik, Yükseklik, Çözünürlük) sahip PNG cihazı oluşturun
	PngDevice pngDevice = new PngDevice(resolution);
	// Belirli bir sayfayı dönüştürün ve görüntüyü akışa kaydedin
	pngDevice.Process(pdfDocument.Pages[1], imageStream);
	// Akışı kapat
	imageStream.Close();
}
```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir sayfayı başarıyla PNG formatına dönüştürdünüz. Artık bu yöntemi, PDF dosyalarından belirli sayfaları ayıklamak ve PNG görüntüleri olarak kaydetmek için kendi projelerinize uygulayabilirsiniz.