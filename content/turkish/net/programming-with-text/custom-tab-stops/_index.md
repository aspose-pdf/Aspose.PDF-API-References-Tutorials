---
title: PDF Dosyasındaki Özel Sekme Durakları
linktitle: PDF Dosyasındaki Özel Sekme Durakları
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak PDF dosyasında özel sekme duraklarının nasıl oluşturulacağını öğrenin.
type: docs
weight: 120
url: /tr/net/programming-with-text/custom-tab-stops/
---

Bu eğitim, Aspose.PDF for .NET'i kullanarak PDF dosyasında özel sekme durakları oluşturma sürecinde size rehberlik edecektir. Sağlanan C# kaynak kodu gerekli adımları gösterir.

## Gereksinimler
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Makinenizde kurulu Visual Studio veya başka herhangi bir C# derleyicisi.
- Aspose.PDF for .NET kitaplığı. Resmi Aspose web sitesinden indirebilir veya yüklemek için NuGet gibi bir paket yöneticisi kullanabilirsiniz.

## 1. Adım: Projeyi ayarlayın
1. Tercih ettiğiniz geliştirme ortamında yeni bir C# projesi oluşturun.
2. Aspose.PDF for .NET kitaplığına bir referans ekleyin.

## 2. Adım: Gerekli ad alanlarını içe aktarın
Özel sekme durakları oluşturmak istediğiniz kod dosyasında, dosyanın en üstüne aşağıdaki kullanma yönergelerini ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 3. Adım: Belge dizinini ayarlayın
 Kodda yazan satırı bulun`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` belgelerinizin saklandığı dizinin yolu ile birlikte.

## 4. Adım: Yeni bir Belge örneği oluşturun
 Yeni bir örnek oluştur`Document` Aşağıdaki kod satırını ekleyerek nesne:

```csharp
Document _pdfdocument = new Document();
```

## 5. Adım: Belgeye bir sayfa ekleyin
 kullanarak belgeye yeni bir sayfa ekleyin.`Add` yöntemi`Pages`Toplamak. Verilen kodda yeni sayfa değişkene atanır.`page`.

```csharp
Page page = _pdfdocument.Pages.Add();
```

## 6. Adım: Özel sekme durakları oluşturun
 Oluşturmak`TabStops` nesneyi seçin ve ona özel sekme durakları ekleyin. Her sekme durağı için hizalama tipini ve lider tipini ayarlayın.

```csharp
TabStops ts = new TabStops();
TabStop ts1 = ts.Add(100);
ts1.AlignmentType = TabAlignmentType.Right;
ts1.LeaderType = TabLeaderType.Solid;

TabStop ts2 = ts.Add(200);
ts2.AlignmentType = TabAlignmentType.Center;
ts2.LeaderType = TabLeaderType.Dash;

TabStop ts3 = ts.Add(300);
ts3.AlignmentType = TabAlignmentType.Left;
ts3.LeaderType = TabLeaderType.Dot;
```

## 7. Adım: Sekme duraklarıyla metin parçaları oluşturun
 Yaratmak`TextFragment` nesneleri seçin ve özel sekme duraklarını onlara iletin. Özel karakterleri kullanın`#$TAB` metin içindeki sekme duraklarını belirtmek için.

```csharp
TextFragment header = new TextFragment("This is an example of forming a table with TAB stops", ts);
TextFragment text0 = new TextFragment("#$TABHead1 #$TABHead2 #$TABHead3", ts);
TextFragment text1 = new TextFragment("#$TABdata11 #$TABdata12 #$TABdata13", ts);
TextFragment text2 = new TextFragment("#$TABdata21 ", ts);
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data22 "));
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data23"));

page.Paragraphs.Add(header);
page.Paragraphs.Add(text0);
page.Paragraphs.Add(text1);
page.Paragraphs.Add(text2);
```

## Adım 8: PDF belgesini kaydedin
 PDF belgesini kullanarak kaydedin.`Save` yöntemi`Document` nesne.

