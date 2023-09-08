---
title: Metin Arayın ve Köprü Ekleyin
linktitle: Metin Arayın ve Köprü Ekleyin
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET'i kullanarak PDF'de metin aramayı, bulunan metne köprüler eklemeyi ve değiştirilen belgeyi kaydetmeyi öğrenin.
type: docs
weight: 450
url: /tr/net/programming-with-text/search-text-and-add-hyperlink/
---
Bu eğitimde, bir PDF belgesinde belirli bir metni aramak, bulunan metne bir köprü eklemek ve değiştirilen belgeyi kaydetmek için Aspose.PDF for .NET'in nasıl kullanılacağı açıklanmaktadır. Sağlanan C# kaynak kodu süreci adım adım gösterir.

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Text;
```

## 3. Adım: Belge dizininin yolunu ayarlayın

 kullanarak belge dizininizin yolunu ayarlayın.`dataDir` değişken:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

## 4. Adım: TextFragmentAbsorber oluşturun

 Oluşturmak`TextFragmentAbsorber` giriş arama ifadesinin tüm örneklerini bulmak için nesne:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

 Yer değiştirmek`"\\d{4}-\\d{4}"` İstediğiniz düzenli ifade modeliyle.

## 5. Adım: Normal ifade aramasını etkinleştirin

 Ayarlayarak normal ifade aramasını etkinleştirin`TextSearchOptions` emicinin özelliği:

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

## 6. Adım: PDF belgesini açın ve bağlayın

 Oluşturmak`PdfContentEditor` nesnesini oluşturun ve onu kaynak PDF dosyasına bağlayın:

```csharp
PdfContentEditor editor = new PdfContentEditor();
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

 Yer değiştirmek`"SearchRegularExpressionPage.pdf"` PDF dosyanızın gerçek adıyla.

## 7. Adım: Sayfanın emicisini kabul edin

Belgenin istenen sayfası için emiciyi kabul edin:

```csharp
editor.Document.Pages[1].Accept(absorber);
```

 Yer değiştirmek`1` İstenilen sayfa numarasıyla.

## 8. Adım: Bulunan metne köprüler ekleyin

Alınan metin parçaları arasında dolaşın ve bunlara köprüler ekleyin:

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

 Yer değiştirmek`"http://www.aspose.com"` istenen köprü URL'si ile.

## 9. Adım: Değiştirilen belgeyi kaydedin ve kapatın

Değiştirilen belgeyi kaydedin ve düzenleyiciyi kapatın:

