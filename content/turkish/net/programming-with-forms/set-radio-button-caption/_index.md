---
title: Radyo Düğmesi Başlığını Ayarla
linktitle: Radyo Düğmesi Başlığını Ayarla
second_title: Aspose.PDF for .NET API Referansı
description: PDF formundaki bir radyo düğmesinin başlığını ayarlamak için Aspose.PDF for .NET'i nasıl kullanacağınızı öğrenin.
type: docs
weight: 280
url: /tr/net/programming-with-forms/set-radio-button-caption/
---
Bu kılavuzda, .NET için Aspose.PDF kütüphanesini kullanarak PDF formundaki bir radyo düğmesinin başlığını nasıl tanımlayacağınızı adım adım açıklayacağız. Radyo düğmesi alanına nasıl erişeceğinizi, yeni bir radyo düğmesi seçeneği nasıl oluşturacağınızı ve düğme başlığını nasıl özelleştireceğinizi göstereceğiz.

## Adım 1: Belge dizinini yapılandırma

 İlk adım, üzerinde çalışmak istediğiniz PDF formunun bulunduğu belge dizinini yapılandırmaktır.`dataDir` dizin yolunu belirtmek için kullanılan değişken.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Değiştirdiğinizden emin olun`"YOUR DOCUMENTS DIRECTORY"` Belgelerinizin bulunduğu dizinin gerçek yolunu belirtin.

## Adım 2: Kaynak PDF formunu yükleme

 Bu adımda, kaynak PDF formunu kullanarak yükleyeceğiz`Aspose.Pdf.Facades.Form` Aspose.PDF sınıfı.

```csharp
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
```

Formu içeren PDF dosyasının belirtilen belgeler dizininde bulunduğundan emin olun.

## Adım 3: Radyo düğmesi başlığını düzenleme

Form alan adları arasında dolaşacağız ve radyo düğmesi alanlarını arayacağız. Eşleşen bir alan bulunursa, özel bir başlıkla yeni bir radyo düğmesi seçeneği oluşturacağız ve bunu mevcut alana ekleyeceğiz.

```csharp
foreach(var item in form1.FieldNames)
{
if (item.Contains("radio1"))
{
Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
fieldoption.OptionName = "Yes";
fieldoption.PartialName = "Yesname";
var updatedFragment = new Aspose.Pdf.Text.TextFragment("test123");
updatedFragment.TextState.Font = FontRepository.FindFont("Arial");
updatedFragment.TextState.FontSize = 10;
updatedFragment.TextState.LineSpacing = 6.32f;
// Bir TextParagraph nesnesi oluşturun
TextParagraph par = new TextParagraph();
// Paragraf konumunu ayarla
par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
// Kelime kaydırma modunu belirtin
by.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
// Paragrafa yeni TextFragment'ı ekleyin
par.AppendLine(updatedFragment);
// TextBuilder kullanarak TextParagraph'ı ekleyin
TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
textBuilder.AppendParagraph(par);
field0.DeleteOption("item1");
}
}
```

Altyazı seçeneğini ve diğer ayarları gerektiği gibi özelleştirin.

## Adım 4: Ortaya Çıkan PDF'yi Kaydetme

 Artık radyo düğmesi başlığını değiştirmeyi tamamladığımıza göre, ortaya çıkan PDF'yi şu şekilde kaydedebiliriz:`Save` yöntemi`Document` sınıf.

