---
title: PDF'den XPS'e
linktitle: PDF'den XPS'e
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım kılavuzla Aspose.PDF for .NET kullanarak PDF'yi XPS'e nasıl dönüştüreceğinizi öğrenin. Geliştiriciler ve belge işleme meraklıları için mükemmeldir.
type: docs
weight: 220
url: /tr/net/document-conversion/pdf-to-xps/
---
## giriiş

Günümüzün dijital dünyasında, belgeleri bir formattan diğerine dönüştürme ihtiyacı her zamankinden daha yaygın. İster belge işlemeyi uygulamanıza entegre etmek isteyen bir geliştirici olun, ister dosyaları evrensel olarak kabul görmüş bir formatta paylaşması gereken bir iş profesyoneli olun, PDF dosyalarını XPS'e (XML Kağıt Spesifikasyonu) nasıl dönüştüreceğinizi anlamak inanılmaz derecede faydalı olabilir. Bu eğitimde, .NET için güçlü Aspose.PDF kitaplığını kullanarak PDF'yi XPS'e dönüştürme sürecine dalacağız.

## Ön koşullar

Başlamadan önce, yerine getirmeniz gereken birkaç ön koşul var:

1. Visual Studio: Makinenizde Visual Studio'nun yüklü olduğundan emin olun. .NET kodunuzu burada yazacak ve çalıştıracaksınız.
2. .NET Framework: Örneklerimizde C# kullanacağımız için .NET framework'e aşinalık şarttır.
3.  Aspose.PDF Kütüphanesi: Aspose.PDF kütüphanesinin kurulu olması gerekir. Bunu şuradan indirebilirsiniz:[Aspose PDF for .NET sürümleri sayfası](https://releases.aspose.com/pdf/net/).
4. Temel C# Bilgisi: C# programlamaya dair temel bir anlayışa sahip olmak, örnekleri takip etmenize yardımcı olacaktır.

## Paketleri İçe Aktar

Aspose.PDF'e başlamak için gerekli paketleri projenize aktarmanız gerekir. Bunu şu şekilde yapabilirsiniz:

1. Visual Studio'yu açın: Visual Studio'yu başlatın ve yeni bir proje oluşturun.
2. Referans Ekle: Çözüm Gezgini'nde projenize sağ tıklayın, "NuGet Paketlerini Yönet"i seçin ve "Aspose.PDF"i arayın. Paketi projenize yükleyin.
3. Yönergeleri Kullanma: C# dosyanızın en üstüne aşağıdaki yönergeyi ekleyin:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
```

Artık her şeyi ayarladığımıza göre, dönüşüm sürecini yönetilebilir adımlara bölelim.

## Adım 1: Belge Dizininizi Ayarlayın

Bir PDF'yi XPS'e dönüştürebilmeniz için, PDF dosyanızın bulunduğu dizini belirtmeniz gerekir. Bu önemlidir çünkü programın giriş dosyasını nerede bulacağını bilmesi gerekir.

Bu adımda, belgeler dizininize giden yolu tutan bir dize değişkeni tanımlayacaksınız. Bu yol, PDF dosyanızın konumunu göstermelidir.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` PDF dosyasının bilgisayarınızda saklandığı gerçek yol ile.

## Adım 2: PDF Belgesini Yükleyin

Artık belge dizininiz ayarlandığına göre, bir sonraki adım dönüştürmek istediğiniz PDF belgesini yüklemektir.

 Bir örneğini oluşturacaksınız`Document` Aspose.PDF kütüphanesinden sınıfını seçin ve PDF dosyanızın yolunu oluşturucusuna geçirin. Bu, PDF belgesini belleğe yükleyecektir.

```csharp
// PDF belgesini yükle
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Değiştirdiğinizden emin olun`"input.pdf"` gerçek PDF dosyanızın adıyla.

## Adım 3: XPS Kaydetme Seçeneklerini Oluşturun

 Belgeyi XPS biçiminde kaydetmeden önce, bir örneğini oluşturmanız gerekir`XpsSaveOptions` sınıf. Bu sınıf, belgeyi kaydetmek için çeşitli seçenekler belirtmenize olanak tanır.

 Örnekleme yaparak`XpsSaveOptions`PDF'nin XPS'e nasıl dönüştürüleceğini özelleştirebilirsiniz. Bu temel dönüşüm için varsayılan ayarları kullanabilirsiniz.

```csharp
// XPS Kaydetme seçeneklerini örneklendir
Aspose.Pdf.XpsSaveOptions saveOptions = new Aspose.Pdf.XpsSaveOptions();
```

## Adım 4: Belgeyi XPS Olarak Kaydedin

Son olarak, yüklenen PDF belgesini XPS dosyası olarak kaydetme zamanı geldi. İşte sihir burada gerçekleşiyor!

 Sen arayacaksın`Save` yöntem üzerinde`pdfDocument` nesne, istenen çıktı dosyası adını ve`saveOptions` daha önce yaratmış olduğunuz.

```csharp
// XPS belgesini kaydedin
pdfDocument.Save("PDFToXPS_out.xps", saveOptions);
```

 Bu kod satırı, adında bir XPS dosyası oluşturacaktır.`PDFToXPS_out.xps` proje dizininizde.

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesini XPS formatına başarıyla dönüştürdünüz. Bu basit ama güçlü kütüphane, çeşitli belge işleme görevlerini kolaylıkla halletmenizi sağlar. İster daha iyi uyumluluk için dosyaları dönüştürüyor olun, ister belgeleri farklı bir formatta arşivliyor olun, Aspose.PDF sizin için her şeyi yapar.

## SSS

### XPS formatı nedir?
XPS (XML Kağıt Spesifikasyonu), Microsoft tarafından geliştirilen ve belgelerin düzenini ve görünümünü koruyan bir belge biçimidir.

### Birden fazla PDF dosyasını aynı anda XPS'e dönüştürebilir miyim?
Evet, aynı yöntemi kullanarak bir dizindeki birden fazla PDF dosyası arasında geçiş yapabilir ve her birini XPS'e dönüştürebilirsiniz.

### Aspose.PDF'i kullanmak ücretsiz mi?
 Aspose.PDF ücretsiz deneme sunar, ancak tam işlevsellik için bir lisans satın almanız gerekir. Daha fazla ayrıntıyı şu adreste bulabilirsiniz:[satın alma sayfası](https://purchase.aspose.com/buy).

### Dönüştürme sırasında sorunlarla karşılaşırsam ne olur?
 Aspose topluluğundan yardım isteyebilirsiniz[destek forumu](https://forum.aspose.com/c/pdf/10).

### Aspose.PDF için geçici lisans alabilir miyim?
 Evet, değerlendirme amaçlı olarak geçici bir lisans talebinde bulunabilirsiniz.[geçici lisans sayfası](https://purchase.aspose.com/temporary-license/).