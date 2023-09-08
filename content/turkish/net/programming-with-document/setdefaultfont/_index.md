---
title: PDF Dosyasında Varsayılan Yazı Tipini Ayarla
linktitle: PDF Dosyasında Varsayılan Yazı Tipini Ayarla
second_title: .NET API Referansı için Aspose.PDF
description: Bu adım adım kılavuzla Aspose.PDF for .NET kullanarak bir PDF dosyasında varsayılan yazı tipini nasıl ayarlayacağınızı öğrenin.
type: docs
weight: 280
url: /tr/net/programming-with-document/setdefaultfont/
---
.NET'te PDF belgeleriyle çalışıyorsanız, PDF'de kullanılan yazı tipinin, görüntülendiği veya yazdırıldığı sistemde bulunmadığı sorunlarla karşılaşabilirsiniz. Bu, metnin yanlış görünmesine veya hiç görünmemesine neden olabilir. Aspose.PDF for .NET, belge için varsayılan bir yazı tipi belirlemenize olanak tanıyarak bu soruna bir çözüm sunar. Bu örnekte, Aspose.PDF for .NET kullanılarak varsayılan yazı tipinin nasıl ayarlanacağı anlatılmaktadır.

## 1. Adım: Belge dizininin yolunu ayarlayın

PDF belgemizin bulunduğu dizinin yolunu ayarlamamız gerekiyor. Bu yolu "dataDir" adlı bir değişkende saklayacağız.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: PDF belgesini yükleyin

 Eksik yazı tiplerine sahip mevcut bir PDF belgesini yükleyerek başlayacağız. Bu örnekte, PDF belgesinin, belirtilen dizinde bulunduğunu varsayacağız.`dataDir` değişken.

```csharp
string documentName = dataDir + "input.pdf";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
    // kod buraya gelecek
}
```

## 3. Adım: Varsayılan yazı tipini ayarlayın

 Daha sonra, PDF belgesi için varsayılan yazı tipini aşağıdaki komutu kullanarak ayarlayacağız:`PdfSaveOptions` sınıf. Bu örnekte varsayılan yazı tipini "Arial" olarak ayarlayacağız.

```csharp
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.DefaultFontName = "Arial";
```

## 4. Adım: Güncellenen belgeyi kaydedin

Son olarak güncellenen belgeyi yeni bir dosyaya kaydedeceğiz. Bu örnekte, güncellenen belgeyi giriş dosyasıyla aynı dizinde bulunan "output_out.pdf" adlı bir dosyaya kaydedeceğiz.

```csharp
document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
```

### Aspose.PDF for .NET kullanarak Varsayılan Yazı Tipini Ayarla için Örnek Kaynak Kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Eksik yazı tipine sahip mevcut bir PDF belgesini yükleyin
string documentName = dataDir + "input.pdf";
string newName = "Arial";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
	PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
	// Varsayılan Yazı Tipi Adını Belirtin
	pdfSaveOptions.DefaultFontName = newName;
	document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
}
```

## Çözüm

Aspose.PDF for .NET kullanarak PDF belgelerinde varsayılan bir yazı tipi ayarlamak, orijinal yazı tipleri mevcut olmasa bile metnin doğru şekilde görüntülenmesini sağlamanın basit ve etkili bir yoludur. Geliştiriciler, adım adım kılavuzu izleyerek ve sağlanan C# kaynak kodunu kullanarak, varsayılan yazı tipini kolayca ayarlayabilir ve farklı ortamlarda tutarlı ve güvenilir bir görüntüleme deneyimi sunan PDF'ler oluşturabilir. Bu özellik özellikle PDF'lerin farklı yazı tipi setlerinin yüklü olduğu çeşitli sistemlerde görüntüleneceği veya yazdırılacağı senaryolarda kullanışlıdır.

### PDF dosyasında varsayılan yazı tipini ayarlamak için SSS

#### S: PDF belgelerinde varsayılan yazı tipini ayarlamak neden önemlidir?

C: PDF belgelerinde varsayılan bir yazı tipi ayarlamak önemlidir çünkü bu, orijinal yazı tipleri PDF'nin görüntülendiği veya yazdırıldığı sistemde mevcut olmasa bile metnin doğru şekilde görüntülenmesini sağlar. Eksik veya bozuk metin gibi sorunların önlenmesine yardımcı olarak tutarlı ve güvenilir bir görüntüleme deneyimi sağlar.

#### S: Aspose.PDF for .NET kullanarak herhangi bir yazı tipini varsayılan yazı tipi olarak seçebilir miyim?

 C: Evet, Aspose.PDF for .NET'i kullanarak sistemde mevcut olan herhangi bir yazı tipini varsayılan yazı tipi olarak seçebilirsiniz. Yazı tipinin adını belirtmeniz yeterlidir.`DefaultFontName` mülkiyeti`PdfSaveOptions` sınıf.

#### S: Belirtilen varsayılan yazı tipi sistemde mevcut değilse ne olur?

C: Belirtilen varsayılan yazı tipi sistemde mevcut değilse, PDF görüntüleyici metni görüntülemek için bir yedek yazı tipi kullanacaktır. Farklı sistemler arasında uyumluluğu sağlamak için Arial veya Times New Roman gibi yaygın olarak bulunan bir yazı tipini seçmeniz önerilir.