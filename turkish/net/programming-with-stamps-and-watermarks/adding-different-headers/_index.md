---
title: PDF Dosyasına Farklı Başlıklar Ekleme
linktitle: PDF Dosyasına Farklı Başlıklar Ekleme
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF dosyasındaki her sayfaya kolayca farklı başlıkları nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 30
url: /tr/net/programming-with-stamps-and-watermarks/adding-different-headers/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak PDF dosyasına nasıl farklı başlıklar ekleyeceğinizi adım adım anlatacağız. PDF dosyasının her sayfasına özel başlıklar eklemek için sağlanan C# kaynak kodunu nasıl kullanacağınızı göstereceğiz.

## 1. Adım: Ortamı ayarlama

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Yüklü bir .NET geliştirme ortamı.
- .NET için Aspose.PDF kitaplığı indirildi ve projenizde referans verildi.

## 2. Adım: PDF belgesini yükleme

İlk adım, mevcut PDF belgesini projenize yüklemektir. İşte nasıl:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Kaynak belgeyi aç
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "AddingDifferentHeaders.pdf");
```

"BELGELER DİZİNİNİZİ", PDF belgenizin bulunduğu dizinin gerçek yolu ile değiştirdiğinizden emin olun.

## 3. Adım: Başlık Arabellekleri Oluşturma

Artık PDF belgesini yüklediğinize göre, eklenecek başlık damgalarını oluşturabilirsiniz. İşte nasıl:

```csharp
// Üç başlık arabelleği oluştur
Aspose.Pdf.TextStamp stamp1 = new Aspose.Pdf.TextStamp("Header 1");
Aspose.Pdf.TextStamp stamp2 = new Aspose.Pdf.TextStamp("Header 2");
Aspose.Pdf.TextStamp stamp3 = new Aspose.Pdf.TextStamp("Header 3");
```

Yukarıdaki kod, belirtilen metni içeren üç yeni başlık arabelleği oluşturur.

## 4. Adım: Başlık arabelleği özelliklerini yapılandırma

Başlık damgalarını PDF belgesine eklemeden önce, her bir damga için hizalama, boyut, renk vb. gibi farklı özellikler yapılandırabilirsiniz. Bunu şu şekilde yapabilirsiniz:

```csharp
// İlk başlık arabelleğini yapılandırın
stamp1.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp1.TextState.FontStyle = FontStyles.Bold;
stamp1.TextState.ForegroundColor = Color.Red;
stamp1.TextState.FontSize = 14;

// İkinci başlık arabelleğinin konfigürasyonu
stamp2.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp2.Zoom = 10;

// Üçüncü başlık arabelleğini yapılandırın
stamp3.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp3.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp3.RotateAngle = 35;
stamp3.TextState.BackgroundColor = Color.Pink;
stamp3.TextState.Font = FontRepository.FindFont("Verdana");
```

Bu özellikleri her başlık arabelleği için gerektiği gibi ayarlayabilirsiniz.

## 5. Adım: PDF'ye Başlık Damgaları Ekleyin

Artık başlık damgaları hazır olduğuna göre, bunları PDF belgesinin belirli her sayfasına ekleyebilirsiniz. İşte nasıl:

```csharp
// Belirli sayfalara başlık arabellekleri ekleyin
doc.Pages[1].AddStamp(stamp1);
doc.Pages[2].AddStamp(stamp2);
doc.Pages[3].AddStamp(stamp3);
```

Yukarıdaki kod, her başlık damgasını PDF belgesinin ilgili sayfasına ekler.

## 6. Adım: Çıktı belgesini kaydedin

Başlık damgalarını ekledikten sonra düzenlenen PDF belgesini kaydedebilirsiniz. İşte nasıl:

```csharp
// Güncellenen belgeyi kaydedin
doc.Save(dataDir);
```

Yukarıdaki kod, düzenlenen PDF belgesini belirtilen dizine kaydeder.

### Aspose.PDF for .NET kullanarak Farklı Başlıklar Eklemek için örnek kaynak kodu 
```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Açık kaynak belgesi
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddingDifferentHeaders.pdf");

// Üç pul oluştur
Aspose.Pdf.TextStamp stamp1 = new Aspose.Pdf.TextStamp("Header 1");
Aspose.Pdf.TextStamp stamp2 = new Aspose.Pdf.TextStamp("Header 2");
Aspose.Pdf.TextStamp stamp3 = new Aspose.Pdf.TextStamp("Header 3");

// Damga hizalamasını ayarlayın (damgayı sayfanın üstüne yerleştirin, yatay olarak ortalayın)
stamp1.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// Yazı tipi stilini Kalın olarak belirtin
stamp1.TextState.FontStyle = FontStyles.Bold;

// Metin ön zemin rengi bilgisini kırmızı olarak ayarlayın
stamp1.TextState.ForegroundColor = Color.Red;

// Yazı tipi boyutunu 14 olarak belirtin
stamp1.TextState.FontSize = 14;

// Şimdi 2. damga nesnesinin dikey hizalamasını Üst olarak ayarlamamız gerekiyor.
stamp2.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

// Damga için yatay hizalama bilgilerini Ortaya hizalanmış olarak ayarlayın
stamp2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// Damga nesnesi için yakınlaştırma faktörünü ayarlayın
stamp2.Zoom = 10;

//3. damga nesnesinin biçimlendirmesini ayarlayın
// Damga nesnesi için Dikey hizalama bilgisini TOP olarak belirtin
stamp3.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

