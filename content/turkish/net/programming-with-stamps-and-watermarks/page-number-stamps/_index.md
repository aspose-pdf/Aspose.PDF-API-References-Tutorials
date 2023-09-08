---
title: PDF Dosyasındaki Sayfa Numarası Damgaları
linktitle: PDF Dosyasındaki Sayfa Numarası Damgaları
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile PDF dosyasına sayfa numarası damgalarının nasıl ekleneceğini öğrenin.
type: docs
weight: 160
url: /tr/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak PDF dosyasına sayfa numarası damgalarının nasıl ekleneceği konusunda size adım adım rehberlik edeceğiz. Mevcut bir PDF belgesini açmak, sayfa numarası damgası oluşturmak, özelliklerini ayarlamak ve bunu PDF dosyasındaki belirli bir sayfaya eklemek için sağlanan C# kaynak kodunu kullanacağız.

## 1. Adım: Ortamı ayarlama

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Kurulu bir .NET geliştirme ortamı.
- .NET için Aspose.PDF kütüphanesini indirip projenizde referans olarak kullanabilirsiniz.

## Adım 2: Mevcut PDF belgesini yükleme

İlk adım mevcut PDF belgesini projenize yüklemektir. İşte nasıl:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Mevcut PDF belgesini aç
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

"BELGELERİNİZ DİZİNİ"ni, PDF belgenizin bulunduğu dizine giden gerçek yolla değiştirdiğinizden emin olun.

## Adım 3: Sayfa Numaralandırma Damgasını Oluşturma ve Yapılandırma

Artık PDF belgesi yüklendiğine göre bir sayfa numaralandırma arabelleği oluşturabilir ve bunu ihtiyaçlarımıza göre yapılandırabiliriz. İşte nasıl:

```csharp
// Sayfa numarası arabelleği oluşturma
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Tamponun arka planda olup olmadığını tanımlayın
pageNumberStamp.Background = false;

// Sayfa numaralandırma arabelleğinin formatı
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;

// Sayfa numaralandırma arabelleğinin alt kenar boşluğu
pageNumberStamp.BottomMargin = 10;

// Sayfa numaralandırma arabelleğinin yatay hizalanması
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;

// Sayfa numaralandırmanın başlangıç sayısı
pageNumberStamp.StartingNumber = 1;

// Sayfa numarası arabellek metni özelliklerini ayarlama
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

Yukarıdaki kod, sayfa numarası formatı, alt kenar boşluğu, yatay hizalama, başlangıç numarası ve metin özellikleri gibi özelliklere sahip bir sayfa numarası damgası oluşturur.

## 4. Adım: Sayfa numarası damgasını belirli bir sayfaya ekleme

Sayfa numarası damgası yapılandırıldıktan sonra bunu PDF belgesinin belirli bir sayfasına ekleyebiliriz. İşte nasıl:

```csharp
// Sayfa numarası arabelleğini belirli bir sayfaya ekleme
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

Yukarıdaki kod, sayfa numarası damgasını PDF belgesinin ilk sayfasına ekler. Sayfa numarasını gerektiği gibi değiştirebilirsiniz.

## Adım 5: Değiştirilen PDF belgesini kaydetme

Sayfa numarası damgası PDF belgesine eklendikten sonra değiştirilen PDF belgesini kaydedebiliriz. İşte nasıl:

```csharp
// Değiştirilen PDF belgesini kaydedin
pdfDocument.Save(dataDir + "PageNumberStamp_out.pdf");
```

"BELGELERİNİZ DİZİNİ"ni, düzenlenen PDF belgesini kaydetmek istediğiniz dizinin gerçek yolu ile değiştirdiğinizden emin olun.

