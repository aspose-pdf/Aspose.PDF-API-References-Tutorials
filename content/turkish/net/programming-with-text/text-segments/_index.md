---
title: PDF Dosyasındaki Metin Segmentleri
linktitle: PDF Dosyasındaki Metin Segmentleri
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET'te düzenli ifadeler kullanarak PDF dosyasındaki belirli metin bölümlerini nasıl arayacağınızı öğrenin.
type: docs
weight: 540
url: /tr/net/programming-with-text/text-segments/
---
Bu eğitimde Aspose.PDF for .NET kullanılarak PDF dosyasındaki belirli metin bölümlerinin nasıl aranacağı açıklanmaktadır. Sağlanan C# kaynak kodu, normal ifadeler kullanan farklı senaryoları gösterir.

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

## 3. Adım: Metin araması için TextFragmentAbsorber'ı kullanın

 Oluşturmak`TextFragmentAbsorber` Düzenli ifadeler kullanarak belirli metin bölümlerini aramak için nesne:

```csharp
TextFragmentAbsorber textFragmentAbsorber;
```

## 4. Adım: Normal ifadelerle metin aramaları gerçekleştirin

Normal ifadeleri kullanarak farklı senaryolara göre metin aramaları gerçekleştirin. İşte birkaç örnek:

- Tam bir kelime eşleşmesi aramak için: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"\bWord\b", new TextSearchOptions(true));
```

- Bir dizeyi büyük veya küçük harfle aramak için: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber("(?i)Line", new TextSearchOptions(true));
```

- PDF belgesindeki tüm dizeleri aramak için: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

- Belirli bir dizeden sonra satır sonuna kadar olan metni bulmak için: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"(?i)the ((.)*)");
```

- Bir normal ifade eşleşmesinden sonraki metni bulmak için: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"(?<=word).*");
```

