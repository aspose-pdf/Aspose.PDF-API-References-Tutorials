---
title: İçindekiler Tablosunda Sayfa Numaralarını Gizle
linktitle: İçindekiler Tablosunda Sayfa Numaralarını Gizle
second_title: .NET API Referansı için Aspose.PDF
description: Bu adım adım kılavuzla Aspose.PDF for .NET kullanarak içindekiler tablosundaki sayfa numaralarını nasıl gizleyeceğinizi öğrenin.
type: docs
weight: 220
url: /tr/net/programming-with-document/hidepagenumbersintoc/
---
Bu yazıda Aspose.PDF for .NET'in TOC'deki Sayfa Numaralarını Gizle özelliğinin C# kullanarak uygulanmasını tartışacağız. Aspose.PDF for .NET'e kısa bir girişle başlayacağız ve ardından bu özelliği uygulamaya yönelik adım adım kılavuza geçeceğiz. 

## Aspose.PDF for .NET'e giriş

Aspose.PDF for .NET, geliştiricilerin PDF dosyalarını programlı olarak oluşturmasına, düzenlemesine ve işlemesine olanak tanıyan güçlü bir PDF işleme bileşenidir. PDF belgeleriyle çalışmayı kolaylaştıran çok çeşitli özellikler ve işlevler sunar. Aspose.PDF for .NET hem 32 bit hem de 64 bit işletim sistemlerini destekler ve .NET Framework, .NET Core ve Xamarin platformlarıyla kullanılabilir. 

## İçindekiler Tablosunda Sayfa Numaralarını Gizle özelliği nedir?

İçindekiler Tablosu (TOC), kullanıcılara içeriğe hızlı bir genel bakış sağlayan bir PDF belgesinin önemli bir parçasıdır. Bazen kullanıcılar, TOC'yi daha kullanıcı dostu hale getirmek için sayfa numaralarını gizlemek isteyebilir. Aspose.PDF for .NET, TOC'deki sayfa numaralarını gizlemek için yerleşik bir özellik sağlar. Bu özellik, daha kullanıcı dostu PDF belgeleri oluşturmak için kullanılabilir. 

## Önkoşullar

Bu öğreticiyi takip etmek için aşağıdakilere ihtiyacınız olacak:

- Visual Studio 2010 veya üzeri
- Aspose.PDF for .NET sisteminizde yüklü
- C# programlama dili hakkında temel bilgi

## İçindekiler Tablosunda Sayfa Numaralarını Gizle özelliğini uygulamaya yönelik adım adım kılavuz

Aspose.PDF for .NET kullanarak İçindekiler Tablosunda Sayfa Numaralarını Gizle özelliğini uygulamak için aşağıdaki adımları izleyin:

## Adım 1: Visual Studio'da yeni bir C# konsol uygulaması oluşturun

Visual Studio'yu açın ve yeni bir C# konsol uygulaması oluşturun.

## Adım 2: Aspose.PDF for .NET'e referans ekleyin

Projenizdeki Referanslar klasörüne sağ tıklayın ve Referans Ekle'yi seçin. Aspose.PDF for .NET'in sisteminizde kurulu olduğu konuma göz atın ve buraya bir referans ekleyin.

## 1. Adım: Yeni bir PDF belgesi oluşturun

Aşağıdaki kodu kullanarak yeni bir PDF belgesi oluşturun:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
```

## 2. Adım: İçindekiler sayfası oluşturun

İçindekiler için yeni bir sayfa oluşturun ve aşağıdaki kodu kullanarak bunu PDF belgesine ekleyin:

```csharp
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
```

## 3. Adım: PDF belgesinin bölümler koleksiyonuna liste bölümünü ekleyin

Aşağıdaki kodu kullanarak liste bölümünü PDF belgesinin bölümler koleksiyonuna ekleyin:

```csharp
tocPage.TocInfo = tocInfo;
```

## 4. Adım: Dört düzey listesinin biçimini tanımlayın

Aşağıdaki kodu kullanarak her düzeyin sol kenar boşluklarını ve metin biçimi ayarlarını ayarlayarak dört düzey listesinin biçimini tanımlayın:

```csharp
tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
Page page = doc.Pages.Add();
```

## Adım 5: Bölüme dört başlık ekleyin

```csharp

