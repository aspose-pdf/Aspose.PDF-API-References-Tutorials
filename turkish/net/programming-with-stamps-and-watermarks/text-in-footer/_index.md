---
title: Alt Bilgideki Metin
linktitle: Alt Bilgideki Metin
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile bir PDF belgesinin altbilgisine metin eklemeyi öğrenin.
type: docs
weight: 180
url: /tr/net/programming-with-stamps-and-watermarks/text-in-footer/
---
Bu öğreticide, Aspose.PDF for .NET kullanarak bir PDF belgesinin altbilgisine nasıl metin ekleyeceğimizi öğreneceğiz. Aşağıdaki adımları takip et:

## 1. Adım: Proje hazırlama

Aspose.PDF for .NET'i kurduğunuzdan ve bir C# projesi oluşturduğunuzdan emin olun.

## 2. Adım: Ad alanlarını içe aktarma

Aşağıdaki ad alanlarını C# kaynak dosyanıza ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 3. Adım: Belgeyi açma

Sağlanan yolu kullanarak mevcut PDF belgesini açın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document pdfDocument = new Document(dataDir + "TextinFooter.pdf");
```

"BELGELER DİZİNİNİZİ", belgeler dizininizin gerçek yolu ile değiştirdiğinizden emin olun.

## 4. Adım: Altbilgi metni oluşturun

Altbilgiye eklemek istediğiniz metinle yeni bir metin damgası oluşturun:

```csharp
TextStamp textStamp = new TextStamp("footer text");
```

Alt kenar boşluğu, yatay hizalama ve dikey hizalama gibi özelliklerini değiştirerek metni özelleştirebilirsiniz.

## 5. Adım: Tüm sayfalara altbilgi metni ekleyin

PDF belgesinin tüm sayfalarını gözden geçirin ve metin damgasını alt bilgiye ekleyin:

```csharp
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(textStamp);
}
```

## 6. Adım: PDF Belgesini Kaydetme

Altbilgi metni tüm sayfalara eklendikten sonra, güncellenmiş PDF belgesini kaydedin:

```csharp
dataDir = dataDir + "TextinFooter_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText in footer added successfully.\nFile saved at: " + dataDir);
```

"BELGELER DİZİNİNİZİ", PDF belgesini kaydetmek istediğiniz dizinin gerçek yolu ile değiştirdiğinizden emin olun.

### Aspose.PDF for .NET kullanan Textin Footer için örnek kaynak kodu 
```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi aç
Document pdfDocument = new Document(dataDir+ "TextinFooter.pdf");

// Alt bilgi oluştur
TextStamp textStamp = new TextStamp("Footer Text");

// Damganın özelliklerini ayarlama
textStamp.BottomMargin = 10;
textStamp.HorizontalAlignment = HorizontalAlignment.Center;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Tüm sayfalara alt bilgi ekle
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(textStamp);
}
dataDir = dataDir + "TextinFooter_out.pdf";

// Güncellenmiş PDF dosyasını kaydet
pdfDocument.Save(dataDir);
Console.WriteLine("\nText in footer added successfully.\nFile saved at " + dataDir);

```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesinin altbilgisine nasıl metin ekleyeceğinizi öğrendiniz. Artık PDF belgelerinize ek metin ekleyerek altbilgilerinizi özelleştirebilirsiniz.
