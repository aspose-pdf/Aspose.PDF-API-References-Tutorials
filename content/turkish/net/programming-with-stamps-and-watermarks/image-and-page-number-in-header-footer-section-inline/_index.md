---
title: Üstbilgi Altbilgi Bölümünde Resim ve Sayfa Numarası Satır İçi
linktitle: Üstbilgi Altbilgi Bölümünde Resim ve Sayfa Numarası Satır İçi
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım kılavuzla Aspose.PDF for .NET'i kullanarak PDF'nin başlık bölümüne satır içi resim ve sayfa numarasının nasıl ekleneceğini öğrenin.
type: docs
weight: 120
url: /tr/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
## giriiş

.NET için Aspose.PDF, PDF dosyalarını düzenlemek ve oluşturmak için kapsamlı yetenekler sağlayan güçlü bir araçtır. İster resim eklemeniz, ister başlıkları ve altbilgileri özelleştirmeniz veya metni yönetmeniz gereksin, Aspose.PDF sizin için her şeyi yapar. Bu eğitimde, bir PDF belgesinin başlığına veya altbilgisine satır içi bir resim ve sayfa numarası eklemeyi keşfedeceğiz. Hemen başlayalım ve süreci adım adım inceleyelim.

## Ön koşullar

Koda geçmeden önce, takip edebilmeniz için her şeyin yerinde olduğundan emin olalım:

