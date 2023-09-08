---
title: Dot Net Regex ile Metin Arama
linktitle: Dot Net Regex ile Metin Arama
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak bir PDF belgesinde .NET normal ifadelerini kullanarak nasıl metin arayacağınızı öğrenin.
type: docs
weight: 480
url: /tr/net/programming-with-text/search-text-with-dot-net-regex/
---
Bu eğitimde, bir PDF belgesinde .NET normal ifadelerini kullanarak metin aramak için Aspose.PDF for .NET'in nasıl kullanılacağı açıklanmaktadır. Sağlanan C# kaynak kodu süreci adım adım gösterir.

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

## 3. Adım: Belge dizininin yolunu ayarlayın

 kullanarak belge dizininizin yolunu ayarlayın.`dataDir` değişken:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

## 4. Adım: .NET Regex nesnesi oluşturun

 Oluşturmak`.NET Regex` Arama modelini tanımlamak için nesne:

```csharp
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
```

 Yer değiştirmek`@"[\S]+"` İstediğiniz düzenli ifade modeliyle.

## 5. Adım: PDF belgesini yükleyin

 PDF belgesini kullanarak yükleyin`Document` sınıf:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
```

 Yer değiştirmek`"SearchTextRegex.pdf"` PDF dosyanızın gerçek adıyla.

## 6. Adım: Belirli bir sayfayı edinin

Belgenin istediğiniz sayfasını alın:

```csharp
Page page = document.Pages[1];
```

 Yer değiştirmek`1` İstenilen sayfa numarasıyla (1 tabanlı dizin).

## Adım 7: TextFragmentAbsorber oluşturun

 Oluşturmak`TextFragmentAbsorber` giriş normal ifadesinin tüm örneklerini bulmak için nesne:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
```

## 8. Adım: Sayfanın emicisini kabul edin

Sayfa için emiciyi kabul edin:

```csharp
page.Accept(textFragmentAbsorber);
```

## 9. Adım: Çıkarılan metin parçalarını alın

Çıkarılan metin parçalarını kullanarak alın`TextFragments` mülkiyeti`TextFragmentAbsorber` nesne:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Adım 10: Metin parçaları arasında dolaşın

Alınan metin parçaları arasında dolaşın ve istediğiniz eylemleri gerçekleştirin:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

Gerekirse her metin parçası üzerinde daha fazla eylem gerçekleştirmek için döngü içindeki kodu değiştirin.

### Aspose.PDF for .NET kullanarak Dot Net Regex ile Metin Arama için örnek kaynak kodu 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Tüm kelimeleri bulmak için Regex nesnesi oluşturun
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
// Belgeyi aç
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
// Belirli bir sayfayı edinin
Page page = document.Pages[1];
// Giriş normal ifadesinin tüm örneklerini bulmak için TextAbsorber nesnesi oluşturun
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
// Sayfanın emicisini kabul edin
page.Accept(textFragmentAbsorber);
// Çıkarılan metin parçalarını alın
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Parçalar arasında döngü yapın
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

## Çözüm

Tebrikler! Aspose.PDF for .NET'i kullanarak bir PDF belgesinde .NET normal ifadelerini kullanarak nasıl metin arayacağınızı başarıyla öğrendiniz. Bu eğitimde, projenin kurulumundan çıkarılan metin parçalarına erişmeye kadar adım adım bir kılavuz sağlanmıştır. Artık PDF dosyalarında gelişmiş metin aramaları gerçekleştirmek için bu kodu kendi C# projelerinize dahil edebilirsiniz.

### SSS'ler

#### S: "Dot Net Regex ile Metin Arama" öğreticisinin amacı nedir?

C: "Dot Net Regex ile Metin Arama" eğitimi, kullanıcılara, .NET normal ifadelerini kullanarak bir PDF belgesi içinde metin aramak için .NET için Aspose.PDF kütüphanesini kullanma konusunda rehberlik etmeyi amaçlamaktadır. Öğretici, süreci göstermek için adım adım talimatlar ve C# kod örnekleri sağlar.

