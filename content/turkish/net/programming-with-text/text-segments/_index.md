---
title: PDF Dosyasındaki Metin Bölümleri
linktitle: PDF Dosyasındaki Metin Bölümleri
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET'te düzenli ifadeler kullanarak PDF dosyasındaki belirli metin parçalarını nasıl arayacağınızı öğrenin.
type: docs
weight: 540
url: /tr/net/programming-with-text/text-segments/
---
Bu eğitim, .NET için Aspose.PDF kullanarak PDF dosyasında belirli metin segmentlerinin nasıl aranacağını açıklar. Sağlanan C# kaynak kodu, düzenli ifadeler kullanılarak farklı senaryoları gösterir.

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

## Adım 3: Metin araması için TextFragmentAbsorber'ı kullanın

 Bir tane oluştur`TextFragmentAbsorber` Düzenli ifadeler kullanarak belirli metin parçalarını arama nesnesi:

```csharp
TextFragmentAbsorber textFragmentAbsorber;
```

## Adım 4: Düzenli ifadelerle metin aramaları gerçekleştirin

Düzenli ifadeleri kullanarak farklı senaryolara dayalı metin aramaları gerçekleştirin. İşte birkaç örnek:

- Tam eşleşen bir kelimeyi aramak için: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"\bWord\b", new TextSearchOptions(true));
```

- Bir dizeyi büyük veya küçük harfle aramak için: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber("(?i)Line", new TextSearchOptions(true));
```

- PDF belgesinin içindeki tüm dizeleri aramak için: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

- Belirli bir dizeden sonraki satır sonuna kadar olan metni bulmak için: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"(?i)the ((.)*)");
```

- Bir regex eşleşmesini takip eden metni bulmak için: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"(?<=word).*");
```