-  Aspose.PDF for .NET: En son sürümü şu adresten indirin:[Aspose PDF İndirme Sayfası](https://releases.aspose.com/pdf/net/).
- Geliştirme Ortamı: Visual Studio gibi bir C# IDE'sine ihtiyacınız olacak.
-  Lisans: Henüz bir lisansınız yoksa, bir lisans alabilirsiniz.[burada geçici lisans](https://purchase.aspose.com/temporary-license/) veya tam bir tane satın alın[Aspose mağazası](https://purchase.aspose.com/buy).

Artık ön koşullar hazır olduğuna göre, başlayalım.

## Paketleri İçe Aktar

Kodlamaya başlamadan önce gerekli ad alanlarını içe aktardığınızdan emin olun:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Bu paketler PDF dosyalarıyla çalışmanıza ve metin düzenlemenize olanak tanır.

## Adım 1: Belge Dizinini Ayarlayın

Yapmamız gereken ilk şey PDF dosyamızın kaydedileceği dizinin yolunu tanımlamaktır. Bu yol projenizin klasörüne veya makinenizdeki herhangi bir konuma göre özelleştirilebilir.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Bu değişken, belgenizin depolanacağı konumu tutar. Değiştir`"YOUR DOCUMENT DIRECTORY"` gerçek yol ile.

## Adım 2: PDF Belgesini Örneklendirin

 Bu adımda, yeni bir örnek oluşturuyoruz`Aspose.Pdf.Document` nesne. Bu nesne PDF dosyanızın omurgasını oluşturacaktır.

```csharp
// Boş oluşturucusunu çağırarak bir Belge nesnesi örneği oluşturun
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

Burada, daha sonra içerikle doldurabileceğimiz boş bir PDF dosyası oluşturuyoruz.

## Adım 3: PDF'ye bir Sayfa Ekleyin

PDF'inizin başlıklar, altbilgiler ve içerik ekleyebileceğiniz en az bir sayfaya ihtiyacı var. Belgemize boş bir sayfa ekleyelim.

```csharp
// Pdf nesnesinde bir sayfa oluşturun
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

 Arayarak`pdf1.Pages.Add()`belgeye üst bilgi ve alt bilgi özelleştirmesine hazır yeni bir sayfa eklenir.

## Adım 4: Başlığı Oluşturun ve Ayarlayın

Şimdi belge için başlığı oluşturma zamanı. Metni, resmi ve sayfa numarasını buraya ekleyeceğiz.

```csharp
// Belgenin Başlık Bölümünü Oluştur
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();
// PDF dosyası için başlığı ayarlayın
page.Header = header;
```

 Biz bir tane yaratıyoruz`HeaderFooter` nesneyi seçin ve onu şuraya atayın:`Header` Sayfanın özelliği, başlığa eklediğimiz her şeyin sayfanın en üstünde görünmesini sağlamaktır.

## Adım 5: Başlığa Satır İçi Metin Ekleyin

 Metin eklemek, bir metin oluşturmak kadar basittir.`TextFragment` ve özelliklerini belirterek. Başlığımıza biraz renkli metin ekleyelim.

```csharp
// Bir Metin nesnesi oluşturun
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");
// Rengi belirtin
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;
```

 Bu adımda bir tane oluşturuyoruz`TextFragment` "Aspose.Pdf, tarafından sağlam bir bileşendir" içeriğiyle ve rengini mavi olarak ayarlayın.`IsInLineParagraph` özelliği metnin satır içi olmasını sağlar, yani diğer öğelerle (görüntü ve ek metin gibi) aynı satırda görünür.

## Adım 6: Başlığa Satır İçi Bir Resim Ekleyin

Başlığınızı görsel olarak çekici hale getirmek için, metinle birlikte satır içi bir resim ekleyebilirsiniz. Bu, şirket logonuz veya başka bir grafik olabilir.

```csharp
// Bölümde bir resim nesnesi oluşturun
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
// Görüntü dosyasının yolunu ayarlayın
image1.File = dataDir + "aspose-logo.jpg";
// Resim genişliğini ayarlayın Bilgi
image1.FixWidth = 50;
image1.FixHeight = 20;
// seg1'in InlineParagraph'ının bir resim olduğunu belirtin.
image1.IsInLineParagraph = true;
```

 Burada, bir resim oluşturarak başlığa bir resim ekliyoruz`Image` nesne, yolunu ayarlama ve genişlik ve yüksekliği ayarlama.`IsInLineParagraph` resmin metinle hizalanmasını sağlar.

## Adım 7: Başlığı Tamamlamak İçin Ek Satır İçi Metin Ekleyin

Satır içi başlığı tamamlamak için biraz daha metin ekleyelim.

```csharp
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

 Bu bölümde başka bir tane yaratıyoruz`TextFragment` "Pty Ltd." içeriğiyle ve rengini bordo olarak ayarlayın. Hem metin parçaları hem de resim başlığa eklenir.

## Adım 8: PDF'yi kaydedin

Başlığı ayarladıktan sonra PDF'yi kaydetme zamanı geldi.

```csharp
// PDF'yi kaydet
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

 The`Save` yöntemi son PDF dosyasını belirtilen konuma yazar.

## Çözüm

Tebrikler! .NET için Aspose.PDF kullanarak bir PDF belgesinin başlığına başarıyla bir resim ve metin eklediniz. Bu eğitim, bir belge oluşturma, sayfa ekleme, başlık ekleme ve metin ve resim gibi satır içi içerik yerleştirme gibi temel adımlarda size yol gösterdi. Aspose.PDF, ister başlıkları, ister altbilgileri veya karmaşık içerikleri düzenlemek olsun, PDF'lerinizi yönetmeniz için inanılmaz bir esneklik sağlar. 

## SSS

### Başlığa sayfa numarası da ekleyebilir miyim?
 Evet! Sayfa numarasını kullanarak kolayca ekleyebilirsiniz.`TextFragment` sınıf ve gerektiği gibi biçimlendirme. Sadece satır içi içerik olarak başlık bölümüne ekleyin.

### Başlıkta arka plan resmini nasıl ayarlarım?
 Kullanabilirsiniz`BackgroundImage` mülkiyeti`HeaderFooter` Arka plan resmi ayarlamak için sınıf. Ancak, bu satır içi içerik değildir ve tüm başlık alanını kaplayacaktır.

### JPEG dışında başka resim formatları kullanmak mümkün müdür?
Kesinlikle! Aspose.PDF PNG, BMP ve GIF gibi çeşitli resim formatlarını destekler.

### Başlıktaki metnin yazı tipini özelleştirebilir miyim?
 Evet, kullanabilirsiniz`TextState`Metnin yazı tipini, boyutunu ve stilini değiştirme nesnesi.

### Aspose.PDF for .NET'i kullanmak için lisansa ihtiyacım var mı?
 Evet, Aspose.PDF'nin üretim amaçlı kullanımı için bir lisansa ihtiyacı vardır, ancak bir lisansla başlayabilirsiniz.[ücretsiz deneme burada](https://releases.aspose.com/).