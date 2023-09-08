---
title: PDF Dosyasındaki Metin Parçasını Kullanarak Metni Döndürme
linktitle: PDF Dosyasındaki Metin Parçasını Kullanarak Metni Döndürme
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET'i kullanarak PDF dosyasındaki metin parçalarını kullanarak metni nasıl döndüreceğinizi öğrenin.
type: docs
weight: 390
url: /tr/net/programming-with-text/rotate-text-using-text-fragment/
---
Bu eğitimde, PDF dosyasındaki metin parçalarını kullanarak metni döndürmek için Aspose.PDF for .NET'in nasıl kullanılacağı açıklanmaktadır. Sağlanan C# kaynak kodu süreci adım adım gösterir.

## Önkoşullar

Eğiticiye devam etmeden önce aşağıdakilere sahip olduğunuzdan emin olun:

- Temel C# programlama dili bilgisi.
- Aspose.PDF for .NET kütüphanesi kuruldu. Bunu Aspose web sitesinden edinebilir veya projenize kurmak için NuGet'i kullanabilirsiniz.

## 1. Adım: Projeyi ayarlayın

Tercih ettiğiniz entegre geliştirme ortamında (IDE) yeni bir C# projesi oluşturarak başlayın ve Aspose.PDF for .NET kitaplığına bir referans ekleyin.

## 2. Adım: Gerekli ad alanlarını içe aktarın

Gerekli ad alanlarını içe aktarmak için C# dosyanızın başına aşağıdaki kullanma yönergelerini ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Text.TextBuilder;
```

## 3. Adım: PDF belgesini oluşturun

 Başlat`Document` Yeni bir PDF belgesi oluşturmak için nesne:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

 Değiştirdiğinizden emin olun`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

## 4. Adım: Sayfa ekleyin

 kullanarak belgeden belirli bir sayfayı alın.`Pages.Add()` yöntem:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## 5. Adım: Metin parçaları oluşturun

 Birden fazla oluştur`TextFragment` nesnelerinin metinlerini ve özelliklerini ayarlayın ve sayfadaki konumlarını belirtin:

```csharp
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;

TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
```

Metni, konumları ve diğer özellikleri istediğiniz gibi ayarlayın.

## Adım 6: Bir TextBuilder oluşturun ve metin parçalarını ekleyin

 Oluşturmak`TextBuilder` kullanarak nesne`pdfPage` ve metin parçalarını PDF sayfasına ekleyin:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
```

## Adım 7: PDF belgesini kaydedin

 Değiştirilen PDF belgesini kullanarak bir dosyaya kaydedin.`Save` yöntem:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

 Değiştirdiğinizden emin olun`"TextFragmentTests_Rotated1_out.pdf"` İstenilen çıktı dosyası adı ile.

### Aspose.PDF for .NET kullanarak Metin Parçası Kullanarak Metni Döndürme için örnek kaynak kodu 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belge nesnesini başlat
Document pdfDocument = new Document();
// Belirli bir sayfayı al
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Metin parçası oluştur
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
// Metin özelliklerini ayarlama
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Döndürülmüş metin parçası oluştur
TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
// Metin özelliklerini ayarlama
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;
// Döndürülmüş metin parçası oluştur
TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
// Metin özelliklerini ayarlama
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
// TextBuilder nesnesi oluştur
TextBuilder textBuilder = new TextBuilder(pdfPage);
// Metin parçasını PDF sayfasına ekleyin
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
// Belgeyi kaydet
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

## Çözüm

Tebrikler! Aspose.PDF for .NET'i kullanarak bir PDF belgesindeki metin parçalarını kullanarak metni nasıl döndüreceğinizi başarıyla öğrendiniz. Bu eğitimde, belgenin oluşturulmasından değiştirilen sürümün kaydedilmesine kadar adım adım bir kılavuz sağlanmıştır. Artık PDF dosyalarındaki metin döndürmeyi değiştirmek için bu kodu kendi C# projelerinize dahil edebilirsiniz.

### SSS'ler

#### S: "Metin Parçasını Kullanarak Metni Döndürme" öğreticisinin amacı nedir?

C: "Metin Parçasını Kullanarak Metni Döndürme" eğitimi, bir PDF belgesindeki metin parçalarını kullanarak metni döndürmek için .NET için Aspose.PDF kütüphanesini kullanma sürecinde size rehberlik etmeyi amaçlamaktadır. Öğreticide, bu işlevselliğe ulaşmak için adım adım talimatlar ve örnek kod sağlanmaktadır.

#### S: "Metin parçalarını kullanarak metni döndürmek" ne anlama geliyor?

C: Metin parçalarını kullanarak metni döndürmek, Aspose.PDF kütüphanesini kullanarak bir PDF belgesi içindeki tek tek metin parçalarına döndürme uygulama yeteneğini ifade eder. Bu teknik, PDF içeriğindeki metnin yönünü farklı açılarda veya konumlarda kontrol etmenize olanak tanır.

#### S: Bir PDF belgesindeki metin parçalarını neden döndürmek isteyeyim?

C: Bir PDF belgesindeki metin parçalarını döndürmek, belirli içeriği vurgulamak, sanatsal tasarımlar oluşturmak veya düzen ve okunabilirliği geliştirmek gibi çeşitli amaçlar için yararlı olabilir.

#### S: Eğitim için projeyi nasıl ayarlarım?

C: Projeyi ayarlamak için:

1. Tercih ettiğiniz tümleşik geliştirme ortamında (IDE) yeni bir C# projesi oluşturun.
2. Aspose.PDF for .NET kitaplığına bir referans ekleyin.
3. Gerekli kullanma yönergelerini C# dosyanıza ekleyin.

#### S: Yeni bir PDF belgesini nasıl oluşturabilirim?

 C: Yeni bir PDF belgesi oluşturmak için bir başlangıç değeri oluşturun.`Document`Aspose.PDF kütüphanesinden nesne. PDF'ye sayfa ve içerik eklemek için bu nesneyi kullanabilirsiniz.

#### S: Metin parçalarını kullanarak metin parçalarını nasıl döndürebilirim?

C: Metin parçalarını kullanarak metin parçalarını döndürmek için:

1.  Yaratmak`TextFragment` nesneler.
2. Metin parçalarının metnini ve özelliklerini ayarlayın.
3. Sayfadaki metin parçalarının konumlarını belirtin.
4.  kullanarak dönüş açısını ayarlayın.`TextState.Rotation` metin parçalarının özelliği.
5.  Oluşturmak`TextBuilder`nesneyi seçin ve metin parçalarını PDF sayfasına ekleyin.

#### S: Farklı metin parçalarına farklı döndürme açıları uygulayabilir miyim?

 C: Evet, farklı yönlere farklı dönüş açıları uygulayabilirsiniz.`TextFragment` nesneler. Her metin parçasının, aşağıdakiler kullanılarak belirlenen kendi dönüş açısı olabilir:`TextState.Rotation` mülk.

#### S: Döndürülmüş metin parçaları içeren PDF belgesini nasıl kaydederim?

 C: PDF belgesini döndürülmüş metin parçalarıyla kaydetmek için`Save` yöntemi`Document` nesnesini seçin ve istenen çıktı dosyası yolunu ve adını sağlayın.