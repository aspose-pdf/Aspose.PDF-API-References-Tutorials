---
title: Çok Sütunlu PDF Oluştur
linktitle: Çok Sütunlu PDF Oluştur
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak çok sütunlu PDF'nin nasıl oluşturulacağını öğrenin.
type: docs
weight: 110
url: /tr/net/programming-with-text/create-multi-column-pdf/
---
Bu eğitim, .NET için Aspose.PDF kullanarak çok sütunlu bir PDF oluşturma sürecinde size rehberlik edecektir. Sağlanan C# kaynak kodu gerekli adımları göstermektedir.

## Gereksinimler
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Bilgisayarınızda Visual Studio veya herhangi bir C# derleyicisi yüklü olmalıdır.
- Aspose.PDF for .NET kütüphanesi. Resmi Aspose web sitesinden indirebilir veya NuGet gibi bir paket yöneticisi kullanarak kurabilirsiniz.

## Adım 1: Projeyi kurun
1. Tercih ettiğiniz geliştirme ortamında yeni bir C# projesi oluşturun.
2. .NET için Aspose.PDF kitaplığına bir referans ekleyin.

## Adım 2: Gerekli ad alanlarını içe aktarın
Çok sütunlu PDF oluşturmak istediğiniz kod dosyasında, dosyanın en üstüne aşağıdaki using yönergelerini ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

## Adım 3: Belge dizinini ayarlayın
 Kodda şu satırı bulun:`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` Belgelerinizin saklandığı dizinin yolunu içeren.

## Adım 4: Yeni bir Belge örneği oluşturun
 Yeni bir örnek oluştur`Document` Aşağıdaki kod satırını ekleyerek nesneyi oluşturun:

```csharp
Document doc = new Document();
```

## Adım 5: Sayfa kenar boşluklarını ayarlayın
 PDF dosyası için sol ve sağ kenar boşluğu bilgilerini belirtin`PageInfo.Margin` mülkiyeti`Document`.

```csharp
doc.PageInfo.Margin.Left = 40;
doc.PageInfo.Margin.Right = 40;
```

## Adım 6: Belgeye bir sayfa ekleyin
 Belgeye yeni bir sayfa eklemek için şunu kullanın:`Add` yöntemi`Pages` koleksiyon. Sağlanan kodda, yeni sayfa değişkene atanır`page`.

```csharp
Page page = doc.Pages.Add();
```

## Adım 7: Bir Grafik nesnesi oluşturun ve bir çizgi ekleyin
 Yeni bir tane oluştur`Graph` belirli boyutlara sahip bir nesne seçin ve ona bir çizgi ekleyin. Ardından,`Graph` itiraz etmek`Paragraphs` Sayfanın koleksiyonu.

```csharp
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
float[] backPos = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
page.Paragraphs.Add(graph1);
```

## Adım 8: HTML biçimlendirmesiyle başlık metni ekleyin
 Bir tane oluştur`HtmlFragment` nesneyi ekleyin ve içeriğini istediğiniz HTML metnine ayarlayın. Ardından, parçayı`Paragraphs` Sayfanın koleksiyonu.

```csharp
string s = "<font face=\"Times New Roman\" size=4>" +
     "<strong>How to Steer Clear of money scams</<strong>" +
     "</font>";
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
```

## Adım 9: Birden fazla sütuna sahip bir FloatingBox oluşturun
 Bir tane oluştur`FloatingBox` nesneyi seçin ve sütun sayısını ve sütun aralığını ayarlayın. Ardından, metin parçaları ve bir satır ekleyin`Paragraphs` koleksiyonu`FloatingBox`.

```csharp
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();
box. ColumnInfo. ColumnCount = 2;
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";

TextFragment text1 = new TextFragment("By A Googling (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.LineSpacing = 2;
box.Paragraphs.Add(text1);

TextFragment text2 = new TextFragment("Sed augue tortor, sodales id, luctus et, pulvinar ut, eros. Suspendisse vel dolor. Sed quam. Curabitur ut massa vitae eros euismod aliquam...");
box.Paragraphs.Add(text2);

Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
box.Paragraphs.Add(graph2);

page.Paragraphs.Add(box);
```

## Adım 10: PDF belgesini kaydedin
 PDF belgesini kullanarak kaydedin`Save` yöntemi`Document` nesne.

```csharp
doc.Save(dataDir);
```

