---
title: Metin Kenarlığı Ekle
linktitle: Metin Kenarlığı Ekle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesine nasıl metin kenarlığı ekleyeceğinizi öğrenin.
type: docs
weight: 70
url: /tr/net/programming-with-text/add-text-border/
---

Bu eğitim, Aspose.PDF for .NET kullanarak bir metin kenarlığı ekleme sürecinde size rehberlik edecektir. Sağlanan C# kaynak kodu, gerekli adımları gösterir.

## Gereksinimler
Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Visual Studio veya makinenizde kurulu başka bir C# derleyicisi.
- Aspose.PDF for .NET kitaplığı. Resmi Aspose web sitesinden indirebilir veya yüklemek için NuGet gibi bir paket yöneticisi kullanabilirsiniz.

## 1. Adım: Projeyi kurun
1. Tercih ettiğiniz geliştirme ortamında yeni bir C# projesi oluşturun.
2. Aspose.PDF for .NET kitaplığına bir referans ekleyin.

## 2. Adım: Gerekli ad alanlarını içe aktarın
Metin kenarlığını eklemek istediğiniz kod dosyasında, dosyanın en üstüne aşağıdaki using yönergesini ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 3. Adım: Belge dizinini ayarlayın
 Kodda yazan satırı bulun`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` belgelerinizin saklandığı dizinin yolu ile.

## 4. Adım: Yeni bir Belge nesnesi oluşturun
 Yeni bir örnek oluştur`Document` aşağıdaki kod satırını ekleyerek nesne:

```csharp
Document pdfDocument = new Document();
```

## 5. Adım: Belgeye bir sayfa ekleyin
 kullanarak belgeye yeni bir sayfa ekleyin.`Add` yöntemi`Pages` Toplamak. Sağlanan kodda, yeni sayfa değişkene atanır.`pdfPage`.

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## 6. Adım: Bir TextFragment Oluşturun
 Oluşturmak`TextFragment`nesne ve istenen metni sağlayın. kullanarak metin parçasının konumunu ayarlayın.`Position` mülk. Sağlanan kodda, metin "ana metin" olarak ayarlanır ve sayfada (100, 600) konumuna getirilir.

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

## 7. Adım: Metin özelliklerini ayarlayın
Yazı tipi boyutu, yazı tipi, arka plan rengi, ön plan rengi vb. gibi metin özelliklerini özelleştirin. Sağlanan kodda, metin parçası için yazı tipi boyutu, yazı tipi, arka plan rengi, ön plan rengi ve vuruş rengi gibi özellikler ayarlanır.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

## 8. Adım: Metin kenarlığını etkinleştirin
 Metin kenarlığını etkinleştirmek için`DrawTextRectangleBorder` metin parçasının özelliği`TextState` ile`true`.

```csharp
textFragment.TextState.DrawTextRectangleBorder = true;
```

## 9. Adım: TextFragment'i sayfaya ekleyin
 Kullan`TextBuilder` eklemek için sınıf`TextFragment` sayfaya itiraz

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

## 10. Adım: PDF belgesini kaydedin
 kullanarak PDF belgesini kaydedin.`Save` yöntemi`Document` nesne. Adım 3'te ayarladığınız çıktı dosyası yolunu belirtin.

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

### Aspose.PDF for .NET kullanarak Add Text Border için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Yeni belge nesnesi oluştur
Document pdfDocument = new Document();
// Belirli bir sayfayı al
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Metin parçası oluştur
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
// Metin özelliklerini ayarla
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// Metin dikdörtgeninin çevresine kenarlık çizmek (vuruş) için StrokingColor özelliğini ayarlayın
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
// DrawTextRectangleBorder özellik değerini true olarak ayarlayın
textFragment.TextState.DrawTextRectangleBorder = true;
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
// belgeyi kaydet
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

## Çözüm
Aspose.PDF for .NET'i kullanarak PDF belgenize başarıyla bir metin kenarlığı eklediniz. Ortaya çıkan PDF dosyası artık belirtilen çıktı dosyası yolunda bulunabilir.