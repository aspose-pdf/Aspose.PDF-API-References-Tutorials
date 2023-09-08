---
title: PDF Dosyasına TOC Ekle
linktitle: PDF Dosyasına TOC Ekle
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak PDF dosyasına içindekiler tablosunu nasıl ekleyeceğinizi öğrenin. Örnek kaynak koduyla adım adım kılavuz. Belge navigasyonunu artırın!
type: docs
weight: 40
url: /tr/net/programming-with-document/addtoc/
---
Bu eğitimde, Aspose.PDF for .NET'in PDF dosyasına TOC (İçindekiler Tablosu) Ekle özelliğinin PDF belgelerine içindekiler tablosu eklemek için nasıl kullanılacağını inceleyeceğiz. Adım adım bir kılavuz sunacağız ve bunu başarmak için gereken C# kaynak kodunu açıklayacağız. Bu eğitimin sonunda Aspose.PDF for .NET'i kullanarak içindekiler tablosu içeren bir PDF belgesi oluşturabileceksiniz.


## 1. Adım: Mevcut PDF dosyasını yükleyin

 Başlamak için mevcut bir PDF dosyasını yüklememiz gerekiyor. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` PDF dosyanızın gerçek yolunu içeren aşağıdaki kodda:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "AddTOC.pdf");
```

## 2. Adım: İçindekiler tablosu için yeni bir sayfa oluşturun

İçindekiler tablosunu tutmak için yeni bir sayfa oluşturacağız. Aşağıdaki kod, dizin 1'e yeni bir sayfa ekler:

```csharp
Page tocPage = doc.Pages.Insert(1);
```

## 3. Adım: İçindekiler bilgilerini tanımlayın

Daha sonra içindekiler bilgisini tanımlamamız gerekiyor. İçindekiler tablosunun başlığını ve diğer özelliklerini ayarlayacağız. Aşağıdaki kodu ekleyin:

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

## 4. Adım: İçindekiler öğelerini oluşturun

Şimdi içindekiler tablosunun elemanlarını oluşturacağız. Bu derste farklı sayfalara karşılık gelen dört TOC öğesi oluşturacağız. Aşağıdaki kodu gereksinimlerinize göre değiştirin:

```csharp
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";

for (int i = 0; i < 2; i++)
{
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);

    heading2.DestinationPage = doc.Pages[i + 2];
    heading2.Top = doc.Pages[i + 2].Rect.Height;

    segment2.Text = titles[i];
    tocPage.Paragraphs.Add(heading2);
}
```

## 5. Adım: Güncellenen belgeyi kaydedin

 Son olarak, değiştirilen belgeyi içindekiler tablosuyla birlikte kaydetmemiz gerekiyor. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` istenen çıktı dosyası yolu ile aşağıdaki kodda:

```csharp
dataDir = dataDir + "TOC_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

### Aspose.PDF for .NET kullanarak PDF belgelerine TOC eklemek için örnek kaynak kodu

```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Mevcut bir PDF dosyasını yükleyin
Document doc = new Document(dataDir + "AddTOC.pdf");

// PDF dosyasının ilk sayfasına erişin
Page tocPage = doc.Pages.Insert(1);

// İçindekiler bilgisini temsil edecek nesne oluşturun
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

// İçindekiler başlığını ayarlayın
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;

//TOC öğeleri olarak kullanılacak dize nesneleri oluşturun
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";
for (int i = 0; i < 2; i++)
{
	// Başlık nesnesi oluştur
	Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
	TextSegment segment2 = new TextSegment();
	heading2.TocPage = tocPage;
	heading2.Segments.Add(segment2);

	// Başlık nesnesi için hedef sayfayı belirtin
	heading2.DestinationPage = doc.Pages[i + 2];

	// Hedef sayfası
	heading2.Top = doc.Pages[i + 2].Rect.Height;

	// Hedef koordinatı
	segment2.Text = titles[i];

	// İçindekiler içeren sayfaya başlık ekleyin
	tocPage.Paragraphs.Add(heading2);
}
dataDir = dataDir + "TOC_out.pdf";
// Güncellenen belgeyi kaydet
doc.Save(dataDir);

Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

## Çözüm

Bu eğitimde Aspose.PDF for .NET kullanarak PDF belgelerine içindekiler tablosunun (TOC) nasıl ekleneceğini araştırdık. Adım adım kılavuzu takip ederek ve sağlanan C# kaynak kodunu kullanarak, kolayca içindekiler tablosu içeren bir PDF belgesi oluşturabilirsiniz. İçindekiler belgesinin kullanılabilirliğini geliştirerek kullanıcıların belirli bölümlere veya sayfalara daha verimli bir şekilde gitmesine olanak tanır. Aspose.PDF for .NET, .NET uygulamalarında PDF dosyalarıyla çalışmak için sağlam ve kullanıcı dostu bir çözüm sunarak kolaylıkla dinamik ve etkileşimli PDF belgeleri oluşturmanıza olanak tanır.

### PDF dosyasına TOC eklemek için SSS

#### S: Aspose.PDF for .NET nedir?

C: Aspose.PDF for .NET, geliştiricilerin .NET uygulamalarındaki PDF dosyalarıyla etkili bir şekilde çalışmasına olanak tanıyan güçlü bir kitaplıktır. PDF belgelerini programlı olarak oluşturmak, değiştirmek ve yönetmek için çok çeşitli özellikler sunar.

#### S: Bir PDF belgesine içindekiler tablosu (TOC) eklemenin amacı nedir?

C: İçindekiler tablosu (TOC), kullanıcılara PDF belgesindeki belirli bölümlere veya sayfalara hızlı bir şekilde atlamalarını sağlayan bir gezinme yardımı sağlar. Belgenin kullanılabilirliğini ve kullanıcı deneyimini geliştirir.

#### S: Aspose.PDF for .NET kullanarak bir PDF belgesine içindekiler tablosunu nasıl eklerim?

C: Aspose.PDF for .NET kullanarak bir PDF belgesine içindekiler tablosu eklemek için, TOC'yi tutacak yeni bir sayfa oluşturmanız, içindekiler tablosu bilgilerini tanımlamanız ve ardından belirli sayfalara veya bunlara karşılık gelen TOC öğeleri oluşturmanız gerekir. belgedeki bölümler.

#### S: İçindekiler tablosunun görünümünü özelleştirebilir miyim?

C: Evet, içindekiler tablosu öğelerinin yazı tipi boyutu, yazı tipi stili ve hizalama gibi çeşitli özelliklerini ayarlayarak içindekiler tablosunun görünümünü özelleştirebilirsiniz. Aspose.PDF for .NET, TOC'yi istediğiniz görünüm ve hisle eşleşecek şekilde tasarlama konusunda esneklik sağlar.

#### S: Aspose.PDF for .NET, PDF belgelerine gelişmiş özellikler eklemek için uygun mudur?

C: Kesinlikle, Aspose.PDF for .NET, PDF belgelerine etkileşimli öğeler, form alanları, dijital imzalar ve daha fazlasını içeren gelişmiş işlevler eklemenizi sağlayan, zengin özelliklere sahip bir kitaplıktır.