### .NET için Aspose.PDF kullanarak Çok Sütunlu PDF Oluşturma için örnek kaynak kodu 
```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
// PDF dosyası için sol kenar boşluğu bilgisini belirtin
doc.PageInfo.Margin.Left = 40;
// PDF dosyası için Sağ kenar boşluğu bilgisini belirtin
doc.PageInfo.Margin.Right = 40;
Page page = doc.Pages.Add();
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
// Satırı bölüm nesnesinin paraphraphs koleksiyonuna ekle
page.Paragraphs.Add(graph1);
// Çizginin koordinatlarını belirtin
float[] posArr = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
// HTML etiketleri içeren metinle dize değişkenleri oluşturun
string s = "<font face=\"Times New Roman\" size=4>" +
"<strong> How to Steer Clear of money scams</<strong> "
+ "</font>";
// HTML metni içeren metin paragrafları oluşturun
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();
// Bölüme dört sütun ekleyin
box.ColumnInfo.ColumnCount = 2;
// Sütunlar arasındaki boşluğu ayarlayın
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";
TextFragment text1 = new TextFragment("By A Googler (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.LineSpacing = 2;
box.Paragraphs.Add(text1);
text1.TextState.FontSize = 10;
text1.TextState.FontStyle = FontStyles.Italic;
// Bir çizgi çizmek için bir grafik nesnesi oluşturun
Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
// Çizginin koordinatlarını belirtin
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
//Satırı bölüm nesnesinin paragraf koleksiyonuna ekle
box.Paragraphs.Add(graph2);
TextFragment text2 = new TextFragment(@"Sed augue tortor, sodales id, luctus et, pulvinar ut, eros. Suspendisse vel dolor. Sed quam. Curabitur ut massa vitae eros euismod aliquam. Pellentesque sit amet elit. Vestibulum interdum pellentesque augue. Cras mollis arcu sit amet purus. Donec augue. Nam mollis tortor a elit. Nulla viverra nisl vel mauris. Vivamus sapien. nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et,nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.");
box.Paragraphs.Add(text2);
page.Paragraphs.Add(box);
dataDir = dataDir + "CreateMultiColumnPdf_out.pdf";
// PDF dosyasını kaydet
doc.Save(dataDir);
Console.WriteLine("\nMulti column pdf file created successfully.\nFile saved at " + dataDir);
```

## Çözüm
Aspose.PDF for .NET kullanarak çok sütunlu bir PDF'yi başarıyla oluşturdunuz. Elde edilen PDF dosyası artık belirtilen çıktı dosyası yolunda bulunabilir.

### SSS

#### S: Bu eğitimin odak noktası nedir?

Bu eğitim, Aspose.PDF for .NET kütüphanesini kullanarak çok sütunlu bir PDF oluşturma sürecinde size rehberlik etmeye odaklanmıştır. Sağlanan C# kaynak kodu, bunu başarmak için gerekli adımları göstermektedir.

#### S: Bu eğitim için hangi ad alanlarını içe aktarmalıyım?

A: Çok sütunlu PDF oluşturmak istediğiniz kod dosyasında, dosyanın başına aşağıdaki ad alanlarını içe aktarın:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

#### S: Belge dizinini nasıl belirlerim?

 A: Kodda şu satırı bulun:`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` belge dizininize giden gerçek yol ile.

#### S: Yeni bir Belge örneği nasıl oluştururum?

 A: 4. Adımda yeni bir örnek oluşturacaksınız`Document` Sağlanan kodu kullanarak nesne.

#### S: Sayfa kenar boşluklarını nasıl ayarlarım?

 A: 5. Adımda şunu kullanacaksınız:`PageInfo.Margin` mülkiyeti`Document` PDF dosyası için sol ve sağ kenar boşluğu bilgilerini belirtmek için.

#### S: Belgeye nasıl sayfa eklerim?

 A: 6. Adımda, belgeye yeni bir sayfa ekleyeceksiniz`Add` yöntemi`Pages` koleksiyon.

#### S: Bir Grafik nesnesi nasıl oluştururum ve bir çizgi nasıl eklerim?

 A: 7. Adımda yeni bir tane oluşturacaksınız`Graph` nesneye bir satır ekleyin ve ardından`Graph` itiraz etmek`Paragraphs` Sayfanın koleksiyonu.

#### S: HTML biçimlendirmesiyle başlık metnini nasıl eklerim?

A: 8. Adımda bir`HtmlFragment` nesneyi seçin ve içeriğini istediğiniz HTML metnine ayarlayın, ardından parçayı`Paragraphs` Sayfanın koleksiyonu.

#### S: Birden fazla sütuna sahip bir FloatingBox nasıl oluştururum?

 A: 9. Adımda bir tane oluşturacaksınız`FloatingBox` birden fazla sütun ve sütun aralığına sahip nesneyi oluşturun, ardından metin parçaları ve bir satır ekleyin`Paragraphs` koleksiyonu`FloatingBox`.

#### S: PDF belgesini nasıl kaydedebilirim?

 A: 10. Adımda, PDF belgesini kullanarak kaydedeceksiniz`Save` yöntemi`Document` nesne.

#### S: Bu eğitimden çıkarılacak en önemli ders nedir?

A: Bu öğreticiyi takip ederek, .NET için Aspose.PDF kullanarak çok sütunlu bir PDF belgesinin nasıl oluşturulacağını öğrendiniz. Bu, içeriği yapılandırılmış ve organize bir düzende görüntülemek için yararlı olabilir.