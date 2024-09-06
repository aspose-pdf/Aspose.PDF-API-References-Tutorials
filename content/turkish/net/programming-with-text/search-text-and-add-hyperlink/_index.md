---
title: Metni Ara ve Köprü Ekle
linktitle: Metni Ara ve Köprü Ekle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET'i kullanarak PDF'te metin aramayı, bulunan metne köprü eklemeyi ve değiştirilmiş belgeyi kaydetmeyi öğrenin.
type: docs
weight: 450
url: /tr/net/programming-with-text/search-text-and-add-hyperlink/
---
Bu eğitim, bir PDF belgesinde belirli bir metni aramak, bulunan metne bir köprü eklemek ve değiştirilmiş belgeyi kaydetmek için Aspose.PDF for .NET'in nasıl kullanılacağını açıklar. Sağlanan C# kaynak kodu, işlemi adım adım gösterir.

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Text;
```

## Adım 3: Belge dizinine giden yolu ayarlayın

 Belge dizininize giden yolu kullanarak ayarlayın`dataDir` değişken:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belge dizininize giden gerçek yol ile.

## Adım 4: Bir TextFragmentAbsorber Oluşturun

 Bir tane oluştur`TextFragmentAbsorber` Giriş arama ifadesinin tüm örneklerini bulmak için nesne:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

 Yer değiştirmek`"\\d{4}-\\d{4}"` İstediğiniz düzenli ifade kalıbıyla.

## Adım 5: Düzenli ifade aramasını etkinleştirin

 Düzenli ifade aramasını etkinleştirmek için şu ayarı yapın:`TextSearchOptions` emicinin özelliği:

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

## Adım 6: PDF belgesini açın ve bağlayın

 Bir tane oluştur`PdfContentEditor` nesneyi oluşturun ve kaynak PDF dosyasına bağlayın:

```csharp
PdfContentEditor editor = new PdfContentEditor();
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

 Yer değiştirmek`"SearchRegularExpressionPage.pdf"` PDF dosyanızın gerçek adıyla.

## Adım 7: Sayfa için emiciyi kabul edin

Belgenin istenilen sayfası için emiciyi kabul edin:

```csharp
editor.Document.Pages[1].Accept(absorber);
```

 Yer değiştirmek`1` İstenilen sayfa numarasıyla.

## Adım 8: Bulunan metne köprü metinleri ekleyin

Alınan metin parçaları arasında dolaşın ve onlara köprü metinleri ekleyin:

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
    // Metin parçasının konumuna göre bir dikdörtgen oluşturun
    System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
        (int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
        (int)Math.Round(textFragment.Rectangle.Height + 1));
    //Dikdörtgene bir web bağlantısı ekleyin
    editor.CreateWebLink(rect, "http://www.aspose.com", 1, System.Drawing.Color.Blue);
}
```

 Yer değiştirmek`"http://www.aspose.com"` İstenilen köprü metni URL'si ile.

## Adım 9: Değiştirilen belgeyi kaydedin ve kapatın

Değiştirilen belgeyi kaydedin ve düzenleyiciyi kapatın:

```csharp
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

 Değiştirdiğinizden emin olun`"SearchTextAndAddHyperlink_out.pdf"` İstenilen çıktı dosya adı ile.

