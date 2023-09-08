---
title: XPS'den PDF'ye
linktitle: XPS'den PDF'ye
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile XPS dosyasını PDF'ye dönüştürmek için adım adım kılavuz.
type: docs
weight: 350
url: /tr/net/document-conversion/xps-to-pdf/
---
Bu eğitimde, .NET için Aspose.PDF kütüphanesini kullanarak XPS dosyasını PDF'ye nasıl dönüştürebileceğinizi adım adım anlatacağız. Sağlanan C# kaynak kodunu ayrıntılarıyla anlatacağız ve bunu kendi projelerinizde nasıl uygulayacağınızı göstereceğiz. Bu eğitimin sonunda XPS dosyalarını kolayca PDF belgelerine dönüştürebileceksiniz.

## 1. Adım: Belge Dizinini Ayarlayın
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```
 Yer değiştirmek`"YOUR DOCUMENTS DIRECTORY"` dosyalarınızı kaydettiğiniz yolla.

## Adım 2: XPS Yükleme Seçeneklerini Kullanarak LoadOptions Nesnesini Örneklendirin
```csharp
Aspose.Pdf.LoadOptions options = new XpsLoadOptions();
```
XPS yükleme seçeneklerini kullanarak LoadOptions nesnesinin bir örneğini oluşturun.

## Adım 3: Belge Nesnesini Oluşturun
```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "XPSToPDF.xps", options);
```
Giriş XPS dosyasını ve yükleme seçeneklerini belirten bir Belge nesnesi oluşturun.

## Adım 4: Ortaya Çıkan PDF Belgesini Kaydedin
```csharp
document.Save(dataDir + "XPSToPDF_out.pdf");
```
Ortaya çıkan PDF belgesini belirtilen dizine kaydedin.

### Aspose.PDF for .NET kullanarak XPS'den PDF'ye dönüştürme için örnek kaynak kodu

```csharp
try
{
	
	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	//XPS yükleme seçeneğini kullanarak LoadOption nesnesini örneklendirin
	Aspose.Pdf.LoadOptions options = new XpsLoadOptions();

	// Belge nesnesi oluştur
	Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "XPSToPDF.xps", options);

	// Ortaya çıkan PDF belgesini kaydedin
	document.Save(dataDir + "XPSToPDF_out.pdf");
	
}
catch(Exception ex)
   
{
	Console.WriteLine(ex.Message);
}
```

## Çözüm
Bu eğitimde, XPS dosyasını Aspose.PDF for .NET kütüphanesini kullanarak PDF'ye nasıl dönüştüreceğimizi öğrendik. Verilen adımları takip ederek bu dönüşümü kendi uygulamalarınızda kolaylıkla gerçekleştirebilirsiniz. XPS dosyalarını PDF'ye dönüştürürken doğru ve profesyonel sonuçlar elde edin.

### SSS'ler

#### S: XPS nedir ve onu neden PDF'ye dönüştürmek isteyeyim?

C: XPS (XML Kağıt Belirtimi), Microsoft tarafından geliştirilen sabit düzende bir belge formatıdır. XPS'yi PDF'ye dönüştürmek, belgeyi daha erişilebilir ve geniş çapta uyumlu hale getirmenize olanak tanır; çünkü PDF, farklı platformlarda ve cihazlarda evrensel olarak desteklenen bir formattır.

#### S: Aspose.PDF kütüphanesi XPS'in yanı sıra diğer dosya formatlarını da destekliyor mu?

C: Evet, Aspose.PDF for .NET dönüştürme için HTML, EPUB, SVG, XML ve daha fazlası gibi diğer çeşitli dosya formatlarını destekler. Ayrıca PDF belgelerini programlı olarak oluşturmanıza ve değiştirmenize olanak tanır.

#### S: Sayfa boyutunu, kenar boşluklarını veya diğer seçenekleri ayarlamak gibi PDF dönüştürme sürecini özelleştirebilir miyim?

C: Evet, Aspose.PDF for .NET'i kullanarak PDF dönüştürme sürecini özelleştirebilirsiniz. Kitaplık, özel gereksinimlerinizi karşılamak amacıyla sayfa boyutunu, kenar boşluklarını, görüntü sıkıştırmayı, yazı tipi yerleştirmeyi ve PDF ile ilgili diğer ayarları kontrol etmek için çok çeşitli seçenekler sunar.

#### S: Aspose.PDF for .NET'in deneme sürümü mevcut mu?

C: Evet, Aspose.PDF for .NET'in deneme sürümünü resmi Aspose web sitesinden indirip deneyebilirsiniz. Deneme sürümü, satın alma işlemi yapmadan önce kütüphanenin özelliklerini keşfetmenize olanak tanır.

#### S: Birden fazla XPS dosyasını toplu işlemle PDF'ye dönüştürebilir miyim?

C: Evet, bir döngü uygulayarak veya XPS dosyaları listesini yineleyerek ve sağlanan kodu kullanarak her dosyayı PDF'ye dönüştürerek birden fazla XPS dosyasını toplu işlemle PDF'ye dönüştürebilirsiniz.