```csharp
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

### Aspose.PDF for .NET kullanan Özel Sekme Durakları için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document _pdfdocument = new Document();
Page page = _pdfdocument.Pages.Add();
Aspose.Pdf.Text.TabStops ts = new Aspose.Pdf.Text.TabStops();
Aspose.Pdf.Text.TabStop ts1 = ts.Add(100);
ts1.AlignmentType = TabAlignmentType.Right;
ts1.LeaderType = TabLeaderType.Solid;
Aspose.Pdf.Text.TabStop ts2 = ts.Add(200);
ts2.AlignmentType = TabAlignmentType.Center;
ts2.LeaderType = TabLeaderType.Dash;
Aspose.Pdf.Text.TabStop ts3 = ts.Add(300);
ts3.AlignmentType = TabAlignmentType.Left;
ts3.LeaderType = TabLeaderType.Dot;
TextFragment header = new TextFragment("This is a example of forming table with TAB stops", ts);
TextFragment text0 = new TextFragment("#$TABHead1 #$TABHead2 #$TABHead3", ts);
TextFragment text1 = new TextFragment("#$TABdata11 #$TABdata12 #$TABdata13", ts);
TextFragment text2 = new TextFragment("#$TABdata21 ", ts);
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data22 "));
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data23"));
page.Paragraphs.Add(header);
page.Paragraphs.Add(text0);
page.Paragraphs.Add(text1);
page.Paragraphs.Add(text2);
dataDir = dataDir + "CustomTabStops_out.pdf";
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

## Çözüm
Aspose.PDF for .NET'i kullanarak özel sekme duraklarına sahip bir PDF belgesini başarıyla oluşturdunuz. Ortaya çıkan PDF dosyası artık belirtilen çıktı dosyası yolunda bulunabilir.

### SSS'ler

#### S: Bu eğitimin odak noktası nedir?

C: Bu eğitim, Aspose.PDF for .NET kitaplığını kullanarak bir PDF dosyasında özel sekme durakları oluşturma sürecinde size rehberlik etmeye odaklanmıştır. Sağlanan C# kaynak kodu, bunu başarmak için gerekli adımları gösterir.

#### S: Bu eğitim için hangi ad alanlarını içe aktarmalıyım?

C: Özel sekme durakları oluşturmak istediğiniz kod dosyasında, dosyanın başında aşağıdaki ad alanlarını içe aktarın:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### S: Belge dizinini nasıl belirlerim?

 A: Kodda satırı bulun`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

#### S: Yeni bir Belge örneğini nasıl oluşturabilirim?

 C: 4. Adımda yeni bir örnek oluşturacaksınız.`Document` sağlanan kodu kullanarak nesne.

#### S: Belgeye nasıl sayfa eklerim?

 C: 5. Adımda belgeye yeni bir sayfa ekleyeceksiniz.`Add` yöntemi`Pages` Toplamak.

#### S: Özel sekme duraklarını nasıl oluşturabilirim?

 C: 6. Adımda bir`TabStops` nesneyi seçin ve ona özel sekme durakları ekleyin. Ayrıca her sekme durağı için hizalama ve lider türlerini de ayarlayacaksınız.

#### S: Sekme duraklarıyla metin parçalarını nasıl oluşturabilirim?

 C: 7. Adımda şunu oluşturacaksınız:`TextFragment` nesneleri seçin ve özel sekme duraklarını onlara iletin. Özel karakterleri kullanacaksınız`#$TAB` metin içindeki sekme duraklarını belirtmek için.

#### S: PDF belgesini nasıl kaydederim?

 C: 8. Adımda, PDF belgesini aşağıdaki komutu kullanarak kaydedeceksiniz:`Save` yöntemi`Document` nesne.

#### S: Bu eğitimden çıkan ana sonuç nedir?

C: Bu eğitimi takip ederek Aspose.PDF for .NET kullanarak özel sekme duraklarına sahip bir PDF belgesinin nasıl oluşturulacağını öğrendiniz. Bu, metni yapılandırılmış bir şekilde düzenlemek ve hizalamak için yararlı olabilir.