```csharp
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

 Değiştirdiğinizden emin olun`"SearchTextAndAddHyperlink_out.pdf"` İstenilen çıktı dosyası adı ile.

### Aspose.PDF for .NET kullanarak Metin Arama ve Köprü Ekleme için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Giriş arama ifadesinin tüm örneklerini bulmak için emici nesne oluşturun
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
// Normal ifade aramasını etkinleştir
absorber.TextSearchOptions = new TextSearchOptions(true);
// Belgeyi aç
PdfContentEditor editor = new PdfContentEditor();
// Kaynak PDF dosyasını bağlayın
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
// Sayfanın emicisini kabul edin
editor.Document.Pages[1].Accept(absorber);
int[] dashArray = { };
String[] LEArray = { };
System.Drawing.Color blue = System.Drawing.Color.Blue;
// Parçalar arasında döngü yapın
foreach (TextFragment textFragment in absorber.TextFragments)
{
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
		(int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
		(int)Math.Round(textFragment.Rectangle.Height + 1));
	Enum[] actionName = new Enum[2] { Aspose.Pdf.Annotations.PredefinedAction.Document_AttachFile, Aspose.Pdf.Annotations.PredefinedAction.Document_ExtractPages };
	editor.CreateWebLink(rect, "http:// Www.aspose.com", 1, blue, actionName);
	editor.CreateLine(rect, "", (float)textFragment.Rectangle.LLX + 1, (float)textFragment.Rectangle.LLY - 1,
		(float)textFragment.Rectangle.URX, (float)textFragment.Rectangle.LLY - 1, 1, 1, blue, "S", dashArray, LEArray);
}
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

## Çözüm

Tebrikler! Aspose.PDF for .NET'i kullanarak bir PDF belgesinde belirli bir metni nasıl arayacağınızı, bulunan metne köprüler eklemeyi ve değiştirilen belgeyi nasıl kaydedeceğinizi başarıyla öğrendiniz. Bu eğitimde, projenin kurulumundan gerekli eylemlerin gerçekleştirilmesine kadar adım adım bir kılavuz sağlanmıştır. Artık metni değiştirmek ve PDF dosyalarına köprüler eklemek için bu kodu kendi C# projelerinize dahil edebilirsiniz.

### SSS'ler

#### S: "Metin Arama ve Köprü Ekleme" eğitiminin amacı nedir?

C: "Metin Arama ve Köprü Ekleme" eğitimi, bir PDF belgesinde belirli bir metni aramak, bulunan metne köprüler eklemek ve ardından değiştirilen belgeyi kaydetmek için Aspose.PDF kütüphanesinin .NET için nasıl kullanılacağını göstermeyi amaçlamaktadır. Öğretici, süreci adım adım göstermek için kapsamlı bir kılavuz ve C# kod örnekleri sağlar.

#### S: Bu eğitim, bir PDF belgesindeki belirli metne köprüler eklemeye nasıl yardımcı olur?

C: Bu eğitim, bir PDF belgesinde belirli bir metni bulmak, tanımlanan metne bir köprü uygulamak ve değiştirilen PDF'yi kaydetmek için Aspose.PDF kütüphanesini kullanma sürecinde size rehberlik eder. Projenin kurulması, belgenin yüklenmesi, normal ifade aramasının etkinleştirilmesi ve bulunan metne köprülerin eklenmesi gibi temel adımları kapsar.

#### S: Bu öğreticiyi takip etmek için hangi önkoşullar gereklidir?

C: Başlamadan önce C# programlama dili hakkında temel bilgiye sahip olmalısınız. Ayrıca, Aspose web sitesinden edinebileceğiniz veya projenizde NuGet kullanarak kurabileceğiniz Aspose.PDF for .NET kütüphanesinin de kurulu olması gerekir.

#### S: Projemi bu öğreticiyi takip edecek şekilde nasıl ayarlayabilirim?

C: Tercih ettiğiniz tümleşik geliştirme ortamında (IDE) yeni bir C# projesi oluşturarak başlayın. Ardından Aspose.PDF for .NET kütüphanesine, kütüphanenin yeteneklerini projenizde kullanmanızı sağlayacak bir referans ekleyin.

#### S: Bu öğreticiyi kullanarak belirli bir metne köprüler ekleyebilir miyim?

C: Evet, bu eğitim özellikle bir PDF belgesindeki belirli metne köprüler eklemeye odaklanmaktadır. Düzenli ifadeler kullanarak istenen metnin nasıl bulunacağını ve çıkarılacağını, metin parçalarıyla ilişkili köprülerin nasıl oluşturulacağını ve değiştirilen PDF'nin nasıl kaydedileceğini gösterir.

#### S: Aramak ve köprü eklemek istediğim metni nasıl tanımlarım?

 C: Aramak ve köprü eklemek istediğiniz metni belirtmek için bir`TextFragmentAbsorber` kullanarak nesneyi seçin ve desenini ayarlayın.`Text` parametre. Varsayılan deseni değiştir`"\\d{4}-\\d{4}"` öğreticinin kodunda istediğiniz normal ifade düzeniyle.

#### S: Metin için normal ifade aramasını nasıl etkinleştirebilirim?

 C: Normal ifade araması, bir`TextSearchOptions` nesne ve değerini ayarlama`true` . Bu nesneyi şuraya atayın:`TextSearchOptions` mülkiyeti`TextFragmentAbsorber` misal. Bu, metin araması sırasında normal ifade modelinin uygulanmasını sağlar.

#### S: Bulunan metne nasıl köprü eklerim?

 C: Metin parçalarını tanımladıktan sonra`TextFragmentAbsorber` , öğretici bu parçalar arasında yineleme yapmak için bir döngü sağlar. Eğitimde her metin parçası için metin renginin nasıl maviye ayarlanacağı ve aşağıdaki komutu kullanarak bir köprü oluşturulacağı gösterilmektedir:`CreateWebLink` yöntem.

#### S: Değiştirilen PDF'yi köprülerle kaydetme adımları nelerdir?

 C: İstediğiniz metin parçalarına köprüler ekledikten sonra,`PdfContentEditor` Değiştirilen belgeyi kaydetmek için sınıf. Eğitimin örnek kodu, düzenlenen PDF'nin nasıl kaydedileceğini, düzenleyicinin nasıl kapatılacağını ve bir başarı mesajının nasıl görüntüleneceğini gösterir.