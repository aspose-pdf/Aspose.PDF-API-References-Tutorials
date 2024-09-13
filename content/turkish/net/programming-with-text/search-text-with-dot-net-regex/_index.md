---
title: Dot Net Regex ile Metin Arama
linktitle: Dot Net Regex ile Metin Arama
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesinde .NET düzenli ifadelerini kullanarak metin aramayı öğrenin.
type: docs
weight: 480
url: /tr/net/programming-with-text/search-text-with-dot-net-regex/
---
Bu eğitim, .NET düzenli ifadelerini kullanarak bir PDF belgesinde metin aramak için Aspose.PDF for .NET'in nasıl kullanılacağını açıklar. Sağlanan C# kaynak kodu, işlemi adım adım gösterir.

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

## Adım 3: Belge dizinine giden yolu ayarlayın

 Belge dizininize giden yolu kullanarak ayarlayın`dataDir` değişken:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belge dizininize giden gerçek yol ile.

## Adım 4: Bir .NET Regex nesnesi oluşturun

 Bir tane oluştur`.NET Regex` arama modelini tanımlayan nesne:

```csharp
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
```

 Yer değiştirmek`@"[\S]+"` İstediğiniz düzenli ifade kalıbıyla.

## Adım 5: PDF belgesini yükleyin

 PDF belgesini kullanarak yükleyin`Document` sınıf:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
```

 Yer değiştirmek`"SearchTextRegex.pdf"` PDF dosyanızın gerçek adıyla.

## Adım 6: Belirli bir sayfayı alın

Belgenin istenilen sayfasını alın:

```csharp
Page page = document.Pages[1];
```

 Yer değiştirmek`1` İstenilen sayfa numarasıyla (1 tabanlı dizin).

## Adım 7: Bir TextFragmentAbsorber Oluşturun

 Bir tane oluştur`TextFragmentAbsorber` Giriş düzenli ifadesinin tüm örneklerini bulmak için nesne:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
```

## Adım 8: Sayfa için emiciyi kabul edin

Sayfa için emiciyi kabul edin:

```csharp
page.Accept(textFragmentAbsorber);
```

## Adım 9: Çıkarılan metin parçalarını alın

 Çıkarılan metin parçalarını kullanarak alın`TextFragments` mülkiyeti`TextFragmentAbsorber` nesne:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Adım 10: Metin parçaları arasında döngü oluşturun

Alınan metin parçaları arasında dolaşın ve istediğiniz eylemleri gerçekleştirin:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

Gerekirse her metin parçası üzerinde daha fazla işlem gerçekleştirmek için döngü içindeki kodu değiştirin.

### .NET için Aspose.PDF kullanarak Nokta Net Regex ile Arama Metni için örnek kaynak kodu 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Tüm kelimeleri bulmak için Regex nesnesi oluşturun
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
// Belgeyi aç
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
// Belirli bir sayfayı al
Page page = document.Pages[1];
// Giriş regex'inin tüm örneklerini bulmak için TextAbsorber nesnesi oluşturun
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
// Sayfa için emiciyi kabul et
page.Accept(textFragmentAbsorber);
// Çıkarılan metin parçalarını alın
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Parçalar arasında döngü
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

## Çözüm

Tebrikler! .NET için Aspose.PDF kullanarak bir PDF belgesinde .NET düzenli ifadelerini kullanarak metin aramayı başarıyla öğrendiniz. Bu eğitim, projeyi kurmaktan çıkarılan metin parçalarına erişmeye kadar adım adım bir kılavuz sağladı. Artık bu kodu kendi C# projelerinize dahil ederek PDF dosyalarında gelişmiş metin aramaları yapabilirsiniz.

### SSS

#### S: "Dot Net Regex ile Metin Arama" eğitiminin amacı nedir?

