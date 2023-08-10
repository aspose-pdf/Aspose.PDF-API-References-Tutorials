---
title: XPS'den PDF'ye
linktitle: XPS'den PDF'ye
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile XPS dosyasını PDF'ye dönüştürmek için adım adım kılavuz.
type: docs
weight: 350
url: /tr/net/document-conversion/xps-to-pdf/
---
Bu eğitimde, adım adım Aspose.PDF library for .NET kullanarak XPS dosyasını PDF'ye nasıl dönüştüreceğinizi göstereceğiz. Sağlanan C# kaynak kodunu detaylandıracağız ve bunu kendi projelerinize nasıl uygulayacağınızı göstereceğiz. Bu eğitimin sonunda, XPS dosyalarını kolayca PDF belgelerine dönüştürebileceksiniz.

## 1. Adım: Belgeler Dizinini Ayarlayın
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```
 Yer değiştirmek`"YOUR DOCUMENTS DIRECTORY"` dosyalarınızı kaydettiğiniz yolla.

## 2. Adım: XPS Yükleme Seçeneklerini Kullanarak LoadOptions Nesnesini Başlatın
```csharp
Aspose.Pdf.LoadOptions options = new XpsLoadOptions();
```
XPS yükleme seçeneklerini kullanarak LoadOptions nesnesinin bir örneğini oluşturun.

## 3. Adım: Belge Nesnesini Oluşturun
```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "XPSToPDF.xps", options);
```
Giriş XPS dosyasını ve yükleme seçeneklerini belirten bir Belge nesnesi oluşturun.

## 4. Adım: Elde Edilen PDF Belgesini Kaydedin
```csharp
document.Save(dataDir + "XPSToPDF_out.pdf");
```
Ortaya çıkan PDF belgesini belirtilen dizine kaydedin.

### Aspose.PDF for .NET kullanarak XPS'den PDF'e örnek kaynak kodu

```csharp
try
{
	
	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	//XPS yükleme seçeneğini kullanarak LoadOption nesnesini oluşturun
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
Bu eğitimde, Aspose.PDF library for .NET kullanarak XPS dosyasını PDF'ye dönüştürmeyi öğrendik. Verilen adımları takip ederek bu dönüşümü kendi uygulamalarınızda kolayca gerçekleştirebilirsiniz. XPS dosyalarını PDF'ye dönüştürürken doğru ve profesyonel sonuçlar alın.

### SSS

#### S: XPS nedir ve neden onu PDF'ye dönüştürmek isteyeyim?

Y: XPS (XML Kağıt Spesifikasyonu), Microsoft tarafından geliştirilen sabit yerleşimli bir belge biçimidir. PDF, farklı platformlarda ve cihazlarda evrensel olarak desteklenen bir biçim olduğundan, XPS'yi PDF'ye dönüştürmek, belgeyi daha erişilebilir ve geniş çapta uyumlu hale getirmenize olanak tanır.

#### S: Aspose.PDF kütüphanesi XPS dışında başka dosya formatlarını destekliyor mu?

C: Evet, Aspose.PDF for .NET, dönüştürme için HTML, EPUB, SVG, XML ve daha fazlası gibi diğer çeşitli dosya formatlarını destekler. Ayrıca, PDF belgelerini programlı olarak oluşturmanıza ve değiştirmenize olanak tanır.

#### S: Sayfa boyutu, kenar boşlukları veya diğer seçenekler gibi PDF dönüştürme sürecini özelleştirebilir miyim?

C: Evet, Aspose.PDF for .NET kullanarak PDF dönüştürme işlemini özelleştirebilirsiniz. Kitaplık, özel gereksinimlerinizi karşılamak için sayfa boyutunu, kenar boşluklarını, görüntü sıkıştırmayı, yazı tipi gömmeyi ve PDF ile ilgili diğer ayarları kontrol etmek için çok çeşitli seçenekler sunar.

#### S: Test için Aspose.PDF for .NET'in deneme sürümü var mı?

C: Evet, resmi Aspose web sitesinden Aspose.PDF for .NET'in deneme sürümünü indirebilir ve deneyebilirsiniz. Deneme sürümü, bir satın alma işlemi yapmadan önce kitaplığın özelliklerini keşfetmenizi sağlar.

#### S: Birden çok XPS dosyasını bir toplu işlemde PDF'ye dönüştürebilir miyim?

C: Evet, bir döngü uygulayarak veya XPS dosyaları listesini yineleyerek ve sağlanan kodu kullanarak her dosyayı PDF'ye dönüştürerek birden çok XPS dosyasını bir toplu işlemde PDF'ye dönüştürebilirsiniz.