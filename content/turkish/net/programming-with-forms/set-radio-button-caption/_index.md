---
title: Radyo Düğmesi Başlığını Ayarla
linktitle: Radyo Düğmesi Başlığını Ayarla
second_title: Aspose.PDF for .NET API Referansı
description: .NET için Aspose.PDF kullanarak PDF'lerde radyo düğmesi başlıklarının nasıl ayarlanacağını öğrenin. Bu adım adım kılavuz, PDF formlarınızı yükleme, değiştirme ve kaydetme konusunda size yol gösterir.
type: docs
weight: 280
url: /tr/net/programming-with-forms/set-radio-button-caption/
---
## giriiş

Aspose.PDF for .NET ile PDF manipülasyonuna dalıyorsanız, sizi bir ziyafet bekliyor! Bugün, pratik bir özelliğe odaklanıyoruz: PDF formlarınızda radyo düğmesi başlıkları ayarlama. Radyo düğmeleri, bir dizi seçenek arasından seçim yapmanız gereken kullanıcı formları için olmazsa olmazdır. Bunları yalnızca bir cevaba izin verilen çoktan seçmeli sorular olarak düşünün. Bu eğitim, PDF formunda radyo düğmesi başlıklarını güncelleme sürecini size gösterecek, böylece belgeleriniz hem etkileşimli hem de kullanıcı dostu olacak. 

## Ön koşullar

Koda dalmadan önce, sahip olduğunuzdan emin olmanız gereken birkaç şey var:

1. .NET için Aspose.PDF: Aspose.PDF kütüphanesinin yüklü olduğundan emin olun. Bu kütüphane PDF dosyalarını programatik olarak düzenlemenize yardımcı olacaktır.
2. Geliştirme Ortamı: Visual Studio gibi bir .NET geliştirme ortamı kurmuş olmanız gerekir.
3. Örnek PDF Formu: Bu eğitim için, radyo düğmeleri olan bir örnek PDF formuna ihtiyacınız olacak. Mevcut herhangi bir PDF formunu kullanabilir veya radyo düğmeleri olan yeni bir form oluşturabilirsiniz.
4. Temel C# Bilgisi: Bu kılavuz, C# ve .NET programlama kavramlarına ilişkin temel bir anlayışa sahip olduğunuzu varsayar.

 Aspose.PDF for .NET'i henüz yüklemediyseniz veya geçici bir lisansa ihtiyacınız varsa,[buradan indirin](https://releases.aspose.com/pdf/net/) veya[geçici lisans almak](https://purchase.aspose.com/temporary-license/).

## Paketleri İçe Aktar

Başlamak için, C# projenize gerekli paketleri içe aktarmanız gerekir. Aspose.PDF kütüphanesini eklemenin yolu şöyledir:

```csharp
using System;
using Aspose.Pdf.Forms;
using System.Collections.Generic;
using Aspose.Pdf.Text;
```

Bu paketlerin projenize NuGet veya tercih ettiğiniz yöntemle eklendiğinden emin olun.

## Adım 1: PDF Formunu yükleyin

 İlk olarak, radyo düğmelerini içeren PDF formunu yüklemeniz gerekir.`Aspose.Pdf.Facades.Form`class bu amaç için kullanılır. İşte bunu nasıl yapacağınız:

```csharp
// Belge dizininize giden yolu tanımlayın
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Kaynak PDF formunu yükleyin
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
Document PDF_Template_PDF_HTML = new Document(dataDir + "RadioButtonField.pdf");
```

Bu kod parçacığında:
- `dataDir` PDF'nizin bulunduğu yolu belirtir.
- `Form` sınıfı, PDF içindeki form alanlarıyla etkileşim kurmak için kullanılır.
- `Document` sınıf PDF belgesinin sayfalarına erişim sağlar.

## Adım 2: Radyo Düğmesi Alanlarında Yineleme Yapın

Daha sonra, radyo düğmesi alanlarını belirlemek ve değiştirmek için formunuzdaki alanlar arasında yineleme yapmanız gerekecektir:

