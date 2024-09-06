---
title: PDF Dosyasının Altbilgisindeki Metin
linktitle: PDF Dosyasının Altbilgisindeki Metin
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF dosyasının altbilgisine metin eklemeyi öğrenin.
type: docs
weight: 180
url: /tr/net/programming-with-stamps-and-watermarks/text-in-footer/
---
Bu eğitimde, .NET için Aspose.PDF kullanarak PDF dosyasının altbilgisine nasıl metin ekleneceğini öğreneceğiz. Aşağıdaki adımları izleyin:

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
Document pdfDocument = new Document(dataDir + "TextinFooter.pdf");
```

"BELGELERİNİZ DİZİNİ" ifadesini belgeler dizininizin gerçek yoluyla değiştirdiğinizden emin olun.

## Adım 4: Altbilgi metni oluşturun

Alt bilgiye eklemek istediğiniz metinle yeni bir metin damgası oluşturun:

```csharp
TextStamp textStamp = new TextStamp("footer text");
```

Metnin alt kenar boşluğu, yatay hizalama, dikey hizalama gibi özelliklerini değiştirerek metni özelleştirebilirsiniz.

## Adım 5: Tüm sayfalara altbilgi metni ekleyin

PDF belgesinin tüm sayfalarını inceleyin ve alt bilgiye metin damgasını ekleyin:

```csharp
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(textStamp);
}
```

## Adım 6: PDF Belgesini Kaydetme

Altbilgi metni tüm sayfalara eklendikten sonra güncellenmiş PDF belgesini kaydedin:

```csharp
dataDir = dataDir + "TextinFooter_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText in footer added successfully.\nFile saved at: " + dataDir);
```

"BELGELERİNİZ DİZİNİ" ifadesini PDF belgenizi kaydetmek istediğiniz dizinin gerçek yoluyla değiştirdiğinizden emin olun.

### .NET için Aspose.PDF kullanılarak Textin Footer için örnek kaynak kodu 
```csharp

// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi aç
Document pdfDocument = new Document(dataDir+ "TextinFooter.pdf");

// Altbilgi oluştur
TextStamp textStamp = new TextStamp("Footer Text");

// Damganın özelliklerini ayarla
textStamp.BottomMargin = 10;
textStamp.HorizontalAlignment = HorizontalAlignment.Center;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Tüm sayfalara altbilgi ekle
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(textStamp);
}
dataDir = dataDir + "TextinFooter_out.pdf";

// Güncellenen PDF dosyasını kaydet
pdfDocument.Save(dataDir);
Console.WriteLine("\nText in footer added successfully.\nFile saved at " + dataDir);

```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesinin alt bilgisine metin eklemeyi öğrendiniz. Artık PDF belgelerinize ek metin ekleyerek alt bilgilerinizi özelleştirebilirsiniz.

### PDF dosyasının altbilgisindeki metin için SSS

#### S: PDF belgesinin alt bilgisine metin eklemenin amacı nedir?

A: Bir PDF belgesinin alt bilgisine metin eklemek, telif hakkı bildirimleri, sayfa numaraları, belge sürümü veya her sayfanın altında tutarlı bir şekilde görünmesini istediğiniz diğer metinler gibi önemli bilgileri eklemenize olanak tanır.

#### S: Sağlanan C# kaynak kodu, bir PDF belgesinin altbilgisine metin eklemeyi nasıl başarıyor?

A: Kod, mevcut bir PDF belgesini açma, istenen alt bilgi metniyle bir metin damgası oluşturma, metin özelliklerini özelleştirme, metin damgasını tüm sayfalara ekleme ve son olarak güncellenen PDF belgesini eklenen alt bilgi metniyle kaydetme sürecini göstermektedir.

#### S: Altbilgi metninin görünümünü, yazı tipini, boyutunu, rengini ve hizalamasını değiştirebilir miyim?

 A: Evet, altbilgi metninin görünümünü, altbilginin özelliklerini değiştirerek özelleştirebilirsiniz.`TextStamp` nesne. Kod örneği, alt kenar boşluğu, yatay hizalama ve dikey hizalama gibi özellikleri ayarlamayı içerir. Ayrıca yazı tipini, boyutunu, rengini ve diğer metinle ilgili özellikleri de ayarlayabilirsiniz.

#### S: Her sayfanın alt bilgisine farklı metin eklemek mümkün mü?

 A: Evet, ayrı bir metin oluşturarak her sayfanın alt bilgisine farklı metin ekleyebilirsiniz.`TextStamp` Farklı metin içeriğine veya özelliklere sahip nesneler ve daha sonra ihtiyaç duyulduğunda belirli sayfalara ekleme.

#### S: PDF belgesinin her sayfasında alt bilgi metninin tutarlı bir şekilde görünmesini nasıl sağlayabilirim?

A: PDF belgesinin tüm sayfalarını dolaşan bir döngü kullanarak ve her sayfaya aynı metin damgasını ekleyerek, alt bilgi metninin her sayfada tutarlı bir şekilde görünmesini sağlarsınız.

#### S: Birden fazla metin satırı ekleyebilir miyim veya altbilgi metnini satır sonlarıyla biçimlendirebilir miyim?

 A: Evet, metin dizesine satır sonları ekleyerek alt bilgiye birden fazla metin satırı ekleyebilirsiniz. Örneğin, kaçış dizisini kullanabilirsiniz`\n` Metinde satır sonunu belirtmek için.

#### S: Aynı PDF belgesinin üst bilgi ve alt bilgisine farklı içerik eklemek istersem ne olur?

A: Başlık ve altbilgi bölümlerine farklı içerik eklemek için her iki bölüm için de benzer adımları izlersiniz. Kod, altbilgiye metin eklemeyi gösterir; başlığa metin eklemek için benzer bir yaklaşım kullanabilirsiniz.

#### S: Bu yaklaşımı kullanarak altbilgi metninin yanına resim veya başka öğeler eklemek mümkün müdür?

A: Sağlanan kod özellikle alt bilgiye metin eklemeyi gösterse de, Aspose.PDF kütüphanesini kullanarak alt bilgi bölümüne resim, çizgi, şekil veya başka içerikler gibi diğer öğeleri eklemek için yaklaşımı genişletebilirsiniz.