#### S: Bu eğitim, PDF'de .NET normal ifadeleri kullanarak metin aramaya nasıl yardımcı olur?

C: Bu eğitim, kullanıcıların Aspose.PDF for .NET'in bir PDF belgesinde .NET normal ifadelerini kullanarak metin arama yeteneklerinden nasıl yararlanabileceklerini anlamalarına yardımcı olur. Sağlanan adımları ve kod örneklerini takip ederek kullanıcılar, belirledikleri normal ifadelerle eşleşen metin kalıplarını etkili bir şekilde arayabilir.

#### S: Bu öğreticiyi takip etmek için hangi ön koşullar gereklidir?

C: Eğitime başlamadan önce C# programlama dili hakkında temel bilgiye sahip olmanız gerekir. Ayrıca Aspose.PDF for .NET kütüphanesinin de kurulu olması gerekir. Bunu Aspose web sitesinden edinebilir veya NuGet'i kullanarak projenize yükleyebilirsiniz.

#### S: Projemi bu öğreticiyi takip edecek şekilde nasıl ayarlayabilirim?

C: Başlamak için tercih ettiğiniz entegre geliştirme ortamında (IDE) yeni bir C# projesi oluşturun ve Aspose.PDF for .NET kütüphanesine bir referans ekleyin. Bu, kitaplığın PDF belgelerini arama ve bunlarla çalışma özelliklerini kullanmanızı sağlayacaktır.

#### S: Bu öğreticiyi, .NET normal ifadelerini kullanarak herhangi bir belirli metin türünü aramak için kullanabilir miyim?

 C: Evet, bu eğitimde bir PDF belgesinde .NET normal ifadeleri kullanılarak nasıl metin aranacağıyla ilgili talimatlar verilmektedir. özelleştirebilirsiniz`.NET Regex` Kullanmak istediğiniz belirli arama modelini tanımlamak için nesneyi seçin.

#### S: Bu öğreticide aranacak .NET normal ifade modelini nasıl belirleyebilirim?

 C: Aramak istediğiniz .NET normal ifade modelini belirtmek için bir`.NET Regex` nesneyi oluşturun ve uygun normal ifade sözdizimini kullanarak desenini ayarlayın. Varsayılanı değiştir`@"[\S]+"` öğreticinin kodunda istediğiniz normal ifadeyi kullanın.

#### S: Çıkarılan metin parçalarının özelliklerini nasıl alabilirim?

 C: Kabul ettikten sonra`TextFragmentAbsorber` PDF'nin belirli bir sayfası için, çıkartılan metin parçalarını`TextFragments` soğurucu nesnenin özelliği. Bu, belirtilen .NET normal ifadesiyle eşleşen metin parçaları koleksiyonuna erişim sağlar.

#### S: Çıkarılan her metin parçasında ek eylemler gerçekleştirmek için kodu özelleştirebilir miyim?

C: Kesinlikle. Öğreticinin örnek kodu, alınan metin parçaları arasında yineleme yapmak için bir döngü içerir. Proje gereksinimlerinize göre çıkarılan her metin parçası üzerinde ek eylemler gerçekleştirmek için bu döngü içindeki kodu özelleştirebilirsiniz.

#### S: Metin parçalarını çıkardıktan sonra değiştirilen PDF belgesini nasıl kaydedebilirim?

C: Bu eğitim öncelikle .NET normal ifadelerini kullanarak metin aramaya ve metin parçalarını almaya odaklanıyor. PDF'de değişiklik yapmayı düşünüyorsanız, belgeyi özel ihtiyaçlarınıza göre nasıl değiştireceğinizi ve kaydedeceğinizi öğrenmek için diğer Aspose.PDF belgelerine başvurabilirsiniz.