### Aspose.PDF for .NET kullanan Sayfa Numarası Damgaları için örnek kaynak kodu 
```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi aç
Document pdfDocument = new Document(dataDir+ "PageNumberStamp.pdf");

// Sayfa numarası damgası oluştur
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Damganın arka planda olup olmadığı
pageNumberStamp.Background = false;
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;
pageNumberStamp.BottomMargin = 10;
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;
pageNumberStamp.StartingNumber = 1;

// Metin özelliklerini ayarlama
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

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesine sayfa numarası damgalarının nasıl ekleneceğini öğrendiniz. Artık anlaşılır ve bilgilendirici sayfa numaraları ekleyerek PDF belgelerinizi kişiselleştirebilirsiniz.

### PDF dosyasındaki sayfa numarası damgaları için SSS

#### S: Sayfa Numarası Damgası nedir ve bir PDF dosyasına sayfa numaraları eklemek için nasıl kullanılır?

C: Sayfa Numarası Damgası, Aspose.PDF'de bir PDF belgesinin belirli sayfalarına dinamik sayfa numaraları eklemenizi sağlayan bir özelliktir. Bu öğreticide bu, bir PageNumberStamp nesnesi oluşturularak, özelliklerinin yapılandırılmasıyla ve belirlenen sayfaya eklenmesiyle gerçekleştirilir.

#### S: Sağlanan C# kaynak kodu, bir PDF dosyasına sayfa numarası damgaları eklemeyi nasıl başarır?

C: Kod, mevcut bir PDF belgesinin nasıl yükleneceğini, PageNumberStamp'ın nasıl oluşturulacağını, çeşitli özelliklerin (biçim, yazı tipi, hizalama vb. gibi) nasıl ayarlanacağını ve ardından damganın belirli bir sayfaya nasıl ekleneceğini gösterir. Damga, toplam sayfa sayısını otomatik olarak hesaplar ve doğru sayfa numaralarını ekler.

#### S: Sayfa numarasının yazı tipi stili, rengi ve boyutu gibi görünümünü özelleştirebilir miyim?

C: Kesinlikle, yazı tipi, yazı tipi boyutu, yazı tipi stili (kalın, italik vb.) ve metin rengi gibi özellikleri ayarlayarak sayfa numarası damgasının görünümünü özelleştirebilirsiniz.

#### S: Bir PDF belgesindeki birden fazla sayfaya sayfa numarası damgaları eklemek mümkün müdür?

C: Evet, birden çok PageNumberStamp nesnesi oluşturup her birini istediğiniz sayfalara ekleyerek birden çok sayfaya sayfa numarası damgaları ekleyebilirsiniz.

#### S: Sayfa numarası damgasının sayfa içeriğinin bir parçası olarak mı yoksa bir arka plan öğesi olarak mı görüneceğini seçebilir miyim?

 C: Evet, sayfa numarası damgasının sayfa içeriğinin bir parçası olarak mı yoksa arka plan öğesi olarak mı görüneceğini ayarlayarak kontrol edebilirsiniz.`Background` PageNumberStamp'ın özelliği.

#### S: Toplam sayfa sayısı da dahil olmak üzere sayfa numarasının biçimini nasıl belirleyebilirim?

 C: Kod şunları kullanır:`Format`Sayfa numarasının biçimini belirtmek için PageNumberStamp özelliği. "# of" makrosu toplam sayfa sayısını temsil etmek için kullanılır.

#### S: Aynı sayfa numarası damgasını birden fazla sayfaya eklersem ne olur?

C: Aynı PageNumberStamp örneğini birden fazla sayfaya eklemek, her sayfa için doğru sayfa numaralarını görüntüleyecektir. Damga, sayfa numarasını ve toplam sayfa sayısını otomatik olarak ayarlar.

#### S: Bir PDF belgesinin üstbilgi veya altbilgi bölümlerine sayfa numarası damgaları ekleyebilir miyim?

C: PageNumberStamp'lar genellikle doğrudan sayfanın içeriğine eklenirken, bunları üstbilgi veya altbilgi bölümlerine konumlandırmak için FloatingBox'ı veya diğer teknikleri kullanabilirsiniz.

#### S: Sayfa numarası damgasının sayfadaki konumunu nasıl belirlerim?

 C:`BottomMargin` Ve`HorizontalAlignment` PageNumberStamp'ın özellikleri damganın sayfa içindeki konumunu kontrol etmenize olanak tanır.

#### S: Sayfa numaralandırmasını 1 yerine farklı bir numaradan başlatmak istersem ne olur?

 C: Ayarlayabilirsiniz`StartingNumber`Başlangıç sayfa numarasını belirtmek için PageNumberStamp özelliği.