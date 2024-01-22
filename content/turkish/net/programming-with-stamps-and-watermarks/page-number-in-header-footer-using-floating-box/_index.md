---
title: Kayan Kutu Kullanarak Üst Bilgi Alt Bilgideki Sayfa Numarası
linktitle: Kayan Kutu Kullanarak Üst Bilgi Alt Bilgideki Sayfa Numarası
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile bir PDF belgesinin üstbilgi ve altbilgisine sayfa numarasını nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 150
url: /tr/net/programming-with-stamps-and-watermarks/page-number-in-header-footer-using-floating-box/
---
Bu eğitimde, Aspose.PDF for .NET ile FloatingBox kullanarak bir PDF belgesinin üstbilgisine ve altbilgisine sayfa numarasının nasıl ekleneceği konusunda size adım adım rehberlik edeceğiz. Bir PDF belgesi oluşturmak, bir sayfa eklemek, bir FloatingBox oluşturmak, konumunu ayarlamak ve sayfa numarasını buna eklemek, ardından değiştirilen PDF belgesini kaydetmek için sağlanan C# kaynak kodunu kullanacağız.

## 1. Adım: Ortamı ayarlama

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Kurulu bir .NET geliştirme ortamı.
- .NET için Aspose.PDF kütüphanesini indirip projenizde referans olarak kullanabilirsiniz.

## Adım 2: PDF belgesini oluşturma ve sayfa ekleme

İlk adım, PDF belgesinin bir örneğini oluşturmak ve ona bir sayfa eklemektir. İşte nasıl:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// PDF belgesini örneklendirin
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// PDF belgesine sayfa ekleme
Aspose.Pdf.Page page = pdf.Pages.Add();
```

"BELGELERİNİZ DİZİNİ"ni, PDF belgesini kaydetmek istediğiniz dizinin gerçek yolu ile değiştirdiğinizden emin olun.

## Adım 3: FloatingBox'ı oluşturma ve sayfa numarasını ekleme

Artık sayfa PDF belgesine eklendiğine göre bir FloatingBox oluşturabilir, konumunu ayarlayabilir ve sayfa numarasını buna ekleyebiliriz. İşte nasıl:

```csharp
// 140 genişliğinde ve 80 yüksekliğinde bir FloatingBox oluşturun
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// Paragrafın sol konumunu ayarlayın
box1. Left = 2;

// Paragrafın üst konumunu ayarlama
box1. Top = 10;

// Sayfa numarasını FloatingBox'a ekleyin
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// FloatingBox'ı sayfaya ekleyin
page.Paragraphs.Add(box1);
```

Yukarıdaki kod genişliği 140, yüksekliği 80 olan bir FloatingBox oluşturuyor. Daha sonra sol ve üst değerlerini belirterek konumunu belirliyoruz. Son olarak, mevcut sayfa numarası ve toplam sayfa sayısıyla değiştirilecek olan "($p/ $P )" sözdizimini içeren bir TextFragment kullanarak sayfa numarasını FloatingBox'a ekliyoruz.

## Adım 4: Değiştirilen PDF belgesini kaydetme

FloatingBox kullanılarak sayfa numarası üstbilgi veya altbilgiye eklendikten sonra değiştirilen PDF belgesini kaydedebiliriz. İşte nasıl:

```csharp
// Değiştirilen PDF belgesini kaydedin
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");
```

Yukarıdaki kod, düzenlenen PDF belgesini belirtilen dizine kaydeder.

### Aspose.PDF for .NET kullanarak Kayan Kutu Kullanan Sayfa Numarasındaki Üst Bilgi Alt Bilgisi için örnek kaynak kodu 
```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belge örneğini oluştur
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// PDF belgesine bir Sayfa ekleyin
Aspose.Pdf.Page page = pdf.Pages.Add();

//FloatingBox sınıfının yeni bir örneğini başlatır
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// Paragrafın sol konumunu gösteren kayan değer
box1.Left = 2;

// Paragrafın üst konumunu gösteren kayan değer
box1.Top = 10;

// Makroları FloatingBox'ın paragraf koleksiyonuna ekleyin
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// Sayfaya bir floatBox ekleyin
page.Paragraphs.Add(box1);

// Belgeyi kaydet
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");

