---
title: Kayan Kutu Kullanılarak Üst Bilgi Alt Bilgide Sayfa Numarası
linktitle: Kayan Kutu Kullanılarak Üst Bilgi Alt Bilgide Sayfa Numarası
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile bir PDF belgesinin üstbilgisine ve altbilgisine sayfa numarasını nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 150
url: /tr/net/programming-with-stamps-and-watermarks/page-number-in-header-footer-using-floating-box/
---
Bu eğitimde, Aspose.PDF for .NET ile FloatingBox kullanarak bir PDF belgesinin üstbilgisine ve altbilgisine nasıl sayfa numarası ekleyeceğiniz konusunda size adım adım rehberlik edeceğiz. Sağlanan C# kaynak kodunu bir PDF belgesi oluşturmak, bir sayfa eklemek, bir FloatingBox oluşturmak, konumunu ayarlamak ve ona sayfa numarasını eklemek, ardından değiştirilen PDF belgesini kaydetmek için kullanacağız.

## 1. Adım: Ortamı ayarlama

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Yüklü bir .NET geliştirme ortamı.
- .NET için Aspose.PDF kitaplığı indirildi ve projenizde referans verildi.

## 2. Adım: PDF belgesini oluşturma ve bir sayfa ekleme

İlk adım, PDF belgesinin bir örneğini oluşturmak ve buna bir sayfa eklemektir. İşte nasıl:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// PDF belgesini somutlaştırın
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// PDF belgesine bir sayfa ekleyin
Aspose.Pdf.Page page = pdf.Pages.Add();
```

"BELGELER DİZİNİNİZİ", PDF belgesini kaydetmek istediğiniz dizinin gerçek yolu ile değiştirdiğinizden emin olun.

## 3. Adım: FloatingBox'ı oluşturma ve sayfa numarasını ekleme

Artık sayfa PDF belgesine eklendiğine göre FloatingBox oluşturabilir, konumunu ayarlayabilir ve sayfa numarasını ona ekleyebiliriz. İşte nasıl:

```csharp
// Genişliği 140 ve yüksekliği 80 olan bir FloatingBox oluşturun
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

//Paragrafın sol konumunu ayarla
box1. Left = 2;

// Paragrafın üst konumunu ayarla
box1. Top = 10;

// Sayfa numarasını FloatingBox'a ekleyin
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// FloatingBox'ı sayfaya ekleyin
page.Paragraphs.Add(box1);
```

Yukarıdaki kod, 140 genişliğinde ve 80 yüksekliğinde bir FloatingBox oluşturuyor. Ardından, sol ve üst değerleri belirterek konumunu ayarlıyoruz. Son olarak, geçerli sayfa numarası ve toplam sayfa sayısı ile değiştirilecek olan "($p/ $P )" sözdizimini içeren bir TextFragment kullanarak sayfa numarasını FloatingBox'a ekliyoruz.

## 4. Adım: Değiştirilen PDF belgesini kaydetme

FloatingBox kullanılarak üst bilgiye veya alt bilgiye sayfa numarası eklendikten sonra, değiştirilen PDF belgesini kaydedebiliriz. İşte nasıl:

```csharp
// Değiştirilen PDF belgesini kaydedin
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");
```

Yukarıdaki kod, düzenlenen PDF belgesini belirtilen dizine kaydeder.

### Aspose.PDF for .NET kullanarak Floating Box Kullanan Sayfa NumarasıÜstbilgi Altbilgi için örnek kaynak kodu 
```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belge örneği örneği
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// Pdf belgesine bir Sayfa ekleyin
Aspose.Pdf.Page page = pdf.Pages.Add();

// FloatingBox sınıfının yeni bir örneğini başlatır
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// Paragrafın sol konumunu gösteren kayan değer
box1.Left = 2;

// Paragrafın üst konumunu gösteren kayan değer
box1.Top = 10;

// Makroları FloatingBox'ın paragraf koleksiyonuna ekleyin
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

//Sayfaya bir floatBox ekleyin
page.Paragraphs.Add(box1);

// belgeyi kaydet
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");

