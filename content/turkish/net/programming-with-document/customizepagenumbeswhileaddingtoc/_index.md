---
title: İçindekiler Eklerken Sayfa Numaralarını Özelleştirin
linktitle: İçindekiler Eklerken Sayfa Numaralarını Özelleştirin
second_title: .NET API Referansı için Aspose.PDF
description: Bu adım adım kılavuz ve kod örneğiyle Aspose.PDF for .NET kullanarak içindekiler tablosu (TOC) eklerken sayfa numaralarını nasıl özelleştireceğinizi öğrenin.
type: docs
weight: 100
url: /tr/net/programming-with-document/customizepagenumbeswhileaddingtoc/
---
Bu eğitimde Aspose.PDF for .NET kullanarak içindekiler tablosu (TOC) eklerken sayfa numaralarının nasıl özelleştirileceğini inceleyeceğiz. Bunu başarmanıza yardımcı olmak için bir kod örneğiyle birlikte adım adım rehberlik sağlayacağız.

## 1. Adım: Mevcut bir PDF dosyasını yükleme

Öncelikle mevcut bir PDF dosyasını yüklememiz gerekiyor. Bu eğitim için "BELGE DİZİNİNİZ" dizininde bulunan "42824.pdf" dosyasını kullanacağız. Bu dizin yolunu, belge dizininizin gerçek yoluyla değiştirin.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
Document doc = new Document(inFile);
```

## 2. Adım: İçindekiler sayfası ekleme

 Daha sonra, belgenin başına TOC sayfası olarak hizmet verecek yeni bir sayfa eklememiz gerekiyor. kullanarak bunu başarabiliriz.`Insert()` yöntemi`Pages` koleksiyonu`Document` nesne.

```csharp
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
```

## 3. Adım: TOC nesnesi oluşturma

 Bir TOC nesnesi oluşturmak için öncelikle bir`TocInfo` nesneyi seçin ve özelliklerini ayarlayın. Bu eğitimde, TOC'nin başlığını "İçindekiler Tablosu" ve sayfa numarası önekini "P" olarak ayarlayacağız.

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
```

## 4. Adım: İçindekiler girişlerini oluşturma

İçindekiler girdileri oluşturmak için, içindekiler sayfası dışındaki belgenin tüm sayfaları arasında döngü yapmamız ve her sayfa için bir başlık nesnesi oluşturmamız gerekir. Daha sonra başlık nesnesini TOC sayfasına ekleyebilir ve hedef sayfasını belirtebiliriz.

```csharp
for (int i = 1; i < doc.Pages.Count; i++)
{
    // Başlık nesnesi oluştur
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);
    // Başlık nesnesi için hedef sayfayı belirtin
    heading2.DestinationPage = doc.Pages[i + 1];
    // Hedef sayfası
    heading2.Top = doc.Pages[i + 1].Rect.Height;
    // Hedef koordinatı
    segment2.Text = "Page " + i.ToString();
    // İçindekiler içeren sayfaya başlık ekleyin
    tocPage.Paragraphs.Add(heading2);
}
```

## 5. Adım: Güncellenen belgeyi kaydetme

Son olarak güncellenen belgeyi yeni bir dosyaya kaydetmemiz gerekiyor. kullanarak bunu başarabiliriz.`Save()` yöntemi`Document` nesne.

```csharp
doc.Save(outFile);
```

### Aspose.PDF for .NET kullanarak İçindekiler eklerken sayfa numaralarını özelleştirmek için örnek kaynak kodu

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
// Mevcut bir PDF dosyasını yükleyin
Document doc = new Document(inFile);
// PDF dosyasının ilk sayfasına erişin
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
// İçindekiler bilgisini temsil edecek nesne oluşturun
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
// İçindekiler başlığını ayarlayın
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
for (int i = 1; i<doc.Pages.Count; i++)
{
	// Başlık nesnesi oluştur
	Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
	TextSegment segment2 = new TextSegment();
	heading2.TocPage = tocPage;
	heading2.Segments.Add(segment2);
	// Başlık nesnesi için hedef sayfayı belirtin
	heading2.DestinationPage = doc.Pages[i + 1];
	// Hedef sayfası
	heading2.Top = doc.Pages[i + 1].Rect.Height;
	// Hedef koordinatı
	segment2.Text = "Page " + i.ToString();
	// İçindekiler içeren sayfaya başlık ekleyin
	tocPage.Paragraphs.Add(heading2);
}

// Güncellenen belgeyi kaydet
doc.Save(outFile);
```

## Çözüm

Bu eğitimde Aspose.PDF for .NET kullanarak TOC eklerken sayfa numaralarının nasıl özelleştirileceği konusunda adım adım rehberlik sağladık. Ayrıca bu özelliği uygulamanıza uygularken referans olarak kullanabileceğiniz bir kod örneği de sunduk.

### SSS'ler

#### S: PDF belgesindeki içindekiler tablosu (TOC) nedir?

C: Bir PDF belgesindeki içindekiler tablosu (TOC), ilgili sayfa numaralarıyla birlikte belge bölümlerinin veya bölümlerinin düzenli bir listesini sağlayan bir gezinme yardımcısıdır. Okuyucuların belge içindeki belirli bölümlere hızlı bir şekilde gitmesine olanak tanır.

#### S:Neden bir İçindekiler Tablosunda sayfa numaralarını özelleştirmek isteyeyim?

C: Belirli bir sayfa numaralandırma biçimini kullanmak veya sayfa numaralarıyla birlikte ek bilgiler eklemek istediğinizde, içindekiler tablosundaki sayfa numaralarını özelleştirmek yararlı olabilir. Daha kişiselleştirilmiş ve bilgilendirici bir içindekiler tablosu oluşturmanıza olanak tanır.

#### S: PDF belgesindeki belirli bölümlere veya sayfalara bağlantı vermek için İçindekiler'e köprüler ekleyebilir miyim?

C: Evet, Aspose.PDF for .NET, TOC'de PDF belgesindeki belirli bölümlere veya sayfalara bağlantı veren köprüler oluşturmanıza olanak tanır. Bu, PDF belgesinin etkileşimini ve gezinmesini geliştirir.

#### S: Aspose.PDF for .NET, PDF/A standartlarıyla uyumlu mu?

C: Evet, Aspose.PDF for .NET, PDF/A-1, PDF/A-2 ve PDF/A-3 dahil olmak üzere PDF/A standartlarını destekler. Arşivleme ve uzun süreli saklama gereksinimlerine uygun PDF belgeleri oluşturmanıza olanak tanır.

#### S: İçindekiler girişlerine yazı tipi stilleri veya renkler gibi daha fazla biçimlendirme ekleyebilir miyim?

C: Evet, Aspose.PDF for .NET'i kullanarak TOC girişlerine yazı tipi stilleri, renkler ve yazı tipi boyutları gibi ek biçimlendirmeler ekleyebilirsiniz. Bu, TOC'nin görünümünü gereksinimlerinize göre özelleştirmenize olanak tanır.
