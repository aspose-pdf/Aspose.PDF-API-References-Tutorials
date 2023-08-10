---
title: Radyo Düğmesi Başlığını Ayarla
linktitle: Radyo Düğmesi Başlığını Ayarla
second_title: Aspose.PDF for .NET API Referansı
description: PDF formundaki bir radyo düğmesinin başlığını ayarlamak için Aspose.PDF for .NET'i nasıl kullanacağınızı öğrenin.
type: docs
weight: 280
url: /tr/net/programming-with-forms/set-radio-button-caption/
---
Bu kılavuzda, bir PDF formundaki bir radyo düğmesinin başlığını tanımlamak için Aspose.PDF kütüphanesinin .NET için nasıl kullanılacağını adım adım açıklayacağız. Radyo düğmesi alanına nasıl erişeceğinizi, yeni bir radyo düğmesi seçeneği oluşturmayı ve düğme başlığını nasıl özelleştireceğinizi göstereceğiz.

## 1. Adım: Belge dizinini yapılandırma

 İlk adım, üzerinde çalışmak istediğiniz PDF formunun bulunduğu belge dizinini yapılandırmaktır. kullanabilirsiniz`dataDir` dizin yolunu belirtmek için değişken.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 değiştirdiğinizden emin olun`"YOUR DOCUMENTS DIRECTORY"` belgeler dizininize giden gerçek yolla.

## 2. Adım: Kaynak PDF formunu yükleme

 Bu adımda, kaynak PDF formunu kullanarak yükleyeceğiz.`Aspose.Pdf.Facades.Form` Aspose.PDF sınıfı.

```csharp
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
```

Formu içeren PDF dosyasının belirtilen belgeler dizininde bulunduğundan emin olun.

## 3. Adım: Radyo düğmesi başlığını düzenleme

Form alan adları arasında dolaşacağız ve radyo düğmesi alanlarını arayacağız. Eşleşen bir alan bulunursa, özel bir başlık içeren yeni bir radyo düğmesi seçeneği oluşturacağız ve bunu mevcut alana ekleyeceğiz.

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
// Sözcük sarma modunu belirtin
by.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
// Yeni TextFragment'i paragrafa ekleyin
par.AppendLine(updatedFragment);
// TextBuilder'ı kullanarak TextParagraph'ı ekleyin
TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
textBuilder.AppendParagraph(par);
field0.DeleteOption("item1");
}
}
```

Altyazı radyo düğmesini ve diğer ayarları gerektiği gibi özelleştirin.

## 4. Adım: Elde Edilen PDF'yi Kaydetme

 Artık radyo düğmesi başlığını değiştirmeyi bitirdiğimize göre, ortaya çıkan PDF'yi kullanarak kaydedebiliriz.`Save` yöntemi`Document` sınıf.

```csharp
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

Ortaya çıkan PDF için tam yolu ve dosya adını belirttiğinizden emin olun.

### Aspose.PDF for .NET kullanarak Set Radio Button Caption için örnek kaynak kodu 
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
		// Sözcük kaydırma modunu belirtin
		par.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
		// Paragrafa yeni TextFragment ekle
		par.AppendLine(updatedFragment);
		// TextBuilder'ı kullanarak TextParagraph'ı ekleyin
		TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
		textBuilder.AppendParagraph(par);
		field0.DeleteOption("item1");
	}
}
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

## Çözüm

Bu kılavuzda, PDF formundaki bir radyo düğmesinin başlığını ayarlamak için Aspose.PDF kitaplığının .NET için nasıl kullanılacağını öğrendik. Açıklanan adımları izleyerek, radyo düğmesi seçeneklerini özelleştirebilir ve başlığı gerektiği gibi değiştirebilirsiniz. PDF dosyalarını işleme olanaklarını genişletmek için Aspose.PDF for .NET'in özelliklerini daha fazla keşfetmekten çekinmeyin.

### SSS

#### S: Aspose.PDF for .NET'i bir PDF formundaki radyo düğmelerine altyazı ayarlamak için kullanabilir miyim?

C: Evet, Aspose.PDF for .NET'i bir PDF formundaki radyo düğmeleri için başlıklar ayarlamak üzere kullanabilirsiniz. Sağlanan örnek kaynak kodu, radyo düğmesi alanına nasıl erişileceğini, özel bir resim yazısı ile yeni bir radyo düğmesi seçeneğinin nasıl oluşturulacağını ve mevcut alanın nasıl güncelleneceğini gösterir.

#### S: Yazı tipi boyutu ve rengi gibi radyo düğmesi başlığının görünümünü nasıl özelleştirebilirim?

 A: Radyo düğmesinin özelliklerini ayarlayarak radyo düğmesi başlığının görünümünü özelleştirebilirsiniz.`TextFragment` başlık için kullanılır. Örneğin yazı tipini, yazı tipi boyutunu, rengini, satır aralığını ve diğer metin biçimlendirme seçeneklerini ayarlayabilirsiniz.

#### S: Tek bir radyo düğmesi grubuna farklı başlıklarla birden fazla radyo düğmesi seçeneği eklemek mümkün müdür?

C: Evet, tek bir radyo düğmesi grubuna farklı başlıklarla birden çok radyo düğmesi seçeneği ekleyebilirsiniz. Her seçenek farklı bir seçeneği temsil edecek ve kullanıcılar gruptan yalnızca bir seçeneği işaretleyebilecek.

#### S: Aspose.PDF for .NET'i bir PDF belgesindeki diğer form alanlarını değiştirmek için kullanabilir miyim?

C: Evet, Aspose.PDF for .NET, bir PDF belgesindeki metin alanları, onay kutuları, açılır listeler ve daha fazlası gibi çeşitli form alanlarını işlemek için kapsamlı bir dizi özellik sunar. Değerleri ayarlamak, görünümleri değiştirmek ve form alanlarına etkileşim eklemek için kitaplığı kullanabilirsiniz.

#### S: Aspose.PDF for .NET, taranan belgeler gibi diğer kaynaklardan oluşturulan PDF'lerle çalışmayı destekliyor mu?

C: Evet, Aspose.PDF for .NET, taranmış belgeler dahil olmak üzere çeşitli kaynaklardan oluşturulan PDF'lerle çalışmayı destekler. Kitaplık, taranan PDF'lerden metin ayıklamak ve içeriği programlı olarak değiştirmek için OCR (Optik Karakter Tanıma) yetenekleri sağlar.