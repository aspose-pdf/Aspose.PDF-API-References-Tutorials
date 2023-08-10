---
title: PDF Dosyasına İçindekiler Ekle
linktitle: PDF Dosyasına İçindekiler Ekle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyasına içindekiler tablosunu nasıl ekleyeceğinizi öğrenin. Örnek kaynak koduyla adım adım kılavuz. Doküman gezintisini artırın!
type: docs
weight: 40
url: /tr/net/programming-with-document/addtoc/
---
Bu öğreticide, PDF belgelerine bir içindekiler tablosu eklemek için Aspose.PDF for .NET'in PDF dosyasına TOC (İçindekiler Tablosu) ekle özelliğinin nasıl kullanılacağını keşfedeceğiz. Adım adım bir kılavuz sunacağız ve bunu başarmak için gereken C# kaynak kodunu açıklayacağız. Bu eğitimin sonunda, Aspose.PDF for .NET kullanarak içindekiler tablosu içeren bir PDF belgesi oluşturabileceksiniz.


## 1. Adım: Mevcut PDF dosyasını yükleyin

 Başlamak için mevcut bir PDF dosyasını yüklememiz gerekiyor. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` PDF dosyanızın gerçek yolu ile aşağıdaki kodda:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "AddTOC.pdf");
```

## 2. Adım: İçindekiler için yeni bir sayfa oluşturun

İçindekiler tablosunu tutmak için yeni bir sayfa oluşturacağız. Aşağıdaki kod, dizin 1'e yeni bir sayfa ekler:

```csharp
Page tocPage = doc.Pages.Insert(1);
```

## 3. Adım: İçindekiler tablosu bilgilerini tanımlayın

Ardından, içindekiler tablosu bilgilerini tanımlamamız gerekiyor. İçindekiler tablosunun başlığını ve diğer özelliklerini ayarlayacağız. Aşağıdaki kodu ekleyin:

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

## 4. Adım: İçindekiler öğelerini oluşturun

Şimdi, içindekiler tablosunun öğelerini oluşturacağız. Bu öğreticide, farklı sayfalara karşılık gelen dört TOC öğesi oluşturacağız. Aşağıdaki kodu gereksinimlerinize göre değiştirin:

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

 Son olarak, değiştirilen belgeyi içindekiler tablosuyla kaydetmemiz gerekiyor. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` istenen çıktı dosyası yolu ile aşağıdaki kodda:

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

// İçindekiler bilgisini temsil edecek nesne oluştur
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

// İçindekiler için başlığı ayarla
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;

//İçindekiler öğesi olarak kullanılacak dize nesneleri oluşturun
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

	// hedef sayfa
	heading2.Top = doc.Pages[i + 2].Rect.Height;

	// hedef koordinat
	segment2.Text = titles[i];

	// İçindekiler içeren sayfaya başlık ekle
	tocPage.Paragraphs.Add(heading2);
}
dataDir = dataDir + "TOC_out.pdf";
// Güncellenen belgeyi kaydedin
doc.Save(dataDir);

Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

## Çözüm

Bu eğitimde, Aspose.PDF for .NET kullanarak PDF belgelerine içindekiler tablosunun (TOC) nasıl ekleneceğini inceledik. Adım adım kılavuzu izleyerek ve sağlanan C# kaynak kodunu kullanarak içindekiler tablosu içeren bir PDF belgesini kolayca oluşturabilirsiniz. İçindekiler belgesi, kullanıcıların belirli bölümlerde veya sayfalarda daha verimli gezinmesine izin vererek belgenin kullanılabilirliğini artırır. Aspose.PDF for .NET, .NET uygulamalarında PDF dosyalarıyla çalışmak için sağlam ve kullanıcı dostu bir çözüm sunarak kolaylıkla dinamik ve etkileşimli PDF belgeleri oluşturmanıza olanak tanır.

### PDF dosyasına TOC eklemek için SSS

#### S: Aspose.PDF for .NET nedir?

Y: Aspose.PDF for .NET, geliştiricilerin .NET uygulamalarında PDF dosyalarıyla etkili bir şekilde çalışmasına olanak tanıyan güçlü bir kitaplıktır. PDF belgelerini programlı olarak oluşturmak, işlemek ve yönetmek için çok çeşitli özellikler sağlar.

#### S: Bir PDF belgesine içindekiler tablosu (TOC) eklemenin amacı nedir?

C: İçindekiler tablosu (TOC), kullanıcılara PDF belgesindeki belirli bölümlere veya sayfalara hızlı bir şekilde atlamalarını sağlayan bir gezinme yardımı sağlar. Belgenin kullanılabilirliğini ve kullanıcı deneyimini geliştirir.

#### S: Aspose.PDF for .NET kullanarak bir PDF belgesine içindekiler tablosunu nasıl eklerim?

C: Aspose.PDF for .NET'i kullanarak bir PDF belgesine içindekiler tablosu eklemek için, İçindekiler'i tutmak için yeni bir sayfa oluşturmanız, içindekiler tablosu bilgilerini tanımlamanız ve ardından belirli sayfalara veya belgedeki bölümler.

#### S: İçindekiler tablosunun görünümünü özelleştirebilir miyim?

C: Evet, İçindekiler öğelerinin yazı tipi boyutu, yazı tipi stili ve hizalama gibi çeşitli özelliklerini ayarlayarak içindekiler tablosunun görünümünü özelleştirebilirsiniz. Aspose.PDF for .NET, TOC'yi istediğiniz görünüm ve hisse uyacak şekilde tasarlamada esneklik sağlar.

#### S: Aspose.PDF for .NET, PDF belgelerine gelişmiş özellikler eklemek için uygun mu?

Y: Kesinlikle, Aspose.PDF for .NET, PDF belgelerine etkileşimli öğeler, form alanları, dijital imzalar ve daha fazlası dahil olmak üzere gelişmiş işlevler eklemenizi sağlayan, zengin özelliklere sahip bir kitaplıktır.