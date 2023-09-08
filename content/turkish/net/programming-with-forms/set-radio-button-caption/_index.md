---
title: Radyo Düğmesi Başlığını Ayarla
linktitle: Radyo Düğmesi Başlığını Ayarla
second_title: .NET API Referansı için Aspose.PDF
description: PDF formundaki bir radyo düğmesinin başlığını ayarlamak için Aspose.PDF for .NET'i nasıl kullanacağınızı öğrenin.
type: docs
weight: 280
url: /tr/net/programming-with-forms/set-radio-button-caption/
---
Bu kılavuzda, PDF formundaki bir radyo düğmesinin başlığını tanımlamak için Aspose.PDF kütüphanesinin .NET için nasıl kullanılacağını adım adım açıklayacağız. Size radyo düğmesi alanına nasıl erişeceğinizi, yeni bir radyo düğmesi seçeneği oluşturacağınızı ve düğme başlığını nasıl özelleştireceğinizi göstereceğiz.

## 1. Adım: Belge dizinini yapılandırma

 İlk adım, üzerinde çalışmak istediğiniz PDF formunun bulunduğu belge dizinini yapılandırmaktır. Şunu kullanabilirsiniz:`dataDir` Dizin yolunu belirtmek için değişken.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Değiştirdiğinizden emin olun`"YOUR DOCUMENTS DIRECTORY"` Belgeler dizininizin gerçek yolu ile.

## 2. Adım: Kaynak PDF formunu yükleme

 Bu adımda, kaynak PDF formunu kullanarak yükleyeceğiz.`Aspose.Pdf.Facades.Form` Aspose.PDF sınıfı.

```csharp
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
```

Formu içeren PDF dosyasının belirtilen belgeler dizininde bulunduğundan emin olun.

## 3. Adım: Radyo düğmesi başlığını düzenleme

Form alanı adları arasında dolaşacağız ve radyo düğmesi alanlarını arayacağız. Eşleşen bir alan bulunursa, özel başlık içeren yeni bir radyo düğmesi seçeneği oluşturup bunu mevcut alana ekleyeceğiz.

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
// TextParagraph nesnesi oluşturma
TextParagraph par = new TextParagraph();
// Paragraf konumunu ayarla
par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
// Kelime kaydırma modunu belirtin
by.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
// Yeni TextFragment'i paragrafa ekleme
par.AppendLine(updatedFragment);
// TextBuilder'ı kullanarak TextParagraph'ı ekleme
TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
textBuilder.AppendParagraph(par);
field0.DeleteOption("item1");
}
}
```

Altyazı radyo düğmesini ve diğer ayarları gerektiği gibi özelleştirin.

## Adım 4: Ortaya Çıkan PDF'yi Kaydetme

 Artık radyo düğmesi başlığını değiştirmeyi bitirdiğimize göre, elde edilen PDF'yi aşağıdaki komutu kullanarak kaydedebiliriz:`Save` yöntemi`Document` sınıf.

```csharp
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

Ortaya çıkan PDF'nin tam yolunu ve dosya adını belirttiğinizden emin olun.

### Aspose.PDF for .NET kullanarak Radyo Düğmesi Başlığını Ayarla için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
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
		// Kelime kaydırma modunu belirtin
		par.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
		// Paragrafa yeni TextFragment ekle
		par.AppendLine(updatedFragment);
		// TextBuilder'ı kullanarak TextParagraph'ı ekleme
		TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
		textBuilder.AppendParagraph(par);
		field0.DeleteOption("item1");
	}
}
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

## Çözüm

Bu kılavuzda, PDF formundaki bir radyo düğmesinin başlığını ayarlamak için .NET için Aspose.PDF kütüphanesini nasıl kullanacağımızı öğrendik. Açıklanan adımları izleyerek radyo düğmesi seçeneklerini özelleştirebilir ve başlığı gerektiği gibi değiştirebilirsiniz. PDF dosyalarını değiştirme olanaklarını genişletmek için Aspose.PDF for .NET'in özelliklerini daha fazla keşfetmekten çekinmeyin.

### SSS'ler

#### S: Aspose.PDF for .NET'i kullanarak PDF formundaki radyo düğmelerinin başlıklarını ayarlayabilir miyim?

C: Evet, PDF formundaki radyo düğmelerinin başlıklarını ayarlamak için Aspose.PDF for .NET'i kullanabilirsiniz. Sağlanan örnek kaynak kodu, radyo düğmesi alanına nasıl erişileceğini, özel başlıkla yeni bir radyo düğmesi seçeneğinin nasıl oluşturulacağını ve mevcut alanın nasıl güncelleneceğini gösterir.

#### S: Radyo düğmesi başlığının yazı tipi boyutu ve rengi gibi görünümünü nasıl özelleştirebilirim?

 C: Radyo düğmesi başlığının özelliklerini ayarlayarak, radyo düğmesi başlığının görünümünü özelleştirebilirsiniz.`TextFragment` başlık için kullanılır. Örneğin yazı tipini, yazı tipi boyutunu, rengini, satır aralığını ve diğer metin biçimlendirme seçeneklerini ayarlayabilirsiniz.

#### S: Tek bir radyo düğmesi grubuna farklı başlıklara sahip birden fazla radyo düğmesi seçeneği eklemek mümkün müdür?

C: Evet, tek bir radyo düğmesi grubuna farklı başlıklara sahip birden fazla radyo düğmesi seçeneği ekleyebilirsiniz. Her seçenek farklı bir seçeneği temsil edecek ve kullanıcılar gruptan yalnızca bir seçeneği seçebilecek.

#### S: Aspose.PDF for .NET'i bir PDF belgesindeki diğer form alanlarını değiştirmek için kullanabilir miyim?

C: Evet, Aspose.PDF for .NET, bir PDF belgesindeki metin alanları, onay kutuları, açılır listeler ve daha fazlası gibi çeşitli form alanlarını yönetmek için kapsamlı bir dizi özellik sağlar. Değerleri ayarlamak, görünümleri değiştirmek ve form alanlarına etkileşim eklemek için kitaplığı kullanabilirsiniz.

#### S: Aspose.PDF for .NET, taranmış belgeler gibi diğer kaynaklardan oluşturulan PDF'lerle çalışmayı destekliyor mu?

C: Evet, Aspose.PDF for .NET, taranmış belgeler de dahil olmak üzere çeşitli kaynaklardan oluşturulan PDF'lerle çalışmayı destekler. Kitaplık, taranan PDF'lerden metin çıkarmak ve içeriği programlı olarak değiştirmek için OCR (Optik Karakter Tanıma) yetenekleri sağlar.