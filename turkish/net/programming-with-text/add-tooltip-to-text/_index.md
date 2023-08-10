---
title: Metne Araç İpucu Ekle
linktitle: Metne Araç İpucu Ekle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesindeki metne nasıl araç ipuçları ekleyeceğinizi öğrenin.
type: docs
weight: 90
url: /tr/net/programming-with-text/add-tooltip-to-text/
---

Bu eğitim, Aspose.PDF for .NET kullanarak bir PDF belgesindeki metne araç ipuçları ekleme sürecinde size rehberlik edecektir. Sağlanan C# kaynak kodu, gerekli adımları gösterir.

## Gereksinimler
Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Visual Studio veya makinenizde kurulu başka bir C# derleyicisi.
- Aspose.PDF for .NET kitaplığı. Resmi Aspose web sitesinden indirebilir veya yüklemek için NuGet gibi bir paket yöneticisi kullanabilirsiniz.

## 1. Adım: Projeyi kurun
1. Tercih ettiğiniz geliştirme ortamında yeni bir C# projesi oluşturun.
2. Aspose.PDF for .NET kitaplığına bir referans ekleyin.

## 2. Adım: Gerekli ad alanlarını içe aktarın
Metne araç ipuçları eklemek istediğiniz kod dosyasında, dosyanın en üstüne aşağıdaki using yönergelerini ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

## 3. Adım: Belge dizinini ayarlayın
 Kodda yazan satırı bulun`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` belgelerinizin saklandığı dizinin yolu ile.

## 4. Adım: Metin içeren örnek bir belge oluşturun
 Yeni bir tane oluştur`Document` nesne ve metin parçaları içeren sayfalar ekleyin. Sağlanan kodda, ilgili araç ipucu metniyle belgeye iki metin parçası eklenir.

```csharp
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
```

## 5. Adım: Belgeyi açın ve metin parçalarını bulun
 Oluşturulan belgeyi kullanarak yükleyin`Document` yapıcı ve kullanarak araç ipuçlarına ihtiyaç duyan metin parçalarını bulun`TextFragmentAbsorber`.

```csharp
Document document = new Document(outputFile);
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
```

## 6. Adım: Metin parçalarına araç ipuçları ekleyin
 Ayıklanan metin parçaları arasında dolaşın ve konumlarında görünmez düğmeler oluşturun. İstediğiniz araç ipucu metnini`AlternateName` mülkiyeti`ButtonField`. Düğme alanlarını belgenin formuna ekleyin.

```csharp
foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Tooltip for text.";
     document.Form.Add(field);
}
```

## 7. Adım: Uzun araç ipuçları içeren ek metin parçaları için tekrarlayın
Uzun araç ipuçları içeren metin parçaları için 5. ve 6. adımları tekrarlayın. Arama kriterlerini ve araç ipucu metnini buna göre değiştirin.

```csharp
absorb = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorb);
textFragments = absorb.TextFragments;

foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Long tooltip text goes here...";
     document.Form.Add(field);
}
```

## 8. Adım: Değiştirilen belgeyi kaydedin
 Değiştirilen PDF belgesini kullanarak kaydedin.`Save` yöntemi`Document` nesne.

```csharp
document. Save(outputFile);
```

### Aspose.PDF for .NET kullanarak Metne Araç İpucu Ekleme için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "Tooltip_out.pdf";
// Metin içeren örnek belge oluşturun
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
// Belgeyi metinle aç
Document document = new Document(outputFile);
// Normal ifadeyle eşleşen tüm ifadeleri bulmak için TextAbsorber nesnesi oluşturun
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
// Belge sayfaları için emiciyi kabul edin
document.Pages.Accept(absorber);
// Ayıklanan metin parçalarını alın
TextFragmentCollection textFragments = absorber.TextFragments;
// Parçalar arasında döngü
foreach (TextFragment fragment in textFragments)
{
	// Metin parçası konumunda görünmez düğme oluştur
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// AlternateName değeri, bir görüntüleyici uygulaması tarafından araç ipucu olarak görüntülenecek
	field.AlternateName = "Tooltip for text.";
	// Belgeye düğme alanı ekle
	document.Form.Add(field);
}
// Sırada çok uzun araç ipucu örneği olacak
absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorber);
textFragments = absorber.TextFragments;
foreach (TextFragment fragment in textFragments)
{
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// Çok uzun metin ayarla
	field.AlternateName = "Lorem ipsum dolor sit amet, consectetur adipiscing elit," +
							" sed do eiusmod tempor incididunt ut labore et dolore magna" +
							" aliqua. Ut enim ad minim veniam, quis nostrud exercitation" +
							" ullamco laboris nisi ut aliquip ex ea commodo consequat." +
							" Duis aute irure dolor in reprehenderit in voluptate velit" +
							" esse cillum dolore eu fugiat nulla pariatur. Excepteur sint" +
							" occaecat cupidatat non proident, sunt in culpa qui officia" +
							" deserunt mollit anim id est laborum.";
	document.Form.Add(field);
}
// Belgeyi kaydet
document.Save(outputFile);
```

## Çözüm
Aspose.PDF for .NET kullanarak bir PDF belgesindeki metne araç ipuçlarını başarıyla eklediniz. Ortaya çıkan PDF dosyası artık belirtilen çıktı dosyası yolunda bulunabilir.