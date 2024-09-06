---
title: PDF Dosyasının Başlığındaki Metin
linktitle: PDF Dosyasının Başlığındaki Metin
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF dosyasının başlığına metin eklemeyi öğrenin.
type: docs
weight: 190
url: /tr/net/programming-with-stamps-and-watermarks/text-in-header/
---
Bu eğitimde, .NET için Aspose.PDF kullanarak PDF dosyasının başlığına nasıl metin ekleneceğini öğreneceğiz. Aşağıdaki adımları izleyin:

## Adım 1: Proje hazırlığı

Aspose.PDF for .NET'i yüklediğinizden ve bir C# projesi oluşturduğunuzdan emin olun.

## Adım 2: Ad alanlarını içe aktarma

Aşağıdaki ad alanlarını C# kaynak dosyanıza ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Adım 3: Belgeyi açma

Mevcut PDF belgesini verilen yolu kullanarak açın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document pdfDocument = new Document(dataDir + "TextinHeader.pdf");
```

"BELGELERİNİZ DİZİNİ" ifadesini belgeler dizininizin gerçek yoluyla değiştirdiğinizden emin olun.

## Adım 4: Başlık Metni Oluşturma

Başlığa eklemek istediğiniz metinle yeni bir metin damgası oluşturun:

```csharp
TextStamp textStamp = new TextStamp("Header text");
```

Metnin üst kenar boşluğu, yatay hizalama, dikey hizalama gibi özelliklerini değiştirerek metni özelleştirebilirsiniz.

## Adım 5: Tüm sayfalara başlık metni ekleyin

PDF belgesinin tüm sayfalarını inceleyin ve başlığa metin damgasını ekleyin:

```csharp
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(textStamp);
}
```

## Adım 6: PDF Belgesini Kaydetme

Başlık metni tüm sayfalara eklendikten sonra güncellenmiş PDF belgesini kaydedin:

```csharp
pdfDocument.Save(dataDir + "TextinHeader_out.pdf");
Console.WriteLine("\nText in header added successfully.\nFile saved at: " + dataDir);
```

"BELGELERİNİZ DİZİNİ" ifadesini PDF belgenizi kaydetmek istediğiniz dizinin gerçek yoluyla değiştirdiğinizden emin olun.

### .NET için Aspose.PDF kullanılarak Textin Başlığı için örnek kaynak kodu 
```csharp

// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi aç
Document pdfDocument = new Document(dataDir+ "TextinHeader.pdf");

// Başlık oluştur
TextStamp textStamp = new TextStamp("Header Text");

// Damganın özelliklerini ayarla
textStamp.TopMargin = 10;
textStamp.HorizontalAlignment = HorizontalAlignment.Center;
textStamp.VerticalAlignment = VerticalAlignment.Top;

// Tüm sayfalara üst bilgi ekle
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(textStamp);
}

// Güncellenen belgeyi kaydet
pdfDocument.Save(dataDir+ "TextinHeader_out.pdf");
Console.WriteLine("\nText in header added successfully.\nFile saved at " + dataDir);

```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesinin başlığına metin eklemeyi öğrendiniz. Artık PDF belgelerinize ek metin ekleyerek başlıklarınızı özelleştirebilirsiniz.

### PDF dosyasının başlığındaki metinle ilgili SSS

#### S: PDF belgesinin başlığına metin eklemenin amacı nedir?

A: PDF belgesinin üst bilgisine metin eklemek, başlıklar, belge adları, tarihler veya her sayfanın en üstünde tutarlı bir şekilde görünmesini istediğiniz diğer metinler gibi önemli bilgileri eklemenize olanak tanır.

#### S: Sağlanan C# kaynak kodu, bir PDF belgesinin başlığına metin eklemeyi nasıl başarıyor?

A: Kod, mevcut bir PDF belgesini açma, istenen başlık metniyle bir metin damgası oluşturma, metin özelliklerini özelleştirme, metin damgasını tüm sayfalara ekleme ve son olarak güncellenen PDF belgesini eklenen başlık metniyle kaydetme sürecini göstermektedir.

#### S: Başlık metninin görünümünü, yazı tipini, boyutunu, rengini ve hizalamasını değiştirebilir miyim?

A: Evet, başlık metninin görünümünü, başlık özelliklerini değiştirerek özelleştirebilirsiniz.`TextStamp` nesne. Kod örneği, üst kenar boşluğu, yatay hizalama ve dikey hizalama gibi özellikleri ayarlamayı içerir. Ayrıca yazı tipini, boyutunu, rengini ve diğer metinle ilgili özellikleri de ayarlayabilirsiniz.

#### S: Her sayfanın başlığına farklı bir metin eklemek mümkün mü?

 A: Evet, ayrı başlıklar oluşturarak her sayfanın başlığına farklı metin ekleyebilirsiniz.`TextStamp` Farklı metin içeriğine veya özelliklere sahip nesneler ve daha sonra ihtiyaç duyulduğunda belirli sayfalara ekleme.

#### S: Başlık metninin PDF belgesinin her sayfasında tutarlı bir şekilde görünmesini nasıl sağlayabilirim?

A: PDF belgesinin tüm sayfalarını dolaşan bir döngü kullanarak ve her sayfaya aynı metin damgasını ekleyerek, başlık metninin her sayfada tutarlı bir şekilde görünmesini sağlarsınız.

#### S: Birden fazla metin satırı ekleyebilir miyim veya başlık metnini satır sonlarıyla biçimlendirebilir miyim?

 A: Evet, metin dizesine satır sonları ekleyerek başlığa birden fazla metin satırı ekleyebilirsiniz. Örneğin, kaçış dizisini kullanabilirsiniz`\n` Metinde satır sonunu belirtmek için.

#### S: Aynı PDF belgesinin üst bilgi ve alt bilgisine farklı içerik eklemek istersem ne olur?

A: Başlık ve altbilgi bölümlerine farklı içerik eklemek için her iki bölüm için de benzer adımları izlersiniz. Kod, başlığa metin eklemeyi gösterir; altbilgiye metin eklemek için benzer bir yaklaşım kullanabilirsiniz.

#### S: Bu yaklaşımı kullanarak başlık metninin yanına resim veya başka öğeler eklemek mümkün müdür?

C: Sağlanan kod özellikle başlığa metin eklemeyi gösterse de, Aspose.PDF kütüphanesini kullanarak başlık bölümüne resim, çizgi, şekil veya başka içerikler gibi diğer öğeleri eklemek için yaklaşımı genişletebilirsiniz.
