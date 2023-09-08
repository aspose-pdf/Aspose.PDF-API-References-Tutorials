---
title: Metin Parçasını ve Paragrafı Kullanarak Metni Döndürme
linktitle: Metin Parçasını ve Paragrafı Kullanarak Metni Döndürme
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET'i kullanarak bir PDF belgesinde metin parçasını ve paragrafı kullanarak metni nasıl döndüreceğinizi öğrenin.
type: docs
weight: 400
url: /tr/net/programming-with-text/rotate-text-using-text-fragment-and-paragraph/
---
Bu eğitimde, metin parçasını ve paragrafı kullanarak metni döndürmek için Aspose.PDF for .NET'in nasıl kullanılacağı açıklanmaktadır. Sağlanan C# kaynak kodu süreci adım adım gösterir.

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

 Birden fazla oluştur`TextFragment` nesneleri, metinlerini ve özelliklerini ayarlayın ve dönüş açısını belirtin:

```csharp
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 315;

TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 270;
```

Metni, döndürme açısını ve diğer özellikleri istediğiniz gibi ayarlayın.

## 6. Adım: Sayfaya metin parçaları ekleyin

 Oluşturulan metin parçalarını sayfaya ekleyerek sayfaya ekleyin.`Paragraphs` Toplamak:

```csharp
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
```

## Adım 7: PDF belgesini kaydedin

 Değiştirilen PDF belgesini kullanarak bir dosyaya kaydedin.`Save` yöntem:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

 Değiştirdiğinizden emin olun`"TextFragmentTests_Rotated3_out.pdf"` İstenilen çıktı dosyası adı ile.

### Aspose.PDF for .NET kullanarak Metin Parçası ve Paragraf Kullanarak Metni Döndürme için örnek kaynak kodu 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belge nesnesini başlat
Document pdfDocument = new Document();
// Belirli bir sayfayı al
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Metin parçası oluştur
TextFragment textFragment1 = new TextFragment("main text");
// Metin özelliklerini ayarlama
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Metin parçası oluştur
TextFragment textFragment2 = new TextFragment("rotated text");
// Metin özelliklerini ayarlama
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Döndürmeyi ayarla
textFragment2.TextState.Rotation = 315;
// Metin parçası oluştur
TextFragment textFragment3 = new TextFragment("rotated text");
// Metin özelliklerini ayarlama
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Döndürmeyi ayarla
textFragment3.TextState.Rotation = 270;
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
// Belgeyi kaydet
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

## Çözüm

Tebrikler! Aspose.PDF for .NET'i kullanarak bir PDF belgesindeki metin parçalarını ve paragrafları kullanarak metni nasıl döndüreceğinizi başarıyla öğrendiniz. Bu eğitimde, belgenin oluşturulmasından değiştirilen sürümün kaydedilmesine kadar adım adım bir kılavuz sağlanmıştır. Artık PDF dosyalarındaki metin döndürmeyi değiştirmek için bu kodu kendi C# projelerinize dahil edebilirsiniz.

### SSS'ler

#### S: "Metin Parçasını ve Paragrafı Kullanarak Metni Döndürme" eğitiminin amacı nedir?

C: "Metin Parçası ve Paragraf Kullanarak Metni Döndürme" eğitimi, bir PDF belgesinde hem metin parçalarını hem de paragrafları kullanarak metni döndürmek için .NET için Aspose.PDF kütüphanesini kullanma sürecinde size rehberlik etmeyi amaçlamaktadır. Öğreticide, bu işlevselliğe ulaşmak için adım adım talimatlar ve örnek kod sağlanmaktadır.

#### S: Bu eğitimin önceki metin döndürme eğitimlerinden farkı nedir?

C: Bu eğitim, bir PDF belgesinde metin döndürmeyi sağlamak için metin parçalarının ve paragrafların kullanımını birleştirir. Metin parçalarının tek tek nasıl döndürüleceğini ve ardından bunların bir sayfanın menüsüne nasıl ekleneceğini gösterir.`Paragraphs` Daha kapsamlı bir metin döndürme efekti elde etmek için koleksiyon.

#### S: Metin döndürme için metin parçalarını ve paragrafları kullanmanın avantajları nelerdir?

C: Metin parçalarını ve paragrafları birlikte kullanmak, metin döndürmede daha fazla esneklik sağlar. Metin parçaları ayrı ayrı döndürme ve biçimlendirme ayarlarını mümkün kılarken, paragraflar metin parçalarının bir sayfa içinde düzenlenmesi ve konumlandırılması için yapı sağlar.

#### S: Aynı paragraftaki farklı metin parçalarına farklı döndürme açıları uygulayabilir miyim?

 C: Evet, farklı yönlere farklı dönüş açıları uygulayabilirsiniz.`TextFragment` aynı paragraftaki nesneler. Her metin parçasının, aşağıdakiler kullanılarak belirlenen kendi dönüş açısı olabilir:`TextState.Rotation` mülk.

#### S: Bu yöntemi kullanarak karmaşık metin döndürme efektleri elde etmek mümkün müdür?

C: Evet, çeşitli döndürme açılarına sahip metin parçalarını birleştirerek ve bunları paragraflar içinde düzenleyerek, karmaşık ve özelleştirilmiş metin döndürme efektleri elde ederek PDF belgelerinizin görsel çekiciliğini artırabilirsiniz.

#### S: Metin parçalarını ve paragrafları kullanarak metni döndürmek hangi adımları içerir?

C: Adımlar şunları içerir:

1. Yeni bir C# projesi oluşturarak ve Aspose.PDF for .NET kütüphanesine bir referans ekleyerek projeyi kurun.
2. PDF belgesi oluşturma ve sayfa ekleme.
3. Metin parçaları oluşturma, bunların özelliklerini ayarlama ve döndürme açılarını belirleme.
4.  Kullanarak sayfaya metin parçaları ekleme`Paragraphs` Toplamak.
5. Değiştirilen PDF belgesini kaydetme.

#### S: Paragrafların tamamına rotasyon uygulayabilir miyim?

 C: Evet, döndürmeyi tüm paragraflara uygulayabilirsiniz.`TextState.Rotation` Paragrafın kendisinin özelliği. Bu, o paragraftaki tüm metin parçalarını döndürecektir.