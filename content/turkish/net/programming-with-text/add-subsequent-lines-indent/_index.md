---
title: PDF Dosyasına Sonraki Satır Girintisini Ekle
linktitle: PDF Dosyasına Sonraki Satır Girintisini Ekle
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak PDF dosyasındaki metne sonraki satır girintilerini nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 60
url: /tr/net/programming-with-text/add-subsequent-lines-indent/
---
Bu eğitim, Aspose.PDF for .NET kullanarak PDF dosyasındaki metne girintili sonraki satırları ekleme sürecinde size rehberlik edecektir. Sağlanan C# kaynak kodu gerekli adımları gösterir.

## Gereksinimler
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Makinenizde kurulu Visual Studio veya başka herhangi bir C# derleyicisi.
- Aspose.PDF for .NET kitaplığı. Resmi Aspose web sitesinden indirebilir veya yüklemek için NuGet gibi bir paket yöneticisi kullanabilirsiniz.

## 1. Adım: Projeyi ayarlayın
1. Tercih ettiğiniz geliştirme ortamında yeni bir C# projesi oluşturun.
2. Aspose.PDF for .NET kitaplığına bir referans ekleyin.

## 2. Adım: Gerekli ad alanlarını içe aktarın
Sonraki satır girintisini eklemek istediğiniz kod dosyasında, dosyanın en üstüne aşağıdaki kullanma yönergesini ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 3. Adım: Belge dizinini ayarlayın
 Kodda yazan satırı bulun`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` belgelerinizin saklandığı dizinin yolu ile birlikte.

## 4. Adım: Yeni bir Belge nesnesi oluşturun
 Yeni bir örnek oluştur`Document` Aşağıdaki kod satırını ekleyerek nesne:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

## 5. Adım: Belgeye bir sayfa ekleyin
 kullanarak belgeye yeni bir sayfa ekleyin.`Add` yöntemi`Pages`Toplamak. Verilen kodda yeni sayfa değişkene atanır.`page`.

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

## Adım 6: Sonraki satır girintileriyle bir TextFragment oluşturun
 Bir örnek oluştur`TextFragment` nesneyi seçin ve istediğiniz metni sağlayın. Sağlanan kodda metin değişkene atanır`text` . Ardından, başlat`TextFormattingOptions` için`TextFragment`ve şunu belirtin`SubsequentLinesIndent` değer.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog." );
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
     SubsequentLinesIndent = 20
};
```

## Adım 7: TextFragment'i sayfaya ekleyin
 Ekle`TextFragment` sayfanın paragraf koleksiyonuna itiraz edin.

```csharp
page.Paragraphs.Add(text);
```

## Adım 8: Ek satırlar için 6. ve 7. adımları tekrarlayın
Aynı girintiye sahip sonraki satırları eklemek için her satır için 6. ve 7. adımları tekrarlayın. Metin içeriğini gerektiği gibi güncelleyin.

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

## 9. Adım: PDF belgesini kaydedin
 PDF belgesini kullanarak kaydedin.`Save` yöntemi`Document` nesne. Çıkış dosyası yolunu belirtin.

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Aspose.PDF for .NET kullanarak Sonraki Satır Girintilerini Ekleme için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Yeni belge nesnesi oluştur
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = document.Pages.Add();
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog.");
// Metin parçası için TextFormattingOptions'ı başlatın ve NextLinesIndent değerini belirtin
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
Aspose.PDF for .NET'i kullanarak metne sonraki satır girintilerini başarıyla eklediniz. Ortaya çıkan PDF dosyası artık belirtilen çıktı dosyası yolunda bulunabilir.

### SSS'ler

#### S: Bu eğitimin odak noktası nedir?

C: Bu eğitim, Aspose.PDF for .NET kitaplığını kullanarak bir PDF dosyasındaki metne sonraki satır girintilerinin nasıl ekleneceği konusunda kapsamlı bir kılavuz sağlar. Bunu başarmak için gerekli adımları gösteren C# kaynak kodu örneklerini içerir.

#### S: Bu eğitim için hangi ad alanlarını içe aktarmam gerekiyor?

C: Sonraki satır girintisini eklemeyi planladığınız kod dosyasında, dosyanın başına aşağıdaki ad alanlarını içe aktarın:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### S: Belge dizinini nasıl belirlerim?

 A: Kodda satırı bulun`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

#### S: Bir Belge nesnesini nasıl oluşturabilirim?

 C: 4. Adımda yeni bir örnek oluşturacaksınız.`Document` aşağıdaki kod satırını kullanarak nesne:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

#### S: Belgeye nasıl sayfa eklerim?

 C: 5. Adımda belgeye yeni bir sayfa ekleyeceksiniz.`Add` yöntemi`Pages` Toplamak:

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

#### S: Metne sonraki satır girintilerini nasıl ekleyebilirim?

 C: 6. Adımda bir`TextFragment` nesneyi seçin ve ona istediğiniz metni atayın. Daha sonra başlatacaksınız`TextFormattingOptions` için`TextFragment`ve şunu belirtin`SubsequentLinesIndent` değer:

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("Your text here");
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
    SubsequentLinesIndent = 20
};
```

#### S: TextFragment'i PDF belgesine nasıl eklerim?

 C: 7. Adımda şunu ekleyeceksiniz:`TextFragment` nesne (`text`) sayfanın paragraf koleksiyonuna:

```csharp
page.Paragraphs.Add(text);
```

#### S: İşlemi ek satırlar için tekrarlayabilir miyim?

 C: Evet, 8. Adımda, yeni satırlar oluşturarak aynı girintiye sahip ek satırlar için işlemi tekrarlayabilirsiniz.`TextFragment` nesneleri ve bunları sayfanın paragraf koleksiyonuna ekleme.

#### S: Ortaya çıkan PDF belgesini nasıl kaydederim?

 C: Metni sonraki satır girintileriyle ekledikten sonra,`Save` yöntemi`Document` PDF belgesini kaydetmek için nesne:

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

#### S: Bu eğitimden çıkarılacak önemli sonuç nedir?

C: Bu eğitimi takip ederek, Aspose.PDF for .NET kullanarak sonraki satır girintilerini ekleyerek bir PDF belgesindeki metnin okunabilirliğini nasıl geliştireceğinizi başarıyla öğrendiniz. Bu teknik çeşitli belge ve rapor türleri için yararlı olabilir.