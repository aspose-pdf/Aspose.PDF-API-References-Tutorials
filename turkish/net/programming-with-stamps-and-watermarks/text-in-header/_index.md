---
title: Başlıktaki Metin
linktitle: Başlıktaki Metin
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile bir PDF belgesinin başlığına nasıl metin ekleyeceğinizi öğrenin.
type: docs
weight: 190
url: /tr/net/programming-with-stamps-and-watermarks/text-in-header/
---
Bu öğreticide, Aspose.PDF for .NET kullanarak bir PDF belgesinin başlığına nasıl metin ekleyeceğimizi öğreneceğiz. Aşağıdaki adımları takip et:

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
Document pdfDocument = new Document(dataDir + "TextinHeader.pdf");
```

"BELGELER DİZİNİNİZİ", belgeler dizininizin gerçek yolu ile değiştirdiğinizden emin olun.

## 4. Adım: Başlık Metni Oluşturma

Başlığa eklemek istediğiniz metinle yeni bir metin damgası oluşturun:

```csharp
TextStamp textStamp = new TextStamp("Header text");
```

Üst kenar boşluğu, yatay hizalama ve dikey hizalama gibi özelliklerini değiştirerek metni özelleştirebilirsiniz.

## 5. Adım: Tüm sayfalara başlık metni ekleyin

PDF belgesinin tüm sayfalarını gözden geçirin ve başlığa metin damgasını ekleyin:

```csharp
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(textStamp);
}
```

## 6. Adım: PDF Belgesini Kaydetme

Başlık metni tüm sayfalara eklendikten sonra, güncellenmiş PDF belgesini kaydedin:

```csharp
pdfDocument.Save(dataDir + "TextinHeader_out.pdf");
Console.WriteLine("\nText in header added successfully.\nFile saved at: " + dataDir);
```

"BELGELER DİZİNİNİZİ", PDF belgesini kaydetmek istediğiniz dizinin gerçek yolu ile değiştirdiğinizden emin olun.

### Aspose.PDF for .NET kullanan Textin Header için örnek kaynak kodu 
```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi aç
Document pdfDocument = new Document(dataDir+ "TextinHeader.pdf");

// Başlık oluştur
TextStamp textStamp = new TextStamp("Header Text");

// Damganın özelliklerini ayarlama
textStamp.TopMargin = 10;
textStamp.HorizontalAlignment = HorizontalAlignment.Center;
textStamp.VerticalAlignment = VerticalAlignment.Top;

// Tüm sayfalara başlık ekle
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(textStamp);
}

// Güncellenen belgeyi kaydet
pdfDocument.Save(dataDir+ "TextinHeader_out.pdf");
Console.WriteLine("\nText in header added successfully.\nFile saved at " + dataDir);

```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesinin başlığına nasıl metin ekleyeceğinizi öğrendiniz. Artık PDF belgelerinize ek metin ekleyerek başlıklarınızı özelleştirebilirsiniz.
