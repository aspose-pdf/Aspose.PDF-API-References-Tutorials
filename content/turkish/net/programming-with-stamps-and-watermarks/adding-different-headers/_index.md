---
title: PDF Dosyasına Farklı Başlıklar Ekleme
linktitle: PDF Dosyasına Farklı Başlıklar Ekleme
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF dosyasının her sayfasına farklı başlıkların nasıl kolayca ekleneceğini öğrenin.
type: docs
weight: 30
url: /tr/net/programming-with-stamps-and-watermarks/adding-different-headers/
---
Bu eğitimde, .NET için Aspose.PDF kullanarak PDF dosyasına farklı başlıkların nasıl ekleneceğini adım adım göstereceğiz. Sağlanan C# kaynak kodunu kullanarak PDF dosyasının her sayfasına özel başlıklar nasıl ekleneceğini göstereceğiz.

## Adım 1: Ortamı kurma

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Kurulu bir .NET geliştirme ortamı.
- .NET için Aspose.PDF kütüphanesi indirildi ve projenizde referans olarak kullanıldı.

## Adım 2: PDF belgesini yükleme

İlk adım, mevcut PDF belgesini projenize yüklemektir. İşte nasıl:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Kaynak belgeyi açın
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "AddingDifferentHeaders.pdf");
```

"BELGELERİNİZ DİZİNİ" ifadesini PDF belgenizin bulunduğu dizinin gerçek yoluyla değiştirdiğinizden emin olun.

## Adım 3: Başlık Arabellekleri Oluşturma

Artık PDF belgenizi yüklediğinize göre, eklemek için başlık damgalarını oluşturabilirsiniz. İşte nasıl:

```csharp
// Üç başlık arabelleği oluştur
Aspose.Pdf.TextStamp stamp1 = new Aspose.Pdf.TextStamp("Header 1");
Aspose.Pdf.TextStamp stamp2 = new Aspose.Pdf.TextStamp("Header 2");
Aspose.Pdf.TextStamp stamp3 = new Aspose.Pdf.TextStamp("Header 3");
```

Yukarıdaki kod belirtilen metni içeren üç yeni başlık tamponu oluşturur.

## Adım 4: Başlık arabelleği özelliklerini yapılandırma

PDF belgesine başlık damgalarını eklemeden önce, her damga için hizalama, boyut, renk vb. gibi farklı özellikler yapılandırabilirsiniz. İşte nasıl:

```csharp
// İlk başlık arabelleğini yapılandırın
stamp1.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp1.TextState.FontStyle = FontStyles.Bold;
stamp1.TextState.ForegroundColor = Color.Red;
stamp1.TextState.FontSize = 14;

// İkinci başlık tamponunun yapılandırması
stamp2.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp2.Zoom = 10;

// Üçüncü başlık tamponunu yapılandırın
stamp3.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp3.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp3.RotateAngle = 35;
stamp3.TextState.BackgroundColor = Color.Pink;
stamp3.TextState.Font = FontRepository.FindFont("Verdana");
```

Bu özellikleri her başlık tamponu için gerektiği gibi ayarlayabilirsiniz.

## Adım 5: PDF'e Başlık Damgaları Ekleyin

Artık başlık damgaları hazır olduğuna göre, bunları PDF belgesinin her bir sayfasına ekleyebilirsiniz. İşte nasıl:

```csharp
// Belirli sayfalara başlık tamponları ekleyin
doc.Pages[1].AddStamp(stamp1);
doc.Pages[2].AddStamp(stamp2);
doc.Pages[3].AddStamp(stamp3);
```

Yukarıdaki kod her başlık damgasını PDF belgesinin ilgili sayfasına ekler.

## Adım 6: Çıktı belgesini kaydedin

Başlık damgalarını ekledikten sonra, düzenlenen PDF belgesini kaydedebilirsiniz. İşte nasıl:

```csharp
// Güncellenen belgeyi kaydet
doc.Save(dataDir);
```

Yukarıdaki kod düzenlenen PDF belgesini belirtilen dizine kaydeder.

### .NET için Aspose.PDF kullanarak Farklı Başlıklar Eklemek için örnek kaynak kodu 
```csharp

// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Açık kaynaklı belge
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddingDifferentHeaders.pdf");

// Üç pul oluştur
Aspose.Pdf.TextStamp stamp1 = new Aspose.Pdf.TextStamp("Header 1");
Aspose.Pdf.TextStamp stamp2 = new Aspose.Pdf.TextStamp("Header 2");
Aspose.Pdf.TextStamp stamp3 = new Aspose.Pdf.TextStamp("Header 3");

// Damga hizalamasını ayarlayın (damgayı sayfanın üstüne, yatay olarak ortalanmış şekilde yerleştirin)
stamp1.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// Yazı tipini Kalın olarak belirtin
stamp1.TextState.FontStyle = FontStyles.Bold;

// Metin ön plan renk bilgisini kırmızı olarak ayarlayın
stamp1.TextState.ForegroundColor = Color.Red;

// Yazı tipi boyutunu 14 olarak belirtin
stamp1.TextState.FontSize = 14;

// Şimdi 2. damga nesnesinin dikey hizalamasını Üst olarak ayarlamamız gerekiyor
stamp2.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

// Damga için Yatay hizalama bilgilerini Orta hizalanmış olarak ayarlayın
stamp2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// Damga nesnesi için yakınlaştırma faktörünü ayarlayın
stamp2.Zoom = 10;

//3. damga nesnesinin biçimlendirmesini ayarlayın
// Damga nesnesi için Dikey hizalama bilgilerini ÜST olarak belirtin
stamp3.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

