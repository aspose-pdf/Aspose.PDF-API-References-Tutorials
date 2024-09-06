---
title: Üstbilgi Altbilgide Yüzen Kutu Kullanarak Sayfa Numarası
linktitle: Üstbilgi Altbilgide Yüzen Kutu Kullanarak Sayfa Numarası
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile bir PDF belgesinin üst bilgi ve alt bilgisine sayfa numarasının nasıl ekleneceğini öğrenin.
type: docs
weight: 150
url: /tr/net/programming-with-stamps-and-watermarks/page-number-in-header-footer-using-floating-box/
---
Bu eğitimde, .NET için Aspose.PDF ile FloatingBox kullanarak bir PDF belgesinin üst bilgisine ve alt bilgisine sayfa numarasının nasıl ekleneceğini adım adım göstereceğiz. Sağlanan C# kaynak kodunu kullanarak bir PDF belgesi oluşturacağız, bir sayfa ekleyeceğiz, bir FloatingBox oluşturacağız, konumunu ayarlayıp sayfa numarasını ekleyeceğiz ve ardından değiştirilmiş PDF belgesini kaydedeceğiz.

## Adım 1: Ortamı kurma

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Kurulu bir .NET geliştirme ortamı.
- .NET için Aspose.PDF kütüphanesi indirildi ve projenizde referans olarak kullanıldı.

## Adım 2: PDF belgesini oluşturma ve bir sayfa ekleme

İlk adım, PDF belgesinin bir örneğini oluşturmak ve ona bir sayfa eklemektir. İşte nasıl:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// PDF belgesini örneklendirin
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// PDF belgesine bir sayfa ekleyin
Aspose.Pdf.Page page = pdf.Pages.Add();
```

"BELGELERİNİZ DİZİNİ" ifadesini PDF belgenizi kaydetmek istediğiniz dizinin gerçek yoluyla değiştirdiğinizden emin olun.

## Adım 3: FloatingBox'ı oluşturma ve sayfa numarasını ekleme

Sayfa artık PDF belgesine eklendiğine göre, bir FloatingBox oluşturabilir, konumunu ayarlayabilir ve sayfa numarasını ekleyebiliriz. İşte nasıl:

```csharp
// 140 genişliğinde ve 80 yüksekliğinde bir FloatingBox oluşturun
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// Paragrafın sol konumunu ayarlayın
box1. Left = 2;

// Paragrafın en üst konumunu ayarlayın
box1. Top = 10;

// Sayfa numarasını FloatingBox'a ekleyin
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// Sayfaya FloatingBox ekleyin
page.Paragraphs.Add(box1);
```

Yukarıdaki kod, 140 genişliğinde ve 80 yüksekliğinde bir FloatingBox oluşturur. Sonra, sol ve üst değerlerini belirterek konumunu ayarlarız. Son olarak, "($p/ $P )" sözdizimini içeren bir TextFragment kullanarak sayfa numarasını FloatingBox'a ekleriz; bu, geçerli sayfa numarası ve toplam sayfa sayısıyla değiştirilecektir.

## Adım 4: Değiştirilen PDF belgesinin kaydedilmesi

Sayfa numarası FloatingBox kullanılarak üstbilgiye veya altbilgiye eklendiğinde, değiştirilmiş PDF belgesini kaydedebiliriz. İşte nasıl:

```csharp
// Değiştirilen PDF belgesini kaydedin
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");
```

Yukarıdaki kod düzenlenen PDF belgesini belirtilen dizine kaydeder.

### .NET için Aspose.PDF kullanarak Yüzen Kutu Kullanarak Sayfa Numarası için Başlık Alt Bilgi için örnek kaynak kodu 
```csharp

// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belge örneğini örneklendir
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// PDF belgesine bir Sayfa ekleyin
Aspose.Pdf.Page page = pdf.Pages.Add();

// FloatingBox sınıfının yeni bir örneğini başlatır
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// Paragrafın sol konumunu gösteren kayan nokta değeri
box1.Left = 2;

// Paragrafın en üst konumunu gösteren kayan nokta değeri
box1.Top = 10;

// Makroları FloatingBox'ın paragraf koleksiyonuna ekleyin
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// Sayfaya bir floatingBox ekleyin
page.Paragraphs.Add(box1);

// Belgeyi kaydet
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");

