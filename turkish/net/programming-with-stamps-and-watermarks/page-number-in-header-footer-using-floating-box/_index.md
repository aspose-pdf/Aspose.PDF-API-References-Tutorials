---
title: Kayan Kutu Kullanılarak Üst Bilgi Alt Bilgideki Sayfa Numarası
linktitle: Kayan Kutu Kullanılarak Üst Bilgi Alt Bilgideki Sayfa Numarası
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

// Paragrafın sol konumunu ayarla
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

// Sayfaya bir floatBox ekleyin
page.Paragraphs.Add(box1);

// belgeyi kaydet
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");

```

## Çözüm

Tebrikler! Aspose.PDF for .NET ile FloatingBox kullanarak PDF belgesinin üstbilgisine ve altbilgisine sayfa numarası eklemeyi öğrendiniz. Artık sayfa numarası gibi dinamik bilgiler ekleyerek üstbilgilerinizi ve altbilgilerinizi özelleştirebilirsiniz.
