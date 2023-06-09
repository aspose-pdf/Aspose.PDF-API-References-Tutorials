---
title: Metin Bölümleri
linktitle: Metin Bölümleri
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET'te düzenli ifadeler kullanarak bir PDF belgesinde belirli metin parçalarını nasıl arayacağınızı öğrenin.
type: docs
weight: 540
url: /tr/net/programming-with-text/text-segments/
---

Bu öğretici, Aspose.PDF for .NET kullanılarak bir PDF belgesinde belirli metin bölümlerinin nasıl aranacağını açıklar. Sağlanan C# kaynak kodu, normal ifadeler kullanan farklı senaryoları gösterir.

## Önkoşullar

Öğreticiye devam etmeden önce, aşağıdakilere sahip olduğunuzdan emin olun:

- C# programlama dili hakkında temel bilgi.
- Aspose.PDF for .NET kitaplığı yüklendi. Aspose web sitesinden edinebilir veya projenize yüklemek için NuGet'i kullanabilirsiniz.

## 1. Adım: Projeyi kurun

Tercih ettiğiniz tümleşik geliştirme ortamında (IDE) yeni bir C# projesi oluşturarak başlayın ve Aspose.PDF for .NET kitaplığına bir referans ekleyin.

## 2. Adım: Gerekli ad alanlarını içe aktarın

Gerekli ad alanlarını içe aktarmak için C# dosyanızın başına aşağıdaki using yönergelerini ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 3. Adım: Metin araması için TextFragmentAbsorber'ı kullanın

 Oluşturmak`TextFragmentAbsorber`normal ifadeler kullanarak belirli metin parçalarını aramak için nesne:

```csharp
TextFragmentAbsorber textFragmentAbsorber;
```

## 4. Adım: Normal ifadelerle metin araması yapın

Normal ifadeleri kullanarak farklı senaryolara dayalı metin aramaları gerçekleştirin. İşte birkaç örnek:

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

- Belirli bir dizeden sonra bir satır sonuna kadar metni bulmak için: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"(?i)the ((.)*)");
```

- Normal ifade eşleşmesinden sonra metni bulmak için: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"(?<=word).*");
```

- PDF belgesinde Köprü/URL aramak için: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"(http|ftp|https):\/\/([\w\-_]+(?:(?:\.[\w\-_]+)+))([\w\-\.,@?^=%&amp;:/~\+#]*[\w\-\@?^=%&amp;/~\+#])?");
```

Normal ifadeleri istediğiniz arama modelleriyle değiştirin.

## 5. Adım: Aramayı gerçekleştirin ve sonuçları işleyin

 Oluşturulanı kullanarak aramayı gerçekleştirin`TextFragmentAbsorber` gereksinimlerinize göre sonuçları itiraz edin ve işleyin.

### Aspose.PDF for .NET kullanan Metin Segmentleri için örnek kaynak kodu 
```csharp
TextFragmentAbsorber textFragmentAbsorber;
// Bir kelimenin tam eşleşmesini aramak için normal ifade kullanmayı düşünebilirsiniz.
textFragmentAbsorber = new TextFragmentAbsorber(@"\bWord\b", new TextSearchOptions(true));
//Bir dizeyi büyük veya küçük harfle aramak için normal ifade kullanmayı düşünebilirsiniz.
textFragmentAbsorber = new TextFragmentAbsorber("(?i)Line", new TextSearchOptions(true));
// PDF belgesindeki tüm dizileri aramak (tüm dizileri ayrıştırmak) için lütfen aşağıdaki normal ifadeyi kullanmayı deneyin.
textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
// Arama dizesinin eşleşmesini bulun ve dizeden sonra satır sonuna kadar her şeyi alın.
textFragmentAbsorber = new TextFragmentAbsorber(@"(?i)the ((.)*)");
// Normal ifade eşleşmesini izleyen metni bulmak için lütfen aşağıdaki normal ifadeyi kullanın.
textFragmentAbsorber = new TextFragmentAbsorber(@"(?<=word).*");
// PDF belgesi içindeki Köprü/URL'leri aramak için lütfen aşağıdaki normal ifadeyi kullanmayı deneyin.
textFragmentAbsorber = new TextFragmentAbsorber(@"(http|ftp|https):\/\/([\w\-_]+(?:(?:\.[\w\-_]+)+))([\w\-\.,@?^=%&amp;:/~\+#]*[\w\-\@?^=%&amp;/~\+#])?");
```


## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesinde belirli metin parçalarını nasıl arayacağınızı başarıyla öğrendiniz. Bu eğitimde, normal ifadelerin kullanıldığı farklı arama senaryolarına ilişkin örnekler sağlanmıştır. Artık PDF dosyalarındaki metin parçalarını aramak ve işlemek için bu kodu kendi C# projelerinize dahil edebilirsiniz.