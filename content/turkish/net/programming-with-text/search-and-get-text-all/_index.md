---
title: Tüm Metinleri Arayın ve Alın
linktitle: Tüm Metinleri Arayın ve Alın
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET'i kullanarak bir PDF belgesinin tüm sayfalarından nasıl metin arayacağınızı ve metin alacağınızı öğrenin.
type: docs
weight: 420
url: /tr/net/programming-with-text/search-and-get-text-all/
---
Bu eğitimde, bir PDF belgesinin tüm sayfalarında metin aramak ve almak için Aspose.PDF for .NET'in nasıl kullanılacağı açıklanmaktadır. Sağlanan C# kaynak kodu süreci adım adım gösterir.

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
```

## 3. Adım: PDF belgesini yükleyin

 PDF belge dizininizin yolunu ayarlayın ve belgeyi kullanarak yükleyin.`Document` sınıf:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Değiştirdiğinizden emin olun`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

## 4. Adım: Metni arayın ve çıkarın

 Oluşturmak`TextFragmentAbsorber` giriş arama ifadesinin tüm örneklerini bulmak için nesne:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Yer değiştirmek`"text"` aramak istediğiniz gerçek metinle birlikte.

## 5. Adım: Tüm sayfalarda arama yapın

Belgenin tüm sayfaları için emiciyi kabul edin:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Adım 6: Çıkarılan metin parçalarını alın

Çıkarılan metin parçalarını kullanarak alın`TextFragments` mülkiyeti`TextFragmentAbsorber` nesne:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Adım 7: Metin parçaları arasında döngü yapın

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

Her metin parçası üzerinde daha fazla eylem gerçekleştirmek için döngü içindeki kodu değiştirebilirsiniz.

### Aspose.PDF for .NET kullanarak Tüm Metinleri Ara ve Al için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// Giriş arama ifadesinin tüm örneklerini bulmak için TextAbsorber nesnesi oluşturun
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Tüm sayfalar için emiciyi kabul edin
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Çıkarılan metin parçalarını alın
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Parçalar arasında döngü yapın
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

Tebrikler! Aspose.PDF for .NET'i kullanarak bir PDF belgesinin tüm sayfalarında metin aramayı ve metin almayı başarıyla öğrendiniz. Bu eğitimde, belgenin yüklenmesinden çıkarılan metin parçalarına erişmeye kadar adım adım bir kılavuz sağlanmıştır. Artık PDF dosyalarındaki metin içeriğini analiz etmek ve işlemek için bu kodu kendi C# projelerinize dahil edebilirsiniz.

### SSS'ler

#### S: "Tüm Metni Ara ve Al" eğitiminin amacı nedir?

C: "Tüm Metni Ara ve Al" eğitimi, bir PDF belgesinin tüm sayfalarından metin aramak ve çıkarmak için Aspose.PDF kütüphanesinin .NET için nasıl kullanılacağını gösterir. Öğreticide, metin araması ve alımı gerçekleştirmek için örnek C# koduyla birlikte adım adım talimatlar sağlanır.

#### S: Bu eğitim, PDF belgelerinden metin çıkarmaya nasıl yardımcı olur?

C: Bu eğitim, bir PDF belgesinin tüm sayfalarından metin çıkarma sürecinde size yol gösterir. Belirli metin ifadelerini bulmak ve konum, yazı tipi özellikleri ve renkler gibi ilgili bilgileri almak için Aspose.PDF kütüphanesini kullanır.

#### S: Bu eğitimi takip etmenin önkoşulları nelerdir?

C: Bu eğitime başlamadan önce C# programlama dili hakkında temel bilgiye sahip olmanız gerekir. Ayrıca Aspose.PDF for .NET kütüphanesinin de kurulu olması gerekir. Bunu Aspose web sitesinden edinebilir veya projenize entegre etmek için NuGet'i kullanabilirsiniz.

#### S: Projemi bu öğreticiyi takip edecek şekilde nasıl ayarlayabilirim?

C: Başlamak için tercih ettiğiniz entegre geliştirme ortamında (IDE) yeni bir C# projesi oluşturun ve Aspose.PDF for .NET kütüphanesine bir referans ekleyin. Bu, projenizdeki kütüphanenin işlevselliğine erişmenizi sağlayacaktır.

#### S: Bir PDF belgesinde belirli bir metni nasıl arayabilirim?

C: Kullanabilirsiniz`TextFragmentAbsorber`PDF belgesinde belirli bir arama ifadesinin örneklerini bulmak için sınıf. Bu sınıfın bir örneğini oluşturarak ve hedef metni belirterek, o metnin tüm oluşumlarını yakalayabilirsiniz.

#### S: PDF belgesinin tüm sayfalarında metin arayabilir miyim?

 C: Evet, eğitimde PDF belgesinin tüm sayfalarında nasıl metin aranacağı gösterilmektedir.`pdfDocument.Pages.Accept(textFragmentAbsorber)` yöntemi tüm sayfalar için emiciyi kabul etmek için kullanılır ve her sayfada istediğiniz metni aramanıza olanak tanır.

#### S: Çıkarılan metin parçalarına nasıl erişebilirim?

 C: Metni aradıktan sonra, çıkarılan metin parçalarına`TextFragments` mülkiyeti`TextFragmentAbsorber` nesne. Bu özellik aşağıdakilerin bir koleksiyonuna erişim sağlar:`TextFragment` ayıklanan metni ve ilgili bilgileri içeren nesneler.

#### S: Çıkarılan metin parçalarından hangi bilgileri alabilirim?

C: Çıkarılan metin parçalarından gerçek metin içeriği, konum (X ve Y koordinatları), yazı tipi bilgileri (ad, boyut, renk vb.) ve daha fazlası gibi çeşitli ayrıntıları alabilirsiniz. Öğreticinin örnek kodu, bu ayrıntılara nasıl erişileceğini ve yazdırılacağını gösterir.

#### S: Çıkarılan metin parçaları üzerinde başka eylemler gerçekleştirebilir miyim?

C: Kesinlikle. Ayıklanan metin parçalarını aldıktan sonra, her bir parça üzerinde özel eylemler gerçekleştirmek için döngü içindeki kodu değiştirebilirsiniz. Bu, çıkarılan metnin kaydedilmesini, metin kalıplarının analiz edilmesini veya biçimlendirme değişikliklerinin uygulanmasını içerebilir.