```csharp
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

Elde edilen PDF için tam yolu ve dosya adını belirttiğinizden emin olun.

### .NET için Aspose.PDF kullanarak Radyo Düğmesi Başlığı Ayarlama için örnek kaynak kodu 
```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Kaynak PDF formunu yükle
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
Document PDF_Template_PDF_HTML = new Document(dataDir + "RadioButtonField.pdf");
foreach (var item in form1.FieldNames)
{
	Console.WriteLine(item.ToString());
	Dictionary<string, string> radioOptions = form1.GetButtonOptionValues(item);
	if (item.Contains("radio1"))
	{
		Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
		Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
		fieldoption.OptionName = "Yes";
		fieldoption.PartialName = "Yesname";
		var updatedFragment = new Aspose.Pdf.Text.TextFragment("test123");
		updatedFragment.TextState.Font = FontRepository.FindFont("Arial");
		updatedFragment.TextState.FontSize = 10;
		updatedFragment.TextState.LineSpacing = 6.32f;
		// TextParagraph nesnesi oluştur
		TextParagraph par = new TextParagraph();
		// Paragraf konumunu ayarla
		par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
		// Kelime sarma modunu belirtin
		par.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
		// Paragrafa yeni TextFragment ekle
		par.AppendLine(updatedFragment);
		// TextBuilder kullanarak TextParagraph'ı ekleyin
		TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
		textBuilder.AppendParagraph(par);
		field0.DeleteOption("item1");
	}
}
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

## Çözüm

Bu kılavuzda, bir PDF formundaki bir radyo düğmesi için başlığı ayarlamak üzere .NET için Aspose.PDF kitaplığının nasıl kullanılacağını öğrendik. Açıklanan adımları izleyerek, radyo düğmesi seçeneklerini özelleştirebilir ve başlığı gerektiği gibi değiştirebilirsiniz. PDF dosyalarını düzenleme olanaklarını genişletmek için .NET için Aspose.PDF'nin özelliklerini daha fazla keşfetmekten çekinmeyin.

### SSS

#### S: PDF formundaki radyo düğmeleri için başlıklar ayarlamak amacıyla Aspose.PDF for .NET'i kullanabilir miyim?

A: Evet, PDF formundaki radyo düğmeleri için başlıklar ayarlamak üzere Aspose.PDF for .NET'i kullanabilirsiniz. Sağlanan örnek kaynak kodu, radyo düğmesi alanına nasıl erişileceğini, özel bir başlıkla yeni bir radyo düğmesi seçeneğinin nasıl oluşturulacağını ve mevcut alanın nasıl güncelleneceğini gösterir.

#### S: Radyo düğmesi başlığının görünümünü (yazı tipi boyutu ve rengi gibi) nasıl özelleştirebilirim?

 A: Radyo düğmesi başlığının görünümünü, özelliklerini ayarlayarak özelleştirebilirsiniz.`TextFragment` başlık için kullanılır. Örneğin, yazı tipini, yazı tipi boyutunu, rengini, satır aralığını ve diğer metin biçimlendirme seçeneklerini ayarlayabilirsiniz.

#### S: Tek bir radyo düğmesi grubuna farklı başlıklara sahip birden fazla radyo düğmesi seçeneği eklemek mümkün müdür?

A: Evet, tek bir radyo düğmesi grubuna farklı başlıklara sahip birden fazla radyo düğmesi seçeneği ekleyebilirsiniz. Her seçenek farklı bir seçimi temsil eder ve kullanıcılar gruptan yalnızca bir seçeneği seçebilir.

#### S: Aspose.PDF for .NET'i bir PDF belgesindeki diğer form alanlarını değiştirmek için kullanabilir miyim?

C: Evet, Aspose.PDF for .NET, metin alanları, onay kutuları, açılır listeler ve daha fazlası gibi bir PDF belgesindeki çeşitli form alanlarını düzenlemek için kapsamlı bir özellik seti sağlar. Kitaplığı, değerleri ayarlamak, görünümleri değiştirmek ve form alanlarına etkileşim eklemek için kullanabilirsiniz.

#### S: Aspose.PDF for .NET, taranmış belgeler gibi diğer kaynaklardan oluşturulan PDF'lerle çalışmayı destekliyor mu?

A: Evet, Aspose.PDF for .NET, taranmış belgeler de dahil olmak üzere çeşitli kaynaklardan oluşturulan PDF'lerle çalışmayı destekler. Kütüphane, taranmış PDF'lerden metin çıkarmak ve içeriği programatik olarak işlemek için OCR (Optik Karakter Tanıma) yetenekleri sağlar.