for (int Level = 1; Level != 5; Level++)
{ 
	Heading heading2 = new Heading(Level); 
	TextSegment segment2 = new TextSegment(); 
	heading2.TocPage = tocPage; 
	heading2.Segments.Add(segment2); 
	heading2.IsAutoSequence = true; 
	segment2.Text = "this is heading of level " + Level; 
	heading2.IsInList = true; 
	page.Paragraphs.Add(heading2); 
}
doc.Save(outFile);

```

### Aspose.PDF for .NET kullanarak TOC'deki Sayfa Numaralarını Gizlemek için Örnek Kaynak Kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
//Liste bölümünü Pdf belgesinin bölümler koleksiyonuna ekleyin
tocPage.TocInfo = tocInfo;
//Sol kenar boşluklarını ayarlayarak dört düzey listesinin biçimini tanımlayın ve
//her düzeyin metin biçimi ayarları

tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
Page page = doc.Pages.Add();
//Bölüme dört başlık ekleyin
for (int Level = 1; Level != 5; Level++)
	{ 
		Heading heading2 = new Heading(Level); 
		TextSegment segment2 = new TextSegment(); 
		heading2.TocPage = tocPage; 
		heading2.Segments.Add(segment2); 
		heading2.IsAutoSequence = true; 
		segment2.Text = "this is heading of level " + Level; 
		heading2.IsInList = true; 
		page.Paragraphs.Add(heading2); 
	}
doc.Save(outFile);
```

## Çözüm

Bu eğitimde Aspose.PDF for .NET kullanarak bir PDF belgesinde XMP meta verileriyle nasıl çalışılacağını araştırdık. XMP meta verileri, PDF belgesi hakkında başlığı, yazarı, oluşturulma tarihi ve daha fazlasını içeren değerli bilgiler sağlar. Aspose.PDF for .NET, geliştiricilerin bu meta verilere erişmesine ve bunları değiştirmesine olanak tanıyarak PDF belgeleriyle çalışmak için esnek ve güçlü bir API sağlar.

### SSS'ler

#### S: Bir PDF belgesindeki XMP meta verileri nedir?

C: PDF belgesindeki XMP (Genişletilebilir Meta Veri Platformu) meta verileri, belge hakkındaki meta veri bilgilerini depolamak için kullanılan standart bir formattır. Belge başlığı, yazar, oluşturulma tarihi, anahtar kelimeler ve daha fazlası gibi ayrıntıları içerir. XMP meta verileri, PDF belgesi hakkındaki bilgileri depolamak ve paylaşmak için yapılandırılmış ve standartlaştırılmış bir yol sağlar.

#### S: Aspose.PDF for .NET'i kullanarak bir PDF belgesinin XMP meta verilerini değiştirebilir miyim?

 C: Evet, Aspose.PDF for .NET'i kullanarak bir PDF belgesinin XMP meta verilerini programlı olarak değiştirebilirsiniz. Şuraya erişebilirsiniz:`Info` mülkiyeti`Document` XMP meta veri özelliklerine erişmenizi sağlayan nesne. Daha sonra PDF belgesinin XMP meta verilerini değiştirmek için bu özelliklerin değerlerini güncelleyebilirsiniz.

#### S: Aspose.PDF for .NET kullanarak bir PDF belgesinden özel XMP meta veri özelliklerini çıkarabilir miyim?

 C: Evet, Aspose.PDF for .NET'i kullanarak özel XMP meta veri özelliklerini bir PDF belgesinden çıkarabilirsiniz. Şunu kullanabilirsiniz:`Metadata` mülkiyeti`Document`PDF belgesinin tüm XMP meta veri özelliklerine erişim sağlayan nesne. Daha sonra özel özellikleri çıkarabilir ve değerlerini gerektiği gibi kullanabilirsiniz.