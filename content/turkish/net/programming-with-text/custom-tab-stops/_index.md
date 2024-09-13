---
title: PDF Dosyasında Özel Sekme Durakları
linktitle: PDF Dosyasında Özel Sekme Durakları
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyasında özel sekme duraklarının nasıl oluşturulacağını öğrenin.
type: docs
weight: 120
url: /tr/net/programming-with-text/custom-tab-stops/
---

Bu eğitim, .NET için Aspose.PDF kullanarak PDF dosyasında özel sekme durakları oluşturma sürecinde size rehberlik edecektir. Sağlanan C# kaynak kodu gerekli adımları göstermektedir.

## Gereksinimler
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Bilgisayarınızda Visual Studio veya herhangi bir C# derleyicisi yüklü olmalıdır.
- Aspose.PDF for .NET kütüphanesi. Resmi Aspose web sitesinden indirebilir veya NuGet gibi bir paket yöneticisi kullanarak kurabilirsiniz.

## Adım 1: Projeyi kurun
1. Tercih ettiğiniz geliştirme ortamında yeni bir C# projesi oluşturun.
2. .NET için Aspose.PDF kitaplığına bir referans ekleyin.

## Adım 2: Gerekli ad alanlarını içe aktarın
Özel sekme durakları oluşturmak istediğiniz kod dosyasında, dosyanın en üstüne aşağıdaki using yönergelerini ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Adım 3: Belge dizinini ayarlayın
 Kodda şu satırı bulun:`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` Belgelerinizin saklandığı dizinin yolunu içeren.

## Adım 4: Yeni bir Belge örneği oluşturun
 Yeni bir örnek oluştur`Document` Aşağıdaki kod satırını ekleyerek nesneyi oluşturun:

```csharp
Document _pdfdocument = new Document();
```

## Adım 5: Belgeye bir sayfa ekleyin
 Belgeye yeni bir sayfa eklemek için şunu kullanın:`Add` yöntemi`Pages` koleksiyon. Sağlanan kodda, yeni sayfa değişkene atanır`page`.

```csharp
Page page = _pdfdocument.Pages.Add();
```

## Adım 6: Özel sekme durakları oluşturun
 Bir tane oluştur`TabStops` nesne ve ona özel sekme durakları ekleyin. Her sekme durağı için hizalama türünü ve lider türünü ayarlayın.

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

## Adım 7: Sekme durakları içeren metin parçaları oluşturun
 Yaratmak`TextFragment` nesneleri kullanın ve özel sekme duraklarını onlara iletin. Özel karakterleri kullanın`#$TAB` metin içindeki sekme duraklarını belirtmek için.

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
 PDF belgesini kullanarak kaydedin`Save` yöntemi`Document` nesne.

```csharp
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

### .NET için Aspose.PDF kullanılarak Özel Sekme Durakları için örnek kaynak kodu 
```csharp
// Belgeler dizinine giden yol.
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
Aspose.PDF for .NET kullanarak özel sekme duraklarına sahip bir PDF belgesini başarıyla oluşturdunuz. Ortaya çıkan PDF dosyası artık belirtilen çıktı dosyası yolunda bulunabilir.

### SSS

#### S: Bu eğitimin odak noktası nedir?

A: Bu eğitim, Aspose.PDF for .NET kitaplığını kullanarak bir PDF dosyasında özel sekme durakları oluşturma sürecinde size rehberlik etmeye odaklanmıştır. Sağlanan C# kaynak kodu, bunu başarmak için gerekli adımları göstermektedir.

#### S: Bu eğitim için hangi ad alanlarını içe aktarmalıyım?

A: Özel sekme durakları oluşturmak istediğiniz kod dosyasında, dosyanın başına aşağıdaki ad alanlarını içe aktarın:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### S: Belge dizinini nasıl belirlerim?

 A: Kodda şu satırı bulun:`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` belge dizininize giden gerçek yol ile.

#### S: Yeni bir Belge örneği nasıl oluştururum?

 A: 4. Adımda yeni bir örnek oluşturacaksınız`Document` Sağlanan kodu kullanarak nesne.

#### S: Belgeye nasıl sayfa eklerim?

 A: 5. Adımda, belgeye yeni bir sayfa ekleyeceksiniz`Add` yöntemi`Pages` koleksiyon.

#### S: Özel sekme duraklarını nasıl oluşturabilirim?

 A: 6. Adımda bir tane oluşturacaksınız`TabStops` nesneye özel sekme durakları ekleyin. Ayrıca her sekme durağı için hizalama ve lider türlerini de ayarlayacaksınız.

#### S: Sekme durakları içeren metin parçaları nasıl oluştururum?

 A: 7. Adımda şunları yaratacaksınız:`TextFragment` nesneleri kullanın ve özel sekme duraklarını onlara iletin. Özel karakterleri kullanacaksınız`#$TAB` metin içindeki sekme duraklarını belirtmek için.

#### S: PDF belgesini nasıl kaydedebilirim?

 A: 8. Adımda, PDF belgesini kullanarak kaydedeceksiniz`Save` yöntemi`Document` nesne.

#### S: Bu eğitimden çıkarılacak en önemli ders nedir?

A: Bu öğreticiyi takip ederek, Aspose.PDF for .NET kullanarak özel sekme duraklarına sahip bir PDF belgesinin nasıl oluşturulacağını öğrendiniz. Bu, metni yapılandırılmış bir şekilde düzenlemek ve hizalamak için yararlı olabilir.