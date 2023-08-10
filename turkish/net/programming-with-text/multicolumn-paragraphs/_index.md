---
title: Çok Sütunlu Paragraflar
linktitle: Çok Sütunlu Paragraflar
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesinde çok sütunlu paragraflarla nasıl çalışacağınızı öğrenin.
type: docs
weight: 250
url: /tr/net/programming-with-text/multicolumn-paragraphs/
---

Bu eğitimde, Aspose.PDF kütüphanesini kullanarak bir PDF belgesinde çok sütunlu paragraflarla nasıl çalışılacağını açıklayacağız. Sağlanan C# kaynak kodunu kullanarak çok sütunlu paragrafları işleme ve bunlara erişme sürecini adım adım inceleyeceğiz.

## Gereksinimler

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Aspose.PDF for .NET kitaplığı yüklendi.
- Temel bir C# programlama anlayışı.

## 1. Adım: Belge Dizinini kurun

 Öncelikle, giriş PDF dosyanızın bulunduğu dizinin yolunu belirlemeniz gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` içinde`dataDir`PDF dosyanızın yolu ile değişken.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: PDF Belgesini Yükleyin

 Ardından, giriş PDF belgesini kullanarak yüklüyoruz.`Document` Aspose.PDF kitaplığından sınıf.

```csharp
Document doc = new Document(dataDir + "MultiColumnPdf.pdf");
```

## 3. Adım: Çok Sütunlu Paragraflara Erişin

 biz kullanıyoruz`ParagraphAbsorber`PDF belgesindeki paragrafları özümsemek ve ziyaret etmek için sınıf. Daha sonra sayfa işaretlemelerini alır ve çok sütunlu paragraflara erişiriz.

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
PageMarkup markup = absorb.PageMarkups[0];
```

## 4. Adım: Çok Sütunlu Paragraflarla Çalışın

Çok sütunlu yapı içinde belirli bölümlere ve paragraflara erişir ve metinlerini yazdırırız.

```csharp
Console.WriteLine("IsMulticolumnParagraphsAllowed == false\r\n");

// Bir bölümdeki son paragrafa erişme
MarkupSection section = markup.Sections[2];
MarkupParagraph paragraph = section.Paragraphs[section.Paragraphs.Count - 1];
Console.WriteLine("Section at {0} last paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);

// Bir bölümdeki ilk paragrafa erişme
section = markup. Sections[1];
paragraph = section.Paragraphs[0];
Console.WriteLine("\r\nSection at {0} first paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);

// Çok sütunlu paragrafları etkinleştirme
markup.IsMulticolumnParagraphsAllowed = true;
Console.WriteLine("\r\nIsMulticolumnParagraphsAllowed == true\r\n");

// Çok sütunlu paragrafları etkinleştirdikten sonra bir bölümdeki son paragrafa erişme
section = markup. Sections[2];
paragraph = section.Paragraphs[section.Paragraphs.Count - 1];
Console.WriteLine("Section at {0} last paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);

// Çok sütunlu paragrafları etkinleştirdikten sonra bir bölümdeki ilk paragrafa erişme
section = markup. Sections[1];
paragraph = section.Paragraphs[0];
Console.WriteLine("\r\nSection at {0} first paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
```

### Aspose.PDF for .NET kullanan Çok Sütunlu Paragraflar için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "MultiColumnPdf.pdf");
ParagraphAbsorber absorber = new ParagraphAbsorber();
absorber.Visit(doc);
PageMarkup markup = absorber.PageMarkups[0];
Console.WriteLine("IsMulticolumnParagraphsAllowed == false\r\n");
MarkupSection section = markup.Sections[2];
MarkupParagraph paragraph = section.Paragraphs[section.Paragraphs.Count - 1];
Console.WriteLine("Section at {0} last paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
section = markup.Sections[1];
paragraph = section.Paragraphs[0];
Console.WriteLine("\r\nSection at {0} first paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
markup.IsMulticolumnParagraphsAllowed = true;
Console.WriteLine("\r\nIsMulticolumnParagraphsAllowed == true\r\n");
section = markup.Sections[2];
paragraph = section.Paragraphs[section.Paragraphs.Count - 1];
Console.WriteLine("Section at {0} last paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
section = markup.Sections[1];
paragraph = section.Paragraphs[0];
Console.WriteLine("\r\nSection at {0} first paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
```

## Çözüm

Bu öğreticide, Aspose.PDF kitaplığını .NET kullanarak bir PDF belgesinde çok sütunlu paragraflarla çalışmayı öğrendiniz. Adım adım kılavuzu izleyerek ve sağlanan C# kodunu yürüterek, bir PDF belgesindeki çok sütunlu paragraflara erişebilir ve bunları değiştirebilirsiniz.