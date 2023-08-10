---
title: PDF Dosyasının Altbilgisindeki Metin
linktitle: PDF Dosyasının Altbilgisindeki Metin
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF dosyasının altbilgisine metin eklemeyi öğrenin.
type: docs
weight: 180
url: /tr/net/programming-with-stamps-and-watermarks/text-in-footer/
---
Bu öğreticide, Aspose.PDF for .NET kullanarak PDF dosyasının altbilgisine nasıl metin ekleyeceğimizi öğreneceğiz. Aşağıdaki adımları takip et:

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
Document pdfDocument = new Document(dataDir + "TextinFooter.pdf");
```

"BELGELER DİZİNİNİZİ", belgeler dizininizin gerçek yolu ile değiştirdiğinizden emin olun.

## 4. Adım: Altbilgi metni oluşturun

Altbilgiye eklemek istediğiniz metinle yeni bir metin damgası oluşturun:

```csharp
TextStamp textStamp = new TextStamp("footer text");
```

Alt kenar boşluğu, yatay hizalama ve dikey hizalama gibi özelliklerini değiştirerek metni özelleştirebilirsiniz.

## 5. Adım: Tüm sayfalara altbilgi metni ekleyin

PDF belgesinin tüm sayfalarını gözden geçirin ve metin damgasını alt bilgiye ekleyin:

```csharp
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(textStamp);
}
```

## 6. Adım: PDF Belgesini Kaydetme

Altbilgi metni tüm sayfalara eklendikten sonra, güncellenmiş PDF belgesini kaydedin:

```csharp
dataDir = dataDir + "TextinFooter_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText in footer added successfully.\nFile saved at: " + dataDir);
```

"BELGELER DİZİNİNİZİ", PDF belgesini kaydetmek istediğiniz dizinin gerçek yolu ile değiştirdiğinizden emin olun.

### Aspose.PDF for .NET kullanan Textin Footer için örnek kaynak kodu 
```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi aç
Document pdfDocument = new Document(dataDir+ "TextinFooter.pdf");

// Alt bilgi oluştur
TextStamp textStamp = new TextStamp("Footer Text");

// Damganın özelliklerini ayarlama
textStamp.BottomMargin = 10;
textStamp.HorizontalAlignment = HorizontalAlignment.Center;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Tüm sayfalara alt bilgi ekle
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(textStamp);
}
dataDir = dataDir + "TextinFooter_out.pdf";

// Güncellenmiş PDF dosyasını kaydet
pdfDocument.Save(dataDir);
Console.WriteLine("\nText in footer added successfully.\nFile saved at " + dataDir);

```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesinin altbilgisine nasıl metin ekleyeceğinizi öğrendiniz. Artık PDF belgelerinize ek metin ekleyerek altbilgilerinizi özelleştirebilirsiniz.

### PDF dosyasının alt bilgisindeki metin için SSS

#### S: Bir PDF belgesinin altbilgisine metin eklemenin amacı nedir?

C: Bir PDF belgesinin altbilgisine metin eklemek, telif hakkı bildirimleri, sayfa numaraları, belge sürümü veya her sayfanın altında tutarlı bir şekilde görünmesini istediğiniz diğer metinler gibi önemli bilgileri eklemenize olanak tanır.

#### S: Sağlanan C# kaynak kodu, bir PDF belgesinin altbilgisine metin eklemeyi nasıl başarıyor?

C: Kod, mevcut bir PDF belgesini açma, istenen altbilgi metniyle bir metin damgası oluşturma, metin özelliklerini özelleştirme, tüm sayfalara metin damgası ekleme ve son olarak eklenen altbilgi metniyle güncellenmiş PDF belgesini kaydetme sürecini gösterir.

#### S: Altbilgi metninin yazı tipi, boyutu, rengi ve hizalaması gibi görünümünü değiştirebilir miyim?

 C: Evet, altbilgi metninin görünümünü, altbilgi metninin özelliklerini değiştirerek özelleştirebilirsiniz.`TextStamp` nesne. Kod örneği, alt kenar boşluğu, yatay hizalama ve dikey hizalama gibi ayar özelliklerini içerir. Yazı tipini, boyutunu, rengini ve metinle ilgili diğer özellikleri de ayarlayabilirsiniz.

#### S: Her sayfanın alt bilgisine farklı metin eklemek mümkün mü?

 C: Evet, ayrı ayrı oluşturarak her sayfanın altbilgisine farklı metin ekleyebilirsiniz.`TextStamp` farklı metin içeriğine veya özelliklerine sahip nesneler ve ardından bunları gerektiği gibi belirli sayfalara ekleyin.

#### S: Altbilgi metninin PDF belgesinin her sayfasında tutarlı bir şekilde görünmesini nasıl sağlayabilirim?

C: PDF belgesinin tüm sayfalarında yinelenen bir döngü kullanarak ve her sayfaya aynı metin damgasını ekleyerek, alt bilgi metninin her sayfada tutarlı bir şekilde görünmesini sağlarsınız.

#### S: Birden fazla metin satırı ekleyebilir veya altbilgi metnini satır sonlarıyla biçimlendirebilir miyim?

 C: Evet, metin dizesine satır sonları ekleyerek altbilgiye birden fazla metin satırı ekleyebilirsiniz. Örneğin, kaçış sırasını kullanabilirsiniz.`\n` metinde bir satır sonunu belirtmek için.

#### S: Aynı PDF belgesinin üstbilgisine ve altbilgisine farklı içerik eklemek istersem ne olur?

C: Üstbilgi ve altbilgi bölümlerine farklı içerik eklemek için her iki bölüm için de benzer adımları izleyeceksiniz. Kod, alt bilgiye metin eklemeyi gösterir; başlığa metin eklemek için benzer bir yaklaşım kullanabilirsiniz.

#### S: Bu yaklaşımı kullanarak altbilgi metninin yanına resimler veya başka öğeler eklemek mümkün müdür?

Y: Sağlanan kod özellikle altbilgiye metin eklenmesini gösterse de, Aspose.PDF kitaplığını kullanarak altbilgi bölümüne resimler, çizgiler, şekiller veya başka herhangi bir içerik eklemek için yaklaşımı genişletebilirsiniz.