A: "Dot Net Regex ile Metin Arama" öğreticisinin amacı, kullanıcıların .NET için Aspose.PDF kütüphanesini kullanarak .NET düzenli ifadelerini kullanarak bir PDF belgesi içinde metin araması yapmaları konusunda rehberlik etmektir. Öğretici, işlemi göstermek için adım adım talimatlar ve C# kod örnekleri sağlar.

#### S: Bu eğitim, .NET düzenli ifadelerini kullanarak PDF'te metin aramada nasıl yardımcı olur?

A: Bu eğitim, kullanıcıların .NET düzenli ifadelerini kullanarak bir PDF belgesi içinde metin aramak için Aspose.PDF for .NET'in yeteneklerinden nasıl yararlanacaklarını anlamalarına yardımcı olur. Sağlanan adımları ve kod örneklerini izleyerek, kullanıcılar belirtilen düzenli ifadeleriyle eşleşen metin desenlerini etkili bir şekilde arayabilir.

#### S: Bu eğitimi takip etmek için hangi ön koşullar gereklidir?

A: Eğitime başlamadan önce, C# programlama dili hakkında temel bir anlayışa sahip olmalısınız. Ek olarak, .NET için Aspose.PDF kütüphanesinin yüklü olması gerekir. Bunu Aspose web sitesinden edinebilir veya NuGet kullanarak projenize yükleyebilirsiniz.

#### S: Bu eğitimi takip edecek şekilde projemi nasıl kurarım?

A: Başlamak için, tercih ettiğiniz entegre geliştirme ortamında (IDE) yeni bir C# projesi oluşturun ve Aspose.PDF for .NET kitaplığına bir referans ekleyin. Bu, PDF belgelerini aramak ve bunlarla çalışmak için kitaplığın özelliklerini kullanmanızı sağlayacaktır.

#### S: Bu eğitimi, .NET düzenli ifadelerini kullanarak herhangi belirli bir metin türünü aramak için kullanabilir miyim?

 A: Evet, bu eğitim, bir PDF belgesi içinde .NET düzenli ifadelerini kullanarak metin arama konusunda talimatlar sağlar. Özelleştirebilirsiniz`.NET Regex` Kullanmak istediğiniz belirli arama modelini tanımlamak için nesne.

#### S: Bu eğitimde arama yapmak için .NET düzenli ifade desenini nasıl belirtirim?

 A: Aramak istediğiniz .NET düzenli ifade desenini belirtmek için bir`.NET Regex` nesneyi seçin ve uygun düzenli ifade sözdizimini kullanarak desenini ayarlayın. Varsayılanı değiştirin`@"[\S]+"` İstediğiniz düzenli ifadeyi eğitimin koduna ekleyin.

#### S: Çıkarılan metin parçalarının özelliklerini nasıl alabilirim?

 A: Kabul ettikten sonra`TextFragmentAbsorber` PDF'nin belirli bir sayfası için, çıkarılan metin parçalarını kullanarak alabilirsiniz`TextFragments` emici nesnenin özelliği. Bu, belirtilen .NET düzenli ifadesiyle eşleşen bir metin parçaları koleksiyonuna erişim sağlar.

#### S: Her çıkarılan metin parçasında ek eylemler gerçekleştirmek için kodu özelleştirebilir miyim?

A: Elbette. Eğitimin örnek kodu, alınan metin parçaları arasında yineleme yapmak için bir döngü içerir. Projenizin gereksinimlerine göre her çıkarılan metin parçasında ek eylemler gerçekleştirmek için bu döngü içindeki kodu özelleştirebilirsiniz.

#### S: Metin parçalarını çıkardıktan sonra değiştirilen PDF belgesini nasıl kaydederim?

A: Bu eğitim, öncelikle .NET düzenli ifadelerini kullanarak metin arama ve metin parçalarını almaya odaklanır. PDF'de değişiklik yapmayı düşünüyorsanız, belgeyi özel ihtiyaçlarınıza göre nasıl düzenleyip kaydedeceğinizi öğrenmek için diğer Aspose.PDF belgelerine başvurabilirsiniz.