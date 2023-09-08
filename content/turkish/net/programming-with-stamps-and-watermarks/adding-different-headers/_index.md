---
title: PDF Dosyasına Farklı Başlıklar Ekleme
linktitle: PDF Dosyasına Farklı Başlıklar Ekleme
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile PDF dosyasındaki her sayfaya kolayca farklı başlıkları nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 30
url: /tr/net/programming-with-stamps-and-watermarks/adding-different-headers/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak PDF dosyasına farklı başlıkların nasıl ekleneceği konusunda size adım adım yol göstereceğiz. PDF dosyasının her sayfasına özel üstbilgiler eklemek için sağlanan C# kaynak kodunu nasıl kullanacağınızı size göstereceğiz.

## 1. Adım: Ortamı ayarlama

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Kurulu bir .NET geliştirme ortamı.
- .NET için Aspose.PDF kütüphanesini indirip projenizde referans olarak kullanabilirsiniz.

## Adım 2: PDF belgesini yükleme

İlk adım mevcut PDF belgesini projenize yüklemektir. İşte nasıl:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Kaynak belgeyi aç
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "AddingDifferentHeaders.pdf");
```

"BELGELERİNİZ DİZİNİ"ni, PDF belgenizin bulunduğu dizine giden gerçek yolla değiştirdiğinizden emin olun.

## Adım 3: Başlık Arabellekleri Oluşturma

Artık PDF belgesini yüklediğinize göre eklenecek başlık damgalarını oluşturabilirsiniz. İşte nasıl:

```csharp
// Üç başlık arabelleği oluşturun
Aspose.Pdf.TextStamp stamp1 = new Aspose.Pdf.TextStamp("Header 1");
Aspose.Pdf.TextStamp stamp2 = new Aspose.Pdf.TextStamp("Header 2");
Aspose.Pdf.TextStamp stamp3 = new Aspose.Pdf.TextStamp("Header 3");
```

Yukarıdaki kod, belirtilen metni içeren üç yeni başlık arabelleği oluşturur.

## 4. Adım: Başlık arabelleği özelliklerini yapılandırma

Başlık damgalarını PDF belgesine eklemeden önce, her damga için hizalama, boyut, renk vb. gibi farklı özellikleri yapılandırabilirsiniz. Bunu şu şekilde yapabilirsiniz:

```csharp
// İlk başlık arabelleğini yapılandırma
stamp1.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp1.TextState.FontStyle = FontStyles.Bold;
stamp1.TextState.ForegroundColor = Color.Red;
stamp1.TextState.FontSize = 14;

// İkinci başlık arabelleğinin konfigürasyonu
stamp2.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp2.Zoom = 10;

// Üçüncü başlık arabelleğini yapılandır
stamp3.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp3.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp3.RotateAngle = 35;
stamp3.TextState.BackgroundColor = Color.Pink;
stamp3.TextState.Font = FontRepository.FindFont("Verdana");
```

Bu özellikleri her başlık arabelleği için gerektiği gibi ayarlayabilirsiniz.

## Adım 5: PDF'ye Başlık Damgaları Ekleme

Artık başlık damgaları hazır olduğuna göre bunları PDF belgesinin her bir sayfasına ekleyebilirsiniz. İşte nasıl:

```csharp
// Belirli sayfalara başlık arabellekleri ekleme
doc.Pages[1].AddStamp(stamp1);
doc.Pages[2].AddStamp(stamp2);
doc.Pages[3].AddStamp(stamp3);
```

Yukarıdaki kod, her başlık damgasını PDF belgesinin ilgili sayfasına ekler.

## Adım 6: Çıktı belgesini kaydedin

Başlık damgalarını ekledikten sonra düzenlenen PDF belgesini kaydedebilirsiniz. İşte nasıl:

```csharp
// Güncellenen belgeyi kaydet
doc.Save(dataDir);
```

Yukarıdaki kod, düzenlenen PDF belgesini belirtilen dizine kaydeder.

### Aspose.PDF for .NET Kullanarak Farklı Başlıklar Eklemek için örnek kaynak kodu 
```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Açık kaynak belge
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddingDifferentHeaders.pdf");

// Üç damga oluştur
Aspose.Pdf.TextStamp stamp1 = new Aspose.Pdf.TextStamp("Header 1");
Aspose.Pdf.TextStamp stamp2 = new Aspose.Pdf.TextStamp("Header 2");
Aspose.Pdf.TextStamp stamp3 = new Aspose.Pdf.TextStamp("Header 3");

// Damga hizalamasını ayarlayın (damgayı sayfanın üstüne, yatay olarak ortalanmış şekilde yerleştirin)
stamp1.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// Yazı tipi stilini Kalın olarak belirtin
stamp1.TextState.FontStyle = FontStyles.Bold;

// Metnin ön zemin rengi bilgisini kırmızı olarak ayarla
stamp1.TextState.ForegroundColor = Color.Red;

// Yazı tipi boyutunu 14 olarak belirtin
stamp1.TextState.FontSize = 14;

// Şimdi 2. damga nesnesinin dikey hizalamasını Üst olarak ayarlamamız gerekiyor
stamp2.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

// Damga için Yatay hizalama bilgilerini Ortaya hizalanmış olarak ayarlayın
stamp2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// Damga nesnesi için yakınlaştırma faktörünü ayarlayın
stamp2.Zoom = 10;

//3. damga nesnesinin formatını ayarlayın
// Damga nesnesi için Dikey hizalama bilgisini TOP olarak belirtin
stamp3.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

// Damga nesnesi için Yatay hizalama bilgilerini Ortaya hizalanmış olarak ayarlayın
stamp3.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// Damga nesnesinin dönüş açısını ayarlayın
stamp3.RotateAngle = 35;

