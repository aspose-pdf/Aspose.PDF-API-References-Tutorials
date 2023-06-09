---
title: Paragraf Olarak Metin ve Resim
linktitle: Paragraf Olarak Metin ve Resim
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesine satır içi paragraflar olarak nasıl metin ve resim ekleyeceğinizi öğrenin.
type: docs
weight: 530
url: /tr/net/programming-with-text/text-and-image-as-paragraph/
---

Bu eğitim, Aspose.PDF for .NET kullanılarak bir PDF belgesine satır içi paragraflar olarak nasıl metin ve resim ekleneceğini açıklar. Sağlanan C# kaynak kodu, süreci adım adım gösterir.

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
using Aspose.Pdf.Drawing;
```

## 3. Adım: Belge dizinine giden yolu ayarlayın

 kullanarak belge dizininize giden yolu ayarlayın.`dataDir` değişken:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

## 4. Adım: Yeni bir Belge ve Sayfa oluşturun

 Yeni bir tane oluştur`Document` nesnesini bulun ve sayfalar koleksiyonuna bir sayfa ekleyin:

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Adım 5: Bir TextFragment oluşturun ve bunu paragraf olarak ekleyin

 Oluşturmak`TextFragment`nesnesini seçin ve sayfanın paragraflar koleksiyonuna ekleyin:

```csharp
TextFragment text = new TextFragment("Hello World.. ");
page.Paragraphs.Add(text);
```

## 6. Adım: Satır içi paragraf olarak bir resim ekleyin

 Oluşturduğunuz bir`Aspose.Pdf.Image` nesnesini seçin ve önceki paragraftan hemen sonra görünmesi için satır içi paragraf olarak ayarlayın:

```csharp
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
image.IsInLineParagraph = true;
image.File = dataDir + "aspose-logo.jpg";
image.FixHeight = 30; // İsteğe bağlı: Görüntü yüksekliğini ayarlayın
image.FixWidth = 100; // İsteğe bağlı: Görüntü genişliğini ayarlayın
page.Paragraphs.Add(image);
```

 Yer değiştirmek`"aspose-logo.jpg"` gerçek görüntü dosyası adıyla ve isteğe bağlı görüntü yüksekliğini ve genişliğini istediğiniz gibi ayarlayın.

## 7. Adım: Satır içi paragraf olarak başka bir TextFragment ekleyin

 yeniden başlat`TextFragment` farklı içeriğe sahip bir nesne oluşturun ve satır içi paragraf olarak ekleyin:

```csharp
text = new TextFragment(" Hello Again..");
text.IsInLineParagraph = true;
page.Paragraphs.Add(text);
```

## 8. Adım: PDF belgesini kaydedin

Değiştirilen PDF belgesini kaydedin:

```csharp
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
```

 değiştirdiğinizden emin olun`"TextAndImageAsParagraph_out.pdf"` istenen çıktı dosyası adıyla.

### Aspose.PDF for .NET kullanan Text And Image As Paragraph için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belge örneği örneği
Document doc = new Document();
// Belge örneğinin sayfa koleksiyonuna sayfa ekleme
Page page = doc.Pages.Add();
// TextFragmnet oluştur
TextFragment text = new TextFragment("Hello World.. ");
// Sayfa nesnesinin paragraf koleksiyonuna metin parçası ekleyin
page.Paragraphs.Add(text);
// Bir görüntü örneği oluşturun
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
// Hemen sonra görünmesi için resmi satır içi paragraf olarak ayarla
// Önceki paragraf nesnesi (TextFragment)
image.IsInLineParagraph = true;
// Görüntü dosyası yolunu belirtin
image.File = dataDir + "aspose-logo.jpg";
// Görüntü Yüksekliğini Ayarla (isteğe bağlı)
image.FixHeight = 30;
// Görüntü Genişliğini Ayarla (isteğe bağlı)
image.FixWidth = 100;
//Sayfa nesnesinin paragraf koleksiyonuna resim ekleyin
page.Paragraphs.Add(image);
// TextFragment nesnesini farklı içeriklerle yeniden başlat
text = new TextFragment(" Hello Again..");
// TextFragment'i satır içi paragraf olarak ayarla
text.IsInLineParagraph = true;
// Sayfanın paragraf koleksiyonuna yeni oluşturulan TextFragment'i ekleyin
page.Paragraphs.Add(text);
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nText and image added successfully as an inline paragraphs.\nFile saved at " + dataDir);
```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesine satır içi paragraflar olarak nasıl metin ve resim ekleyeceğinizi başarıyla öğrendiniz. Bu öğretici, projeyi ayarlamaktan değiştirilen belgeyi kaydetmeye kadar adım adım bir kılavuz sağladı. PDF dosyalarındaki metin ve görüntülerin düzenini özelleştirmek için artık bu kodu kendi C# projelerinize dahil edebilirsiniz.