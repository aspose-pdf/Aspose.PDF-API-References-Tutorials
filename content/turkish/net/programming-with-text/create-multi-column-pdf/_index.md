---
title: Çok Sütunlu Pdf Oluştur
linktitle: Çok Sütunlu Pdf Oluştur
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET'i kullanarak çok sütunlu bir PDF'nin nasıl oluşturulacağını öğrenin.
type: docs
weight: 110
url: /tr/net/programming-with-text/create-multi-column-pdf/
---
Bu eğitim, Aspose.PDF for .NET kullanarak çok sütunlu bir PDF oluşturma sürecinde size rehberlik edecektir. Sağlanan C# kaynak kodu gerekli adımları gösterir.

## Gereksinimler
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Makinenizde kurulu Visual Studio veya başka herhangi bir C# derleyicisi.
- Aspose.PDF for .NET kitaplığı. Resmi Aspose web sitesinden indirebilir veya yüklemek için NuGet gibi bir paket yöneticisi kullanabilirsiniz.

## 1. Adım: Projeyi ayarlayın
1. Tercih ettiğiniz geliştirme ortamında yeni bir C# projesi oluşturun.
2. Aspose.PDF for .NET kitaplığına bir referans ekleyin.

## 2. Adım: Gerekli ad alanlarını içe aktarın
Çok sütunlu bir PDF oluşturmak istediğiniz kod dosyasında, dosyanın en üstüne aşağıdaki kullanarak yönergeleri ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

## 3. Adım: Belge dizinini ayarlayın
 Kodda yazan satırı bulun`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` belgelerinizin saklandığı dizinin yolu ile birlikte.

## 4. Adım: Yeni bir Belge örneği oluşturun
 Yeni bir örnek oluştur`Document` Aşağıdaki kod satırını ekleyerek nesne:

```csharp
Document doc = new Document();
```

## 5. Adım: Sayfa kenar boşluklarını ayarlayın
 PDF dosyası için sol ve sağ kenar boşluğu bilgilerini aşağıdaki düğmeyi kullanarak belirtin:`PageInfo.Margin` mülkiyeti`Document`.

```csharp
doc.PageInfo.Margin.Left = 40;
doc.PageInfo.Margin.Right = 40;
```

## 6. Adım: Belgeye bir sayfa ekleyin
 kullanarak belgeye yeni bir sayfa ekleyin.`Add` yöntemi`Pages`Toplamak. Verilen kodda yeni sayfa değişkene atanır.`page`.

```csharp
Page page = doc.Pages.Add();
```

## Adım 7: Bir Grafik nesnesi oluşturun ve bir çizgi ekleyin
 Yeni bir tane oluştur`Graph` belirli boyutlara sahip nesneyi seçin ve ona bir çizgi ekleyin. Daha sonra şunu ekleyin:`Graph` itiraz`Paragraphs` sayfanın toplanması.

```csharp
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
float[] backPos = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
page.Paragraphs.Add(graph1);
```

## 8. Adım: HTML biçimlendirmesiyle başlık metnini ekleyin
 Oluşturduğunuz bir`HtmlFragment` nesnesini seçin ve içeriğini istediğiniz HTML metnine ayarlayın. Daha sonra parçayı şuraya ekleyin:`Paragraphs` sayfanın toplanması.

```csharp
string s = "<font face=\"Times New Roman\" size=4>" +
     "<strong>How to Steer Clear of money scams</<strong>" +
     "</font>";
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
```

## Adım 9: Birden çok sütuna sahip bir FloatingBox oluşturun
 Oluşturmak`FloatingBox` nesneyi seçin ve sütun sayısını ve sütun aralığını ayarlayın. Daha sonra metin parçalarını ve bir satırı ekleyin.`Paragraphs` koleksiyonu`FloatingBox`.

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
 PDF belgesini kullanarak kaydedin.`Save` yöntemi`Document` nesne.

```csharp
doc.Save(dataDir);
```

