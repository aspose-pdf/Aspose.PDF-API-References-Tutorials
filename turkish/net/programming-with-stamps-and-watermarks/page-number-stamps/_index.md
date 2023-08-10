---
title: PDF Dosyasında Sayfa Numarası Damgaları
linktitle: PDF Dosyasında Sayfa Numarası Damgaları
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF dosyasına sayfa numarası damgalarının nasıl ekleneceğini öğrenin.
type: docs
weight: 160
url: /tr/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak PDF dosyasına sayfa numarası damgalarının nasıl ekleneceği konusunda size adım adım rehberlik edeceğiz. Mevcut bir PDF belgesini açmak, bir sayfa numarası damgası oluşturmak, özelliklerini ayarlamak ve bunu PDF dosyasındaki belirli bir sayfaya eklemek için sağlanan C# kaynak kodunu kullanacağız.

## 1. Adım: Ortamı ayarlama

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Yüklü bir .NET geliştirme ortamı.
- .NET için Aspose.PDF kitaplığı indirildi ve projenizde referans verildi.

## 2. Adım: Mevcut PDF belgesini yükleme

İlk adım, mevcut PDF belgesini projenize yüklemektir. İşte nasıl:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Mevcut PDF belgesini aç
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

"BELGELER DİZİNİNİZİ", PDF belgenizin bulunduğu dizinin gerçek yolu ile değiştirdiğinizden emin olun.

## 3. Adım: Sayfa Numaralandırma Damgasını Oluşturma ve Yapılandırma

Artık PDF belgesi yüklendiğine göre, bir sayfa numaralandırma arabelleği oluşturabilir ve ihtiyaçlarımıza göre yapılandırabiliriz. İşte nasıl:

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

// Sayfa numaralandırma başlangıç numarası
pageNumberStamp.StartingNumber = 1;

// Sayfa numarası arabelleği metin özelliklerini ayarla
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

Yukarıdaki kod, sayfa numarası formatı, alt kenar boşluğu, yatay hizalama, başlangıç numarası ve metin özellikleri gibi özelliklere sahip bir sayfa numarası damgası oluşturur.

## 4. Adım: Belirli bir sayfaya sayfa numarası damgası ekleme

Sayfa numarası damgası yapılandırıldıktan sonra, onu PDF belgesinin belirli bir sayfasına ekleyebiliriz. İşte nasıl:

```csharp
// Sayfa numarası arabelleğini belirli bir sayfaya ekleyin
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

Yukarıdaki kod, sayfa numarası damgasını PDF belgesinin ilk sayfasına ekler. Sayfa numarasını gerektiği gibi değiştirebilirsiniz.

## 5. Adım: Değiştirilen PDF belgesini kaydetme

PDF belgesine sayfa numarası damgası eklendikten sonra, değiştirilen PDF belgesini kaydedebiliriz. İşte nasıl:

```csharp
// Değiştirilen PDF belgesini kaydedin
pdfDocument.Save(dataDir + "PageNumberStamp_out.pdf");
```

"BELGELER DİZİNİNİZ"i, düzenlenmiş PDF belgesini kaydetmek istediğiniz dizinin gerçek yolu ile değiştirdiğinizden emin olun.

### Aspose.PDF for .NET kullanan Sayfa Numarası Damgaları için örnek kaynak kodu 
```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi aç
Document pdfDocument = new Document(dataDir+ "PageNumberStamp.pdf");

// Sayfa numarası damgası oluştur
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Damganın arka plan olup olmadığı
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

// Çıkış belgesini kaydet
pdfDocument.Save(dataDir);
Console.WriteLine("\nPage number stamp added successfully.\nFile saved at " + dataDir);