```

## Çözüm

Tebrikler! Aspose.PDF for .NET ile FloatingBox kullanarak PDF belgesinin üstbilgisine ve altbilgisine sayfa numarası eklemeyi öğrendiniz. Artık sayfa numarası gibi dinamik bilgiler ekleyerek üstbilgilerinizi ve altbilgilerinizi özelleştirebilirsiniz.

### SSS

#### S: FloatingBox nedir ve bir PDF belgesinin üstbilgisine veya altbilgisine sayfa numaraları eklemek için nasıl kullanılır?

C: Bir FloatingBox, Aspose.PDF'de metin ve resimler de dahil olmak üzere çeşitli içerikleri tutabilen çok yönlü bir düzen öğesidir. Bu öğreticide, geçerli sayfa numarasını ve toplam sayfa sayısını üstbilgiye veya altbilgiye dinamik olarak eklemenize olanak tanıyan sayfa numarası için bir kap oluşturmak için kullanılır.

#### S: Sağlanan C# kaynak kodu, bir FloatingBox kullanarak sayfa numaraları eklemeyi nasıl başarıyor?

A: Kod parçacığı, bir PDF belgesinin nasıl oluşturulacağını, bir sayfanın nasıl ekleneceğini, bir FloatingBox'ın nasıl oluşturulacağını, sayfa içindeki konumunun nasıl ayarlanacağını ve bir TextFragment kullanarak sayfa numarasının nasıl ekleneceğini gösterir. TextFragment içindeki "($p/ $P )" sözdizimi, geçerli sayfa numarası ve toplam sayfa sayısı ile değiştirilir.

#### S: FloatingBox kullanılarak eklenen sayfa numarasının görünümünü ve biçimlendirmesini özelleştirebilir miyim?

C: Evet, FloatingBox içindeki TextFragment özelliklerini değiştirerek sayfa numarasının görünümünü özelleştirebilirsiniz. Yazı tipi boyutunu, rengini, stilini, hizalamasını ve diğer biçimlendirme seçeneklerini değiştirebilirsiniz.

#### S: Benzer bir yaklaşım kullanarak üst bilgiye veya alt bilgiye tarih ve saat gibi farklı dinamik öğeler eklemek mümkün müdür?

C: Kesinlikle, FloatingBox içindeki TextFragment içeriğini değiştirerek tarih, saat, belge meta verileri veya özel metin gibi farklı dinamik öğeler ekleyebilirsiniz. Sayfa numaraları için "($p/ $P )" veya geçerli tarih için "($date)" gibi makrolar kullanabilirsiniz.

#### S: FloatingBox'ın üst bilgi veya alt bilgi bölümündeki konumunu nasıl belirlerim?
 A: Sağlanan kod, FloatingBox'ın konumunu kullanarak ayarlar.`Left` Ve`Top` özellikler. FloatingBox'ı üst bilgi veya alt bilgi bölümünde istediğiniz gibi konumlandırmak için bu değerleri ayarlayabilirsiniz.

#### S: Üstbilgi veya altbilgideki sayfa numarası için farklı bir yazı tipi veya stil kullanabilir miyim?

C: Evet, FloatingBox içindeki TextFragment özelliklerini değiştirerek sayfa numarası metninin yazı tipini, stilini ve diğer biçimlendirme özelliklerini özelleştirebilirsiniz.

#### S: FloatingBox'taki içerik boyutlarını aşarsa ne olur?

C: FloatingBox içindeki içerik boyutlarını aşarsa kesilebilir veya yerleşim sorunları ortaya çıkabilir. FloatingBox boyutlarının içeriği barındırmaya uygun olduğundan emin olun ve gerekirse sayfa düzenini ayarlamayı düşünün.

#### S: Aynı sayfanın üstbilgisine veya altbilgisine farklı içeriğe sahip birden fazla FloatingBox eklemek mümkün müdür?

C: Evet, ayrı FloatingBox örnekleri oluşturarak ve bunları sayfanın Paragraphs koleksiyonuna ekleyerek aynı sayfanın üstbilgisine veya altbilgisine farklı içeriğe sahip birden fazla FloatingBox ekleyebilirsiniz.

#### S: PDF belgesinin gövde veya kenar boşlukları gibi diğer bölümlerine içerik eklemek için FloatingBox yaklaşımını kullanabilir miyim?

C: FloatingBox'lar genellikle üstbilgiler ve altbilgiler için kullanılsa da, bunları sayfa içinde uygun şekilde konumlandırarak PDF belgesinin gövde veya kenar boşlukları gibi diğer bölümlerine içerik eklemek için de kullanabilirsiniz.