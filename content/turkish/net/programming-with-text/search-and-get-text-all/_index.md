---
title: Ara ve Tüm Metni Al
linktitle: Ara ve Tüm Metni Al
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesinin tüm sayfalarında nasıl arama yapacağınızı ve metin alacağınızı öğrenin.
type: docs
weight: 420
url: /tr/net/programming-with-text/search-and-get-text-all/
---
Bu eğitim, bir PDF belgesinin tüm sayfalarından metin aramak ve almak için Aspose.PDF for .NET'in nasıl kullanılacağını açıklar. Sağlanan C# kaynak kodu, işlemi adım adım gösterir.

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
```

## Adım 3: PDF belgesini yükleyin

 PDF belge dizininize giden yolu ayarlayın ve belgeyi kullanarak yükleyin`Document` sınıf:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Değiştirdiğinizden emin olun`"YOUR DOCUMENT DIRECTORY"` belge dizininize giden gerçek yol ile.

## Adım 4: Metni arayın ve çıkarın

 Bir tane oluştur`TextFragmentAbsorber` Giriş arama ifadesinin tüm örneklerini bulmak için nesne:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Yer değiştirmek`"text"` Aramak istediğiniz gerçek metinle birlikte.

## Adım 5: Tüm sayfalarda arama yapın

Belgenin tüm sayfaları için emiciyi kabul edin:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Adım 6: Çıkarılan metin parçalarını alın

 Çıkarılan metin parçalarını kullanarak alın`TextFragments` mülkiyeti`TextFragmentAbsorber` nesne:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Adım 7: Metin parçaları arasında döngü oluşturun

getd metin parçaları arasında dolaşın ve özelliklerine erişin:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
    Console.WriteLine("Text: {0} ", textFragment.Text);
    Console.WriteLine("Position: {0} ", textFragment.Position);
    Console.WriteLine("XIndent: {0} ", textFragment.Position.XIndent);
    Console.WriteLine("YIndent: {0} ", textFragment.Position.YIndent);
    Console.WriteLine("Font - Name: {0}", textFragment.TextState.Font.FontName);
    Console.WriteLine("Font - IsAccessible: {0} ", textFragment.TextState.Font.IsAccessible);
    Console.WriteLine("Font - IsEmbedded: {0} ", textFragment.TextState.Font.IsEmbedded);
    Console.WriteLine("Font - IsSubset: {0} ", textFragment.TextState.Font.IsSubset);
    Console.WriteLine("Font Size: {0} ", textFragment.TextState.FontSize);
    Console.WriteLine("Foreground Color: {0} ", textFragment.TextState.ForegroundColor);
}
```

Döngü içindeki kodu, her metin parçası üzerinde daha fazla işlem gerçekleştirecek şekilde değiştirebilirsiniz.

### .NET için Aspose.PDF kullanarak Arama ve Tüm Metni Alma için örnek kaynak kodu 
```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// Giriş arama ifadesinin tüm örneklerini bulmak için TextAbsorber nesnesi oluşturun
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Tüm sayfalar için emiciyi kabul et
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Çıkarılan metin parçalarını alın
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Parçalar arasında döngü
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine("Text : {0} ", textFragment.Text);
	Console.WriteLine("Position : {0} ", textFragment.Position);
	Console.WriteLine("XIndent : {0} ", textFragment.Position.XIndent);
	Console.WriteLine("YIndent : {0} ", textFragment.Position.YIndent);
	Console.WriteLine("Font - Name : {0}", textFragment.TextState.Font.FontName);
	Console.WriteLine("Font - IsAccessible : {0} ", textFragment.TextState.Font.IsAccessible);
	Console.WriteLine("Font - IsEmbedded : {0} ", textFragment.TextState.Font.IsEmbedded);
	Console.WriteLine("Font - IsSubset : {0} ", textFragment.TextState.Font.IsSubset);
	Console.WriteLine("Font Size : {0} ", textFragment.TextState.FontSize);
	Console.WriteLine("Foreground Color : {0} ", textFragment.TextState.ForegroundColor);
}
```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesinin tüm sayfalarından metin aramayı ve almayı başarıyla öğrendiniz. Bu eğitim, belgeyi yüklemekten çıkarılan metin parçalarına erişmeye kadar adım adım bir kılavuz sağladı. Artık bu kodu kendi C# projelerinize dahil ederek PDF dosyalarındaki metin içeriğini analiz edebilir ve işleyebilirsiniz.

