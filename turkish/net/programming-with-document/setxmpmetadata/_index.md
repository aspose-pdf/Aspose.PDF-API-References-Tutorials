---
title: XMPMetadata'yı ayarla
linktitle: XMPMetadata'yı ayarla
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyalarında XMPMetadata'yı nasıl ayarlayacağınızı öğrenin. Bu adım adım kılavuzu izleyin.
type: docs
weight: 330
url: /tr/net/programming-with-document/setxmpmetadata/
---
Bu makalede, bir PDF dosyasında XMP meta verilerini ayarlamak için Aspose.PDF for .NET'in nasıl kullanılacağına dair adım adım bir kılavuz sağlayacağız. Makalenin sonunda tam bir örnek kaynak kodu sağlayacağız.

## 1. Adım: Belge dizinine giden yolu ayarlayın

Başlamadan önce, PDF belgemizin bulunduğu dizinin yolunu belirlememiz gerekiyor. Bu yolu "dataDir" adlı bir değişkende saklayacağız.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 değiştirdiğinizden emin olun`YOUR DOCUMENT DIRECTORY` PDF dosyanızın gerçek yolu ile.

## Adım 2: PDF Dosyasını Açın

İlk adım, XMP meta verilerini ayarlamak istediğiniz PDF dosyasını açmaktır. Bunu yapmak için yeni bir tane oluşturmanız gerekir.`Document` nesne ve PDF dosyanızın yolunu iletin.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi aç
Document pdfDocument = new Document(dataDir + "SetXMPMetadata.pdf");
```

## 3. Adım: XMP Meta Veri Özelliklerini Ayarlayın

Artık PDF dosyanızı açtığınıza göre, XMP meta veri özelliklerini ayarlamaya başlayabilirsiniz. Ayarladığınız özellikler, özel ihtiyaçlarınıza bağlı olacaktır, ancak ayarlamak isteyebileceğiniz bazı genel özellikler şunlardır:

- `xmp:CreateDate`: PDF dosyasının oluşturulma tarihi.
- `xmp:Nickname`: PDF dosyası için bir takma ad veya takma ad.
- `xmp:CustomProperty`: Belirttiğiniz bir değere sahip özel bir özellik.

 Bu özellikleri ayarlamak için,`Metadata` mülkiyeti`Document` nesne. İşte bir örnek:

```csharp
// Özellikleri ayarla
pdfDocument.Metadata["xmp:CreateDate"] = DateTime.Now;
pdfDocument.Metadata["xmp:Nickname"] = "Nickname";
pdfDocument.Metadata["xmp:CustomProperty"] = "Custom Value";
```

Bu eğitimde, oluşturma tarihini geçerli tarih ve saate, takma adı "Takma Ad"a ve özel bir özelliği "Özel Değer" olarak ayarlıyoruz. Bu değerleri kendi değerlerinizle değiştirebilirsiniz.

## 4. Adım: PDF Dosyasını Kaydedin

 XMP meta veri özelliklerini ayarladıktan sonra, PDF dosyasını kaydetmeniz gerekir. Bunu yapmak için,`Save` yöntemi`Document` nesnesini seçin ve yolu güncellenmiş PDF dosyasını kaydetmek istediğiniz yere iletin.

```csharp
dataDir = dataDir + "SetXMPMetadata_out.pdf";
//Belgeyi kaydet
pdfDocument.Save(dataDir);
```

### Aspose.PDF for .NET kullanarak XMPMetadata Ayarı için Örnek Kaynak Kodu

İşte Aspose.PDF for .NET kullanarak XMPMetadata'yı ayarlamak için eksiksiz örnek kaynak kodu:

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Belgeyi aç
	Document pdfDocument = new Document(dataDir + "SetXMPMetadata.pdf");

	// Özellikleri ayarla
	pdfDocument.Metadata["xmp:CreateDate"] = DateTime.Now;
	pdfDocument.Metadata["xmp:Nickname"] = "Nickname";
	pdfDocument.Metadata["xmp:CustomProperty"] = "Custom Value";

	dataDir = dataDir + "SetXMPMetadata_out.pdf";
	//Belgeyi kaydet
	pdfDocument.Save(dataDir);
	
	Console.WriteLine("\nXMP metadata in a pdf file setup successfully.\nFile saved at " + dataDir);

```
