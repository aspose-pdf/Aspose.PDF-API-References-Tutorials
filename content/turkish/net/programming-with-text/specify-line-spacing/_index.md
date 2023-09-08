---
title: PDF Dosyasında Satır Aralığını Belirtin
linktitle: PDF Dosyasında Satır Aralığını Belirtin
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak PDF dosyasında satır aralığını nasıl belirleyeceğinizi öğrenin.
type: docs
weight: 510
url: /tr/net/programming-with-text/specify-line-spacing/
---
Bu eğitimde Aspose.PDF for .NET kullanılarak PDF dosyasında satır aralığının nasıl belirleneceği açıklanmaktadır. Sağlanan C# kaynak kodu süreci adım adım gösterir.

## Önkoşullar

Eğiticiye devam etmeden önce aşağıdakilere sahip olduğunuzdan emin olun:

- Temel C# programlama dili bilgisi.
- Aspose.PDF for .NET kütüphanesi kuruldu. Bunu Aspose web sitesinden edinebilir veya projenize kurmak için NuGet'i kullanabilirsiniz.

## 1. Adım: Projeyi ayarlayın

Tercih ettiğiniz entegre geliştirme ortamında (IDE) yeni bir C# projesi oluşturarak başlayın ve Aspose.PDF for .NET kitaplığına bir referans ekleyin.

## 2. Adım: Gerekli ad alanlarını içe aktarın

Gerekli ad alanlarını içe aktarmak için C# dosyanızın başına aşağıdaki kullanma yönergelerini ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

## 3. Adım: Belge dizininin yolunu ayarlayın

 kullanarak belge dizininizin yolunu ayarlayın.`dataDir` değişken:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

## 4. Adım: Giriş PDF dosyasını yükleyin

 Giriş PDF dosyasını kullanarak yükleyin.`Document` sınıf:

```csharp
Document doc = new Document();
```

## Adım 5: TextFormattingOptions'ı oluşturun

 Oluşturmak`TextFormattingOptions` nesneyi seçin ve satır aralığı modunu şu şekilde ayarlayın:`FullSize`:

```csharp
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
```

## Adım 6: Bir TextFragment Oluşturun

 Oluşturmak`TextFragment` nesneyi seçin ve metin içeriğini belirtin:

```csharp
TextFragment textFragment = new TextFragment("Hello world");
```

## 7. Adım: Yazı tipi dosyasını yükleyin (isteğe bağlı)

 Metin için belirli bir yazı tipi kullanmak istiyorsanız TrueType yazı tipi dosyasını bir`FileStream` nesne:

```csharp
string fontFile = dataDir + "HPSimplified.TTF";
using (FileStream fontStream = File.OpenRead(fontFile))
{
    textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
}
```

 Yer değiştirmek`"HPSimplified.TTF"` gerçek yazı tipi dosyası adı ile.

## 8. Adım: Metin konumunu ve satır aralığını belirtin

 Metin parçasının konumunu ayarlayın ve`TextFormattingOptions` -e`TextState.FormattingOptions` mülk:

```csharp
textFragment.Position = new Position(100, 600);
textFragment.TextState.FormattingOptions = formattingOptions;
```

## 9. Adım: Metni belgeye ekleyin

 Metin parçasını bir dosyaya ekleyerek belgeye ekleyin.`TextBuilder` veya doğrudan bir sayfanın`Paragraphs` Toplamak:

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

 Değiştirdiğinizden emin olun`"SpecifyLineSpacing_out.pdf"` İstenilen çıktı dosyası adı ile.

