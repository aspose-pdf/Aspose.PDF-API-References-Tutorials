---
title: Metin Parçası ve Paragraf Kullanarak Metni Döndürme
linktitle: Metin Parçası ve Paragraf Kullanarak Metni Döndürme
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesinde metin parçası ve paragraf kullanarak metni nasıl döndüreceğinizi öğrenin.
type: docs
weight: 400
url: /tr/net/programming-with-text/rotate-text-using-text-fragment-and-paragraph/
---
Bu eğitim, metin parçası ve paragraf kullanarak metni döndürmek için Aspose.PDF for .NET'in nasıl kullanılacağını açıklar. Sağlanan C# kaynak kodu, işlemi adım adım gösterir.

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

 Birden fazla oluştur`TextFragment` nesneleri seçin, metinlerini ve özelliklerini ayarlayın ve dönüş açısını belirtin:

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

Metni, dönüş açısını ve diğer özellikleri istediğiniz gibi ayarlayın.

## Adım 6: Sayfaya metin parçaları ekleyin

 Oluşturulan metin parçalarını sayfaya ekleyerek ekleyin.`Paragraphs` koleksiyon:

```csharp
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
```

## Adım 7: PDF belgesini kaydedin

 Değiştirilen PDF belgesini bir dosyaya kaydedin`Save` yöntem:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

 Değiştirdiğinizden emin olun`"TextFragmentTests_Rotated3_out.pdf"` İstenilen çıktı dosya adı ile.

### Aspose.PDF for .NET kullanarak Metin Parçası ve Paragraf Kullanarak Metni Döndürme için örnek kaynak kodu 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belge nesnesini başlat
Document pdfDocument = new Document();
// Belirli sayfayı al
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Metin parçası oluştur
TextFragment textFragment1 = new TextFragment("main text");
// Metin özelliklerini ayarla
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Metin parçası oluştur
TextFragment textFragment2 = new TextFragment("rotated text");
// Metin özelliklerini ayarla
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Döndürmeyi ayarla
textFragment2.TextState.Rotation = 315;
// Metin parçası oluştur
TextFragment textFragment3 = new TextFragment("rotated text");
// Metin özelliklerini ayarla
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

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesinde metin parçaları ve paragraflar kullanarak metni döndürmeyi başarıyla öğrendiniz. Bu eğitim, belgeyi oluşturmaktan değiştirilmiş sürümü kaydetmeye kadar adım adım bir kılavuz sağladı. Artık bu kodu PDF dosyalarındaki metin döndürmeyi yönetmek için kendi C# projelerinize dahil edebilirsiniz.

### SSS

#### S: "Metin Parçası ve Paragraf Kullanarak Metni Döndürme" eğitiminin amacı nedir?

A: "Metin Parçası ve Paragraf Kullanarak Metni Döndürme" öğreticisinin amacı, bir PDF belgesindeki hem metin parçalarını hem de paragrafları kullanarak metni döndürmek için .NET için Aspose.PDF kitaplığını kullanma sürecinde size rehberlik etmektir. Öğretici, bu işlevi elde etmek için adım adım talimatlar ve örnek kod sağlar.

#### S: Bu eğitim önceki metin döndürme eğitimlerinden nasıl farklı?

A: Bu eğitim, bir PDF belgesi içinde metin döndürmeyi başarmak için metin parçaları ve paragrafların kullanımını birleştirir. Metin parçalarının tek tek nasıl döndürüleceğini ve ardından bir sayfanın`Paragraphs` Daha kapsamlı bir metin döndürme efekti elde etmek için koleksiyon.

#### S: Metin döndürme için metin parçaları ve paragraflar kullanmanın avantajları nelerdir?

A: Metin parçaları ve paragrafları birlikte kullanmak, metin rotasyonunda daha fazla esneklik sağlar. Metin parçaları, bireysel rotasyon ve biçimlendirme ayarlarını etkinleştirirken, paragraflar, metin parçalarının bir sayfa içinde düzenlenmesi ve konumlandırılması için yapı sağlar.

#### S: Aynı paragraf içindeki farklı metin parçalarına farklı döndürme açıları uygulayabilir miyim?

 A: Evet, farklı dönüş açılarını farklı şekilde uygulayabilirsiniz.`TextFragment` aynı paragraf içindeki nesneler. Her metin parçası, belirtilen kendi dönüş açısına sahip olabilir`TextState.Rotation` mülk.

#### S: Bu yöntemle karmaşık metin döndürme efektleri elde etmek mümkün mü?

C: Evet, çeşitli dönüş açılarına sahip metin parçalarını birleştirerek ve bunları paragraflar içerisinde düzenleyerek karmaşık ve özelleştirilmiş metin döndürme efektleri elde edebilir, PDF belgelerinizin görsel çekiciliğini artırabilirsiniz.

#### S: Metin parçalarını ve paragrafları kullanarak metni döndürmek hangi adımları içerir?

A: Adımlar şunları içerir:

1. Yeni bir C# projesi oluşturarak ve Aspose.PDF for .NET kütüphanesine bir referans ekleyerek projeyi kuruyoruz.
2. PDF belgesinin oluşturulması ve bir sayfa eklenmesi.
3. Metin parçaları oluşturma, özelliklerini ayarlama ve dönüş açılarını belirleme.
4.  Sayfaya metin parçaları ekleme`Paragraphs` koleksiyon.
5. Değiştirilen PDF belgesi kaydediliyor.

#### S: Döndürmeyi tüm paragraflara uygulayabilir miyim?

 A: Evet, döndürmeyi tüm paragraflara ayarlayarak uygulayabilirsiniz.`TextState.Rotation` paragrafın kendisinin özelliğidir. Bu, o paragrafın içindeki tüm metin parçalarını döndürecektir.