```

## Çözüm

Tebrikler! Aspose.PDF for .NET ile FloatingBox kullanarak PDF belgesinin üstbilgisine ve altbilgisine sayfa numarasının nasıl ekleneceğini öğrendiniz. Artık sayfa numarası gibi dinamik bilgiler ekleyerek üstbilgilerinizi ve altbilgilerinizi özelleştirebilirsiniz.

### SSS'ler

#### S: FloatingBox nedir ve bir PDF belgesinin üstbilgisine veya altbilgisine sayfa numaraları eklemek için nasıl kullanılır?

C: FloatingBox, Aspose.PDF'de metin ve resimler de dahil olmak üzere çeşitli içerikleri tutabilen çok yönlü bir düzen öğesidir. Bu öğreticide, sayfa numarası için bir kapsayıcı oluşturmak için kullanılır; bu, geçerli sayfa numarasını ve toplam sayfa sayısını üstbilgi veya altbilgiye dinamik olarak eklemenize olanak tanır.

#### S: Sağlanan C# kaynak kodu, FloatingBox kullanarak sayfa numaraları eklemeyi nasıl başarır?

C: Kod pasajı, bir PDF belgesinin nasıl oluşturulacağını, bir sayfanın nasıl ekleneceğini, bir FloatingBox'un nasıl oluşturulacağını, sayfa içindeki konumunun nasıl ayarlanacağını ve bir TextFragment kullanarak sayfa numarasının nasıl ekleneceğini gösterir. TextFragment'teki "($p/ $P )" sözdizimi, geçerli sayfa numarası ve toplam sayfa sayısıyla değiştirilir.

#### S: FloatingBox kullanarak eklenen sayfa numarasının görünümünü ve formatını özelleştirebilir miyim?

C: Evet, FloatingBox içindeki TextFragment'in özelliklerini değiştirerek sayfa numarasının görünümünü özelleştirebilirsiniz. Yazı tipi boyutunu, rengini, stilini, hizalamasını ve diğer biçimlendirme seçeneklerini değiştirebilirsiniz.

#### S: Benzer bir yaklaşım kullanarak üst bilgi veya alt bilgiye tarih ve saat gibi farklı dinamik öğeler eklemek mümkün müdür?

C: Kesinlikle, FloatingBox içindeki TextFragment içeriğini değiştirerek tarih, saat, belge meta verileri veya özel metin gibi farklı dinamik öğeler ekleyebilirsiniz. Sayfa numaraları için "($p/ $P )" veya güncel tarih için "($date)" gibi makroları kullanabilirsiniz.

#### S: FloatingBox'un üstbilgi veya altbilgi bölümündeki konumunu nasıl belirlerim?
 C: Sağlanan kod, FloatingBox'un konumunu şunu kullanarak ayarlar:`Left` Ve`Top` özellikler. FloatingBox'ı üstbilgi veya altbilgi bölümünde istediğiniz gibi konumlandırmak için bu değerleri ayarlayabilirsiniz.

#### S: Üstbilgi veya altbilgideki sayfa numarası için farklı bir yazı tipi veya stil kullanabilir miyim?

C: Evet, FloatingBox içindeki TextFragment özelliklerini değiştirerek sayfa numarası metninin yazı tipi, stili ve diğer formatlama özelliklerini özelleştirebilirsiniz.

#### S: FloatingBox'taki içerik boyutlarını aşarsa ne olur?

C: FloatingBox içindeki içerik boyutlarını aşarsa kesilebilir veya düzen sorunları ortaya çıkabilir. FloatingBox'ın boyutlarının içeriğe uyum sağlamaya uygun olduğundan emin olun ve gerekirse sayfa düzenini ayarlamayı düşünün.

#### S: Aynı sayfanın üstbilgisine veya altbilgisine farklı içeriğe sahip birden fazla FloatingBox eklemek mümkün müdür?

C: Evet, ayrı FloatingBox örnekleri oluşturup bunları sayfanın Paragraphs koleksiyonuna ekleyerek aynı sayfanın üstbilgisine veya altbilgisine farklı içeriğe sahip birden fazla FloatingBox ekleyebilirsiniz.

#### S: PDF belgesinin gövde veya kenar boşlukları gibi diğer bölümlerine içerik eklemek için FloatingBox yaklaşımını kullanabilir miyim?

C: FloatingBox'lar genellikle üstbilgiler ve altbilgiler için kullanılsa da, bunları sayfa içinde uygun şekilde konumlandırarak PDF belgesinin gövde veya kenar boşlukları gibi diğer bölümlerine içerik eklemek için de kullanabilirsiniz.