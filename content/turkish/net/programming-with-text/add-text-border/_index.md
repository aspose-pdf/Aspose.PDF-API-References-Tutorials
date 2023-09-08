---
title: PDF Dosyasına Metin Kenarlığı Ekleme
linktitle: PDF Dosyasına Metin Kenarlığı Ekleme
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak PDF dosyasına nasıl metin kenarlığı ekleyeceğinizi öğrenin.
type: docs
weight: 70
url: /tr/net/programming-with-text/add-text-border/
---
Bu eğitim, Aspose.PDF for .NET kullanarak PDF dosyasına metin kenarlığı ekleme sürecinde size rehberlik edecektir. Sağlanan C# kaynak kodu gerekli adımları gösterir.

## Gereksinimler
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Makinenizde kurulu Visual Studio veya başka herhangi bir C# derleyicisi.
- Aspose.PDF for .NET kitaplığı. Resmi Aspose web sitesinden indirebilir veya yüklemek için NuGet gibi bir paket yöneticisi kullanabilirsiniz.

## 1. Adım: Projeyi ayarlayın
1. Tercih ettiğiniz geliştirme ortamında yeni bir C# projesi oluşturun.
2. Aspose.PDF for .NET kitaplığına bir referans ekleyin.

## 2. Adım: Gerekli ad alanlarını içe aktarın
Metin kenarlığını eklemek istediğiniz kod dosyasında, dosyanın en üstüne aşağıdaki kullanma yönergesini ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 3. Adım: Belge dizinini ayarlayın
 Kodda yazan satırı bulun`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` belgelerinizin saklandığı dizinin yolu ile birlikte.

## 4. Adım: Yeni bir Belge nesnesi oluşturun
 Yeni bir örnek oluştur`Document` Aşağıdaki kod satırını ekleyerek nesne:

```csharp
Document pdfDocument = new Document();
```

## 5. Adım: Belgeye bir sayfa ekleyin
 kullanarak belgeye yeni bir sayfa ekleyin.`Add` yöntemi`Pages`Toplamak. Verilen kodda yeni sayfa değişkene atanır.`pdfPage`.

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Adım 6: Bir TextFragment Oluşturun
 Oluşturmak`TextFragment` nesneyi seçin ve istediğiniz metni sağlayın. kullanarak metin parçasının konumunu ayarlayın.`Position` mülk. Verilen kodda metin "ana metin" olarak ayarlanıp sayfada (100, 600) konumuna konumlandırılmıştır.

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

## 7. Adım: Metin özelliklerini ayarlayın
Yazı tipi boyutu, yazı tipi, arka plan rengi, ön plan rengi vb. gibi metin özelliklerini özelleştirin. Sağlanan kodda, metin parçası için yazı tipi boyutu, yazı tipi, arka plan rengi, ön plan rengi ve kontur rengi gibi özellikler ayarlanır.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

## 8. Adım: Metin kenarlığını etkinleştirin
 Metin kenarlığını etkinleştirmek için`DrawTextRectangleBorder`metin parçasının özelliği`TextState` ile`true`.

```csharp
textFragment.TextState.DrawTextRectangleBorder = true;
```

## 9. Adım: TextFragment'i sayfaya ekleyin
 Kullan`TextBuilder` eklenecek sınıf`TextFragment` sayfaya itiraz ediyorum.

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

## Adım 10: PDF belgesini kaydedin
 PDF belgesini kullanarak kaydedin.`Save` yöntemi`Document` nesne. 3. Adımda ayarladığınız çıktı dosyası yolunu belirtin.

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

### Aspose.PDF for .NET kullanarak Metin Kenarlığı Ekleme için örnek kaynak kodu 
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
// Metin özelliklerini ayarlama
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// Metin dikdörtgeninin etrafına kenarlık (kontur) çizmek için StrokingColor özelliğini ayarlayın
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
// DrawTextRectangleBorder özellik değerini true olarak ayarlayın
textFragment.TextState.DrawTextRectangleBorder = true;
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
// Belgeyi kaydet
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

## Çözüm
Aspose.PDF for .NET'i kullanarak PDF belgenize başarılı bir şekilde metin kenarlığı eklediniz. Ortaya çıkan PDF dosyası artık belirtilen çıktı dosyası yolunda bulunabilir.

### SSS'ler

#### S: Bu eğitimin ana odağı nedir?

C: Bu eğitim, Aspose.PDF for .NET kitaplığını kullanarak bir PDF dosyasına metin kenarlığı ekleme sürecinde size yol gösterir. Sağlanan C# kaynak kodu, bunu başarmak için gerekli adımları gösterir.

#### S: Bu eğitim için hangi ad alanlarını içe aktarmam gerekiyor?

C: Metin kenarlığını eklemek istediğiniz kod dosyasında, dosyanın başına aşağıdaki ad alanlarını içe aktarın:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### S: Belge dizinini nasıl belirlerim?

 A: Kodda satırı bulun`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

#### S: Bir Belge nesnesini nasıl oluşturabilirim?

 C: 4. Adımda yeni bir örnek oluşturacaksınız.`Document` aşağıdaki kod satırını kullanarak nesne:

```csharp
Document pdfDocument = new Document();
```

#### S: Belgeye nasıl sayfa eklerim?

 C: 5. Adımda belgeye yeni bir sayfa ekleyeceksiniz.`Add` yöntemi`Pages` Toplamak:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

#### S: TextFragment'i nasıl oluşturabilirim ve konumunu nasıl ayarlayabilirim?

 C: 6. Adımda bir`TextFragment`kullanarak nesneyi seçin ve sayfadaki konumunu ayarlayın.`Position` mülk:

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

#### S: Metin kenarlığı da dahil olmak üzere metin özelliklerini nasıl özelleştirebilirim?

C: 7. Adımda yazı tipi boyutu, yazı tipi türü, arka plan rengi, ön plan rengi ve metin kenarlığı gibi çeşitli metin özelliklerini özelleştireceksiniz:

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
textFragment.TextState.DrawTextRectangleBorder = true;
```

#### S: TextFragment'i PDF belgesine nasıl eklerim?

 C: 9. Adımda şunları kullanacaksınız:`TextBuilder` eklenecek sınıf`TextFragment` sayfaya itiraz:

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

#### S: Ortaya çıkan PDF belgesini nasıl kaydederim?

 C: Metni kenarlıklı olarak ekledikten sonra,`Save` yöntemi`Document` PDF belgesini kaydetmek için nesne:

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

#### S: Bu eğitimden çıkan ana sonuç nedir?

C: Bu eğitimi takip ederek Aspose.PDF for .NET kullanarak metin kenarlığı ekleyerek PDF belgenizi nasıl geliştireceğinizi başarıyla öğrendiniz. Bu, özellikle PDF dosyalarınızdaki belirli metin içeriğini vurgulamak için yararlı olabilir.