---
title: Başlıktaki Resim
linktitle: Başlıktaki Resim
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile bir PDF belgesinin başlık bölümüne nasıl resim ekleyeceğinizi öğrenin.
type: docs
weight: 140
url: /tr/net/programming-with-stamps-and-watermarks/image-in-header/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesinin başlık bölümüne nasıl resim ekleyeceğiniz konusunda size adım adım rehberlik edeceğiz. Mevcut bir PDF belgesini açmak, bir görüntü arabelleği oluşturmak, özelliklerini ayarlamak ve onu PDF belgesinin tüm sayfalarına eklemek için sağlanan C# kaynak kodunu kullanacağız.

## 1. Adım: Ortamı ayarlama

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Yüklü bir .NET geliştirme ortamı.
- .NET için Aspose.PDF kitaplığı indirildi ve projenizde referans verildi.

## 2. Adım: Mevcut PDF belgesini yükleme

İlk adım, mevcut PDF belgesini projenize yüklemektir. İşte nasıl:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Mevcut PDF belgesini aç
Document pdfDocument = new Document(dataDir + "ImageinHeader.pdf");
```

"BELGELER DİZİNİNİZİ", PDF belgenizin bulunduğu dizinin gerçek yolu ile değiştirdiğinizden emin olun.

## 3. Adım: Başlık bölümünde görseli oluşturma ve ekleme

Artık PDF belgesi yüklendiğine göre, bir görüntü arabelleği oluşturabilir ve bunu belgenin tüm sayfalarına başlık bölümü olarak ekleyebiliriz. İşte nasıl:

```csharp
// Çerçeve arabelleğini oluştur
ImageStamp imageStamp = new ImageStamp(dataDir + "aspose-logo.jpg");

// Görüntü arabelleği özelliklerini ayarla
imageStamp.TopMargin = 10;
imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
imageStamp.VerticalAlignment = VerticalAlignment.Top;

//Tüm sayfalara resim arabelleği ekle
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(imageStamp);
}
```

Yukarıdaki kod, "aspose-logo.jpg" dosyasından bir görüntü arabelleği oluşturur ve üst kenar boşluğu, yatay ve dikey hizalama gibi özelliklerini ayarlar. Daha sonra görüntü damgası, PDF belgesinin tüm sayfalarına başlık bölümü olarak eklenir.

## 4. Adım: Değiştirilen PDF belgesini kaydetme

Resim başlık bölümüne eklendikten sonra, değiştirilen PDF belgesini kaydedebiliriz. İşte nasıl:

```csharp
// Değiştirilen PDF belgesini kaydedin
pdfDocument.Save(dataDir + "ImageinHeader_out.pdf");
```

Yukarıdaki kod, düzenlenen PDF belgesini belirtilen dizine kaydeder.

### Aspose.PDF for .NET kullanan Imagein Header için örnek kaynak kodu 

```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi aç
Document pdfDocument = new Document(dataDir+ "ImageinHeader.pdf");

// Başlık oluştur
ImageStamp imageStamp = new ImageStamp(dataDir+ "aspose-logo.jpg");

// Damganın özelliklerini ayarlama
imageStamp.TopMargin = 10;
imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
imageStamp.VerticalAlignment = VerticalAlignment.Top;

// Tüm sayfalara başlık ekle
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(imageStamp);
}
dataDir = dataDir + "ImageinHeader_out.pdf";

// Güncellenen belgeyi kaydet
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage in header added successfully.\nFile saved at " + dataDir);                        

```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesinin başlık bölümüne nasıl resim ekleyeceğinizi öğrendiniz. Artık resimler ekleyerek PDF belgelerinizin başlıklarını özelleştirebilirsiniz.
