---
title: PDF Dosyasında Metin Parçasını Kullanarak Metni Döndürme
linktitle: PDF Dosyasında Metin Parçasını Kullanarak Metni Döndürme
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyasındaki metin parçalarını kullanarak metnin nasıl döndürüleceğini öğrenin.
type: docs
weight: 390
url: /tr/net/programming-with-text/rotate-text-using-text-fragment/
---
Bu eğitim, PDF dosyasındaki metin parçalarını kullanarak metni döndürmek için Aspose.PDF for .NET'in nasıl kullanılacağını açıklar. Sağlanan C# kaynak kodu, işlemi adım adım gösterir.

## Ön koşullar

Eğitime başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- C# programlama dilinin temel bilgisi.
- .NET kütüphanesi için Aspose.PDF yüklendi. Bunu Aspose web sitesinden edinebilir veya projenize yüklemek için NuGet'i kullanabilirsiniz.

## Adım 1: Projeyi kurun

Tercih ettiğiniz entegre geliştirme ortamında (IDE) yeni bir C# projesi oluşturarak başlayın ve .NET için Aspose.PDF kitaplığına bir başvuru ekleyin.

## Adım 2: Gerekli ad alanlarını içe aktarın

Gerekli ad alanlarını içe aktarmak için C# dosyanızın başına aşağıdaki using yönergelerini ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Text.TextBuilder;
```

## Adım 3: PDF belgesini oluşturun

 Başlat`Document` Yeni bir PDF belgesi oluşturmak için nesne:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

 Değiştirdiğinizden emin olun`"YOUR DOCUMENT DIRECTORY"` belge dizininize giden gerçek yol ile.

## Adım 4: Bir sayfa ekleyin

 Belgeden belirli bir sayfayı almak için şunu kullanın:`Pages.Add()` yöntem:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Adım 5: Metin parçaları oluşturun

 Birden fazla oluştur`TextFragment` nesneleri ayarlayın, metinlerini ve özelliklerini ayarlayın ve sayfadaki konumlarını belirtin:

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

## Adım 6: Bir TextBuilder oluşturun ve metin parçaları ekleyin

 Bir tane oluştur`TextBuilder` nesneyi kullanarak`pdfPage` ve metin parçalarını PDF sayfasına ekleyin:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
```

## Adım 7: PDF belgesini kaydedin

 Değiştirilen PDF belgesini bir dosyaya kaydedin`Save` yöntem:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

 Değiştirdiğinizden emin olun`"TextFragmentTests_Rotated1_out.pdf"` İstenilen çıktı dosya adı ile.

### .NET için Aspose.PDF kullanarak Metin Parçası Kullanarak Metni Döndürme için örnek kaynak kodu 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belge nesnesini başlat
Document pdfDocument = new Document();
// Belirli sayfayı al
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Metin parçası oluştur
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
// Metin özelliklerini ayarla
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Döndürülmüş metin parçası oluştur
TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
// Metin özelliklerini ayarla
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;
// Döndürülmüş metin parçası oluştur
TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
// Metin özelliklerini ayarla
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
// TextBuilder nesnesi oluştur
TextBuilder textBuilder = new TextBuilder(pdfPage);
// Metin parçasını PDF sayfasına ekle
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
// Belgeyi kaydet
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesinde metin parçalarını kullanarak metni döndürmeyi başarıyla öğrendiniz. Bu eğitim, belgeyi oluşturmaktan değiştirilmiş sürümü kaydetmeye kadar adım adım bir kılavuz sağladı. Artık bu kodu PDF dosyalarındaki metin döndürmeyi yönetmek için kendi C# projelerinize dahil edebilirsiniz.

### SSS

#### S: "Metin Parçasını Kullanarak Metni Döndürme" eğitiminin amacı nedir?

A: "Metin Parçası Kullanarak Metni Döndür" öğreticisinin amacı, bir PDF belgesinde metin parçalarını kullanarak metni döndürmek için .NET için Aspose.PDF kitaplığını kullanma sürecinde size rehberlik etmektir. Öğretici, bu işlevi elde etmek için adım adım talimatlar ve örnek kod sağlar.

#### S: "Metin parçalarını kullanarak metni döndürmek" ne anlama geliyor?

A: Metin parçalarını kullanarak metni döndürme, Aspose.PDF kitaplığını kullanarak bir PDF belgesindeki ayrı metin parçalarına döndürme uygulama becerisini ifade eder. Bu teknik, PDF içeriğindeki farklı açılarda veya konumlarda metnin yönünü kontrol etmenizi sağlar.

#### S: Neden bir PDF belgesindeki metin parçalarını döndürmek isteyeyim?

A: PDF belgesindeki metin parçalarını döndürmek, belirli içerikleri vurgulamak, sanatsal tasarımlar oluşturmak veya düzeni ve okunabilirliği iyileştirmek gibi çeşitli amaçlar için yararlı olabilir.

#### S: Eğitim için projeyi nasıl kurarım?

A: Projeyi kurmak için:

1. Tercih ettiğiniz entegre geliştirme ortamında (IDE) yeni bir C# projesi oluşturun.
2. .NET için Aspose.PDF kitaplığına bir referans ekleyin.
3. Gerekli using yönergelerini C# dosyanıza ekleyin.

#### S: Yeni bir PDF belgesi nasıl oluşturabilirim?

 A: Yeni bir PDF belgesi oluşturmak için bir`Document`Aspose.PDF kitaplığından nesne. Bu nesneyi PDF'ye sayfalar ve içerik eklemek için kullanabilirsiniz.

#### S: Metin parçalarını kullanarak metin parçalarını nasıl döndürebilirim?

A: Metin parçalarını kullanarak metin parçalarını döndürmek için:

1.  Yaratmak`TextFragment` nesneler.
2. Metin parçalarının metnini ve özelliklerini ayarlayın.
3. Metin parçalarının sayfadaki konumlarını belirtin.
4.  Dönüş açısını kullanarak ayarlayın`TextState.Rotation` metin parçalarının özelliği.
5.  Bir tane oluştur`TextBuilder`nesneyi seçin ve metin parçalarını PDF sayfasına ekleyin.

#### S: Farklı metin parçalarına farklı dönüş açıları uygulayabilir miyim?

 A: Evet, farklı dönüş açılarını farklı şekilde uygulayabilirsiniz.`TextFragment` nesneler. Her metin parçası, kullanılarak belirtilen kendi dönüş açısına sahip olabilir.`TextState.Rotation` mülk.

#### S: Döndürülmüş metin parçaları içeren PDF belgesini nasıl kaydederim?

 A: PDF belgesini döndürülmüş metin parçalarıyla kaydetmek için şunu kullanın:`Save` yöntemi`Document` nesneyi seçin ve istenen çıktı dosyası yolunu ve adını sağlayın.