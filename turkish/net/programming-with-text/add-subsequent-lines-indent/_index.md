---
title: Sonraki Satır Girintisi Ekle
linktitle: Sonraki Satır Girintisi Ekle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak metne sonraki satır girintilerini nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 60
url: /tr/net/programming-with-text/add-subsequent-lines-indent/
---

Bu öğretici, Aspose.PDF for .NET kullanarak metne sonraki satır girintilerini ekleme sürecinde size rehberlik edecektir. Sağlanan C# kaynak kodu, gerekli adımları gösterir.

## Gereksinimler
Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Visual Studio veya makinenizde kurulu başka bir C# derleyicisi.
- Aspose.PDF for .NET kitaplığı. Resmi Aspose web sitesinden indirebilir veya yüklemek için NuGet gibi bir paket yöneticisi kullanabilirsiniz.

## 1. Adım: Projeyi kurun
1. Tercih ettiğiniz geliştirme ortamında yeni bir C# projesi oluşturun.
2. Aspose.PDF for .NET kitaplığına bir referans ekleyin.

## 2. Adım: Gerekli ad alanlarını içe aktarın
Sonraki satır girintilerini eklemek istediğiniz kod dosyasında, dosyanın en üstüne aşağıdaki using yönergesini ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 3. Adım: Belge dizinini ayarlayın
 Kodda yazan satırı bulun`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` belgelerinizin saklandığı dizinin yolu ile.

## 4. Adım: Yeni bir Belge nesnesi oluşturun
 Yeni bir örnek oluştur`Document` aşağıdaki kod satırını ekleyerek nesne:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

## 5. Adım: Belgeye bir sayfa ekleyin
 kullanarak belgeye yeni bir sayfa ekleyin.`Add` yöntemi`Pages` Toplamak. Sağlanan kodda, yeni sayfa değişkene atanır.`page`.

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

## Adım 6: Sonraki satır girintili bir TextFragment oluşturun
 Bir örneğini oluşturun`TextFragment` nesne ve istenen metni sağlayın. Sağlanan kodda, metin değişkene atanır`text` . Ardından, başlat`TextFormattingOptions` için`TextFragment` ve belirtin`SubsequentLinesIndent` değer.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog." );
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
     SubsequentLinesIndent = 20
};
```

## Adım 7: TextFragment'i sayfaya ekleyin
 Ekle`TextFragment` sayfanın paragraflar koleksiyonuna itiraz.

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
 kullanarak PDF belgesini kaydedin.`Save` yöntemi`Document` nesne. Çıktı dosyası yolunu belirtin.

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Aspose.PDF for .NET kullanarak Sonraki Satır Girintisi Ekleme için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Yeni belge nesnesi oluştur
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = document.Pages.Add();
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog.");
//Metin parçası için TextFormattingOptions'ı başlatın ve SubsequentLinesIndent değerini belirtin
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
Aspose.PDF for .NET kullanarak metne sonraki satır girintilerini başarıyla eklediniz. Ortaya çıkan PDF dosyası artık belirtilen çıktı dosyası yolunda bulunabilir.