```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesine sayfa numarası damgalarının nasıl ekleneceğini öğrendiniz. Artık net ve bilgilendirici sayfa numaraları ekleyerek PDF belgelerinizi kişiselleştirebilirsiniz.

### PDF dosyasındaki sayfa numarası damgaları için SSS

#### S: Sayfa Numarası Damgası nedir ve bir PDF dosyasına sayfa numaraları eklemek için nasıl kullanılır?

C: Sayfa Numarası Damgası, bir PDF belgesinin belirli sayfalarına dinamik sayfa numaraları eklemenizi sağlayan Aspose.PDF'deki bir özelliktir. Bu öğreticide, bir PageNumberStamp nesnesi oluşturarak, özelliklerini yapılandırarak ve onu belirlenmiş bir sayfaya ekleyerek elde edilir.

#### S: Sağlanan C# kaynak kodu, bir PDF dosyasına sayfa numarası damgaları eklemeyi nasıl başarıyor?

Y: Kod, mevcut bir PDF belgesinin nasıl yükleneceğini, bir PageNumberStamp oluşturulacağını, çeşitli özelliklerin (biçim, yazı tipi, hizalama vb.) nasıl ayarlanacağını ve ardından belirli bir sayfaya damganın nasıl ekleneceğini gösterir. Damga, toplam sayfa sayısını otomatik olarak hesaplar ve doğru sayfa numaralarını ekler.

#### S: Yazı tipi stili, rengi ve boyutu gibi sayfa numarasının görünümünü özelleştirebilir miyim?

C: Kesinlikle, yazı tipi, yazı tipi boyutu, yazı tipi stili (kalın, italik vb.) ve metin rengi gibi özellikleri ayarlayarak sayfa numarası damgasının görünümünü özelleştirebilirsiniz.

#### S: Bir PDF belgesinde birden çok sayfaya sayfa numarası damgası eklemek mümkün müdür?

C: Evet, birden çok PageNumberStamp nesnesi oluşturarak ve her birini istenen sayfalara ekleyerek birden çok sayfaya sayfa numarası damgası ekleyebilirsiniz.

#### S: Sayfa numarası damgasının sayfa içeriğinin bir parçası olarak mı yoksa bir arka plan öğesi olarak mı görüneceğini seçebilir miyim?

 C: Evet, sayfa numarası damgasının sayfa içeriğinin bir parçası olarak mı yoksa bir arka plan öğesi olarak mı görüneceğini ayarlayarak kontrol edebilirsiniz.`Background` PageNumberStamp özelliği.

#### S: Toplam sayfa sayısı da dahil olmak üzere sayfa numarasının biçimini nasıl belirleyebilirim?

 C: Kod şunu kullanır:`Format`sayfa numarasının biçimini belirtmek için PageNumberStamp özelliği. "# of" makrosu, toplam sayfa sayısını temsil etmek için kullanılır.

#### S: Aynı sayfa numarası damgasını birden fazla sayfaya eklersem ne olur?

C: Aynı PageNumberStamp örneğini birden çok sayfaya eklemek, her sayfa için doğru sayfa numaralarını görüntüler. Damga, sayfa numarasını ve toplam sayfa sayısını otomatik olarak ayarlar.

#### S: Bir PDF belgesinin üst bilgi veya alt bilgi bölümlerine sayfa numarası damgaları ekleyebilir miyim?

C: PageNumberStamps tipik olarak doğrudan sayfanın içeriğine eklenirken, bunları üst bilgi veya alt bilgi bölümlerinde konumlandırmak için FloatingBox veya diğer teknikleri kullanabilirsiniz.

#### S: Sayfa numarası damgasının sayfadaki konumunu nasıl belirleyebilirim?

 C:`BottomMargin` Ve`HorizontalAlignment` PageNumberStamp'ın özellikleri, damganın sayfa içindeki konumunu kontrol etmenize izin verir.

#### S: Sayfa numaralandırmaya 1 yerine farklı bir numaradan başlamak istersem ne olur?

 A: ayarlayabilirsiniz`StartingNumber`Başlangıç sayfa numarasını belirtmek için PageNumberStamp özelliği.