// Damga nesnesi için Yatay hizalama bilgisini Ortaya hizalanmış olarak ayarlayın
stamp3.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// Damga nesnesi için dönüş açısını ayarlayın
stamp3.RotateAngle = 35;

// Damga için arka plan rengi olarak pembeyi ayarla
stamp3.TextState.BackgroundColor = Color.Pink;

// Damga için yazı tipi yüzü bilgisini Verdana olarak değiştirin
stamp3.TextState.Font = FontRepository.FindFont("Verdana");

// İlk kaşe ilk sayfaya eklenir;
doc.Pages[1].AddStamp(stamp1);

// İkinci sayfaya ikinci kaşe eklenir;
doc.Pages[2].AddStamp(stamp2);

// Üçüncü sayfaya üçüncü kaşe eklenmiştir.
doc.Pages[3].AddStamp(stamp3);
dataDir = dataDir + "multiheader_out.pdf";

// Güncellenen belgeyi kaydedin
doc.Save(dataDir);
Console.WriteLine("\nDifferent headers added successfully.\nFile saved at " + dataDir);

```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesinin her sayfasına nasıl farklı başlıklar ekleyeceğinizi öğrendiniz. Artık bu bilgiyi, PDF belgelerinizin başlıklarını özelleştirmek için kendi projelerinize uygulayabilirsiniz.

### PDF dosyasına farklı başlıklar eklemek için SSS

#### S: Aspose.PDF for .NET kullanarak bir PDF dosyasına farklı başlıklar eklemenin amacı nedir?

C: Aspose.PDF for .NET kullanarak bir PDF dosyasına farklı başlıklar eklemek, her sayfanın üst kısmında görüntülenen içeriği özelleştirmenizi sağlar. Bu özellik, bir PDF belgesinin farklı sayfalarında değişiklik gösteren başlıklar, bölüm adları, sayfa numaraları ve diğer bilgileri eklemek için özellikle kullanışlıdır.

#### S: Hizalama, yazı tipi, boyut, renk ve döndürme gibi her başlığın görünümünü özelleştirebilir miyim?

 C: Evet, her başlık damgasının görünümünü tamamen özelleştirebilirsiniz. Sağlanan C# kaynak kodu, çeşitli özelliklerin nasıl ayarlanacağını gösterir.`TextStamp` dikey ve yatay hizalama, yazı tipi stili, yazı tipi boyutu, yazı tipi rengi, arka plan rengi ve döndürme açısı dahil olmak üzere her başlık için nesneler.

#### S: Bir PDF belgesinin aynı sayfasına birden fazla başlık damgası eklemek mümkün müdür?

Y: Sağlanan öğretici, bir PDF belgesinin farklı sayfalarına farklı başlıklar eklemeyi gösterse de, aynı sayfaya birden fazla başlık damgası eklemek için kodu uyarlayabilirsiniz. Aynı bölüm içinde çeşitli başlıkları görüntülemek istiyorsanız bu yararlı olabilir.

#### S: Başlıkların PDF sayfalarının ana içeriğiyle örtüşmemesini nasıl sağlayabilirim?

 A: Üst üste binmeyi önlemek için`VerticalAlignment`, `HorizontalAlignment` ve diğer özellikleri`TextStamp` nesneler. Bu ayarlar, başlıkların sayfada nereye yerleştirileceğini kontrol ederek, ana içeriği engellemeyecek şekilde konumlandırmanıza olanak tanır.

#### S: Farklı sayıda sayfaya sahip mevcut PDF belgelerine başlık eklemek için bu yöntemi kullanabilir miyim?

C: Evet, farklı sayıda sayfaya sahip mevcut PDF belgelerine başlıklar eklemek için sağlanan kaynak kodunu uyarlayabilirsiniz. Kodu, eklemek istediğiniz başlık sayısına uyacak şekilde ayarlayın ve her başlığı istediğiniz sayfayla ilişkilendirin.

#### S: Yalnızca ilk üç sayfaya değil de belirli sayfalara başlık eklemek istersem ne olur?

 Y: Öğretici, açıklama amacıyla ilk üç sayfaya başlık eklemeyi gösterir. İlk üç sayfanın ötesindeki belirli sayfalara başlık eklemek için ilgili sayfa dizinlerine başvurarak ve`TextStamp` her sayfa için nesneler.

#### S: Metin yerine üst bilgi olarak resimleri kullanabilir miyim?

 A: Sağlanan öğretici, metin tabanlı üstbilgiler eklemeye odaklanır. Ancak, kullanarak görüntü tabanlı başlıklar eklemek için benzer bir yaklaşım uygulayabilirsiniz.`ImageStamp` nesneler yerine`TextStamp` nesneler. Bu, oluşturmayı ve yapılandırmayı içerir`ImageStamp` istenen özelliklere sahip nesneler.

#### S: Bir PDF belgesinin her sayfasına farklı alt bilgiler eklemek için bu bilgiyi nasıl uygulayabilirim?

 C: Bu eğitimde gösterilen yaklaşımın aynısı, bir PDF belgesinin her sayfasına farklı alt bilgiler eklemek için uygulanabilir. Başlıklar yerine, oluşturup yapılandırırsınız`TextStamp` veya`ImageStamp` kullanarak bunları her sayfanın altına ekleyin.`AddStamp` yöntem.

#### S: Bir toplu işlemde birden çok PDF belgesine başlık ekleme sürecini otomatikleştirebilir miyim?

C: Evet, bir belge listesi boyunca yinelenen ve her belgeye başlık damgalama işlemi uygulayan bir komut dosyası veya program kullanarak birden fazla PDF belgesine başlık ekleme işlemini otomatikleştirebilirsiniz.