---
title: RGB'den Gri Tonlamaya Dönüştür
linktitle: RGB'den Gri Tonlamaya Dönüştür
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF'leri RGB'den Gri Tonlamaya nasıl dönüştüreceğinizi öğrenin. Baskı kalitesini artırın ve dosya boyutunu azaltın.
type: docs
weight: 60
url: /tr/net/programming-with-document/convertfromrgbtograyscale/
---

Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesini RGB renk alanından Gri Tonlamaya dönüştürme sürecinde size rehberlik edeceğiz. Bu dönüştürme, dosya boyutunu küçültmek veya belgeleri yazdırmak için hazırlamak gibi çeşitli amaçlar için yararlı olabilir. Aşağıdaki adım adım kılavuzu izleyin:

## 1. Adım: Kaynak PDF dosyasını yükleyin

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
using (Document document = new Document(dataDir + "input.pdf"))
{
    // Kodunuz burada...
}
```

## 2. Adım: Dönüşüm stratejisini belirleyin

```csharp
Aspose.Pdf.RgbToDeviceGrayConversionStrategy strategy = new Aspose.Pdf.RgbToDeviceGrayConversionStrategy();
```

## 3. Adım: Her sayfayı gri tonlamaya dönüştürün

```csharp
for (int idxPage = 1; idxPage <= document.Pages.Count; idxPage++)
{
    Page page = document.Pages[idxPage];
    strategy.Convert(page);
}
```

## 4. Adım: Ortaya çıkan dosyayı kaydedin

```csharp
document.Save(dataDir + "Test-gray_out.pdf");
```

Tebrikler! Aspose.PDF for .NET'i kullanarak PDF belgesini RGB'den Gri Tonlamaya başarıyla dönüştürdünüz.

### Aspose.PDF for .NET kullanarak RGB'den Gri Tonlamaya Dönüştürme için örnek kaynak kodu:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Kaynak PDF dosyasını yükle
using (Document document = new Document(dataDir + "input.pdf"))
{
    Aspose.Pdf.RgbToDeviceGrayConversionStrategy strategy = new Aspose.Pdf.RgbToDeviceGrayConversionStrategy();

    for (int idxPage = 1; idxPage <= document.Pages.Count; idxPage++)
    {
        Page page = document.Pages[idxPage];
        strategy.Convert(page);
    }

    document.Save(dataDir + "Test-gray_out.pdf");
}
```

Artık Aspose.PDF for .NET kullanarak PDF belgelerinizi RGB'den Gri Tonlamaya kolayca dönüştürebilirsiniz.

