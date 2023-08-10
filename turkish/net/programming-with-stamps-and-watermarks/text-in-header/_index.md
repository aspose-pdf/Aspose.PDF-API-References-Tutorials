---
title: PDF Dosyasının Başlığında Metin
linktitle: PDF Dosyasının Başlığında Metin
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF dosyasının başlığına nasıl metin ekleyeceğinizi öğrenin.
type: docs
weight: 190
url: /tr/net/programming-with-stamps-and-watermarks/text-in-header/
---
Bu öğreticide, Aspose.PDF for .NET kullanarak PDF dosyasının başlığına nasıl metin ekleyeceğimizi öğreneceğiz. Aşağıdaki adımları takip et:

## 1. Adım: Proje hazırlama

Aspose.PDF for .NET'i kurduğunuzdan ve bir C# projesi oluşturduğunuzdan emin olun.

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

"BELGELER DİZİNİNİZİ", belgeler dizininizin gerçek yolu ile değiştirdiğinizden emin olun.

## 4. Adım: Başlık Metni Oluşturma

Başlığa eklemek istediğiniz metinle yeni bir metin damgası oluşturun:

```csharp
TextStamp textStamp = new TextStamp("Header text");
```

Üst kenar boşluğu, yatay hizalama ve dikey hizalama gibi özelliklerini değiştirerek metni özelleştirebilirsiniz.

## 5. Adım: Tüm sayfalara başlık metni ekleyin

PDF belgesinin tüm sayfalarını gözden geçirin ve başlığa metin damgasını ekleyin:

```csharp
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(textStamp);
}
```

## 6. Adım: PDF Belgesini Kaydetme

Başlık metni tüm sayfalara eklendikten sonra, güncellenmiş PDF belgesini kaydedin:

```csharp
pdfDocument.Save(dataDir + "TextinHeader_out.pdf");
Console.WriteLine("\nText in header added successfully.\nFile saved at: " + dataDir);
```

"BELGELER DİZİNİNİZİ", PDF belgesini kaydetmek istediğiniz dizinin gerçek yolu ile değiştirdiğinizden emin olun.

### Aspose.PDF for .NET kullanan Textin Header için örnek kaynak kodu 
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

// Tüm sayfalara başlık ekle
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

### PDF dosyasının başlığındaki metin için SSS

#### S: Bir PDF belgesinin başlığına metin eklemenin amacı nedir?

C: Bir PDF belgesinin başlığına metin eklemek, başlıklar, belge adları, tarihler gibi önemli bilgileri veya her sayfanın başında tutarlı bir şekilde görünmesini istediğiniz diğer metinleri eklemenize olanak tanır.

#### S: Sağlanan C# kaynak kodu, bir PDF belgesinin başlığına metin eklemeyi nasıl başarıyor?

C: Kod, mevcut bir PDF belgesini açma, istenen başlık metniyle bir metin damgası oluşturma, metin özelliklerini özelleştirme, tüm sayfalara metin damgası ekleme ve son olarak eklenen başlık metniyle güncellenmiş PDF belgesini kaydetme sürecini gösterir.

#### S: Başlık metninin yazı tipi, boyutu, rengi ve hizalaması gibi görünümünü değiştirebilir miyim?

C: Evet, başlık metninin özelliklerini değiştirerek başlık metninin görünümünü özelleştirebilirsiniz.`TextStamp` nesne. Kod örneği, üst kenar boşluğu, yatay hizalama ve dikey hizalama gibi ayar özelliklerini içerir. Yazı tipini, boyutunu, rengini ve metinle ilgili diğer özellikleri de ayarlayabilirsiniz.

#### S: Her sayfanın başlığına farklı bir metin eklemek mümkün mü?

 C: Evet, ayrı ayrı oluşturarak her sayfanın başlığına farklı metin ekleyebilirsiniz.`TextStamp` farklı metin içeriğine veya özelliklerine sahip nesneler ve ardından bunları gerektiği gibi belirli sayfalara ekleyin.

#### S: Başlık metninin PDF belgesinin her sayfasında tutarlı bir şekilde görünmesini nasıl sağlayabilirim?

Y: PDF belgesinin tüm sayfalarında yinelenen bir döngü kullanarak ve her sayfaya aynı metin damgasını ekleyerek, başlık metninin her sayfada tutarlı bir şekilde görünmesini sağlarsınız.

#### S: Birden fazla metin satırı ekleyebilir veya başlık metnini satır sonlarıyla biçimlendirebilir miyim?

 C: Evet, metin dizesine satır sonları ekleyerek başlığa birden fazla metin satırı ekleyebilirsiniz. Örneğin, kaçış sırasını kullanabilirsiniz.`\n` metinde bir satır sonunu belirtmek için.

#### S: Aynı PDF belgesinin üstbilgisine ve altbilgisine farklı içerik eklemek istersem ne olur?

C: Üstbilgi ve altbilgi bölümlerine farklı içerik eklemek için her iki bölüm için de benzer adımları izleyeceksiniz. Kod, başlığa metin eklemeyi gösterir; altbilgiye metin eklemek için benzer bir yaklaşım kullanabilirsiniz.

#### S: Bu yaklaşımı kullanarak başlık metninin yanına resimler veya başka öğeler eklemek mümkün müdür?

Y: Sağlanan kod özellikle başlığa metin eklenmesini gösterse de, Aspose.PDF kitaplığını kullanarak üstbilgi bölümüne resimler, çizgiler, şekiller veya başka herhangi bir içerik gibi diğer öğeleri eklemek için yaklaşımı genişletebilirsiniz.