### Aspose.PDF for .NET kullanarak Çok Sütunlu PDF Oluşturma için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
// PDF dosyası için sol kenar boşluğu bilgisini belirtin
doc.PageInfo.Margin.Left = 40;
//PDF dosyası için Sağ kenar boşluğu bilgisini belirtin
doc.PageInfo.Margin.Right = 40;
Page page = doc.Pages.Add();
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
// Satırı bölüm nesnesinin paragraf koleksiyonuna ekleyin
page.Paragraphs.Add(graph1);
// Çizginin koordinatlarını belirtin
float[] posArr = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
// Html etiketleri içeren metinlerle dize değişkenleri oluşturun
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
// Çizgi çizmek için bir grafik nesnesi oluşturun
Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
// Çizginin koordinatlarını belirtin
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
// Satırı bölüm nesnesinin paragraf koleksiyonuna ekleyin
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
Aspose.PDF for .NET'i kullanarak başarıyla çok sütunlu bir PDF oluşturdunuz. Ortaya çıkan PDF dosyası artık belirtilen çıktı dosyası yolunda bulunabilir.

### SSS'ler

#### S: Bu eğitimin odak noktası nedir?

Bu eğitim, Aspose.PDF for .NET kitaplığını kullanarak çok sütunlu bir PDF oluşturma sürecinde size rehberlik etmeye odaklanmıştır. Sağlanan C# kaynak kodu, bunu başarmak için gerekli adımları gösterir.

#### S: Bu eğitim için hangi ad alanlarını içe aktarmalıyım?

C: Çok sütunlu bir PDF oluşturmak istediğiniz kod dosyasında, dosyanın başında aşağıdaki ad alanlarını içe aktarın:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

#### S: Belge dizinini nasıl belirlerim?

 A: Kodda satırı bulun`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

#### S: Yeni bir Belge örneğini nasıl oluşturabilirim?

 C: 4. Adımda yeni bir örnek oluşturacaksınız.`Document` sağlanan kodu kullanarak nesne.

#### S: Sayfa kenar boşluklarını nasıl ayarlarım?

 C: 5. Adımda şunları kullanacaksınız:`PageInfo.Margin` mülkiyeti`Document` PDF dosyası için sol ve sağ kenar boşluğu bilgilerini belirtmek için.

#### S: Belgeye nasıl sayfa eklerim?

 C: 6. Adımda belgeye yeni bir sayfa ekleyeceksiniz.`Add` yöntemi`Pages` Toplamak.

#### S: Graph nesnesini nasıl oluşturup çizgi eklerim?

 C: 7. Adımda yeni bir`Graph` nesneye bir satır ekleyin ve ardından`Graph` itiraz`Paragraphs` sayfanın toplanması.

#### S: HTML biçimlendirmesiyle başlık metnini nasıl eklerim?

 C: 8. Adımda bir`HtmlFragment` nesnesini seçin ve içeriğini istediğiniz HTML metnine ayarlayın, ardından parçayı`Paragraphs` sayfanın toplanması.

#### S: Birden fazla sütuna sahip bir FloatingBox'ı nasıl oluşturabilirim?

 C: 9. Adımda bir`FloatingBox` birden çok sütun ve sütun aralığına sahip nesneyi seçin, ardından metin parçaları ve bir satır ekleyin.`Paragraphs` koleksiyonu`FloatingBox`.

#### S: PDF belgesini nasıl kaydederim?

 C: 10. Adımda, PDF belgesini aşağıdaki komutu kullanarak kaydedeceksiniz:`Save` yöntemi`Document` nesne.

#### S: Bu eğitimden çıkan ana sonuç nedir?

C: Bu eğitimi takip ederek Aspose.PDF for .NET kullanarak çok sütunlu bir PDF belgesinin nasıl oluşturulacağını öğrendiniz. Bu, içeriği yapılandırılmış ve organize bir düzende görüntülemek için yararlı olabilir.