### .NET için Aspose.PDF kullanarak Arama Metni ve Köprü Ekleme için örnek kaynak kodu 
```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Giriş arama ifadesinin tüm örneklerini bulmak için emici nesne oluşturun
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
// Düzenli ifade aramasını etkinleştir
absorber.TextSearchOptions = new TextSearchOptions(true);
// Belgeyi aç
PdfContentEditor editor = new PdfContentEditor();
// Kaynak PDF dosyasını bağla
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
// Sayfa için emiciyi kabul et
editor.Document.Pages[1].Accept(absorber);
int[] dashArray = { };
String[] LEArray = { };
System.Drawing.Color blue = System.Drawing.Color.Blue;
// Parçalar arasında döngü
foreach (TextFragment textFragment in absorber.TextFragments)
{
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
		(int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
		(int)Math.Round(textFragment.Rectangle.Height + 1));
	Enum[] actionName = new Enum[2] { Aspose.Pdf.Annotations.PredefinedAction.Document_AttachFile, Aspose.Pdf.Annotations.PredefinedAction.Document_ExtractPages };
	editor.CreateWebLink(rect, "http:// Www.aspose.com", 1, mavi, actionName);
	editor.CreateLine(rect, "", (float)textFragment.Rectangle.LLX + 1, (float)textFragment.Rectangle.LLY - 1,
		(float)textFragment.Rectangle.URX, (float)textFragment.Rectangle.LLY - 1, 1, 1, blue, "S", dashArray, LEArray);
}
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

## Çözüm

Tebrikler! Bir PDF belgesinde belirli bir metni nasıl arayacağınızı, bulunan metne köprüler nasıl ekleyeceğinizi ve Aspose.PDF for .NET kullanarak değiştirilmiş belgeyi nasıl kaydedeceğinizi başarıyla öğrendiniz. Bu eğitim, projeyi kurmaktan gerekli eylemleri gerçekleştirmeye kadar adım adım bir kılavuz sağladı. Artık bu kodu kendi C# projelerinize dahil ederek metni düzenleyebilir ve PDF dosyalarına köprüler ekleyebilirsiniz.

### SSS

#### S: "Metin Arama ve Köprü Ekleme" eğitiminin amacı nedir?

A: "Metin Ara ve Köprü Ekle" öğreticisinin amacı, .NET için Aspose.PDF kütüphanesinin bir PDF belgesi içinde belirli bir metni aramak, bulunan metne köprüler eklemek ve ardından değiştirilmiş belgeyi kaydetmek için nasıl kullanılacağını göstermektir. Öğretici, adım adım süreci göstermek için kapsamlı bir kılavuz ve C# kod örnekleri sağlar.

#### S: Bu eğitim, bir PDF belgesindeki belirli bir metne köprü metni eklemeye nasıl yardımcı olur?

A: Bu eğitim, bir PDF belgesinde belirli bir metni bulmak, tanımlanan metne bir köprü metni uygulamak ve değiştirilmiş PDF'yi kaydetmek için Aspose.PDF kitaplığını kullanma sürecinde size rehberlik eder. Projeyi kurma, belgeyi yükleme, düzenli ifade aramasını etkinleştirme ve bulunan metne köprü metinleri ekleme gibi temel adımları kapsar.

#### S: Bu eğitimi takip etmek için hangi ön koşullara ihtiyaç var?

A: Başlamadan önce, C# programlama dili hakkında temel bir anlayışa sahip olmalısınız. Ayrıca, Aspose web sitesinden edinilebilen veya projenizde NuGet kullanılarak yüklenebilen Aspose.PDF for .NET kütüphanesinin yüklü olması gerekir.

#### S: Bu eğitimi takip edecek şekilde projemi nasıl kurarım?

A: Tercih ettiğiniz entegre geliştirme ortamında (IDE) yeni bir C# projesi oluşturarak başlayın. Ardından, projenizde kütüphanenin yeteneklerini kullanmanızı sağlayacak olan Aspose.PDF for .NET kütüphanesine bir referans ekleyin.

#### S: Bu eğitimi kullanarak belirli bir metne köprü metni ekleyebilir miyim?

C: Evet, bu eğitim özellikle bir PDF belgesindeki belirli bir metne köprüler eklemeye odaklanır. Düzenli ifadeler kullanarak istenen metni nasıl bulup çıkaracağınızı, metin parçalarıyla ilişkili köprüler nasıl oluşturacağınızı ve değiştirilmiş PDF'yi nasıl kaydedeceğinizi gösterir.

#### S: Aramak ve bağlantı eklemek istediğim metni nasıl tanımlarım?

 A: Aramak istediğiniz metni belirtmek ve ona köprü metni eklemek için bir`TextFragmentAbsorber` nesneyi seçin ve desenini kullanarak ayarlayın`Text` parametre. Varsayılan deseni değiştir`"\\d{4}-\\d{4}"` İstediğiniz düzenli ifade kalıbını kullanarak eğitimin koduna yazın.

#### S: Metin için düzenli ifade aramasını nasıl etkinleştirebilirim?

 A: Düzenli ifade araması, bir`TextSearchOptions` nesne ve değerini ayarlama`true` Bu nesneyi şuraya atayın:`TextSearchOptions` mülkiyeti`TextFragmentAbsorber` Örnek. Bu, metin araması sırasında düzenli ifade deseninin uygulanmasını sağlar.

#### S: Bulunan metne nasıl köprü metni eklerim?

 A: Metin parçalarını kullanarak tanımladıktan sonra`TextFragmentAbsorber` , öğretici bu parçalar arasında yineleme yapmak için bir döngü sağlar. Her metin parçası için öğretici, metin renginin maviye nasıl ayarlanacağını ve köprü metni kullanılarak nasıl oluşturulacağını gösterir.`CreateWebLink` Yöntem.

#### S: Değiştirilmiş PDF'i hiper bağlantılarla kaydetmek için hangi adımları izlemeliyim?

 A: İstenilen metin parçalarına köprü metinleri ekledikten sonra,`PdfContentEditor` Değiştirilen belgeyi kaydetmek için sınıf. Eğitimin örnek kodu, düzenlenen PDF'nin nasıl kaydedileceğini, düzenleyicinin nasıl kapatılacağını ve bir başarı mesajının nasıl görüntüleneceğini gösterir.