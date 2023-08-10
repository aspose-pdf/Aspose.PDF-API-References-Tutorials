---
title: PDF Dosyasında Sayı Stilini Uygula
linktitle: PDF Dosyasında Sayı Stilini Uygula
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyasındaki başlıklara numaralandırma stilini nasıl uygulayacağınızı öğrenin. Adım adım rehber.
type: docs
weight: 10
url: /tr/net/programming-with-headings/apply-number-style/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak PDF dosyasına numaralandırma stilini uygulamak için aşağıdaki C# kaynak kodunda adım adım yol göstereceğiz.

Başlamadan önce Aspose.PDF kitaplığını kurduğunuzdan ve geliştirme ortamınızı kurduğunuzdan emin olun. Ayrıca temel C# programlama bilgisine sahip olmak.

### 1. Adım: Belge Dizini Kurulumu

Sağlanan kaynak kodunda, oluşturulan PDF dosyasını kaydetmek istediğiniz dizini belirtmeniz gerekir. "dataDir" değişkenini istenen dizine değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### 2. Adım: PDF Belgesini Oluşturma

Belirtilen boyutlara ve kenar boşluklarına sahip yeni bir PDF belgesi oluşturuyoruz.

```csharp
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

### 3. Adım: Sayfa ve Kayan Kapsayıcı Oluşturma

Belgeye bir sayfa ekliyoruz ve içeriği düzenlemek için yüzen bir kap oluşturuyoruz.

```csharp
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
```

### 4. Adım: Numaralandırmalı başlıklar ekleyin

Belirtilen numaralandırmalara sahip başlıklar oluşturuyoruz ve bunları kayan konteynere ekliyoruz.

```csharp
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading. IsInList = true;
heading. StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading. IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);

Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "Listing 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);

Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "The value, at the effective date of the plan, of the assets to be distributed under the plan

";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
```

### 5. Adım: PDF Belgesini Kaydetme

Oluşturulan PDF belgesini belirtilen dizine kaydediyoruz.

```csharp
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumbering style successfully applied to headers.\nFile saved as: " + dataDir);
```

### Aspose.PDF for .NET kullanarak Number Style Apply için örnek kaynak kodu 
```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
TextFragment textFragment = new TextFragment();
TextSegment segment = new TextSegment();
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading.IsInList = true;
heading.StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);
Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "List 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);
Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "the value, as of the effective date of the plan, of property to be distributed under the plan onaccount of each allowed";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumber style applied successfully in headings.\nFile saved at " + dataDir);  
          
```

## Çözüm

Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesindeki başlıklara numaralandırma stilinin nasıl uygulanacağını açıkladık. Artık bu bilgiyi, başlıklar için özel numaralandırmalara sahip PDF belgeleri oluşturmak için kullanabilirsiniz.

### PDF dosyasında sayı stilini uygulamayla ilgili SSS

#### S: Bir PDF belgesindeki numaralandırma stili nedir?

C: Numaralandırma stili, bir PDF belgesinde başlıkların veya bölümlerin numaralandırıldığı biçimi ifade eder. Hiyerarşik bir yapı sağlamak için rakamlar, harfler veya diğer karakterleri içerebilir.

#### S: Neden bir PDF belgesindeki başlıklara numaralandırma stili uygulamam gerekiyor?

Y: Başlıklara numaralandırma stili uygulamak, PDF belgenizin okunabilirliğini ve düzenini artırır. Okuyucuların içeriğin hiyerarşik yapısını kolayca gezinmesine ve anlamasına yardımcı olur.

#### S: Aspose.PDF for .NET nedir?

Y: Aspose.PDF for .NET, geliştiricilerin .NET uygulamalarında programlı olarak PDF dosyalarıyla çalışmasına olanak sağlayan bir kitaplıktır. PDF belgeleri oluşturmak, düzenlemek, dönüştürmek ve değiştirmek için çok çeşitli özellikler sağlar.

#### S: C# projem için gerekli kitaplıkları nasıl içeri aktarırım?

A: C# projeniz için gerekli kitaplıkları içe aktarmak için aşağıdaki içe aktarma yönergelerini ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Bu yönergeler, PDF belgeleriyle çalışmak ve numaralandırma stillerini uygulamak için gereken sınıflara ve yöntemlere erişmenizi sağlar.

#### S: Oluşturulan PDF dosyasının kaydedileceği dizini nasıl belirleyebilirim?

Y: Sağlanan kaynak kodunda, oluşturulan PDF dosyasını kaydetmek istediğiniz dizini belirtmek için "dataDir" değişkenini değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENTS DIRECTORY"` gerçek dizin yolu ile.

#### S: Belirtilen boyutlara ve kenar boşluklarına sahip bir PDF belgesini nasıl oluştururum?

A: Belirtilen boyutlara ve kenar boşluklarına sahip bir PDF belgesi oluşturmak için aşağıdaki kodu kullanın:

```csharp
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

#### S: Numaralandırma stiline sahip başlıkları PDF belgesine nasıl eklerim?

Y: PDF belgesine numaralandırma stiline sahip başlıklar eklemek için, sağlanan kod örneklerini kullanarak başlıklar oluşturun ve bunların numaralandırma stillerini özelleştirin. Metin, numaralandırma stili, başlangıç numarası ve otomatik sıralama gibi özellikleri gerektiği gibi ayarlayın.

#### S: Oluşturulan PDF belgesini nasıl kaydedebilirim?

 C: Oluşturulan PDF belgesini kaydetmek için`Save` yöntemi`pdfDoc` nesne:

```csharp
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumbering style applied to headers.\nFile saved as: " + dataDir);
```

#### S: Numaralandırma stilinin uygulandığını nasıl doğrulayabilirim?

A: Belirtilen numaralandırma stilinin başlıklara uygulandığını doğrulamak için oluşturulan PDF dosyasını açın.

#### S: Numaralandırma stilini daha da özelleştirebilir miyim?

 A: Evet, özellikleri ayarlayarak numaralandırma stilini daha da özelleştirebilirsiniz.`Heading` numaralandırma stili türü, başlangıç numarası ve otomatik sıralama gibi nesneler.

#### S: Belgenin farklı bölümlerine farklı numaralandırma stilleri uygulayabilir miyim?

C: Evet, birden fazla numara oluşturarak belgenin farklı bölümlerine farklı numaralandırma stilleri uygulayabilirsiniz.`Heading` farklı stil ve dizilere sahip nesneler.