- PDF belgesinde Köprü/URL aramak için: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"(http|ftp|https):\/\/([\w\-_]+(?:(?:\.[\w\-_]+)+))([\w\-\.,@?^=%&amp;:/~\+#]*[\w\-\@?^=%&amp;/~\+#])?");
```

Normal ifadeleri istediğiniz arama kalıplarıyla değiştirin.

## Adım 5: Aramayı gerçekleştirin ve sonuçları işleyin

 Aramayı oluşturulanı kullanarak gerçekleştirin`TextFragmentAbsorber` Sonuçları gereksinimlerinize göre nesneleştirin ve işleyin.

### Aspose.PDF for .NET kullanan Metin Segmentleri için örnek kaynak kodu 
```csharp
TextFragmentAbsorber textFragmentAbsorber;
// Bir kelimenin tam eşleşmesini aramak için normal ifadeyi kullanmayı düşünebilirsiniz.
textFragmentAbsorber = new TextFragmentAbsorber(@"\bWord\b", new TextSearchOptions(true));
// Bir dizeyi büyük veya küçük harfle aramak için normal ifadeyi kullanmayı düşünebilirsiniz.
textFragmentAbsorber = new TextFragmentAbsorber("(?i)Line", new TextSearchOptions(true));
//PDF belgesindeki tüm dizeleri aramak (tüm dizeleri ayrıştırmak) için lütfen aşağıdaki normal ifadeyi kullanmayı deneyin.
textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
// Arama dizesinin eşleşmesini bulun ve satır sonuna kadar dizeden sonraki herhangi bir şeyi alın.
textFragmentAbsorber = new TextFragmentAbsorber(@"(?i)the ((.)*)");
// Regex eşleşmesini takip eden metni bulmak için lütfen aşağıdaki normal ifadeyi kullanın.
textFragmentAbsorber = new TextFragmentAbsorber(@"(?<=word).*");
// PDF belgesindeki Köprü/URL'yi aramak için lütfen aşağıdaki normal ifadeyi kullanmayı deneyin.
textFragmentAbsorber = new TextFragmentAbsorber(@"(http|ftp|https):\/\/([\w\-_]+(?:(?:\.[\w\-_]+)+))([\w\-\.,@?^=%&amp;:/~\+#]*[\w\-\@?^=%&amp;/~\+#])?");
```


## Çözüm

Tebrikler! Aspose.PDF for .NET'i kullanarak bir PDF belgesinde belirli metin bölümlerini nasıl arayacağınızı başarıyla öğrendiniz. Bu eğitimde, normal ifadeler kullanılarak farklı arama senaryolarının örnekleri verilmiştir. Artık PDF dosyalarındaki metin bölümlerini aramak ve işlemek için bu kodu kendi C# projelerinize dahil edebilirsiniz.

### SSS'ler

#### S: "PDF Dosyasındaki Metin Segmentleri" eğitiminin amacı nedir?

C: "PDF Dosyasındaki Metin Segmentleri" eğitimi, kullanıcılara Aspose.PDF for .NET kullanarak bir PDF dosyasındaki belirli metin segmentlerini nasıl arayabilecekleri konusunda rehberlik etmeyi amaçlamaktadır. Öğreticide, normal ifadeler kullanılarak farklı senaryolara göre metin aramaları gerçekleştirmek için adım adım talimatlar ve C# kod örnekleri sağlanır.

#### S: Bu eğitim, bir PDF belgesindeki metin bölümlerini aramaya nasıl yardımcı olur?

C: Bu eğitim, kullanıcıların bir PDF belgesinde belirli metin bölümlerini aramak için Aspose.PDF for .NET kitaplığını nasıl kullanacaklarını anlamalarına yardımcı olur. Kullanıcılar, çeşitli kod örnekleri ve normal ifadeler sağlayarak, PDF dosyalarında istenen içeriği bulmak için metin arama sorgularını özelleştirebilir.

#### S: Bu öğreticiyi takip etmek için hangi ön koşullar gereklidir?

C: Eğitime başlamadan önce C# programlama dili hakkında temel bilgiye sahip olmanız gerekir. Ayrıca Aspose.PDF for .NET kütüphanesinin de kurulu olması gerekir. Bunu Aspose web sitesinden edinebilir veya NuGet'i kullanarak projenize yükleyebilirsiniz.

#### S: Projemi bu öğreticiyi takip edecek şekilde nasıl ayarlayabilirim?

C: Başlamak için tercih ettiğiniz entegre geliştirme ortamında (IDE) yeni bir C# projesi oluşturun ve Aspose.PDF for .NET kütüphanesine bir referans ekleyin. Bu, kitaplığın PDF belgeleri ve metin parçalarıyla çalışma işlevselliğinden yararlanmanıza olanak tanır.

#### S: Bir PDF dosyasındaki belirli metin bölümlerini nasıl arayabilirim?

 C: Belirli metin bölümlerini aramak için bir`TextFragmentAbsorber` nesne. Öğreticide, farklı arama senaryolarını göstermek için normal ifadeler kullanan çeşitli kod örnekleri sağlanır. Normal ifadeleri değiştirerek istediğiniz arama modellerini tanımlayabilirsiniz.

#### S: Eğitimde ne tür arama senaryoları ele alınıyor?

C: Eğitim, tam kelime eşleşmeleri, büyük/küçük harfe duyarlı olmayan aramalar, bir belge içindeki tüm dizelerin aranması, belirli dizelerden sonraki metnin bulunması ve köprülerin/URL'lerin aranması gibi normal ifadeler kullanan bir dizi arama senaryosunu kapsar. Sağlanan kod örnekleri, özel arama gereksinimlerinize uyacak şekilde özelleştirilebilir.

#### S: Metin araması yaptıktan sonra arama sonuçlarını nasıl işlerim?

 C: Oluşturduktan sonra`TextFragmentAbsorber`nesneyi seçip aramayı gerçekleştirerek, arama sonuçlarını gereksinimlerinize göre işleyebilirsiniz. Eğitim, arama sürecinin kendisini göstermeye odaklanırken, arama sonuçlarını nasıl işleyeceğiniz ve kullanacağınız projenizin ihtiyaçlarına bağlıdır.

#### S: Verilen kod örneklerini kendi projelerimde kullanabilir miyim?

C: Evet, sağlanan kod örneklerini kendi C# projelerinizde referans olarak kullanabilirsiniz. Örnekler, aramanın nasıl ayarlanacağını, normal ifadelerin nasıl tanımlanacağını ve metin aramalarının nasıl gerçekleştirileceğini gösterir. PDF dosyalarındaki belirli metin bölümlerini aramak için bu kodu uygulamalarınıza uyarlayabilir ve entegre edebilirsiniz.

#### S: Öğreticinin tamamını örnek kodla birlikte nerede bulabilirim?

 C: Aşağıdaki bağlantıyı ziyaret ederek eğitimin tamamına erişebilir ve sağlanan örnek C# kodunu görüntüleyebilirsiniz:[https://bit.ly/TextSegmentsTutorial](https://bit.ly/TextSegmentsTutorial)