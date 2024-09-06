---
title: PDF Dosyasında Satır Aralığını Belirleyin
linktitle: PDF Dosyasında Satır Aralığını Belirleyin
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyasında satır aralığının nasıl belirleneceğini öğrenin.
type: docs
weight: 510
url: /tr/net/programming-with-text/specify-line-spacing/
---
Bu eğitim, .NET için Aspose.PDF kullanarak PDF dosyasında satır aralığının nasıl belirleneceğini açıklar. Sağlanan C# kaynak kodu, işlemi adım adım gösterir.

## Ön koşullar

Eğitime başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- C# programlama dilinin temel bilgisi.
- .NET kütüphanesi için Aspose.PDF yüklendi. Bunu Aspose web sitesinden edinebilir veya projenize yüklemek için NuGet'i kullanabilirsiniz.

## Adım 1: Projeyi kurun

Tercih ettiğiniz entegre geliştirme ortamında (IDE) yeni bir C# projesi oluşturarak başlayın ve .NET için Aspose.PDF kitaplığına bir başvuru ekleyin.

## Adım 2: Gerekli ad alanlarını içe aktarın

Gerekli ad alanlarını içe aktarmak için C# dosyanızın başına aşağıdaki using yönergelerini ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

## Adım 3: Belge dizinine giden yolu ayarlayın

 Belge dizininize giden yolu kullanarak ayarlayın`dataDir` değişken:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belge dizininize giden gerçek yol ile.

## Adım 4: Girdi PDF dosyasını yükleyin

 Giriş PDF dosyasını kullanarak yükleyin`Document` sınıf:

```csharp
Document doc = new Document();
```

## Adım 5: TextFormattingOptions'ı Oluşturun

 Bir tane oluştur`TextFormattingOptions` nesneyi seçin ve satır aralığı modunu ayarlayın`FullSize`:

```csharp
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
```

## Adım 6: Bir TextFragment Oluşturun

 Bir tane oluştur`TextFragment` nesneyi seçin ve metin içeriğini belirtin:

```csharp
TextFragment textFragment = new TextFragment("Hello world");
```

## Adım 7: Yazı tipi dosyasını yükleyin (isteğe bağlı)

 Metin için belirli bir yazı tipi kullanmak istiyorsanız, TrueType yazı tipi dosyasını bir`FileStream` nesne:

```csharp
string fontFile = dataDir + "HPSimplified.TTF";
using (FileStream fontStream = File.OpenRead(fontFile))
{
    textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
}
```

 Yer değiştirmek`"HPSimplified.TTF"` gerçek yazı tipi dosya adı ile.

## Adım 8: Metin konumunu ve satır aralığını belirtin

 Metin parçası için konumu ayarlayın ve atayın`TextFormattingOptions` için`TextState.FormattingOptions` mülk:

```csharp
textFragment.Position = new Position(100, 600);
textFragment.TextState.FormattingOptions = formattingOptions;
```

## Adım 9: Metni belgeye ekleyin

 Metin parçasını, bir belgeye ekleyerek ekleyin.`TextBuilder` veya doğrudan bir sayfanın`Paragraphs` koleksiyon:

```csharp
var page = doc.Pages.Add();
page.Paragraphs.Add(textFragment);
```

## Adım 10: Ortaya çıkan PDF belgesini kaydedin

Değiştirilen PDF belgesini kaydedin:

```csharp
dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
doc.Save(dataDir);
```

 Değiştirdiğinizden emin olun`"SpecifyLineSpacing_out.pdf"` İstenilen çıktı dosya adı ile.

### .NET için Aspose.PDF kullanarak Satır Aralığını Belirleme için örnek kaynak kodu 
```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string fontFile = dataDir + "HPSimplified.TTF";
// Giriş PDF dosyasını yükle
Document doc = new Document();
//LineSpacingMode.FullSize ile TextFormattingOptions Oluşturun
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
// Belgenin ilk sayfası için metin oluşturucu nesnesi oluşturun
//TextBuilder textBuilder = yeni TextBuilder(doc.Pages[1]);
// Örnek dizeyle metin parçası oluştur
TextFragment textFragment = new TextFragment("Hello world");
if (fontFile != "")
{
	// TrueType yazı tipini akış nesnesine yükleyin
	using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
	{
		// Metin dizesi için yazı tipi adını ayarlayın
		textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
		//Metin Parçası için konumu belirtin
		textFragment.Position = new Position(100, 600);
		//Geçerli parçanın TextFormattingOptions'ını önceden tanımlanmış olarak ayarlayın (LineSpacingMode.FullSize'ı işaret eder)
		textFragment.TextState.FormattingOptions = formattingOptions;
		// Metni TextBuilder'a ekleyin, böylece PDF dosyasının üzerine yerleştirilebilir
		//textBuilder.AppendText(metinParçası);
		var page = doc.Pages.Add();
		page.Paragraphs.Add(textFragment);
	}
	dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
	// Ortaya çıkan PDF belgesini kaydedin
	doc.Save(dataDir);
}
```