```

## Çözüm

Tebrikler! FloatingBox with Aspose.PDF for .NET kullanarak PDF belgesinin üstbilgi ve altbilgisine sayfa numarası eklemeyi öğrendiniz. Artık sayfa numarası gibi dinamik bilgiler ekleyerek üstbilgi ve altbilgilerinizi özelleştirebilirsiniz.

### SSS

#### S: FloatingBox nedir ve bir PDF belgesinin üst bilgi veya alt bilgisine sayfa numaraları eklemek için nasıl kullanılır?

A: FloatingBox, Aspose.PDF'de metin ve resimler dahil olmak üzere çeşitli içerikleri tutabilen çok yönlü bir düzen öğesidir. Bu eğitimde, sayfa numarası için bir kapsayıcı oluşturmak için kullanılır ve geçerli sayfa numarasını ve toplam sayfa sayısını üstbilgiye veya altbilgiye dinamik olarak eklemenize olanak tanır.

#### S: Sağlanan C# kaynak kodunda FloatingBox kullanılarak sayfa numaraları nasıl ekleniyor?

A: Kod parçacığı bir PDF belgesinin nasıl oluşturulacağını, bir sayfanın nasıl ekleneceğini, bir FloatingBox'ın nasıl oluşturulacağını, sayfadaki konumunun nasıl ayarlanacağını ve bir TextFragment kullanılarak sayfa numarasının nasıl ekleneceğini gösterir. TextFragment'taki "($p/ $P )" sözdizimi geçerli sayfa numarası ve toplam sayfa sayısıyla değiştirilir.

#### S: FloatingBox kullanılarak eklenen sayfa numarasının görünümünü ve biçimlendirmesini özelleştirebilir miyim?

A: Evet, FloatingBox içindeki TextFragment'ın özelliklerini değiştirerek sayfa numarasının görünümünü özelleştirebilirsiniz. Yazı tipi boyutunu, rengini, stilini, hizalamasını ve diğer biçimlendirme seçeneklerini değiştirebilirsiniz.

#### S: Benzer bir yaklaşımla üstbilgi veya altbilgiye tarih ve saat gibi farklı dinamik öğeler eklemek mümkün müdür?

A: Kesinlikle, FloatingBox içindeki TextFragment içeriğini değiştirerek tarih, saat, belge meta verileri veya özel metin gibi farklı dinamik öğeler ekleyebilirsiniz. Sayfa numaraları için "($p/ $P )" veya geçerli tarih için "($date)" gibi makrolar kullanabilirsiniz.

#### S: FloatingBox'ın başlık veya altbilgi bölümündeki konumunu nasıl belirlerim?
 A: Sağlanan kod, FloatingBox'ın konumunu şu şekilde ayarlar:`Left` Ve`Top` özellikleri. Bu değerleri ayarlayarak FloatingBox'ı başlık veya altbilgi bölümünde istediğiniz gibi konumlandırabilirsiniz.

#### S: Üstbilgi veya altbilgideki sayfa numarası için farklı bir yazı tipi veya stil kullanabilir miyim?

C: Evet, FloatingBox içindeki TextFragment özelliklerini değiştirerek sayfa numarası metninin yazı tipini, stilini ve diğer biçimlendirme özelliklerini özelleştirebilirsiniz.

#### S: FloatingBox'taki içerik boyutlarını aşarsa ne olur?

A: FloatingBox içindeki içerik boyutlarını aşarsa, kesilebilir veya düzen sorunları ortaya çıkabilir. FloatingBox boyutlarının içeriği barındırmaya uygun olduğundan emin olun ve gerekirse sayfa düzenini ayarlamayı düşünün.

#### S: Aynı sayfanın üst bilgisine veya alt bilgisine farklı içeriklere sahip birden fazla FloatingBox eklemek mümkün müdür?

C: Evet, aynı sayfanın üst bilgisine veya alt bilgisine farklı içeriklere sahip birden fazla FloatingBox ekleyebilirsiniz. Bunun için ayrı FloatingBox örnekleri oluşturup bunları sayfanın Paragraflar koleksiyonuna ekleyebilirsiniz.

#### S: FloatingBox yaklaşımını PDF belgesinin gövde veya kenar boşlukları gibi diğer bölümlerine içerik eklemek için kullanabilir miyim?

A: FloatingBox'lar genellikle başlıklar ve altbilgiler için kullanılsa da, bunları sayfanın içinde uygun şekilde konumlandırarak PDF belgesinin gövde veya kenar boşlukları gibi diğer bölümlerine içerik eklemek için de kullanabilirsiniz.