### SSS

#### S: "Ara ve Metnin Tamamını Al" eğitiminin amacı nedir?

A: "Search And Get Text All" öğreticisi, .NET için Aspose.PDF kütüphanesinin bir PDF belgesinin tüm sayfalarından metin aramak ve çıkarmak için nasıl kullanılacağını gösterir. Öğretici, metin arama ve alma işlemini gerçekleştirmek için örnek C# koduyla birlikte adım adım talimatlar sağlar.

#### S: Bu eğitim PDF belgelerinden metin çıkarmada nasıl yardımcı oluyor?

A: Bu eğitim, bir PDF belgesinin tüm sayfalarından metin çıkarma sürecinde size rehberlik eder. Belirli metin ifadelerini bulmak ve konum, yazı tipi özellikleri ve renkler gibi ilişkili bilgileri almak için Aspose.PDF kitaplığını kullanır.

#### S: Bu eğitimi takip etmek için ön koşullar nelerdir?

A: Bu eğitime başlamadan önce, C# programlama dili hakkında temel bir anlayışa sahip olmalısınız. Ek olarak, .NET için Aspose.PDF kütüphanesinin yüklü olması gerekir. Bunu Aspose web sitesinden edinebilir veya projenize entegre etmek için NuGet'i kullanabilirsiniz.

#### S: Bu eğitimi takip edecek şekilde projemi nasıl kurarım?

A: Başlamak için, tercih ettiğiniz entegre geliştirme ortamında (IDE) yeni bir C# projesi oluşturun ve .NET için Aspose.PDF kitaplığına bir başvuru ekleyin. Bu, projenizde kitaplığın işlevselliğine erişmenizi sağlayacaktır.

#### S: PDF belgesinde belirli bir metni nasıl arayabilirim?

 A: Kullanabilirsiniz`TextFragmentAbsorber`PDF belgesi içinde belirli bir arama ifadesinin örneklerini bulmak için sınıf. Bu sınıfın bir örneğini oluşturarak ve hedef metni belirterek, o metnin tüm oluşumlarını yakalayabilirsiniz.

#### S: PDF belgesinin tüm sayfalarında metin arayabilir miyim?

 A: Evet, eğitim PDF belgesinin tüm sayfalarında metin aramanın nasıl yapılacağını gösterir.`pdfDocument.Pages.Accept(textFragmentAbsorber)` Tüm sayfalar için emiciyi kabul eden yöntem kullanılarak, her sayfada istediğiniz metni aramanıza olanak sağlanır.

#### S: Çıkarılan metin parçalarına nasıl ulaşabilirim?

 A: Metni aradıktan sonra, çıkarılan metin parçalarına şu şekilde erişebilirsiniz:`TextFragments` mülkiyeti`TextFragmentAbsorber` nesne. Bu özellik, bir koleksiyona erişim sağlar`TextFragment` Çıkarılan metni ve ilgili bilgileri içeren nesneler.

#### S: Çıkarılan metin parçalarından hangi bilgileri alabilirim?

A: Çıkarılan metin parçalarından gerçek metin içeriği, konum (X ve Y koordinatları), yazı tipi bilgisi (isim, boyut, renk vb.) ve daha fazlası gibi çeşitli ayrıntıları alabilirsiniz. Eğitimin örnek kodu, bu ayrıntılara nasıl erişileceğini ve yazdırılacağını gösterir.

#### S: Çıkarılan metin parçaları üzerinde başka işlemler yapabilir miyim?

A: Kesinlikle. Çıkarılan metin parçalarına sahip olduğunuzda, her parçada özel eylemler gerçekleştirmek için döngü içindeki kodu değiştirebilirsiniz. Bu, çıkarılan metni kaydetmeyi, metin desenlerini analiz etmeyi veya biçimlendirme değişiklikleri uygulamayı içerebilir.