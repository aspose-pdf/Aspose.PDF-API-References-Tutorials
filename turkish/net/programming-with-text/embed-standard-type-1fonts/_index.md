---
title: Standart Tip 1 Yazı Tiplerini Göm
linktitle: Standart Tip 1 Yazı Tiplerini Göm
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak standart Tip 1 yazı tiplerini bir PDF belgesine nasıl gömeceğinizi öğrenin.
type: docs
weight: 140
url: /tr/net/programming-with-text/embed-standard-type-1fonts/
---

Bu eğitim, standart Tip 1 yazı tiplerini Aspose.PDF for .NET kullanarak bir PDF belgesine gömme sürecinde size rehberlik edecektir. Sağlanan C# kaynak kodu, gerekli adımları gösterir.

## Gereksinimler
Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Visual Studio veya makinenizde kurulu başka bir C# derleyicisi.
- Aspose.PDF for .NET kitaplığı. Resmi Aspose web sitesinden indirebilir veya yüklemek için NuGet gibi bir paket yöneticisi kullanabilirsiniz.

## 1. Adım: Projeyi kurun
1. Tercih ettiğiniz geliştirme ortamında yeni bir C# projesi oluşturun.
2. Aspose.PDF for .NET kitaplığına bir referans ekleyin.

## 2. Adım: Gerekli ad alanlarını içe aktarın
Standart Type 1 yazı tiplerini gömmek istediğiniz kod dosyasında, dosyanın en üstüne aşağıdaki using yönergesini ekleyin:

```csharp
using Aspose.Pdf;
```

## 3. Adım: Belge dizinini ayarlayın
 Kodda yazan satırı bulun`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` belgelerinizin saklandığı dizinin yolu ile.

## 4. Adım: Mevcut PDF belgesini yükleyin
 kullanarak mevcut bir PDF belgesini yükleyin.`Document` yapıcı ve yolu giriş PDF dosyasına geçirme.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## Adım 5: EmbedStandardFonts özelliğini ayarlayın
 Yı kur`EmbedStandardFonts` belgenin özelliği`true` standart Tip 1 yazı tiplerini gömmeyi etkinleştirmek için.

```csharp
pdfDocument.EmbedStandardFonts = true;
```

## 6. Adım: Yazı tiplerini her sayfaya gömün
 PDF belgesinin her sayfasında dolaşın ve yazı tiplerinin zaten gömülü olup olmadığını kontrol edin. Değilse,`IsEmbedded` mülkiyet`true` yazı tipini gömmek için.

```csharp
foreach(Page page in pdfDocument.Pages)
{
     if (page.Resources.Fonts != null)
     {
         foreach(Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
         {
             if (!pageFont.IsEmbedded)
             {
                 pageFont.IsEmbedded = true;
             }
         }
     }
}
```

## 7. Adım: Güncellenmiş PDF belgesini kaydedin
 Güncellenmiş PDF belgesini kullanarak kaydedin.`Save` yöntemi`Document` çıktı dosyası yolunu belirten nesne.

```csharp
pdfDocument.Save(dataDir + "EmbeddedFonts-updated_out.pdf");
```

### Aspose.PDF for .NET kullanarak Standard Type 1Fonts'u Gömmek için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Mevcut bir PDF Belgesini yükleyin
Document pdfDocument = new Document(dataDir + "input.pdf");
// Belgenin EmbedStandardFonts özelliğini ayarlayın
pdfDocument.EmbedStandardFonts = true;
foreach (Aspose.Pdf.Page page in pdfDocument.Pages)
{
	if (page.Resources.Fonts != null)
	{
		foreach (Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
		{
			// Yazı tipinin zaten gömülü olup olmadığını kontrol edin
			if (!pageFont.IsEmbedded)
			{
				pageFont.IsEmbedded = true;
			}
		}
	}
}
pdfDocument.Save(dataDir + "EmbeddedFonts-updated_out.pdf");
```

## Çözüm
Aspose.PDF for .NET kullanarak standart Tip 1 yazı tiplerini bir PDF belgesine başarıyla gömdünüz. Gömülü yazı tipleriyle güncellenmiş PDF dosyası, belirtilen çıktı dosyası yoluna kaydedildi.