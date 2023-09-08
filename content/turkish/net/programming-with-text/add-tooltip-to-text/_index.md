---
title: PDF Dosyasındaki Metne Araç İpucu Ekle
linktitle: PDF Dosyasındaki Metne Araç İpucu Ekle
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak PDF dosyasındaki metne nasıl araç ipuçları ekleyeceğinizi öğrenin.
type: docs
weight: 90
url: /tr/net/programming-with-text/add-tooltip-to-text/
---
Bu eğitim, Aspose.PDF for .NET kullanarak PDF dosyasındaki metne araç ipuçları ekleme sürecinde size rehberlik edecektir. Sağlanan C# kaynak kodu gerekli adımları gösterir.

## Gereksinimler
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Makinenizde kurulu Visual Studio veya başka herhangi bir C# derleyicisi.
- Aspose.PDF for .NET kitaplığı. Resmi Aspose web sitesinden indirebilir veya yüklemek için NuGet gibi bir paket yöneticisi kullanabilirsiniz.

## 1. Adım: Projeyi ayarlayın
1. Tercih ettiğiniz geliştirme ortamında yeni bir C# projesi oluşturun.
2. Aspose.PDF for .NET kitaplığına bir referans ekleyin.

## 2. Adım: Gerekli ad alanlarını içe aktarın
Metne araç ipuçları eklemek istediğiniz kod dosyasında, dosyanın en üstüne aşağıdaki kullanarak yönergeleri ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

## 3. Adım: Belge dizinini ayarlayın
 Kodda yazan satırı bulun`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` belgelerinizin saklandığı dizinin yolu ile birlikte.

## 4. Adım: Metin içeren örnek bir belge oluşturun
 Yeni bir tane oluştur`Document` nesne ve metin parçaları içeren sayfalar ekleyin. Sağlanan kodda, ilgili araç ipucu metnini içeren iki metin parçası belgeye eklenir.

```csharp
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
```

## Adım 5: Belgeyi açın ve metin parçalarını bulun
 Oluşturulan belgeyi kullanarak yükleyin.`Document` yapıcıyı kullanarak araç ipuçlarına ihtiyaç duyan metin parçalarını bulun.`TextFragmentAbsorber`.

```csharp
Document document = new Document(outputFile);
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
```

## 6. Adım: Metin parçalarına araç ipuçları ekleyin
 Çıkarılan metin parçaları arasında dolaşın ve konumlarında görünmez düğmeler oluşturun. İstediğiniz araç ipucu metnini`AlternateName` mülkiyeti`ButtonField`. Düğme alanlarını belgenin formuna ekleyin.

```csharp
foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Tooltip for text.";
     document.Form.Add(field);
}
```

## 7. Adım: Uzun araç ipuçlarına sahip ek metin parçaları için tekrarlayın
Uzun araç ipuçlarına sahip metin parçaları için 5. ve 6. adımları tekrarlayın. Arama kriterlerini ve araç ipucu metnini buna göre değiştirin.

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

## Adım 8: Değiştirilen belgeyi kaydedin
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
// Metin içeren belgeyi aç
Document document = new Document(outputFile);
// Normal ifadeyle eşleşen tüm ifadeleri bulmak için TextAbsorber nesnesi oluşturun
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
// Belge sayfaları için emiciyi kabul edin
document.Pages.Accept(absorber);
// Çıkarılan metin parçalarını alın
TextFragmentCollection textFragments = absorber.TextFragments;
// Parçalar arasında döngü yapın
foreach (TextFragment fragment in textFragments)
{
	// Metin parçası konumunda görünmez düğme oluşturun
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// AlternateName değeri bir görüntüleyici uygulaması tarafından ipucu olarak görüntülenecektir
	field.AlternateName = "Tooltip for text.";
	// Belgeye düğme alanı ekleyin
	document.Form.Add(field);
}
// Sırada çok uzun bir araç ipucunun örneği olacak
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
Aspose.PDF for .NET'i kullanarak bir PDF belgesindeki metne başarıyla araç ipuçları eklediniz. Ortaya çıkan PDF dosyası artık belirtilen çıktı dosyası yolunda bulunabilir.

## SSS

#### S: Bu eğitimin odak noktası nedir?

C: Bu eğitim, Aspose.PDF for .NET kütüphanesini kullanarak bir PDF dosyası içindeki metne araç ipuçları eklemeye odaklanmaktadır. Sağlanan C# kaynak kodu, bunu başarmak için gereken adımları gösterir.

#### S: Bu eğitim için hangi ad alanlarının içe aktarılması gerekiyor?

C: Metne araç ipuçları eklemek istediğiniz kod dosyasında, dosyanın başında aşağıdaki ad alanlarını içe aktarın:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

#### S: Belge dizinini nasıl belirlerim?

 A: Kodda satırı bulun`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

#### S: Metin içeren örnek bir belgeyi nasıl oluşturabilirim?

 C: 4. Adımda yeni bir`Document` nesne ve metin parçaları içeren sayfalar ekleyin. Sağlanan kod, ilgili araç ipucu metniyle birlikte iki metin parçası ekler.

#### S: Belgeyi nasıl açarım ve metin parçalarını nasıl bulurum?

 C: 5. Adımda, oluşturulan belgeyi aşağıdaki komutu kullanarak yükleyeceksiniz:`Document` yapıcıyı kullanın ve araç ipuçlarını gerektiren metin parçalarını bulun.`TextFragmentAbsorber`.

#### S: Metin parçalarına nasıl araç ipuçları eklerim?

 C: 6. Adımda, çıkarılan metin parçaları arasında geçiş yapacak ve konumlarında görünmez düğmeler oluşturacaksınız. Araç ipucu metni şuraya atanır:`AlternateName` mülkiyeti`ButtonField`belgenin formuna eklenir.

#### S: Uzun araç ipuçlarına sahip ek metin parçaları için işlemi nasıl tekrarlayabilirim?

C: Uzun araç ipuçlarına sahip metin parçaları için 5. ve 6. Adımları tekrarlayın. Arama kriterlerini ve araç ipucu metnini buna göre değiştirin.

#### S: Değiştirilen belgeyi nasıl kaydedebilirim?

 C: 8. Adımda, değiştirilen PDF belgesini aşağıdaki komutu kullanarak kaydedeceksiniz:`Save` yöntemi`Document` nesne.

#### S: Bu eğitimden çıkan ana sonuç nedir?

C: Bu eğitimi takip ederek Aspose.PDF for .NET kullanarak metne araç ipuçları ekleyerek PDF belgenizi nasıl geliştireceğinizi öğrendiniz. Bu, PDF içeriğiyle etkileşime girdiklerinde okuyuculara değerli ek bilgiler sağlayabilir.