## Çözüm

Tebrikler! .NET için Aspose.PDF kullanarak bir PDF belgesinde satır aralığını nasıl belirleyeceğinizi başarıyla öğrendiniz. Bu eğitim, projeyi kurmaktan değiştirilmiş belgeyi kaydetmeye kadar adım adım bir kılavuz sağladı. Artık bu kodu kendi C# projelerinize dahil ederek PDF dosyalarındaki metnin satır aralığını özelleştirebilirsiniz.

### SSS

#### S: "PDF Dosyasında Satır Aralığını Belirleme" eğitiminin amacı nedir?

A: "PDF Dosyasında Satır Aralığını Belirleme" öğreticisinin amacı, kullanıcılara PDF belgesindeki metnin satır aralığını özelleştirmek için .NET için Aspose.PDF kitaplığını nasıl kullanacakları konusunda rehberlik etmektir. Öğretici, işlemi göstermek için adım adım talimatlar ve C# kod örnekleri sağlar.

#### S: Bu eğitim PDF belgesinde satır aralığını belirlemeye nasıl yardımcı olur?

A: Bu eğitim, kullanıcıların PDF belgesinde metin için satır aralığını belirtmek üzere Aspose.PDF for .NET'in yeteneklerini nasıl kullanacaklarını anlamalarına yardımcı olur. Sağlanan adımları ve kod örneklerini izleyerek kullanıcılar satır aralığını kendi tercihlerine göre ayarlayabilirler.

#### S: Bu eğitimi takip etmek için hangi ön koşullar gereklidir?

A: Eğitime başlamadan önce, C# programlama dili hakkında temel bir anlayışa sahip olmalısınız. Ek olarak, .NET için Aspose.PDF kütüphanesinin yüklü olması gerekir. Bunu Aspose web sitesinden edinebilir veya NuGet kullanarak projenize yükleyebilirsiniz.

#### S: Bu eğitimi takip edecek şekilde projemi nasıl kurarım?

A: Başlamak için, tercih ettiğiniz entegre geliştirme ortamında (IDE) yeni bir C# projesi oluşturun ve Aspose.PDF for .NET kitaplığına bir referans ekleyin. Bu, PDF belgeleriyle çalışmak ve satır aralığını özelleştirmek için kitaplığın özelliklerinden yararlanmanızı sağlar.

#### S: Bu eğitimi herhangi bir metin türü için satır aralığını belirlemek amacıyla kullanabilir miyim?

C: Evet, bu eğitim, .NET için Aspose.PDF kullanarak bir PDF belgesindeki herhangi bir metin içeriği için satır aralığının nasıl belirleneceğine dair talimatlar sağlar. Metnin satır aralığını ihtiyaçlarınıza göre ayarlamak için sağlanan kod örneklerini kullanabilirsiniz.

#### S: Eğitimde satır aralığı modunu nasıl belirleyebilirim?

 A: Eğitimde bir`TextFormattingOptions` nesne ve onu ayarla`LineSpacing` mülk`TextFormattingOptions.LineSpacingMode.FullSize`Bu mod, metin içeriği için tam satır aralığını belirtir.

#### S: Metne özel bir yazı tipi nasıl yükleyebilirim?

 A: Metin içeriği için belirli bir yazı tipi kullanmak istiyorsanız, eğitimde TrueType yazı tipi dosyasının bir bilgisayara nasıl yükleneceği konusunda rehberlik sağlanmaktadır.`FileStream` nesneyi seçin ve onu yazı tipi olarak ayarlayın`TextFragment`Bu, metnin yazı tipini ve satır aralığını özelleştirmenizi sağlar.

#### S: PDF belgesindeki metnin konumunu nasıl özelleştirebilirim?

 A: Metnin konumunu özelleştirmek için bir`TextFragment` nesne ve onu ayarla`Position`özelliği istenilen koordinatlara (X ve Y) ayarlayın. Bu, metnin PDF belgesi içinde nereye yerleştirileceğini kontrol etmenizi sağlar.

#### S: Bu satır aralığı değişikliklerini mevcut PDF belgelerine uygulayabilir miyim?

 A: Evet, mevcut PDF belgelerindeki metinler için satır aralığını değiştirebilirsiniz. Eğitim, bir satır aralığının nasıl oluşturulacağını gösterir.`TextFragment` belirtilen satır aralığı ve konumla, ve sonra bunu bir sayfanın`Paragraphs` koleksiyon.