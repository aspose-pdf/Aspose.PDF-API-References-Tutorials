---
title: PDF Dosyasında Sayfa Numarası Damgaları
linktitle: PDF Dosyasında Sayfa Numarası Damgaları
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF dosyasına sayfa numarası damgalarının nasıl ekleneceğini öğrenin.
type: docs
weight: 160
url: /tr/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
Bu eğitimde, .NET için Aspose.PDF kullanarak PDF dosyasına sayfa numarası damgalarının nasıl ekleneceğini adım adım göstereceğiz. Mevcut bir PDF belgesini açmak, bir sayfa numarası damgası oluşturmak, özelliklerini ayarlamak ve bunu PDF dosyasındaki belirli bir sayfaya eklemek için sağlanan C# kaynak kodunu kullanacağız.

## Adım 1: Ortamı kurma

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Kurulu bir .NET geliştirme ortamı.
- .NET için Aspose.PDF kütüphanesi indirildi ve projenizde referans olarak kullanıldı.

## Adım 2: Mevcut PDF belgesini yükleme

İlk adım, mevcut PDF belgesini projenize yüklemektir. İşte nasıl:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Mevcut PDF belgesini açın
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

"BELGELERİNİZ DİZİNİ" ifadesini PDF belgenizin bulunduğu dizinin gerçek yoluyla değiştirdiğinizden emin olun.

## Adım 3: Sayfa Numaralandırma Damgasını Oluşturma ve Yapılandırma

Artık PDF belgesi yüklendiğine göre, bir sayfa numaralandırma tamponu oluşturabilir ve ihtiyaçlarımıza göre yapılandırabiliriz. İşte nasıl:

```csharp
// Bir sayfa numarası arabelleği oluşturun
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Tamponun arka planda olup olmadığını tanımlayın
pageNumberStamp.Background = false;

// Sayfa numaralandırma arabelleğinin biçimi
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;

// Sayfa numaralandırma arabelleğinin alt kenar boşluğu
pageNumberStamp.BottomMargin = 10;

// Sayfa numaralandırma arabelleğinin yatay hizalaması
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;

// Sayfa numaralandırmasının başlangıç numarası
pageNumberStamp.StartingNumber = 1;

// Sayfa numarası arabelleği metin özelliklerini ayarla
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

Yukarıdaki kod, sayfa numarası biçimi, alt kenar boşluğu, yatay hizalama, başlangıç numarası ve metin özellikleri gibi özelliklere sahip bir sayfa numarası damgası oluşturur.

## Adım 4: Belirli bir sayfaya sayfa numarası damgası ekleme

Sayfa numarası damgası yapılandırıldıktan sonra, bunu PDF belgesinin belirli bir sayfasına ekleyebiliriz. İşte nasıl:

```csharp
// Sayfa numarası tamponunu belirli bir sayfaya ekleyin
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

Yukarıdaki kod, PDF belgesinin ilk sayfasına sayfa numarası damgası ekler. Sayfa numarasını gerektiği gibi değiştirebilirsiniz.

## Adım 5: Değiştirilen PDF belgesinin kaydedilmesi

Sayfa numarası damgası PDF belgesine eklendiğinde, değiştirilmiş PDF belgesini kaydedebiliriz. İşte nasıl:

```csharp
// Değiştirilen PDF belgesini kaydedin
pdfDocument.Save(dataDir + "PageNumberStamp_out.pdf");
```

"BELGELERİNİZ DİZİNİ" ifadesini, düzenlenen PDF belgesini kaydetmek istediğiniz dizinin gerçek yoluyla değiştirdiğinizden emin olun.

### .NET için Aspose.PDF kullanılarak Sayfa Numarası Damgaları için örnek kaynak kodu 
```csharp

// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi aç
Document pdfDocument = new Document(dataDir+ "PageNumberStamp.pdf");

// Sayfa numarası damgası oluştur
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Pulun arka plan olup olmadığı
pageNumberStamp.Background = false;
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;
pageNumberStamp.BottomMargin = 10;
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;
pageNumberStamp.StartingNumber = 1;

// Metin özelliklerini ayarla
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;

// Belirli bir sayfaya damga ekle
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
dataDir = dataDir + "PageNumberStamp_out.pdf";

// Çıktı belgesini kaydet
pdfDocument.Save(dataDir);
Console.WriteLine("\nPage number stamp added successfully.\nFile saved at " + dataDir);

```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesine sayfa numarası damgalarının nasıl ekleneceğini öğrendiniz. Artık PDF belgelerinizi net ve bilgilendirici sayfa numaraları ekleyerek kişiselleştirebilirsiniz.

