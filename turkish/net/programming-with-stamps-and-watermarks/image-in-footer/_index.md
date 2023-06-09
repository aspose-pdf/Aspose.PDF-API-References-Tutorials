---
title: Altbilgideki Resim
linktitle: Altbilgideki Resim
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile bir PDF belgesinin alt bilgi bölümüne nasıl resim ekleyeceğinizi öğrenin.
type: docs
weight: 130
url: /tr/net/programming-with-stamps-and-watermarks/image-in-footer/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesinin altbilgi bölümüne nasıl resim ekleyeceğiniz konusunda adım adım rehberlik edeceğiz. Mevcut bir PDF belgesini açmak, bir görüntü arabelleği oluşturmak, özelliklerini ayarlamak ve onu PDF belgesinin tüm sayfalarına eklemek için sağlanan C# kaynak kodunu kullanacağız.

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
Document pdfDocument = new Document(dataDir + "ImageInFooter.pdf");
```

"BELGELER DİZİNİNİZİ", PDF belgenizin bulunduğu dizinin gerçek yolu ile değiştirdiğinizden emin olun.

## 3. Adım: Görüntüyü altbilgi bölümünde oluşturma ve ekleme

Artık PDF belgesi yüklendiğine göre, bir görüntü damgası oluşturabilir ve bunu belgenin tüm sayfalarına ekleyebiliriz. İşte nasıl:

```csharp
// Çerçeve arabelleğini oluştur
ImageStamp imageStamp = new ImageStamp(dataDir + "aspose-logo.jpg");

// Görüntü arabelleği özelliklerini ayarla
imageStamp.BottomMargin = 10;
imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
imageStamp.VerticalAlignment = VerticalAlignment.Bottom;

//Tüm sayfalara resim arabelleği ekle
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(imageStamp);
}
```

Yukarıdaki kod, "aspose-logo.jpg" dosyasından bir görüntü arabelleği oluşturur ve alt kenar boşluğu, yatay ve dikey hizalama gibi özelliklerini ayarlar. Ardından, görüntü arabelleği PDF belgesinin tüm sayfalarına eklenir.

## 4. Adım: Değiştirilen PDF belgesini kaydetme

Resim altbilgi bölümüne eklendikten sonra, değiştirilen PDF belgesini kaydedebiliriz. İşte nasıl:

```csharp
// Değiştirilen PDF belgesini kaydedin
pdfDocument.Save(dataDir + "ImageInFooter_out.pdf");
```

Yukarıdaki kod, düzenlenen PDF belgesini belirtilen dizine kaydeder.

### Aspose.PDF for .NET kullanan Image In Footer için örnek kaynak kodu 
```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi aç
Document pdfDocument = new Document(dataDir+ "ImageInFooter.pdf");

// Alt bilgi oluştur
ImageStamp imageStamp = new ImageStamp(dataDir+ "aspose-logo.jpg");

// Damganın özelliklerini ayarlama
imageStamp.BottomMargin = 10;
imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
imageStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Tüm sayfalara alt bilgi ekle
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(imageStamp);
}
dataDir = dataDir + "ImageInFooter_out.pdf";

// Güncellenmiş PDF dosyasını kaydet
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage in footer added successfully.\nFile saved at " + dataDir);
```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesinin alt bilgi bölümüne nasıl resim ekleyeceğinizi öğrendiniz. Artık resimler ekleyerek PDF belgelerinizin altbilgilerini özelleştirebilirsiniz.
