---
title: Metin Arayın ve Köprü Ekleyin
linktitle: Metin Arayın ve Köprü Ekleyin
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF'de metin aramayı, bulunan metne köprüler eklemeyi ve değiştirilen belgeyi kaydetmeyi öğrenin.
type: docs
weight: 450
url: /tr/net/programming-with-text/search-text-and-add-hyperlink/
---

Bu eğitim, Aspose.PDF for .NET'in bir PDF belgesinde belirli bir metni aramak, bulunan metne köprü eklemek ve değiştirilen belgeyi kaydetmek için nasıl kullanılacağını açıklar. Sağlanan C# kaynak kodu, süreci adım adım gösterir.

## Önkoşullar

Öğreticiye devam etmeden önce, aşağıdakilere sahip olduğunuzdan emin olun:

- C# programlama dili hakkında temel bilgi.
- Aspose.PDF for .NET kitaplığı yüklendi. Aspose web sitesinden edinebilir veya projenize yüklemek için NuGet'i kullanabilirsiniz.

## 1. Adım: Projeyi kurun

Tercih ettiğiniz tümleşik geliştirme ortamında (IDE) yeni bir C# projesi oluşturarak başlayın ve Aspose.PDF for .NET kitaplığına bir referans ekleyin.

## 2. Adım: Gerekli ad alanlarını içe aktarın

Gerekli ad alanlarını içe aktarmak için C# dosyanızın başına aşağıdaki using yönergelerini ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Text;
```

## 3. Adım: Belge dizinine giden yolu ayarlayın

 kullanarak belge dizininize giden yolu ayarlayın.`dataDir` değişken:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

## Adım 4: Bir TextFragmentAbsorber Oluşturun

 Oluşturmak`TextFragmentAbsorber` girdi arama ifadesinin tüm örneklerini bulmak için nesne:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

 Yer değiştirmek`"\\d{4}-\\d{4}"` istediğiniz düzenli ifade modeliyle.

## 5. Adım: Normal ifade aramasını etkinleştirin

ayarlayarak normal ifade aramasını etkinleştirin.`TextSearchOptions` emicinin özelliği:

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

## 6. Adım: PDF belgesini açın ve ciltleyin

 Oluşturmak`PdfContentEditor` nesne ve onu kaynak PDF dosyasına bağlayın:

```csharp
PdfContentEditor editor = new PdfContentEditor();
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

 Yer değiştirmek`"SearchRegularExpressionPage.pdf"` PDF dosyanızın gerçek adıyla.

## 7. Adım: Sayfa için emiciyi kabul edin

Dokümanın istenen sayfası için emiciyi kabul edin:

```csharp
editor.Document.Pages[1].Accept(absorber);
```

 Yer değiştirmek`1` İstenilen sayfa numarası ile

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
    // Dikdörtgene bir web bağlantısı ekleyin
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

 değiştirdiğinizden emin olun`"SearchTextAndAddHyperlink_out.pdf"` istenen çıktı dosyası adıyla.

### Aspose.PDF for .NET kullanarak Metin Arama ve Köprü Ekleme için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Giriş arama ifadesinin tüm örneklerini bulmak için soğurucu nesne oluşturun
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
// Normal ifade aramasını etkinleştir
absorber.TextSearchOptions = new TextSearchOptions(true);
// Belgeyi aç
PdfContentEditor editor = new PdfContentEditor();
//Bağlama kaynağı PDF dosyası
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
// Sayfa için soğurucuyu kabul edin
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

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesinde belirli bir metni aramayı, bulunan metne köprüler eklemeyi ve değiştirilen belgeyi kaydetmeyi başarıyla öğrendiniz. Bu öğretici, projeyi ayarlamaktan gerekli eylemleri gerçekleştirmeye kadar adım adım bir kılavuz sağladı. Artık metni değiştirmek ve PDF dosyalarına köprüler eklemek için bu kodu kendi C# projelerinize dahil edebilirsiniz.