- PDF belgesinin içinde Köprü/URL aramak için: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"(http|ftp|https):\/\/([\w\-_]+(?:(?:\.[\w\-_]+)+))([\w\-\.,@?^=%&amp;:/~\+#]*[\w\-\@?^=%&amp;/~\+#])?");
```

Düzenli ifadeleri istediğiniz arama kalıplarıyla değiştirin.

## Adım 5: Aramayı gerçekleştirin ve sonuçları işleyin

 Oluşturulan aramayı kullanarak aramayı gerçekleştirin`TextFragmentAbsorber` İhtiyaçlarınıza göre sonuçları nesnelleştirin ve işleyin.

### .NET için Aspose.PDF kullanılarak Metin Segmentleri için örnek kaynak kodu 
```csharp
TextFragmentAbsorber textFragmentAbsorber;
// Bir kelimenin tam eşleşmesini aramak için düzenli ifade kullanmayı düşünebilirsiniz.
textFragmentAbsorber = new TextFragmentAbsorber(@"\bWord\b", new TextSearchOptions(true));
// Bir dizgeyi büyük veya küçük harfle aramak için düzenli ifade kullanmayı düşünebilirsiniz.
textFragmentAbsorber = new TextFragmentAbsorber("(?i)Line", new TextSearchOptions(true));
//PDF dokümanı içerisindeki tüm dizeleri aramak (tüm dizeleri ayrıştırmak) için lütfen aşağıdaki düzenli ifadeyi kullanmayı deneyin.
textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
// Arama dizesinin eşleşmesini bul ve dizenin sonundan satır sonuna kadar olan her şeyi al.
textFragmentAbsorber = new TextFragmentAbsorber(@"(?i)the ((.)*)");
// Regex eşleşmesini izleyen metni bulmak için lütfen aşağıdaki düzenli ifadeyi kullanın.
textFragmentAbsorber = new TextFragmentAbsorber(@"(?<=word).*");
// PDF dokümanı içerisinde Hyperlink/URL'leri aramak için lütfen aşağıdaki düzenli ifadeyi kullanmayı deneyin.
textFragmentAbsorber = new TextFragmentAbsorber(@"(http|ftp|https):\/\/([\w\-_]+(?:(?:\.[\w\-_]+)+))([\w\-\.,@?^=%&amp;:/~\+#]*[\w\-\@?^=%&amp;/~\+#])?");
```


## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesindeki belirli metin parçalarını aramayı başarıyla öğrendiniz. Bu eğitimde düzenli ifadeler kullanılarak farklı arama senaryolarına dair örnekler verilmiştir. Artık bu kodu kendi C# projelerinize dahil ederek PDF dosyalarındaki metin parçalarını arayabilir ve işleyebilirsiniz.

### SSS

#### S: "PDF Dosyasındaki Metin Parçaları" eğitiminin amacı nedir?

A: "PDF Dosyasındaki Metin Segmentleri" öğreticisinin amacı, kullanıcılara .NET için Aspose.PDF kullanarak bir PDF dosyasında belirli metin segmentlerini nasıl arayacakları konusunda rehberlik etmektir. Öğretici, düzenli ifadeler kullanarak farklı senaryolara dayalı metin aramaları gerçekleştirmek için adım adım talimatlar ve C# kod örnekleri sağlar.

#### S: Bu eğitim PDF belgesinde metin parçalarını aramada nasıl yardımcı oluyor?

A: Bu eğitim, kullanıcıların bir PDF belgesindeki belirli metin bölümlerini aramak için Aspose.PDF for .NET kitaplığını nasıl kullanacaklarını anlamalarına yardımcı olur. Çeşitli kod örnekleri ve düzenli ifadeler sağlayarak, kullanıcılar PDF dosyalarında istedikleri içeriği bulmak için metin arama sorgularını özelleştirebilir.

#### S: Bu eğitimi takip etmek için hangi ön koşullar gereklidir?

A: Eğitime başlamadan önce, C# programlama dili hakkında temel bir anlayışa sahip olmalısınız. Ek olarak, .NET için Aspose.PDF kütüphanesinin yüklü olması gerekir. Bunu Aspose web sitesinden edinebilir veya NuGet kullanarak projenize yükleyebilirsiniz.

#### S: Bu eğitimi takip edecek şekilde projemi nasıl kurarım?

A: Başlamak için, tercih ettiğiniz entegre geliştirme ortamında (IDE) yeni bir C# projesi oluşturun ve Aspose.PDF for .NET kitaplığına bir referans ekleyin. Bu, PDF belgeleri ve metin parçalarıyla çalışmak için kitaplığın işlevselliğinden yararlanmanızı sağlayacaktır.

#### S: PDF dosyası içindeki belirli metin bölümlerini nasıl arayabilirim?

 A: Belirli metin bölümlerini aramak için bir`TextFragmentAbsorber` nesne. Eğitim, farklı arama senaryolarını göstermek için düzenli ifadeler kullanan çeşitli kod örnekleri sağlar. Düzenli ifadeleri değiştirerek istediğiniz arama kalıplarını tanımlayabilirsiniz.

#### S: Eğitimde hangi tür arama senaryoları ele alınıyor?

A: Eğitim, tam kelime eşleşmeleri, büyük/küçük harfe duyarlı olmayan aramalar, bir belgedeki tüm dizeleri arama, belirli dizelerden sonra metin bulma ve köprü metinleri/URL'leri arama gibi düzenli ifadeler kullanan bir dizi arama senaryosunu kapsar. Sağlanan kod örnekleri, belirli arama gereksinimlerinize uyacak şekilde özelleştirilebilir.

#### S: Metin araması yaptıktan sonra arama sonuçlarını nasıl işlerim?

 A: Bir tane oluşturduktan sonra`TextFragmentAbsorber`nesne ve aramayı gerçekleştirerek, arama sonuçlarını gereksinimlerinize göre işleyebilirsiniz. Eğitim, arama sürecinin kendisini göstermeye odaklanırken, arama sonuçlarını nasıl işleyip kullanacağınız projenizin ihtiyaçlarına bağlıdır.

#### S: Sağlanan kod örneklerini kendi projelerimde kullanabilir miyim?

C: Evet, sağlanan kod örneklerini kendi C# projelerinizde referans olarak kullanabilirsiniz. Örnekler aramanın nasıl kurulacağını, düzenli ifadelerin nasıl tanımlanacağını ve metin aramalarının nasıl gerçekleştirileceğini gösterir. Bu kodu PDF dosyalarında belirli metin bölümlerini aramak için uygulamalarınıza uyarlayabilir ve entegre edebilirsiniz.

#### S: Örnek kodla birlikte tam eğitimi nerede bulabilirim?

 A: Aşağıdaki bağlantıyı ziyaret ederek tam eğitime erişebilir ve verilen örnek C# kodunu görüntüleyebilirsiniz:[https://bit.ly/TextSegmentsTutorial](https://bit.ly/TextSegmentsTutorial)