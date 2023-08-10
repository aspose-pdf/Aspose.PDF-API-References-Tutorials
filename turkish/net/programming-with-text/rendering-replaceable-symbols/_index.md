---
title: Değiştirilebilir Sembolleri Oluşturma
linktitle: Değiştirilebilir Sembolleri Oluşturma
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesinde değiştirilebilir sembollerin nasıl oluşturulacağını öğrenin.
type: docs
weight: 310
url: /tr/net/programming-with-text/rendering-replaceable-symbols/
---

Bu öğreticide, .NET için Aspose.PDF kitaplığı kullanılarak bir PDF belgesinde değiştirilebilir sembollerin nasıl oluşturulacağını açıklayacağız. Sağlanan C# kaynak kodunu kullanarak bir PDF oluşturma, yeni satır işaretçileriyle bir metin parçası ekleme, metin özelliklerini ayarlama, metni konumlandırma ve PDF'yi kaydetme sürecini adım adım inceleyeceğiz.

## Önkoşullar

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Aspose.PDF for .NET kitaplığı yüklendi.
- Temel bir C# programlama anlayışı.

## 1. Adım: Belge Dizinini kurun

 Öncelikle, oluşturulan PDF dosyasını kaydetmek istediğiniz dizinin yolunu belirlemeniz gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` içinde`dataDir` istediğiniz dizinin yolu ile değişken.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Bir PDF Belgesi ve Sayfası Oluşturun

 Ardından, yeni bir PDF belgesi oluşturuyoruz ve bunu kullanarak ona bir sayfa ekliyoruz.`Document` sınıf ve`Page` Aspose.PDF kitaplığından sınıf.

```csharp
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
```

## 3. Adım: Yeni Satır İşaretçileriyle Metin Parçası Ekleyin

 biz bir yaratırız`TextFragment` nesnesini seçin ve metnini yeni satır işaretçileri içerecek şekilde ayarlayın (`Environment.NewLine`) birden fazla metin satırını temsil etmek için.

```csharp
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
```

## 4. Adım: Metin Parçası Özelliklerini Ayarlayın

İstenirse metin parçası için yazı tipi boyutu, yazı tipi, arka plan rengi ve ön plan rengi gibi çeşitli özellikler ayarlayabiliriz.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
```

## Adım 5: Metin Paragrafı ve Konum Oluşturun

 biz bir yaratırız`TextParagraph` nesnesini seçin, metin parçasını paragrafa ekleyin ve paragrafın sayfadaki konumunu ayarlayın.

```csharp
TextParagraph par = new TextParagraph();
par.AppendLine(textFragment);
par.Position = new Aspose.Pdf.Text.Position(100, 600);
```

## 6. Adım: Sayfaya Metin Paragrafı Ekleyin

 biz bir yaratırız`TextBuilder`sayfa ile nesne ve metin paragrafını metin oluşturucuya ekleyin.

```csharp
TextBuilder textBuilder = new TextBuilder(applicationFirstPage);
textBuilder.AppendParagraph(par);
```

## 7. Adım: PDF Belgesini Kaydedin

Son olarak, PDF belgesini belirtilen çıktı dosyasına kaydediyoruz.

```csharp
dataDir = dataDir + "RenderingReplaceableSymbols_out.pdf";
pdfApplicationDoc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols rendered successfully during PDF creation.\nFile saved at " + dataDir);
```

### Aspose.PDF for .NET kullanarak Değiştirilebilir Sembolleri Oluşturmak için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
// Gerekli yeni satır işaretçilerini içeren metinle yeni TextFragment'i başlat
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
// Gerekirse metin parçası özelliklerini ayarlayın
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// TextParagraph nesnesi oluştur
TextParagraph par = new TextParagraph();
// Paragrafa yeni TextFragment ekle
par.AppendLine(textFragment);
// Paragraf konumunu ayarla
par.Position = new Aspose.Pdf.Text.Position(100, 600);
// TextBuilder nesnesi oluştur
TextBuilder textBuilder = new TextBuilder(applicationFirstPage);
// TextBuilder'ı kullanarak TextParagraph'ı ekleyin
textBuilder.AppendParagraph(par);
dataDir = dataDir + "RenderingReplaceableSymbols_out.pdf";
pdfApplicationDoc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols render successfully duing pdf creation.\nFile saved at " + dataDir);
```

## Çözüm

Bu öğreticide, .NET için Aspose.PDF kitaplığını kullanarak bir PDF belgesinde değiştirilebilir sembollerin nasıl oluşturulacağını öğrendiniz. Adım adım kılavuzu izleyerek ve verilen C# kodunu yürüterek bir PDF oluşturabilir, yeni satır işaretçileriyle metin ekleyebilir, metin özelliklerini ayarlayabilir, metni sayfada konumlandırabilir ve PDF'yi kaydedebilirsiniz.