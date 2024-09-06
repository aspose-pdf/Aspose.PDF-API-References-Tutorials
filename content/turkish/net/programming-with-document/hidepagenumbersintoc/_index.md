---
title: İçindekiler Tablosunda Sayfa Numaralarını Gizle
linktitle: İçindekiler Tablosunda Sayfa Numaralarını Gizle
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım kılavuzla Aspose.PDF for .NET'i kullanarak içindekiler tablosunda sayfa numaralarının nasıl gizleneceğini öğrenin.
type: docs
weight: 220
url: /tr/net/programming-with-document/hidepagenumbersintoc/
---
Bu makalede, Aspose.PDF for .NET'in İçindekiler Tablosunda Sayfa Numaralarını Gizle özelliğinin C# kullanılarak uygulanmasını ele alacağız. Aspose.PDF for .NET'e kısa bir girişle başlayıp ardından bu özelliği uygulamak için adım adım kılavuza dalacağız. 

## .NET için Aspose.PDF'ye Giriş

Aspose.PDF for .NET, geliştiricilerin PDF dosyalarını programatik olarak oluşturmasına, düzenlemesine ve işlemesine olanak tanıyan güçlü bir PDF işleme bileşenidir. PDF belgeleriyle çalışmayı kolaylaştıran çok çeşitli özellikler ve işlevler sunar. Aspose.PDF for .NET, hem 32 bit hem de 64 bit işletim sistemlerini destekler ve .NET Framework, .NET Core ve Xamarin platformlarıyla kullanılabilir. 

## İçindekiler Tablosunda Sayfa Numaralarını Gizle özelliği nedir?

İçindekiler Tablosu (TOC), kullanıcılara içerik hakkında hızlı bir genel bakış sağlayan bir PDF belgesinin temel bir parçasıdır. Bazen kullanıcılar, TOC'yi daha kullanıcı dostu hale getirmek için sayfa numaralarını gizlemek isteyebilir. .NET için Aspose.PDF, TOC'deki sayfa numaralarını gizlemek için yerleşik bir özellik sunar. Bu özellik, daha kullanıcı dostu PDF belgeleri oluşturmak için kullanılabilir. 

## Ön koşullar

Bu eğitimi takip etmek için aşağıdakilere ihtiyacınız olacak:

- Visual Studio 2010 veya üzeri
- Sisteminizde .NET için Aspose.PDF yüklü
- C# programlama dilinin temel bilgisi

## İçindekiler Tablosunda Sayfa Numaralarını Gizle özelliğini uygulamak için adım adım kılavuz

Aspose.PDF for .NET'i kullanarak İçindekiler Tablosunda Sayfa Numaralarını Gizle özelliğini uygulamak için aşağıdaki adımları izleyin:

## Adım 1: Visual Studio'da yeni bir C# konsol uygulaması oluşturun

Visual Studio'yu açın ve yeni bir C# konsol uygulaması oluşturun.

## Adım 2: .NET için Aspose.PDF'ye referans ekleyin

Projenizdeki Referanslar klasörüne sağ tıklayın ve Referans Ekle'yi seçin. Aspose.PDF for .NET'in sisteminizde kurulu olduğu konuma gidin ve ona bir referans ekleyin.

## Adım 1: Yeni bir PDF belgesi oluşturun

Aşağıdaki kodu kullanarak yeni bir PDF belgesi oluşturun:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
```

## Adım 2: İçindekiler sayfası oluşturun

İçindekiler için yeni bir sayfa oluşturun ve aşağıdaki kodu kullanarak bunu PDF belgesine ekleyin:

```csharp
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
```

## Adım 3: PDF belgesinin bölümler koleksiyonuna liste bölümü ekleyin

Aşağıdaki kodu kullanarak PDF belgesinin bölümler koleksiyonuna liste bölümünü ekleyin:

```csharp
tocPage.TocInfo = tocInfo;
```

## Adım 4: Dört seviyeli listenin formatını tanımlayın

Aşağıdaki kodu kullanarak her seviyenin sol kenar boşluklarını ve metin biçimi ayarlarını belirleyerek dört seviyeli listenin biçimini tanımlayın:

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

### .NET için Aspose.PDF kullanarak İçindekiler Tablosunda Sayfa Numaralarını Gizlemek için Örnek Kaynak Kodu

```csharp
// Belgeler dizinine giden yol.
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
//Sol kenar boşluklarını ayarlayarak dört seviyeli listenin biçimini tanımlayın ve
//her seviyenin metin biçimi ayarları

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

Bu eğitimde, .NET için Aspose.PDF kullanarak bir PDF belgesinde XMP meta verileriyle nasıl çalışılacağını inceledik. XMP meta verileri, PDF belgesinin başlığı, yazarı, oluşturulma tarihi ve daha fazlası dahil olmak üzere değerli bilgiler sağlar. .NET için Aspose.PDF, geliştiricilerin bu meta verilere erişmesine ve bunları düzenlemesine olanak tanır ve PDF belgeleriyle çalışmak için esnek ve güçlü bir API sağlar.

### SSS

#### S: PDF belgesinde XMP meta verisi nedir?

A: PDF belgesindeki XMP (Genişletilebilir Meta Veri Platformu) meta verisi, belge hakkında meta veri bilgilerini depolamak için standart bir biçimdir. Belge başlığı, yazar, oluşturma tarihi, anahtar sözcükler ve daha fazlası gibi ayrıntıları içerir. XMP meta verisi, PDF belgesi hakkında bilgi depolamak ve paylaşmak için yapılandırılmış ve standartlaştırılmış bir yol sağlar.

#### S: Aspose.PDF for .NET kullanarak bir PDF belgesinin XMP meta verilerini değiştirebilir miyim?

 A: Evet, .NET için Aspose.PDF'yi kullanarak bir PDF belgesinin XMP meta verilerini programatik olarak değiştirebilirsiniz. Şuraya erişebilirsiniz:`Info` mülkiyeti`Document` XMP meta veri özelliklerine erişmenizi sağlayan nesne. Daha sonra bu özelliklerin değerlerini güncelleyerek PDF belgesinin XMP meta verilerini değiştirebilirsiniz.

#### S: Aspose.PDF for .NET kullanarak bir PDF belgesinden özel XMP meta veri özelliklerini çıkarabilir miyim?

 A: Evet, Aspose.PDF for .NET kullanarak bir PDF belgesinden özel XMP meta veri özelliklerini çıkarabilirsiniz.`Metadata` mülkiyeti`Document`PDF belgesinin tüm XMP meta veri özelliklerine erişim sağlayan nesne. Daha sonra özel özellikleri çıkarabilir ve değerlerini gerektiği gibi kullanabilirsiniz.