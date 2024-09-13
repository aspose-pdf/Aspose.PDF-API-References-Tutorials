---
title: PDF Dosyasında Düzenli İfade Arama
linktitle: PDF Dosyasında Düzenli İfade Arama
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyasında düzenli ifadeler kullanarak metin aramayı ve almayı öğrenin.
type: docs
weight: 440
url: /tr/net/programming-with-text/search-regular-expression/
---
Bu eğitim, PDF dosyasındaki düzenli ifadeyle eşleşen metni aramak ve almak için Aspose.PDF for .NET'in nasıl kullanılacağını açıklar. Sağlanan C# kaynak kodu, işlemi adım adım gösterir.

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
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
```

 Değiştirdiğinizden emin olun`"YOUR DOCUMENT DIRECTORY"` belge dizininize giden gerçek yol ile.

## Adım 4: Düzenli ifadeyle arama yapın

 Bir tane oluştur`TextFragmentAbsorber` nesneyi seçin ve düzenli ifade desenini, desenle eşleşen tüm ifadeleri bulacak şekilde ayarlayın:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // 1999-2000 gibi
```

 Yer değiştirmek`"\\d{4}-\\d{4}"` İstediğiniz düzenli ifade kalıbıyla.

## Adım 5: Metin arama seçeneklerini ayarlayın

 Bir tane oluştur`TextSearchOptions` nesneyi seçin ve onu şuraya ayarlayın:`TextSearchOptions` mülkiyeti`TextFragmentAbsorber` düzenli ifade kullanımını etkinleştirmek için nesne:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
```

## Adım 6: Tüm sayfalarda arama yapın

Belgenin tüm sayfaları için emiciyi kabul edin:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Adım 7: Çıkarılan metin parçalarını alın

 Çıkarılan metin parçalarını kullanarak alın`TextFragments` mülkiyeti`TextFragmentAbsorber` nesne:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Adım 8: Metin parçaları arasında döngü oluşturun

Alınan metin parçaları arasında dolaşın ve özelliklerine erişin:

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

### .NET için Aspose.PDF kullanarak Arama Düzenli İfadesi için örnek kaynak kodu 
```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
//Düzenli ifadeyle eşleşen tüm ifadeleri bulmak için TextAbsorber nesnesi oluşturun
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // 1999-2000 gibi
// Düzenli ifade kullanımını belirtmek için metin arama seçeneğini ayarlayın
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
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

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesinde düzenli ifadeyle eşleşen metni aramayı ve almayı başarıyla öğrendiniz. Bu eğitim, belgeyi yüklemekten çıkarılan metin parçalarına erişmeye kadar adım adım bir kılavuz sağladı. Artık bu kodu kendi C# projelerinize dahil ederek PDF dosyalarında gelişmiş metin aramaları yapabilirsiniz.

### SSS

#### S: "PDF Dosyasında Düzenli İfade Arama" eğitiminin amacı nedir?

A: "PDF Dosyasında Düzenli İfade Arama" öğreticisinin amacı, .NET için Aspose.PDF kütüphanesinin PDF dosyasında belirtilen düzenli ifade örüntüsüyle eşleşen metni aramak ve çıkarmak için nasıl kullanılacağını göstermektir. Öğretici, süreci göstermek için kapsamlı rehberlik ve örnek C# kodu sağlar.

#### S: Bu eğitim, bir PDF belgesinde düzenli ifadeler kullanarak metin aramada nasıl yardımcı olur?

A: Bu eğitim, bir PDF belgesinde düzenli ifade desenine dayalı metin aramaları yapmak için Aspose.PDF kitaplığını kullanmaya yönelik adım adım bir yaklaşım sunar. Projenin nasıl kurulacağını, PDF belgesinin nasıl yükleneceğini, düzenli ifade deseninin nasıl tanımlanacağını ve eşleşen metin parçalarının nasıl alınacağını ayrıntılı olarak açıklar.

#### S: Bu eğitimi takip etmek için ön koşullar nelerdir?

A: Bu eğitime başlamadan önce, C# programlama dili hakkında temel bir anlayışa sahip olmalısınız. Ek olarak, .NET için Aspose.PDF kütüphanesinin yüklü olması gerekir. Bunu Aspose web sitesinden edinebilir veya projenize entegre etmek için NuGet'i kullanabilirsiniz.

#### S: Bu eğitimi takip edecek şekilde projemi nasıl kurarım?

A: Başlamak için, tercih ettiğiniz entegre geliştirme ortamında (IDE) yeni bir C# projesi oluşturun ve .NET için Aspose.PDF kitaplığına bir referans ekleyin. Bu, kitaplığın yeteneklerinden projeniz içinde yararlanmanızı sağlayacaktır.

#### S: PDF belgesinde metin aramak için normal ifadeleri kullanabilir miyim?

 A: Evet, bu eğitim, PDF belgesinden metin aramak ve çıkarmak için düzenli ifadelerin nasıl kullanılacağını gösterir.`TextFragmentAbsorber` sınıfını belirleyip, verilen desenle eşleşen ifadeleri bulmak için düzenli ifade desenini belirtme.

#### S: Metin araması için düzenli ifade desenini nasıl tanımlarım?

 A: Metin araması için düzenli bir ifade deseni tanımlamak için bir`TextFragmentAbsorber` nesneyi seçin ve desenini kullanarak ayarlayın`Text` parametre. Varsayılan deseni değiştir`"\\d{4}-\\d{4}"` İstediğiniz düzenli ifade kalıbını kullanarak eğitimin koduna yazın.

#### S: Metin araması için düzenli ifade kullanımını nasıl etkinleştirebilirim?

 A: Düzenli ifade kullanımı, bir`TextSearchOptions` nesne ve değerini ayarlama`true` Bu nesneyi şuraya atayın:`TextSearchOptions` mülkiyeti`TextFragmentAbsorber` Örnek. Bu, metin araması sırasında düzenli ifade deseninin uygulanmasını sağlar.

#### S: Düzenli ifade kalıbıyla eşleşen metin parçalarını alabilir miyim?

 A: Kesinlikle. PDF belgesine düzenli ifade aramasını uyguladıktan sonra, çıkarılan metin parçalarını kullanarak alabilirsiniz.`TextFragments` mülkiyeti`TextFragmentAbsorber` nesne. Bu metin parçaları belirtilen düzenli ifade örüntüsüyle eşleşen metin segmentlerini içerir.

#### S: Alınan metin parçalarından neye erişebilirim?

A: Alınan metin parçalarından, eşleşen metin içeriği, konum (X ve Y koordinatları), yazı tipi bilgisi (ad, boyut, renk) ve daha fazlası gibi çeşitli özelliklere erişebilirsiniz. Eğitimin döngüsündeki örnek kod, bu özelliklere nasıl erişileceğini ve bunların nasıl görüntüleneceğini gösterir.

#### S: Çıkarılan metin parçaları üzerindeki eylemleri nasıl özelleştirebilirim?

A: Çıkarılan metin parçalarına sahip olduğunuzda, her metin parçasında ek eylemler gerçekleştirmek için döngü içindeki kodu özelleştirebilirsiniz. Bu, çıkarılan metni kaydetmeyi, desenleri analiz etmeyi veya gereksinimlerinize göre biçimlendirme değişiklikleri uygulamayı içerebilir.