// Damga için arka plan rengi olarak pembeyi ayarla
stamp3.TextState.BackgroundColor = Color.Pink;

// Damganın yazı tipi yüzü bilgisini Verdana olarak değiştirin
stamp3.TextState.Font = FontRepository.FindFont("Verdana");

// İlk damga ilk sayfaya eklenir;
doc.Pages[1].AddStamp(stamp1);

// İkinci damga ikinci sayfaya eklenmiştir;
doc.Pages[2].AddStamp(stamp2);

// Üçüncü damga üçüncü sayfaya eklenmiştir.
doc.Pages[3].AddStamp(stamp3);
dataDir = dataDir + "multiheader_out.pdf";

// Güncellenen belgeyi kaydet
doc.Save(dataDir);
Console.WriteLine("\nDifferent headers added successfully.\nFile saved at " + dataDir);

```

## Çözüm

Tebrikler! Aspose.PDF for .NET'i kullanarak bir PDF belgesinin her sayfasına nasıl farklı başlıklar ekleyeceğinizi öğrendiniz. Artık PDF belgelerinizin başlıklarını özelleştirmek için bu bilgiyi kendi projelerinize uygulayabilirsiniz.

### PDF dosyasına farklı başlıklar eklemeyle ilgili SSS'ler

#### S: Aspose.PDF for .NET kullanarak bir PDF dosyasına farklı başlıklar eklemenin amacı nedir?

C: Aspose.PDF for .NET kullanarak bir PDF dosyasına farklı başlıklar eklemek, her sayfanın üst kısmında görüntülenen içeriği özelleştirmenize olanak tanır. Bu özellik özellikle bir PDF belgesinin farklı sayfalarına göre değişen başlıklar, bölüm adları, sayfa numaraları ve diğer bilgileri eklemek için kullanışlıdır.

#### S: Her başlığın hizalama, yazı tipi, boyut, renk ve döndürme gibi görünümünü özelleştirebilir miyim?

 C: Evet, her başlık damgasının görünümünü tamamen özelleştirebilirsiniz. Sağlanan C# kaynak kodu, C#'ın çeşitli özelliklerinin nasıl ayarlanacağını gösterir.`TextStamp` dikey ve yatay hizalama, yazı tipi stili, yazı tipi boyutu, yazı tipi rengi, arka plan rengi ve dönüş açısı dahil olmak üzere her başlık için nesneler.

#### S: Bir PDF belgesinin aynı sayfasına birden fazla başlık damgası eklemek mümkün müdür?

C: Sağlanan eğitim, bir PDF belgesinin farklı sayfalarına farklı başlıklar eklemeyi gösterse de, aynı sayfaya birden fazla başlık damgası eklemek için kodu uyarlayabilirsiniz. Aynı bölümde çeşitli başlıkları görüntülemek istiyorsanız bu yararlı olabilir.

#### S: Başlıkların PDF sayfalarının ana içeriğiyle çakışmamasını nasıl sağlayabilirim?

 C: Üst üste binmeyi önlemek için`VerticalAlignment`, `HorizontalAlignment` ve diğer özellikleri`TextStamp` nesneler. Bu ayarlar, başlıkların sayfada nereye konumlandırılacağını kontrol ederek, bunları ana içeriği engellemeyecek şekilde konumlandırmanıza olanak tanır.

#### S: Bu yöntemi, farklı sayıda sayfaya sahip mevcut PDF belgelerine başlık eklemek için kullanabilir miyim?

C: Evet, farklı sayıda sayfaya sahip mevcut PDF belgelerine başlık eklemek için sağlanan kaynak kodunu uyarlayabilirsiniz. Kodu, eklemek istediğiniz başlık sayısıyla eşleşecek şekilde ayarlayın ve her başlığı istediğiniz sayfayla ilişkilendirin.

#### S: Yalnızca ilk üç sayfaya değil, belirli sayfalara da başlık eklemek istersem ne olur?

 C: Eğitimde, açıklama amacıyla ilk üç sayfaya başlık eklenmesi gösterilmektedir. İlk üçün ötesindeki belirli sayfalara başlık eklemek için ilgili sayfa dizinlerine başvurarak ve aşağıdakileri oluşturarak kodu ayarlayın:`TextStamp` Her sayfa için nesneler.

#### S: Metin yerine başlık olarak görselleri kullanabilir miyim?

 C: Sağlanan eğitim, metin tabanlı başlıklar eklemeye odaklanıyor. Ancak görsel tabanlı başlıklar eklemek için benzer bir yaklaşım uygulayabilirsiniz.`ImageStamp` bunun yerine nesneler`TextStamp` nesneler. Bu, oluşturmayı ve yapılandırmayı içerecektir`ImageStamp` İstenilen özelliklere sahip nesneler.

#### S: Bir PDF belgesinin her sayfasına farklı altbilgiler eklemek için bu bilgiyi nasıl uygulayabilirim?

 C: Bu eğitimde gösterilen yaklaşımın aynısı, bir PDF belgesinin her sayfasına farklı altbilgiler eklemek için uygulanabilir. Başlıklar yerine oluşturup yapılandırırsınız`TextStamp` veya`ImageStamp` kullanarak nesneleri her sayfanın altına ekleyin.`AddStamp` yöntem.

#### S: Toplu işlemde birden çok PDF belgesine başlık ekleme işlemini otomatikleştirebilir miyim?

C: Evet, bir belge listesi boyunca ilerleyen ve başlık damgalama işlemini her belgeye uygulayan bir komut dosyası veya program kullanarak birden çok PDF belgesine başlık ekleme işlemini otomatikleştirebilirsiniz.