### PDF dosyasındaki sayfa numarası damgaları için SSS

#### S: Sayfa Numarası Damgası nedir ve bir PDF dosyasına sayfa numaraları eklemek için nasıl kullanılır?

A: Sayfa Numarası Damgası, Aspose.PDF'de bir PDF belgesinin belirli sayfalarına dinamik sayfa numaraları eklemenize olanak tanıyan bir özelliktir. Bu eğitimde, bir PageNumberStamp nesnesi oluşturularak, özelliklerini yapılandırarak ve belirlenmiş bir sayfaya ekleyerek elde edilir.

#### S: Sağlanan C# kaynak kodu bir PDF dosyasına sayfa numarası damgası eklemeyi nasıl başarıyor?

A: Kod, mevcut bir PDF belgesinin nasıl yükleneceğini, bir PageNumberStamp'ın nasıl oluşturulacağını, çeşitli özelliklerin (biçim, yazı tipi, hizalama vb. gibi) nasıl ayarlanacağını ve ardından damganın belirli bir sayfaya nasıl ekleneceğini gösterir. Damga, toplam sayfa sayısını otomatik olarak hesaplar ve doğru sayfa numaralarını ekler.

#### S: Sayfa numarasının görünümünü (yazı tipi, rengi ve boyutu gibi) özelleştirebilir miyim?

C: Kesinlikle, yazı tipi, yazı tipi boyutu, yazı tipi stili (kalın, italik vb.) ve metin rengi gibi özellikleri ayarlayarak sayfa numarası damgasının görünümünü özelleştirebilirsiniz.

#### S: Bir PDF belgesinin birden fazla sayfasına sayfa numarası damgası eklemek mümkün müdür?

C: Evet, birden fazla PageNumberStamp nesnesi oluşturarak ve her birini istediğiniz sayfaya ekleyerek birden fazla sayfaya sayfa numarası damgası ekleyebilirsiniz.

#### S: Sayfa numarası damgasının sayfa içeriğinin bir parçası olarak mı yoksa arka plan öğesi olarak mı görüneceğini seçebilir miyim?

 A: Evet, sayfa numarası damgasının sayfanın içeriğinin bir parçası olarak mı yoksa arka plan öğesi olarak mı görüneceğini,`Background` PageNumberStamp'ın özelliği.

#### S: Toplam sayfa sayısı dahil olmak üzere sayfa numarasının biçimini nasıl belirleyebilirim?

 A: Kod şunu kullanır:`Format`Sayfa numarasının biçimini belirtmek için PageNumberStamp özelliği. "# of" makrosu toplam sayfa sayısını temsil etmek için kullanılır.

#### S: Aynı sayfa numarası damgasını birden fazla sayfaya eklersem ne olur?

A: Aynı PageNumberStamp örneğini birden fazla sayfaya eklemek, her sayfa için doğru sayfa numaralarını görüntüler. Damga, sayfa numarasını ve toplam sayfa sayısını otomatik olarak ayarlar.

#### S: PDF belgesinin üst bilgi veya alt bilgi bölümlerine sayfa numarası damgası ekleyebilir miyim?

A: PageNumberStamps genellikle doğrudan sayfanın içeriğine eklenir, ancak bunları başlık veya alt bilgi bölümlerine yerleştirmek için FloatingBox veya diğer teknikleri kullanabilirsiniz.

#### S: Sayfa numarası damgasının sayfadaki konumunu nasıl belirlerim?

 A:`BottomMargin` Ve`HorizontalAlignment` PageNumberStamp'ın özellikleri, damganın sayfadaki konumunu kontrol etmenizi sağlar.

#### S: Sayfa numaralandırmasını 1'den farklı bir rakamla başlatmak istersem ne olur?

 A: Ayarlayabilirsiniz`StartingNumber`Başlangıç sayfa numarasını belirtmek için PageNumberStamp'ın özelliği.