// Damga nesnesi için Yatay hizalama bilgisini Orta hizalanmış olarak ayarlayın
stamp3.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// Damga nesnesi için dönüş açısını ayarlayın
stamp3.RotateAngle = 35;

// Pul için arka plan rengini pembe olarak ayarlayın
stamp3.TextState.BackgroundColor = Color.Pink;

// Damga için yazı tipi bilgisini Verdana olarak değiştirin
stamp3.TextState.Font = FontRepository.FindFont("Verdana");

// İlk damga ilk sayfaya eklenir;
doc.Pages[1].AddStamp(stamp1);

// İkinci sayfaya ikinci damga eklenmiştir;
doc.Pages[2].AddStamp(stamp2);

// Üçüncü sayfaya üçüncü damga eklenmiştir.
doc.Pages[3].AddStamp(stamp3);
dataDir = dataDir + "multiheader_out.pdf";

// Güncellenen belgeyi kaydet
doc.Save(dataDir);
Console.WriteLine("\nDifferent headers added successfully.\nFile saved at " + dataDir);

```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesinin her sayfasına farklı başlıklar eklemeyi öğrendiniz. Artık bu bilgiyi kendi projelerinize uygulayarak PDF belgeleriniz için başlıkları özelleştirebilirsiniz.

### PDF dosyasına farklı başlıklar eklemeye ilişkin SSS

#### S: Aspose.PDF for .NET kullanarak bir PDF dosyasına farklı başlıklar eklemenin amacı nedir?

A: Aspose.PDF for .NET kullanarak bir PDF dosyasına farklı başlıklar eklemek, her sayfanın en üstünde görüntülenen içeriği özelleştirmenize olanak tanır. Bu özellik, özellikle bir PDF belgesinin farklı sayfalarında değişen başlıklar, bölüm adları, sayfa numaraları ve diğer bilgileri eklemek için kullanışlıdır.

#### S: Her başlığın hizalama, yazı tipi, boyut, renk ve dönüş gibi görünümünü özelleştirebilir miyim?

 A: Evet, her başlık damgasının görünümünü tamamen özelleştirebilirsiniz. Sağlanan C# kaynak kodu, çeşitli özelliklerin nasıl ayarlanacağını gösterir`TextStamp` Her başlık için dikey ve yatay hizalama, yazı tipi stili, yazı tipi boyutu, yazı tipi rengi, arka plan rengi ve dönüş açısı gibi nesneler.

#### S: Bir PDF belgesinin aynı sayfasına birden fazla başlık damgası eklemek mümkün müdür?

A: Sağlanan eğitim, bir PDF belgesinin farklı sayfalarına farklı başlıklar eklemeyi gösterirken, aynı sayfaya birden fazla başlık damgası eklemek için kodu uyarlayabilirsiniz. Bu, aynı bölümde çeşitli başlıklar görüntülemek istiyorsanız yararlı olabilir.

#### S: Başlıkların PDF sayfalarının ana içeriğiyle örtüşmemesini nasıl sağlayabilirim?

 A: Çakışmayı önlemek için,`VerticalAlignment`, `HorizontalAlignment` ve diğer özellikleri`TextStamp` nesneler. Bu ayarlar, başlıkların sayfada nerede konumlandırılacağını kontrol ederek, bunları ana içeriği engellemeyecek şekilde konumlandırmanıza olanak tanır.

#### S: Bu yöntemi, farklı sayfa sayılarına sahip mevcut PDF belgelerine başlık eklemek için kullanabilir miyim?

A: Evet, mevcut PDF belgelerine farklı sayfa sayılarına sahip başlıklar eklemek için sağlanan kaynak kodunu uyarlayabilirsiniz. Kodu eklemek istediğiniz başlık sayısına uyacak şekilde ayarlayın ve her başlığı istediğiniz sayfayla ilişkilendirin.

#### S: Sadece ilk üç sayfaya değil, belirli sayfalara da başlık eklemek istersem ne olur?

 A: Eğitim, örnek amaçlı olarak ilk üç sayfaya başlık eklemeyi gösterir. İlk üç sayfadan sonraki belirli sayfalara başlık eklemek için, karşılık gelen sayfa dizinlerine başvurarak ve`TextStamp` her sayfa için nesneler.

#### S: Başlık olarak metin yerine resim kullanabilir miyim?

 A: Sağlanan eğitim, metin tabanlı başlıklar eklemeye odaklanmaktadır. Ancak, benzer bir yaklaşımı kullanarak görüntü tabanlı başlıklar eklemek için de uygulayabilirsiniz`ImageStamp` nesneler yerine`TextStamp` nesneler. Bu, oluşturmayı ve yapılandırmayı içerir`ImageStamp` İstenilen özelliklere sahip nesneler.

#### S: Bu bilgiyi, bir PDF belgesinin her sayfasına farklı altbilgiler eklemek için nasıl uygulayabilirim?

 A: Bu eğitimde gösterilen aynı yaklaşım, bir PDF belgesinin her sayfasına farklı altbilgiler eklemek için uygulanabilir. Üstbilgiler yerine, oluşturup yapılandırabilirsiniz`TextStamp` veya`ImageStamp` nesneleri ekleyin ve bunları her sayfanın altına ekleyin`AddStamp` Yöntem.

#### S: Birden fazla PDF belgesine toplu işlemle başlık ekleme sürecini otomatikleştirebilir miyim?

C: Evet, bir belge listesinde gezinen ve her belgeye başlık damgalama işlemini uygulayan bir betik veya program kullanarak birden fazla PDF belgesine başlık ekleme sürecini otomatikleştirebilirsiniz.