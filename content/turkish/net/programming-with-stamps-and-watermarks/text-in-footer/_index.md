---
title: PDF Dosyasının Alt Bilgisindeki Metin
linktitle: PDF Dosyasının Alt Bilgisindeki Metin
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile PDF dosyasının alt bilgisine metin eklemeyi öğrenin.
type: docs
weight: 180
url: /tr/net/programming-with-stamps-and-watermarks/text-in-footer/
---
Bu derste Aspose.PDF for .NET kullanarak PDF dosyasının altbilgisine nasıl metin ekleneceğini öğreneceğiz. Aşağıdaki adımları takip et:

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
Document pdfDocument = new Document(dataDir + "TextinFooter.pdf");
```

"BELGELERİNİZ DİZİNİ"ni belge dizininizin gerçek yolu ile değiştirdiğinizden emin olun.

## 4. Adım: Altbilgi metni oluşturun

Alt bilgiye eklemek istediğiniz metni içeren yeni bir metin damgası oluşturun:

```csharp
TextStamp textStamp = new TextStamp("footer text");
```

Alt kenar boşluğu, yatay hizalama ve dikey hizalama gibi özelliklerini değiştirerek metni özelleştirebilirsiniz.

## 5. Adım: Tüm sayfalara altbilgi metni ekleyin

PDF belgesinin tüm sayfalarını inceleyin ve altbilgiye metin damgasını ekleyin:

```csharp
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(textStamp);
}
```

## Adım 6: PDF Belgesini Kaydetme

Alt bilgi metni tüm sayfalara eklendikten sonra güncellenen PDF belgesini kaydedin:

```csharp
dataDir = dataDir + "TextinFooter_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText in footer added successfully.\nFile saved at: " + dataDir);
```

"BELGELERİNİZ DİZİNİ"ni, PDF belgesini kaydetmek istediğiniz dizinin gerçek yolu ile değiştirdiğinizden emin olun.

### Aspose.PDF for .NET kullanan Metin Alt Bilgisi için örnek kaynak kodu 
```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi aç
Document pdfDocument = new Document(dataDir+ "TextinFooter.pdf");

// Altbilgi oluştur
TextStamp textStamp = new TextStamp("Footer Text");

// Damganın özelliklerini ayarlama
textStamp.BottomMargin = 10;
textStamp.HorizontalAlignment = HorizontalAlignment.Center;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Tüm sayfalara altbilgi ekleyin
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

### PDF dosyasının altbilgisindeki metinler için SSS

#### S: Bir PDF belgesinin altbilgisine metin eklemenin amacı nedir?

C: Bir PDF belgesinin alt bilgisine metin eklemek, telif hakkı bildirimleri, sayfa numaraları, belge sürümü gibi önemli bilgileri veya her sayfanın altında tutarlı bir şekilde görünmesini istediğiniz diğer metinleri eklemenize olanak tanır.

#### S: Sağlanan C# kaynak kodu, bir PDF belgesinin altbilgisine metin eklenmesini nasıl başarır?

C: Kod, mevcut bir PDF belgesini açma, istenen altbilgi metniyle bir metin damgası oluşturma, metin özelliklerini özelleştirme, metin damgasını tüm sayfalara ekleme ve son olarak güncellenmiş PDF belgesini eklenen altbilgi metniyle kaydetme sürecini gösterir.

#### S: Alt bilgi metninin yazı tipi, boyutu, rengi ve hizalaması gibi görünümünü değiştirebilir miyim?

 C: Evet, altbilgi metninin görünümünü, altbilgi metninin özelliklerini değiştirerek özelleştirebilirsiniz.`TextStamp` nesne. Kod örneği, alt kenar boşluğu, yatay hizalama ve dikey hizalama gibi özelliklerin ayarlanmasını içerir. Ayrıca yazı tipini, boyutunu, rengini ve metinle ilgili diğer özellikleri de ayarlayabilirsiniz.

#### S: Her sayfanın alt bilgisine farklı metin eklemek mümkün mü?

 C: Evet, her sayfanın altbilgisine ayrı metinler oluşturarak farklı metinler ekleyebilirsiniz.`TextStamp` farklı metin içeriğine veya özelliklere sahip nesneler oluşturma ve ardından bunları gerektiğinde belirli sayfalara ekleme.

#### S: Altbilgi metninin PDF belgesinin her sayfasında tutarlı bir şekilde görünmesini nasıl sağlayabilirim?

C: PDF belgesinin tüm sayfaları boyunca yinelenen bir döngü kullanarak ve her sayfaya aynı metin damgasını ekleyerek, alt bilgi metninin her sayfada tutarlı bir şekilde görünmesini sağlarsınız.

#### S: Birden fazla metin satırı ekleyebilir miyim veya alt bilgi metnini satır sonlarıyla biçimlendirebilir miyim?

 C: Evet, metin dizesine satır sonları ekleyerek alt bilgiye birden fazla metin satırı ekleyebilirsiniz. Örneğin kaçış sırasını kullanabilirsiniz`\n` Metinde satır sonunu belirtmek için.

#### S: Aynı PDF belgesinin üstbilgisine ve altbilgisine farklı içerik eklemek istersem ne olur?

C: Üstbilgi ve altbilgi bölümlerine farklı içerik eklemek için her iki bölüm için de benzer adımları izleyeceksiniz. Kod, altbilgiye metin eklemeyi gösterir; Başlığa metin eklemek için benzer bir yaklaşım kullanabilirsiniz.

#### S: Bu yaklaşımı kullanarak alt bilgi metninin yanına resim veya başka öğeler eklemek mümkün müdür?

C: Sağlanan kod özellikle altbilgiye metin eklemeyi gösterse de, Aspose.PDF kütüphanesini kullanarak yaklaşımı resimler, çizgiler, şekiller veya diğer herhangi bir içerik gibi diğer öğeleri altbilgi bölümüne ekleyecek şekilde genişletebilirsiniz.