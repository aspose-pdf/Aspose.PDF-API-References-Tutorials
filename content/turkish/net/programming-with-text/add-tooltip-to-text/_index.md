---
title: PDF Dosyasındaki Metne İpucu Ekle
linktitle: PDF Dosyasındaki Metne İpucu Ekle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyasındaki metne araç ipuçlarının nasıl ekleneceğini öğrenin.
type: docs
weight: 90
url: /tr/net/programming-with-text/add-tooltip-to-text/
---
Bu eğitim, .NET için Aspose.PDF kullanarak PDF dosyasındaki metne araç ipuçları ekleme sürecinde size rehberlik edecektir. Sağlanan C# kaynak kodu gerekli adımları göstermektedir.

## Gereksinimler
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Bilgisayarınızda Visual Studio veya herhangi bir C# derleyicisi yüklü olmalıdır.
- Aspose.PDF for .NET kütüphanesi. Resmi Aspose web sitesinden indirebilir veya NuGet gibi bir paket yöneticisi kullanarak kurabilirsiniz.

## Adım 1: Projeyi kurun
1. Tercih ettiğiniz geliştirme ortamında yeni bir C# projesi oluşturun.
2. .NET için Aspose.PDF kitaplığına bir referans ekleyin.

## Adım 2: Gerekli ad alanlarını içe aktarın
Metne araç ipuçları eklemek istediğiniz kod dosyasında, dosyanın en üstüne aşağıdaki using yönergelerini ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

## Adım 3: Belge dizinini ayarlayın
 Kodda şu satırı bulun:`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` Belgelerinizin saklandığı dizinin yolunu içeren.

## Adım 4: Metin içeren bir örnek belge oluşturun
 Yeni bir tane oluştur`Document`nesne ve metin parçalarıyla sayfalar ekleyin. Sağlanan kodda, iki metin parçası ilgili araç ipucu metniyle belgeye eklenir.

```csharp
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
```

## Adım 5: Belgeyi açın ve metin parçalarını bulun
 Oluşturulan belgeyi kullanarak yükleyin`Document` oluşturucuyu kullanın ve araç ipuçlarına ihtiyaç duyan metin parçalarını bulun`TextFragmentAbsorber`.

```csharp
Document document = new Document(outputFile);
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
```

## Adım 6: Metin parçalarına araç ipuçları ekleyin
 Çıkarılan metin parçaları arasında dolaşın ve konumlarında görünmez düğmeler oluşturun. İstenilen araç ipucu metnini atayın`AlternateName` mülkiyeti`ButtonField`. Belgenin formuna düğme alanlarını ekleyin.

```csharp
foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Tooltip for text.";
     document.Form.Add(field);
}
```

## Adım 7: Uzun araç ipuçlarına sahip ek metin parçaları için tekrarlayın
Uzun araç ipuçlarına sahip metin parçaları için 5. ve 6. adımları tekrarlayın. Arama ölçütlerini ve araç ipucu metnini buna göre değiştirin.

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
 Değiştirilen PDF belgesini kullanarak kaydedin`Save` yöntemi`Document` nesne.

```csharp
document. Save(outputFile);
```

### .NET için Aspose.PDF kullanarak Metne İpucu Ekleme için örnek kaynak kodu 
```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "Tooltip_out.pdf";
// Metin içeren örnek belge oluşturun
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
// Metin içeren belgeyi aç
Document document = new Document(outputFile);
//Düzenli ifadeyle eşleşen tüm ifadeleri bulmak için TextAbsorber nesnesi oluşturun
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
// Belge sayfaları için emiciyi kabul edin
document.Pages.Accept(absorber);
// Çıkarılan metin parçalarını alın
TextFragmentCollection textFragments = absorber.TextFragments;
// Parçalar arasında döngü
foreach (TextFragment fragment in textFragments)
{
	// Metin parçası konumunda görünmez düğme oluştur
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// AlternateName değeri bir görüntüleyici uygulaması tarafından araç ipucu olarak gösterilecektir
	field.AlternateName = "Tooltip for text.";
	// Belgeye düğme alanı ekle
	document.Form.Add(field);
}
// Sonraki çok uzun bir ipucu örneği olacak
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
.NET için Aspose.PDF kullanarak bir PDF belgesindeki metne araç ipuçlarını başarıyla eklediniz. Elde edilen PDF dosyası artık belirtilen çıktı dosyası yolunda bulunabilir.

## SSS

#### S: Bu eğitimin odak noktası nedir?

A: Bu eğitim, .NET için Aspose.PDF kitaplığını kullanarak bir PDF dosyasındaki metne araç ipuçları eklemeye odaklanır. Sağlanan C# kaynak kodu, bunu başarmak için gereken adımları gösterir.

#### S: Bu eğitim için hangi ad alanlarının içe aktarılması gerekiyor?

A: Metne araç ipuçları eklemek istediğiniz kod dosyasında, dosyanın başına aşağıdaki ad alanlarını içe aktarın:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

#### S: Belge dizinini nasıl belirlerim?

 A: Kodda şu satırı bulun:`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` belge dizininize giden gerçek yol ile.

#### S: Metin içeren bir örnek belge nasıl oluşturabilirim?

 A: 4. Adımda yeni bir tane oluşturacaksınız`Document` nesne ve metin parçalarıyla sayfalar ekleyin. Sağlanan kod, ilgili araç ipucu metniyle iki metin parçası ekler.

#### S: Belgeyi nasıl açabilirim ve metin parçalarını nasıl bulabilirim?

 A: 5. Adımda, oluşturulan belgeyi kullanarak yükleyeceksiniz`Document` oluşturucuyu kullanın ve araç ipuçlarını gerektiren metin parçalarını bulun`TextFragmentAbsorber`.

#### S: Metin parçalarına araç ipuçlarını nasıl eklerim?

 A: 6. Adımda, çıkarılan metin parçaları arasında dolaşacak ve konumlarında görünmez düğmeler oluşturacaksınız. Araç ipucu metni,`AlternateName` mülkiyeti`ButtonField`Belgenin formuna eklenen.

#### S: Uzun araç ipuçlarına sahip ek metin parçaları için işlemi nasıl tekrarlarım?

A: Uzun araç ipuçlarına sahip metin parçaları için 5. ve 6. Adımları tekrarlayın. Arama kriterlerini ve araç ipucu metnini buna göre değiştirin.

#### S: Değiştirilen belgeyi nasıl kaydedebilirim?

 A: 8. Adımda, değiştirilen PDF belgesini kullanarak kaydedeceksiniz`Save` yöntemi`Document` nesne.

#### S: Bu eğitimden çıkarılacak en önemli ders nedir?

A: Bu öğreticiyi takip ederek, Aspose.PDF for .NET kullanarak metne araç ipuçları ekleyerek PDF belgenizi nasıl geliştireceğinizi öğrendiniz. Bu, okuyucular PDF içeriğiyle etkileşime girdiklerinde değerli ek bilgiler sağlayabilir.