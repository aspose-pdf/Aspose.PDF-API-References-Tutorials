---
title: PDF Dosyasında Normal İfadeyi Ara
linktitle: PDF Dosyasında Normal İfadeyi Ara
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET'i kullanarak PDF dosyasında normal ifadeleri kullanarak metni nasıl arayacağınızı ve alacağınızı öğrenin.
type: docs
weight: 440
url: /tr/net/programming-with-text/search-regular-expression/
---
Bu eğitimde, PDF dosyasındaki normal ifadeyle eşleşen metni aramak ve almak için Aspose.PDF for .NET'in nasıl kullanılacağı açıklanmaktadır. Sağlanan C# kaynak kodu süreci adım adım gösterir.

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
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
```

 Değiştirdiğinizden emin olun`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

## 4. Adım: Normal ifadeyle arama yapın

 Oluşturmak`TextFragmentAbsorber` nesnesini açın ve kalıpla eşleşen tüm ifadeleri bulmak için normal ifade modelini ayarlayın:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // 1999-2000 gibi
```

 Yer değiştirmek`"\\d{4}-\\d{4}"` İstediğiniz düzenli ifade modeliyle.

## 5. Adım: Metin arama seçeneklerini ayarlayın

 Oluşturmak`TextSearchOptions` nesneyi seçin ve buna ayarlayın`TextSearchOptions` mülkiyeti`TextFragmentAbsorber` Düzenli ifade kullanımını etkinleştirmek için nesne:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
```

## 6. Adım: Tüm sayfalarda arama yapın

Belgenin tüm sayfaları için emiciyi kabul edin:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## 7. Adım: Çıkarılan metin parçalarını alın

Çıkarılan metin parçalarını kullanarak alın`TextFragments` mülkiyeti`TextFragmentAbsorber` nesne:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Adım 8: Metin parçaları arasında döngü yapın

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

### Aspose.PDF for .NET kullanarak Normal İfade Arama için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
// Normal ifadeyle eşleşen tüm ifadeleri bulmak için TextAbsorber nesnesi oluşturun
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // 1999-2000 gibi
// Normal ifade kullanımını belirtmek için metin arama seçeneğini ayarlayın
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
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

Tebrikler! Aspose.PDF for .NET'i kullanarak bir PDF belgesinde normal ifadeyle eşleşen metni nasıl arayacağınızı ve alacağınızı başarıyla öğrendiniz. Bu eğitimde, belgenin yüklenmesinden çıkarılan metin parçalarına erişmeye kadar adım adım bir kılavuz sağlanmıştır. Artık PDF dosyalarında gelişmiş metin aramaları gerçekleştirmek için bu kodu kendi C# projelerinize dahil edebilirsiniz.

### SSS'ler

#### S: "PDF Dosyasında Normal İfadeyi Ara" eğitiminin amacı nedir?

C: "PDF Dosyasında Normal İfadeyi Ara" eğitimi, bir PDF dosyasındaki belirli bir düzenli ifade düzeniyle eşleşen metni aramak ve çıkarmak için Aspose.PDF kütüphanesinin .NET için nasıl kullanılacağını göstermeyi amaçlamaktadır. Öğretici, süreci göstermek için kapsamlı rehberlik ve örnek C# kodu sağlar.

#### S: Bu eğitim, bir PDF belgesinde normal ifadeler kullanılarak metin aranmasına nasıl yardımcı olur?

C: Bu eğitim, Aspose.PDF kütüphanesinin düzenli ifade düzenine dayalı olarak bir PDF belgesinde metin araması yapmak için kullanılmasına yönelik adım adım bir yaklaşım sağlar. Projenin nasıl kurulacağı, PDF belgesinin nasıl yükleneceği, düzenli ifade modelinin nasıl tanımlanacağı ve eşleşen metin parçalarının nasıl alınacağı ayrıntılarıyla anlatılmaktadır.

#### S: Bu eğitimi takip etmenin önkoşulları nelerdir?

C: Bu eğitime başlamadan önce C# programlama dili hakkında temel bilgiye sahip olmanız gerekir. Ayrıca Aspose.PDF for .NET kütüphanesinin de kurulu olması gerekir. Bunu Aspose web sitesinden edinebilir veya projenize entegre etmek için NuGet'i kullanabilirsiniz.

#### S: Projemi bu öğreticiyi takip edecek şekilde nasıl ayarlayabilirim?

C: Başlamak için tercih ettiğiniz entegre geliştirme ortamında (IDE) yeni bir C# projesi oluşturun ve Aspose.PDF for .NET kütüphanesine bir referans ekleyin. Bu, projeniz dahilinde kütüphanenin yeteneklerinden yararlanmanıza olanak sağlayacaktır.

#### S: Bir PDF belgesinde metin aramak için normal ifadeleri kullanabilir miyim?

 C: Evet, bu eğitimde bir PDF belgesinde metin aramak ve çıkarmak için normal ifadelerin nasıl kullanılacağı gösterilmektedir. Şunların kullanılmasını içerir:`TextFragmentAbsorber` sınıfını kullanarak ve sağlanan kalıpla eşleşen cümleleri bulmak için bir normal ifade modeli belirleyerek.

#### S: Metin araması için normal ifade modelini nasıl tanımlarım?

 C: Metin aramaya yönelik bir normal ifade modeli tanımlamak için`TextFragmentAbsorber` kullanarak nesneyi seçin ve desenini ayarlayın.`Text` parametre. Varsayılan deseni değiştir`"\\d{4}-\\d{4}"` öğreticinin kodunda istediğiniz normal ifade düzeniyle.

#### S: Metin araması için normal ifade kullanımını nasıl etkinleştirebilirim?

 C: Normal ifade kullanımı, bir`TextSearchOptions` nesne ve değerini ayarlama`true` . Bu nesneyi şuraya atayın:`TextSearchOptions` mülkiyeti`TextFragmentAbsorber` misal. Bu, metin araması sırasında normal ifade modelinin uygulanmasını sağlar.

#### S: Normal ifade düzeniyle eşleşen metin parçalarını alabilir miyim?

 C: Kesinlikle. PDF belgesinde normal ifade aramasını uyguladıktan sonra, çıkartılan metin parçalarını`TextFragments` mülkiyeti`TextFragmentAbsorber` nesne. Bu metin parçaları, belirtilen düzenli ifade düzeniyle eşleşen metin parçalarını içerir.

#### S: Alınan metin parçalarından neye erişebilirim?

C: Alınan metin parçalarından eşleşen metin içeriği, konum (X ve Y koordinatları), yazı tipi bilgileri (ad, boyut, renk) ve daha fazlası gibi çeşitli özelliklere erişebilirsiniz. Öğreticinin döngüsündeki örnek kod, bu özelliklere nasıl erişileceğini ve görüntüleneceğini gösterir.

#### S: Çıkarılan metin parçaları üzerindeki eylemleri nasıl özelleştirebilirim?

C: Çıkarılan metin parçalarını aldıktan sonra, her metin parçası üzerinde ek eylemler gerçekleştirmek için döngü içindeki kodu özelleştirebilirsiniz. Bu, çıkarılan metnin kaydedilmesini, kalıpların analiz edilmesini veya gereksinimlerinize göre biçimlendirme değişikliklerinin uygulanmasını içerebilir.