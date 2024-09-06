---
title: PDF Dosyasında Varsayılan Yazı Tipini Ayarla
linktitle: PDF Dosyasında Varsayılan Yazı Tipini Ayarla
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım kılavuzla Aspose.PDF for .NET kullanarak bir PDF dosyasında varsayılan yazı tipini nasıl ayarlayacağınızı öğrenin.
type: docs
weight: 280
url: /tr/net/programming-with-document/setdefaultfont/
---
.NET'te PDF belgeleriyle çalışıyorsanız, PDF'de kullanılan yazı tipinin görüntülendiği veya yazdırıldığı sistemde mevcut olmaması gibi sorunlarla karşılaşabilirsiniz. Bu, metnin yanlış görünmesine veya hiç görünmemesine neden olabilir. .NET için Aspose.PDF, belge için varsayılan bir yazı tipi ayarlamanıza izin vererek bu soruna bir çözüm sunar. Bu örnekte, .NET için Aspose.PDF kullanılarak varsayılan yazı tipinin nasıl ayarlanacağı gösterilmektedir.

## Adım 1: Belge dizinine giden yolu ayarlayın

PDF belgemizin bulunduğu dizine giden yolu ayarlamamız gerekiyor. Bu yolu "dataDir" adlı bir değişkende saklayacağız.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: PDF belgesini yükleyin

 Eksik yazı tiplerine sahip mevcut bir PDF belgesini yükleyerek başlayacağız. Bu örnekte, PDF belgesinin belirtilen dizinde bulunduğunu varsayacağız.`dataDir` değişken.

```csharp
string documentName = dataDir + "input.pdf";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
    // kod buraya gelir
}
```

## Adım 3: Varsayılan yazı tipini ayarlayın

 Daha sonra, PDF belgesi için varsayılan yazı tipini şu şekilde ayarlayacağız:`PdfSaveOptions`sınıf. Bu örnekte, varsayılan yazı tipini "Arial" olarak ayarlayacağız.

```csharp
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.DefaultFontName = "Arial";
```

## Adım 4: Güncellenen belgeyi kaydedin

Son olarak, güncellenen belgeyi yeni bir dosyaya kaydedeceğiz. Bu örnekte, güncellenen belgeyi giriş dosyasıyla aynı dizinde bulunan "output_out.pdf" adlı bir dosyaya kaydedeceğiz.

```csharp
document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
```

### .NET için Aspose.PDF kullanarak Varsayılan Yazı Tipini Ayarlamak için Örnek Kaynak Kodu

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Eksik yazı tipine sahip mevcut bir PDF belgesini yükleyin
string documentName = dataDir + "input.pdf";
string newName = "Arial";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
	PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
	// Varsayılan Yazı Tipi Adını Belirle
	pdfSaveOptions.DefaultFontName = newName;
	document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
}
```

## Çözüm

Aspose.PDF for .NET kullanarak PDF belgelerinde varsayılan bir yazı tipi ayarlamak, orijinal yazı tipleri mevcut olmasa bile metnin doğru şekilde görüntülenmesini sağlamanın basit ve etkili bir yoludur. Adım adım kılavuzu izleyerek ve sağlanan C# kaynak kodunu kullanarak, geliştiriciler varsayılan yazı tipini kolayca ayarlayabilir ve farklı ortamlarda tutarlı ve güvenilir bir görüntüleme deneyimi sunan PDF'ler oluşturabilir. Bu özellik, PDF'lerin farklı yazı tipi setleri yüklü olabilecek çeşitli sistemlerde görüntüleneceği veya yazdırılacağı senaryolarda özellikle yararlıdır.

### PDF dosyasında varsayılan yazı tipini ayarlama hakkında SSS

#### S: PDF belgelerinde varsayılan yazı tipini ayarlamak neden önemlidir?

A: PDF belgelerinde varsayılan bir yazı tipi ayarlamak önemlidir çünkü PDF'nin görüntülendiği veya yazdırıldığı sistemde orijinal yazı tipleri mevcut olmasa bile metnin doğru şekilde görüntülenmesini sağlar. Eksik veya bozuk metin gibi sorunları önlemeye yardımcı olarak tutarlı ve güvenilir bir görüntüleme deneyimi sağlar.

#### S: Aspose.PDF for .NET'i kullanarak varsayılan yazı tipi olarak herhangi bir yazı tipini seçebilir miyim?

 A: Evet, Aspose.PDF for .NET'i kullanarak sistemde bulunan herhangi bir yazı tipini varsayılan yazı tipi olarak seçebilirsiniz. Sadece yazı tipinin adını belirtin`DefaultFontName` mülkiyeti`PdfSaveOptions` sınıf.

#### S: Belirtilen varsayılan yazı tipi sistemde mevcut değilse ne olur?

A: Belirtilen varsayılan yazı tipi sistemde mevcut değilse, PDF görüntüleyici metni görüntülemek için bir yedek yazı tipi kullanacaktır. Farklı sistemler arasında uyumluluğu sağlamak için Arial veya Times New Roman gibi yaygın olarak bulunan bir yazı tipi seçmeniz önerilir.