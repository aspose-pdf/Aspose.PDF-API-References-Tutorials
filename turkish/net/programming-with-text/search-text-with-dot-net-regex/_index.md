---
title: Dot Net Regex ile Metin Ara
linktitle: Dot Net Regex ile Metin Ara
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesinde .NET normal ifadelerini kullanarak metin aramayı öğrenin.
type: docs
weight: 480
url: /tr/net/programming-with-text/search-text-with-dot-net-regex/
---

Bu öğretici, bir PDF belgesinde .NET normal ifadeleri kullanarak metin aramak için Aspose.PDF for .NET'in nasıl kullanılacağını açıklar. Sağlanan C# kaynak kodu, süreci adım adım gösterir.

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

## 3. Adım: Belge dizinine giden yolu ayarlayın

 kullanarak belge dizininize giden yolu ayarlayın.`dataDir` değişken:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

## 4. Adım: Bir .NET Regex nesnesi oluşturun

 Oluşturmak`.NET Regex` arama modelini tanımlamak için nesne:

```csharp
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
```

 Yer değiştirmek`@"[\S]+"` istediğiniz düzenli ifade modeliyle.

## 5. Adım: PDF belgesini yükleyin

 kullanarak PDF belgesini yükleyin.`Document` sınıf:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
```

 Yer değiştirmek`"SearchTextRegex.pdf"` PDF dosyanızın gerçek adıyla.

## 6. Adım: Belirli bir sayfa edinin

Belgenin istenen sayfasını alın:

```csharp
Page page = document.Pages[1];
```

 Yer değiştirmek`1` istenen sayfa numarasıyla (1 tabanlı dizin).

## 7. Adım: Bir TextFragmentAbsorber Oluşturun

 Oluşturmak`TextFragmentAbsorber`giriş düzenli ifadesinin tüm örneklerini bulmak için nesne:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
```

## Adım 8: Sayfa için emiciyi kabul edin

Sayfa için emiciyi kabul edin:

```csharp
page.Accept(textFragmentAbsorber);
```

## 9. Adım: Ayıklanan metin parçalarını alın

Ayıklanan metin parçalarını kullanarak alın`TextFragments` mülkiyeti`TextFragmentAbsorber` nesne:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## 10. Adım: Metin parçaları arasında geçiş yapın

Alınan metin parçaları arasında dolaşın ve istenen eylemleri gerçekleştirin:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

Gerekirse her bir metin parçasında başka eylemler gerçekleştirmek için döngü içindeki kodu değiştirin.

### Aspose.PDF for .NET kullanarak Dot Net Regex ile Metin Arama için örnek kaynak kodu 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Tüm kelimeleri bulmak için Regex nesnesi oluşturun
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
// Belgeyi aç
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
// Belirli bir sayfayı al
Page page = document.Pages[1];
// Normal ifade girişinin tüm örneklerini bulmak için TextAbsorber nesnesi oluşturun
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
// Sayfa için soğurucuyu kabul edin
page.Accept(textFragmentAbsorber);
// Ayıklanan metin parçalarını alın
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Parçalar arasında döngü
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesinde .NET normal ifadeleri kullanarak metin aramayı başarıyla öğrendiniz. Bu öğretici, projeyi ayarlamaktan çıkarılan metin parçalarına erişmeye kadar adım adım bir kılavuz sağladı. Artık PDF dosyalarında gelişmiş metin aramaları yapmak için bu kodu kendi C# projelerinize dahil edebilirsiniz.