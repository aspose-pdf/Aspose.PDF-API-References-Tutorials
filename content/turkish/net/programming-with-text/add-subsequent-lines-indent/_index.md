---
title: PDF Dosyasında Sonraki Satırlara Girinti Ekle
linktitle: PDF Dosyasında Sonraki Satırlara Girinti Ekle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyasındaki metne sonraki satır girintisinin nasıl ekleneceğini öğrenin.
type: docs
weight: 60
url: /tr/net/programming-with-text/add-subsequent-lines-indent/
---
Bu eğitim, .NET için Aspose.PDF kullanarak PDF dosyasındaki metne sonraki satır girintisi ekleme sürecinde size rehberlik edecektir. Sağlanan C# kaynak kodu gerekli adımları göstermektedir.

## Gereksinimler
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Bilgisayarınızda Visual Studio veya herhangi bir C# derleyicisi yüklü olmalıdır.
- Aspose.PDF for .NET kütüphanesi. Resmi Aspose web sitesinden indirebilir veya NuGet gibi bir paket yöneticisi kullanarak kurabilirsiniz.

## Adım 1: Projeyi kurun
1. Tercih ettiğiniz geliştirme ortamında yeni bir C# projesi oluşturun.
2. .NET için Aspose.PDF kitaplığına bir referans ekleyin.

## Adım 2: Gerekli ad alanlarını içe aktarın
Sonraki satırlara girinti eklemek istediğiniz kod dosyasında, dosyanın en üstüne aşağıdaki using yönergesini ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Adım 3: Belge dizinini ayarlayın
 Kodda şu satırı bulun:`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` Belgelerinizin saklandığı dizinin yolunu içeren.

## Adım 4: Yeni bir Belge nesnesi oluşturun
 Yeni bir örnek oluştur`Document` Aşağıdaki kod satırını ekleyerek nesneyi oluşturun:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

## Adım 5: Belgeye bir sayfa ekleyin
 Belgeye yeni bir sayfa eklemek için şunu kullanın:`Add` yöntemi`Pages`koleksiyon. Sağlanan kodda, yeni sayfa değişkene atanır`page`.

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

## Adım 6: Sonraki satırların girintisiyle bir TextFragment oluşturun
 Bir örnek oluştur`TextFragment` nesne ve istenen metni sağlayın. Sağlanan kodda, metin değişkene atanır`text` . Ardından, başlatın`TextFormattingOptions` için`TextFragment`ve belirtin`SubsequentLinesIndent` değer.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog." );
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
     SubsequentLinesIndent = 20
};
```

## Adım 7: Sayfaya TextFragment'ı ekleyin
 Ekle`TextFragment` sayfanın paragraf koleksiyonuna nesne.

```csharp
page.Paragraphs.Add(text);
```

## Adım 8: Ek satırlar için 6. ve 7. adımları tekrarlayın
Aynı girintiye sahip sonraki satırları eklemek için, her satır için 6. ve 7. adımları tekrarlayın. Gerektiğinde metin içeriğini güncelleyin.

```csharp
text = new Aspose.Pdf.Text.TextFragment("Line2");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line3");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line4");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line5");
page.Paragraphs.Add(text);
```

## Adım 9: PDF belgesini kaydedin
 PDF belgesini kullanarak kaydedin`Save` yöntemi`Document` nesne. Çıktı dosya yolunu belirtin.

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### .NET için Aspose.PDF kullanarak Sonraki Satır Girintisi Ekleme için örnek kaynak kodu 
```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Yeni belge nesnesi oluştur
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = document.Pages.Add();
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog.");
// Metin parçası için TextFormattingOptions'ı başlatın ve SubsequentLinesIndent değerini belirtin
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
	SubsequentLinesIndent = 20
};
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line2");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line3");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line4");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line5");
page.Paragraphs.Add(text);
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## Çözüm
Aspose.PDF for .NET kullanarak metne sonraki satır girintisini başarıyla eklediniz. Elde edilen PDF dosyası artık belirtilen çıktı dosyası yolunda bulunabilir.

### SSS

#### S: Bu eğitimin odak noktası nedir?

A: Bu eğitim, Aspose.PDF for .NET kütüphanesini kullanarak bir PDF dosyasındaki metne sonraki satır girintisinin nasıl ekleneceğine dair kapsamlı bir kılavuz sağlar. Bunu başarmak için gereken adımları göstermek üzere C# kaynak kodu örnekleri içerir.

#### S: Bu eğitim için hangi ad alanlarını içe aktarmam gerekiyor?

A: Sonraki satırlara girinti eklemek istediğiniz kod dosyasında, dosyanın başına aşağıdaki ad alanlarını ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### S: Belge dizinini nasıl belirlerim?

 A: Kodda şu satırı bulun:`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` belge dizininize giden gerçek yol ile.

#### S: Belge nesnesi nasıl oluştururum?

 A: 4. Adımda yeni bir örnek oluşturacaksınız`Document` Aşağıdaki kod satırını kullanarak nesneyi oluşturun:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

#### S: Belgeye nasıl sayfa eklerim?

 A: 5. Adımda, belgeye yeni bir sayfa ekleyeceksiniz`Add` yöntemi`Pages` koleksiyon:

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

#### S: Metne sonraki satır girintisini nasıl ekleyebilirim?

 A: 6. Adımda bir tane oluşturacaksınız`TextFragment` nesneyi seçin ve ona istediğiniz metni atayın. Ardından, başlatacaksınız`TextFormattingOptions` için`TextFragment`ve belirtin`SubsequentLinesIndent` değer:

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("Your text here");
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
    SubsequentLinesIndent = 20
};
```

#### S: TextFragment'ı PDF belgesine nasıl eklerim?

 A: 7. Adımda şunları ekleyeceksiniz:`TextFragment` nesne (`text`) sayfanın paragraf koleksiyonuna:

```csharp
page.Paragraphs.Add(text);
```

#### S: Ek satırlar için işlemi tekrarlayabilir miyim?

 A: Evet, 8. Adımda, yeni bir girinti oluşturarak aynı girintiye sahip ek satırlar için işlemi tekrarlayabilirsiniz.`TextFragment` nesneleri seçip sayfanın paragraf koleksiyonuna ekleyin.

#### S: Ortaya çıkan PDF belgesini nasıl kaydedebilirim?

 A: Metni, sonraki satır girintileriyle ekledikten sonra,`Save` yöntemi`Document` PDF belgesini kaydetmek için nesne:

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

#### S: Bu eğitimden çıkarılacak en önemli ders nedir?

A: Bu öğreticiyi takip ederek, .NET için Aspose.PDF kullanarak bir PDF belgesindeki metnin okunabilirliğini, sonraki satır girintilerini ekleyerek nasıl artıracağınızı başarıyla öğrendiniz. Bu teknik, çeşitli belge ve rapor türleri için yararlı olabilir.