---
title: PDF Dosyasına Metin Kenarlığı Ekle
linktitle: PDF Dosyasına Metin Kenarlığı Ekle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyasına metin kenarlığı eklemeyi öğrenin.
type: docs
weight: 70
url: /tr/net/programming-with-text/add-text-border/
---
Bu eğitim, .NET için Aspose.PDF kullanarak PDF dosyasına metin kenarlığı ekleme sürecinde size rehberlik edecektir. Sağlanan C# kaynak kodu gerekli adımları göstermektedir.

## Gereksinimler
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Bilgisayarınızda Visual Studio veya herhangi bir C# derleyicisi yüklü olmalıdır.
- Aspose.PDF for .NET kütüphanesi. Resmi Aspose web sitesinden indirebilir veya NuGet gibi bir paket yöneticisi kullanarak kurabilirsiniz.

## Adım 1: Projeyi kurun
1. Tercih ettiğiniz geliştirme ortamında yeni bir C# projesi oluşturun.
2. .NET için Aspose.PDF kitaplığına bir referans ekleyin.

## Adım 2: Gerekli ad alanlarını içe aktarın
Metin kenarlığını eklemek istediğiniz kod dosyasında, dosyanın en üstüne aşağıdaki using yönergesini ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Adım 3: Belge dizinini ayarlayın
 Kodda şu satırı bulun:`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` Belgelerinizin saklandığı dizinin yolunu içeren.

## Adım 4: Yeni bir Belge nesnesi oluşturun
 Yeni bir örnek oluştur`Document` Aşağıdaki kod satırını ekleyerek nesneyi oluşturun:

```csharp
Document pdfDocument = new Document();
```

## Adım 5: Belgeye bir sayfa ekleyin
 Belgeye yeni bir sayfa eklemek için şunu kullanın:`Add` yöntemi`Pages` koleksiyon. Sağlanan kodda, yeni sayfa değişkene atanır`pdfPage`.

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Adım 6: Bir TextFragment Oluşturun
 Bir tane oluştur`TextFragment`nesneyi seçin ve istediğiniz metni sağlayın. Metin parçasının konumunu kullanarak ayarlayın`Position` özellik. Sağlanan kodda, metin "ana metin" olarak ayarlanmıştır ve sayfada (100, 600) konumunda konumlandırılmıştır.

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

## Adım 7: Metin özelliklerini ayarlayın
Yazı tipi boyutu, yazı tipi, arka plan rengi, ön plan rengi vb. gibi metin özelliklerini özelleştirin. Sağlanan kodda, yazı tipi boyutu, yazı tipi, arka plan rengi, ön plan rengi ve vuruş rengi gibi özellikler metin parçası için ayarlanır.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

## Adım 8: Metin kenarlığını etkinleştirin
 Metin kenarlığını etkinleştirmek için,`DrawTextRectangleBorder` metin parçasının özelliği`TextState` ile`true`.

```csharp
textFragment.TextState.DrawTextRectangleBorder = true;
```

## Adım 9: Sayfaya TextFragment'ı ekleyin
 Kullanın`TextBuilder` sınıf eklemek için`TextFragment` sayfaya nesne.

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

## Adım 10: PDF belgesini kaydedin
 PDF belgesini kullanarak kaydedin`Save` yöntemi`Document` nesne. Adım 3'te ayarladığınız çıktı dosyası yolunu belirtin.

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

### .NET için Aspose.PDF kullanarak Metin Kenarlığı Ekleme için örnek kaynak kodu 
```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Yeni belge nesnesi oluştur
Document pdfDocument = new Document();
// Belirli sayfayı al
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Metin parçası oluştur
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
// Metin özelliklerini ayarla
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// Metin dikdörtgeni etrafına kenarlık (vuruş) çizmek için StrokingColor özelliğini ayarlayın
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
// DrawTextRectangleBorder özelliğinin değerini true olarak ayarlayın
textFragment.TextState.DrawTextRectangleBorder = true;
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
// Belgeyi kaydet
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

## Çözüm
Aspose.PDF for .NET kullanarak PDF belgenize başarıyla bir metin kenarlığı eklediniz. Ortaya çıkan PDF dosyası artık belirtilen çıktı dosyası yolunda bulunabilir.

### SSS

#### S: Bu eğitimin ana odak noktası nedir?

A: Bu eğitim, Aspose.PDF for .NET kitaplığını kullanarak bir PDF dosyasına metin kenarlığı ekleme sürecinde size rehberlik eder. Sağlanan C# kaynak kodu, bunu başarmak için gerekli adımları gösterir.

#### S: Bu eğitim için hangi ad alanlarını içe aktarmam gerekiyor?

A: Metin kenarlığını eklemek istediğiniz kod dosyasında, dosyanın başına aşağıdaki ad alanlarını ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### S: Belge dizinini nasıl belirlerim?

 A: Kodda şu satırı bulun:`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` belge dizininize giden gerçek yol ile.

#### S: Belge nesnesi nasıl oluştururum?

 A: 4. Adımda yeni bir örnek oluşturacaksınız`Document` Aşağıdaki kod satırını kullanarak nesneyi oluşturun:

```csharp
Document pdfDocument = new Document();
```

#### S: Belgeye nasıl sayfa eklerim?

 A: 5. Adımda, belgeye yeni bir sayfa ekleyeceksiniz`Add` yöntemi`Pages` koleksiyon:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

#### S: Bir TextFragment nasıl oluştururum ve konumunu nasıl ayarlarım?

 A: 6. Adımda bir tane oluşturacaksınız`TextFragment` nesneyi seçin ve sayfadaki konumunu ayarlayın`Position` mülk:

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

#### S: Metin kenarlığı da dahil olmak üzere metin özelliklerini nasıl özelleştirebilirim?

A: 7. Adımda yazı tipi boyutu, yazı tipi, arka plan rengi, ön plan rengi ve metin kenarlığı gibi çeşitli metin özelliklerini özelleştireceksiniz:

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
textFragment.TextState.DrawTextRectangleBorder = true;
```

#### S: TextFragment'ı PDF belgesine nasıl eklerim?

 A: 9. Adımda şunu kullanacaksınız:`TextBuilder` sınıf eklemek için`TextFragment` sayfaya itiraz:

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

#### S: Ortaya çıkan PDF belgesini nasıl kaydedebilirim?

A: Kenarlıklı metni ekledikten sonra,`Save` yöntemi`Document` PDF belgesini kaydetmek için nesne:

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

#### S: Bu eğitimden çıkarılacak en önemli ders nedir?

A: Bu öğreticiyi takip ederek, Aspose.PDF for .NET kullanarak bir metin kenarlığı ekleyerek PDF belgenizi nasıl geliştireceğinizi başarıyla öğrendiniz. Bu, özellikle PDF dosyalarınızdaki belirli metin içeriğini vurgulamak için yararlı olabilir.