### Aspose.PDF for .NET kullanarak Satır Aralığını Belirleme için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string fontFile = dataDir + "HPSimplified.TTF";
// Giriş PDF dosyasını yükle
Document doc = new Document();
//LineSpacingMode.FullSize ile TextFormattingOptions oluşturun
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
// Belgenin ilk sayfası için metin oluşturucu nesnesi oluşturun
//TextBuilder textBuilder = new TextBuilder(doc.Pages[1]);
// Örnek dizeyle metin parçası oluşturun
TextFragment textFragment = new TextFragment("Hello world");
if (fontFile != "")
{
	// TrueType yazı tipini akış nesnesine yükleyin
	using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
	{
		//Metin dizesi için yazı tipi adını ayarlama
		textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
		// Metin Parçası için konumu belirtin
		textFragment.Position = new Position(100, 600);
		//Geçerli parçanın TextFormattingOptions'ını önceden tanımlanmış olarak ayarlayın (bu, LineSpacingMode.FullSize'a işaret eder)
		textFragment.TextState.FormattingOptions = formattingOptions;
		// Metni TextBuilder'a ekleyerek PDF dosyasının üzerine yerleştirilebilmesini sağlayın
		//textBuilder.AppendText(textFragment);
		var page = doc.Pages.Add();
		page.Paragraphs.Add(textFragment);
	}
	dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
	// Ortaya çıkan PDF belgesini kaydet
	doc.Save(dataDir);
}
```

## Çözüm

Tebrikler! Aspose.PDF for .NET'i kullanarak bir PDF belgesinde satır aralığını nasıl belirleyeceğinizi başarıyla öğrendiniz. Bu eğitimde, projenin kurulumundan değiştirilen belgenin kaydedilmesine kadar adım adım bir kılavuz sağlanmıştır. Artık PDF dosyalarındaki metnin satır aralığını özelleştirmek için bu kodu kendi C# projelerinize dahil edebilirsiniz.

### SSS'ler

#### S: "PDF Dosyasında Satır Aralığını Belirleme" eğitiminin amacı nedir?

C: "PDF Dosyasında Satır Aralığını Belirleme" eğitimi, kullanıcılara bir PDF belgesi içindeki metnin satır aralığını özelleştirmek için .NET için Aspose.PDF kütüphanesini nasıl kullanacakları konusunda rehberlik etmeyi amaçlamaktadır. Öğretici, süreci göstermek için adım adım talimatlar ve C# kod örnekleri sağlar.

#### S: Bu eğitim, bir PDF belgesinde satır aralığını belirlemede nasıl yardımcı olur?

C: Bu eğitim, kullanıcıların bir PDF belgesindeki metin için satır aralığını belirlemek amacıyla Aspose.PDF for .NET'in özelliklerinden nasıl yararlanacaklarını anlamalarına yardımcı olur. Kullanıcılar verilen adımları ve kod örneklerini takip ederek satır aralıklarını tercihlerine göre ayarlayabilirler.

#### S: Bu öğreticiyi takip etmek için hangi ön koşullar gereklidir?

C: Eğitime başlamadan önce C# programlama dili hakkında temel bilgiye sahip olmanız gerekir. Ayrıca Aspose.PDF for .NET kütüphanesinin de kurulu olması gerekir. Bunu Aspose web sitesinden edinebilir veya NuGet'i kullanarak projenize yükleyebilirsiniz.

#### S: Projemi bu öğreticiyi takip edecek şekilde nasıl ayarlayabilirim?

C: Başlamak için tercih ettiğiniz entegre geliştirme ortamında (IDE) yeni bir C# projesi oluşturun ve Aspose.PDF for .NET kütüphanesine bir referans ekleyin. Bu, kitaplığın PDF belgeleriyle çalışma ve satır aralığını özelleştirme özelliklerinden yararlanmanıza olanak tanır.

#### S: Bu öğreticiyi herhangi bir metin türü için satır aralığını belirlemek amacıyla kullanabilir miyim?

C: Evet, bu eğitimde Aspose.PDF for .NET kullanılarak bir PDF belgesindeki herhangi bir metin içeriği için satır aralığının nasıl belirleneceğine ilişkin talimatlar verilmektedir. Metnin satır aralığını ihtiyaçlarınıza göre ayarlamak için sağlanan kod örneklerini kullanabilirsiniz.

#### S: Öğreticide satır aralığı modunu nasıl belirlerim?

 C: Eğitimde nasıl oluşturulacağı gösterilmektedir.`TextFormattingOptions` nesneyi ve onu ayarlayın`LineSpacing` mülkiyet`TextFormattingOptions.LineSpacingMode.FullSize`. Bu mod, metin içeriği için tam satır aralığını belirtir.

#### S: Metin için belirli bir yazı tipini nasıl yükleyebilirim?

 C: Metin içeriği için belirli bir yazı tipi kullanmak istiyorsanız eğitimde TrueType yazı tipi dosyasının bir yazı tipine nasıl yükleneceği konusunda rehberlik sağlanır.`FileStream` nesneyi seçin ve onu yazı tipi olarak ayarlayın.`TextFragment`. Bu, metnin yazı tipini satır aralığıyla birlikte özelleştirmenizi sağlar.

#### S: PDF belgesindeki metnin konumunu nasıl özelleştiririm?

 C: Metnin konumunu özelleştirmek için bir`TextFragment` nesneyi ve onu ayarlayın`Position`özelliği istenen koordinatlara (X ve Y) ayarlayın. Bu, metnin PDF belgesinde nereye yerleştirileceğini kontrol etmenizi sağlar.

#### S: Bu satır aralığı değişikliklerini mevcut PDF belgelerine uygulayabilir miyim?

 C: Evet, mevcut PDF belgelerindeki metinlerin satır aralığını değiştirebilirsiniz. Öğreticide nasıl oluşturulacağı gösterilmektedir`TextFragment` belirtilen satır aralığı ve konumuyla seçin ve ardından bunu bir sayfanın`Paragraphs` Toplamak.