```csharp
foreach (var item in form1.FieldNames)
{
    Console.WriteLine(item.ToString());
    Dictionary<string, string> radioOptions = form1.GetButtonOptionValues(item);
```

Bu döngüde:
- `FieldNames` PDF'deki tüm alan adlarının bir listesini sağlar.
- `GetButtonOptionValues(item)` her radyo düğmesi için kullanılabilir seçenekleri alır.

## Adım 3: Radyo Düğmesi Seçeneklerini Değiştirin

 Radyo düğmesi alanlarını tanımladıktan sonra, seçeneklerini değiştirebilirsiniz. Bunun için, alanı şu şekilde dönüştürmeniz gerekir:`RadioButtonField` ve seçeneklerini güncelleyin:

```csharp
    if (item.Contains("radio1"))
    {
        Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
        Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
        fieldoption.OptionName = "Yes";
        fieldoption.PartialName = "Yesname";
```

Burada:
- Değiştirmek istediğimiz belirli radyo düğmesi alanını belirlemek için alan adının "radio1" içerip içermediğini kontrol ediyoruz.
- `RadioButtonField`Belirli değişiklikler yapmak için form alanlarından döküm yapılır.

## Adım 4: Radyo Düğmesi için Başlığı Ayarlayın

 Radyo düğmesinin başlığını ayarlamak veya güncellemek için bir başlık oluşturmanız gerekir.`TextFragment` ve kullan`TextBuilder` istenilen yere yerleştirmek için:

```csharp
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
```

Bu bölümde:
- `TextFragment` Metni ve görünümünü tanımlamak için kullanılır.
- `TextParagraph` Metnin konumlandırılmasına ve biçimlendirilmesine yardımcı olur.
- `TextBuilder` metni PDF'in belirtilen sayfasına ekler.

## Adım 5: Güncellenen PDF'yi Kaydedin

Son olarak güncellenen PDF'i yeni bir dosyaya kaydedin:

```csharp
        field0.DeleteOption("item1");
    }
}
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

Bu, şunları sağlayacaktır:
- Değişiklikler PDF'e uygulanır.
- Orijinal radyo düğmesi seçeneği belirtildiği şekilde kaldırıldı.

## Çözüm

.NET için Aspose.PDF kullanarak bir PDF formundaki radyo düğmesi başlıklarını değiştirmek, belgelerinizin etkileşimini ve kullanılabilirliğini büyük ölçüde artırabilir. Bu eğitimde özetlenen adımlarla, bir PDF'yi kolayca yükleyebilir, radyo düğmesi seçeneklerini güncelleyebilir ve değişikliklerinizi kaydedebilirsiniz. Bu yaklaşım, form yönetimi için kullanışlıdır ve PDF'lerinizin kullanıcılarınızın tam ihtiyaçlarını karşılamasını sağlar. Aspose.PDF'ye dalın ve diğer PDF düzenlemeleri için yeteneklerini keşfedin!

## SSS

### Birden fazla radyo düğmesi alanını aynı anda güncelleyebilir miyim?
Evet, tüm radyo düğmesi alanlarında yineleme yapabilir ve gerektiği gibi değişiklikleri uygulayabilirsiniz.

### Aspose.PDF'i kullanmak için lisansa ihtiyacım var mı?
 Ücretsiz deneme ile başlayabilirsiniz ancak uzun süreli kullanım için lisans gereklidir.[Buradan lisans alın](https://purchase.aspose.com/buy).

### PDF'i kaydetmeden önce değişiklikleri nasıl test edebilirim?
PDF'yi geliştirme ortamınızda önizleyebilir veya değişiklikleri kontrol etmek için bir PDF görüntüleyicisi kullanabilirsiniz.

### Aspose.PDF .NET'in tüm sürümleriyle uyumlu mudur?
Aspose.PDF çeşitli .NET sürümlerini destekler. Belirli .NET sürümünüzle uyumluluğunu kontrol ettiğinizden emin olun.

### Diğer form alanlarını da benzer şekilde düzenleyebilir miyim?
Evet, benzer teknikler PDF belgelerindeki diğer form alanlarına da uygulanabilir.