---
title: PDF Dosyasının Başlığında Metin
linktitle: PDF Dosyasının Başlığında Metin
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile PDF dosyasının başlığına nasıl metin ekleyeceğinizi öğrenin.
type: docs
weight: 190
url: /tr/net/programming-with-stamps-and-watermarks/text-in-header/
---
Bu derste Aspose.PDF for .NET kullanarak PDF dosyasının başlığına nasıl metin ekleneceğini öğreneceğiz. Aşağıdaki adımları takip et:

## Adım 1: Proje hazırlama

Aspose.PDF for .NET'i yüklediğinizden ve bir C# projesi oluşturduğunuzdan emin olun.

## 2. Adım: Ad alanlarını içe aktarma

Aşağıdaki ad alanlarını C# kaynak dosyanıza ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 3. Adım: Belgeyi açma

Sağlanan yolu kullanarak mevcut PDF belgesini açın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document pdfDocument = new Document(dataDir + "TextinHeader.pdf");
```

"BELGELERİNİZ DİZİNİ"ni belge dizininizin gerçek yolu ile değiştirdiğinizden emin olun.

## Adım 4: Başlık Metni Oluşturma

Başlığa eklemek istediğiniz metni içeren yeni bir metin damgası oluşturun:

```csharp
TextStamp textStamp = new TextStamp("Header text");
```

Üst kenar boşluğu, yatay hizalama ve dikey hizalama gibi özelliklerini değiştirerek metni özelleştirebilirsiniz.

## 5. Adım: Tüm sayfalara başlık metni ekleyin

PDF belgesinin tüm sayfalarını inceleyin ve başlığa metin damgasını ekleyin:

```csharp
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(textStamp);
}
```

## Adım 6: PDF Belgesini Kaydetme

Başlık metni tüm sayfalara eklendikten sonra güncellenen PDF belgesini kaydedin:

```csharp
pdfDocument.Save(dataDir + "TextinHeader_out.pdf");
Console.WriteLine("\nText in header added successfully.\nFile saved at: " + dataDir);
```

"BELGELERİNİZ DİZİNİ"ni, PDF belgesini kaydetmek istediğiniz dizinin gerçek yolu ile değiştirdiğinizden emin olun.

### Aspose.PDF for .NET kullanan Textin Başlığı için örnek kaynak kodu 
```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi aç
Document pdfDocument = new Document(dataDir+ "TextinHeader.pdf");

// Başlık oluştur
TextStamp textStamp = new TextStamp("Header Text");

// Damganın özelliklerini ayarlama
textStamp.TopMargin = 10;
textStamp.HorizontalAlignment = HorizontalAlignment.Center;
textStamp.VerticalAlignment = VerticalAlignment.Top;

// Tüm sayfalara başlık ekleyin
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(textStamp);
}

// Güncellenen belgeyi kaydet
pdfDocument.Save(dataDir+ "TextinHeader_out.pdf");
Console.WriteLine("\nText in header added successfully.\nFile saved at " + dataDir);

```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesinin başlığına nasıl metin ekleyeceğinizi öğrendiniz. Artık PDF belgelerinize ek metin ekleyerek başlıklarınızı özelleştirebilirsiniz.

### PDF dosyasının başlığındaki metinler için SSS

#### S: Bir PDF belgesinin başlığına metin eklemenin amacı nedir?

C: Bir PDF belgesinin başlığına metin eklemek, başlıklar, belge adları, tarihler veya her sayfanın üst kısmında tutarlı bir şekilde görünmesini istediğiniz diğer metinler gibi önemli bilgileri eklemenize olanak tanır.

#### S: Sağlanan C# kaynak kodu, bir PDF belgesinin başlığına metin eklenmesini nasıl başarır?

C: Kod, mevcut bir PDF belgesini açma, istenen başlık metniyle bir metin damgası oluşturma, metin özelliklerini özelleştirme, metin damgasını tüm sayfalara ekleme ve son olarak güncellenen PDF belgesini eklenen başlık metniyle kaydetme sürecini gösterir.

#### S: Başlık metninin yazı tipi, boyutu, rengi ve hizalaması gibi görünümünü değiştirebilir miyim?

 C: Evet, başlık metninin görünümünü, başlık metninin özelliklerini değiştirerek özelleştirebilirsiniz.`TextStamp`nesne. Kod örneği, üst kenar boşluğu, yatay hizalama ve dikey hizalama gibi özelliklerin ayarlanmasını içerir. Ayrıca yazı tipini, boyutunu, rengini ve metinle ilgili diğer özellikleri de ayarlayabilirsiniz.

#### S: Her sayfanın başlığına farklı metin eklemek mümkün mü?

 C: Evet, her sayfanın başlığına ayrı metinler oluşturarak farklı metinler ekleyebilirsiniz.`TextStamp` farklı metin içeriğine veya özelliklere sahip nesneler oluşturma ve ardından bunları gerektiğinde belirli sayfalara ekleme.

#### S: Başlık metninin PDF belgesinin her sayfasında tutarlı bir şekilde görünmesini nasıl sağlayabilirim?

C: PDF belgesinin tüm sayfaları boyunca yinelenen bir döngü kullanarak ve her sayfaya aynı metin damgasını ekleyerek, başlık metninin her sayfada tutarlı bir şekilde görünmesini sağlarsınız.

#### S: Birden fazla metin satırı ekleyebilir miyim veya başlık metnini satır sonlarıyla biçimlendirebilir miyim?

 C: Evet, metin dizesine satır sonları ekleyerek başlığa birden fazla metin satırı ekleyebilirsiniz. Örneğin kaçış sırasını kullanabilirsiniz`\n` Metinde satır sonunu belirtmek için.

#### S: Aynı PDF belgesinin üstbilgisine ve altbilgisine farklı içerik eklemek istersem ne olur?

C: Üstbilgi ve altbilgi bölümlerine farklı içerik eklemek için her iki bölüm için de benzer adımları izleyeceksiniz. Kod, başlığa metin eklemeyi gösterir; altbilgiye metin eklemek için benzer bir yaklaşım kullanabilirsiniz.

#### S: Bu yaklaşımı kullanarak başlık metninin yanına resim veya başka öğeler eklemek mümkün müdür?

C: Sağlanan kod özellikle başlığa metin eklemeyi gösterse de, Aspose.PDF kütüphanesini kullanarak yaklaşımı resimler, çizgiler, şekiller veya başka herhangi bir içerik gibi diğer öğeleri başlık bölümüne ekleyecek şekilde genişletebilirsiniz.
