---
title: PDF Dosyasına Sayı Stili Uygula
linktitle: PDF Dosyasına Sayı Stili Uygula
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyasındaki başlıklara numaralandırma stilinin nasıl uygulanacağını öğrenin. Adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-headings/apply-number-style/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak PDF dosyasına numaralandırma stilini uygulamak için aşağıdaki C# kaynak kodunu adım adım inceleyeceğiz.

Başlamadan önce Aspose.PDF kütüphanesini yüklediğinizden ve geliştirme ortamınızı ayarladığınızdan emin olun. Ayrıca C# programlamanın temel bilgisine sahip olun.

### Adım 1: Belge Dizini Kurulumu

Sağlanan kaynak kodunda, oluşturulan PDF dosyasını kaydetmek istediğiniz dizini belirtmeniz gerekir. "dataDir" değişkenini istediğiniz dizine değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Adım 2: PDF Belgesini Oluşturma

Belirtilen boyutlar ve kenar boşluklarıyla yeni bir PDF belgesi oluşturuyoruz.

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

### Adım 3: Bir Sayfa ve Yüzen Kapsayıcı Oluşturma

Belgeye bir sayfa ekliyoruz ve içeriği düzenlemek için yüzen bir kapsayıcı oluşturuyoruz.

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

### Adım 4: Numaralandırma ile başlıklar ekleyin

Belirtilen numaralandırmalarla başlıklar oluşturuyoruz ve bunları yüzen konteynere ekliyoruz.

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

### Adım 5: PDF Belgesini Kaydetme

Oluşturulan PDF dokümanını belirtilen dizine kaydediyoruz.

```csharp
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumbering style successfully applied to headers.\nFile saved as: " + dataDir);
```

### .NET için Aspose.PDF kullanarak Sayı Stili Uygula için örnek kaynak kodu 
```csharp

// Belgeler dizinine giden yol.
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

Bu eğitimde, .NET için Aspose.PDF kullanarak bir PDF belgesindeki başlıklara numaralandırma stilinin nasıl uygulanacağını açıkladık. Artık bu bilgiyi kullanarak başlıklar için özel numaralandırmalara sahip PDF belgeleri oluşturabilirsiniz.

### PDF dosyasında numara stilini uygulama hakkında SSS

#### S: PDF belgesinde numaralandırma stili nedir?

A: Numaralandırma stili, bir PDF belgesinde başlıkların veya bölümlerin numaralandırıldığı biçimi ifade eder. Hiyerarşik bir yapı sağlamak için sayılar, harfler veya diğer karakterleri içerebilir.

#### S: PDF belgesindeki başlıklara neden numaralandırma stili uygulamam gerekir?

A: Başlıklara numaralandırma stili uygulamak PDF belgenizin okunabilirliğini ve organizasyonunu artırır. Okuyucuların içeriğin hiyerarşik yapısını kolayca gezinmesine ve anlamasına yardımcı olur.

#### S: Aspose.PDF for .NET nedir?

A: Aspose.PDF for .NET, geliştiricilerin .NET uygulamalarında PDF dosyalarıyla programatik olarak çalışmasına olanak tanıyan bir kütüphanedir. PDF belgeleri oluşturmak, düzenlemek, dönüştürmek ve düzenlemek için çok çeşitli özellikler sunar.

#### S: C# projem için gerekli kütüphaneleri nasıl içe aktarabilirim?

A: C# projeniz için gerekli kütüphaneleri içe aktarmak için aşağıdaki içe aktarma yönergelerini ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Bu yönergeler, PDF belgeleriyle çalışmak ve numaralandırma stilleri uygulamak için gereken sınıflara ve yöntemlere erişmenizi sağlar.

#### S: Oluşturulan PDF dosyasının kaydedileceği dizini nasıl belirlerim?

A: Sağlanan kaynak kodunda, oluşturulan PDF dosyasını kaydetmek istediğiniz dizini belirtmek için "dataDir" değişkenini değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENTS DIRECTORY"` gerçek dizin yolu ile.

#### S: Belirtilen boyutlar ve kenar boşluklarıyla bir PDF belgesi nasıl oluşturabilirim?

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

#### S: PDF belgesine numaralandırma stiliyle başlıklar nasıl eklerim?

A: PDF belgesine numaralandırma stiline sahip başlıklar eklemek için, başlıklar oluşturmak ve numaralandırma stillerini özelleştirmek için sağlanan kod örneklerini kullanın. Metin, numaralandırma stili, başlangıç numarası ve otomatik sıra gibi özellikleri gerektiği gibi ayarlayın.

#### S: Oluşturulan PDF belgesini nasıl kaydedebilirim?

 A: Oluşturulan PDF belgesini kaydetmek için şunu kullanın:`Save` yöntemi`pdfDoc` nesne:

```csharp
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumbering style applied to headers.\nFile saved as: " + dataDir);
```

#### S: Numaralandırma stilinin uygulandığını nasıl teyit edebilirim?

A: Başlıklara belirtilen numaralandırma stilinin uygulandığını doğrulamak için oluşturulan PDF dosyasını açın.

#### S: Numaralandırma stilini daha fazla özelleştirebilir miyim?

 A: Evet, numaralandırma stilini, numaralandırma özelliklerini ayarlayarak daha da özelleştirebilirsiniz.`Heading` numaralandırma stili türü, başlangıç numarası ve otomatik sıra gibi nesneler.

#### S: Belgenin farklı bölümlerine farklı numaralandırma stilleri uygulayabilir miyim?

 A: Evet, birden fazla numaralandırma stili oluşturarak belgenin farklı bölümlerine farklı numaralandırma stilleri uygulayabilirsiniz.`Heading` farklı stil ve dizilişlere sahip nesneler.