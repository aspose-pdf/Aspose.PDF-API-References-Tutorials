---
title: Etiketli Metin ile PDF Oluşturun
linktitle: Etiketli Metin ile PDF Oluşturun
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak etiketli metin içeren bir PDF oluşturmak için adım adım kılavuz.
type: docs
weight: 50
url: /tr/net/programming-with-tagged-pdf/create-pdf-with-tagged-text/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak etiketli metin içeren bir PDF belgesinin nasıl oluşturulacağına dair adım adım bir kılavuz sağlayacağız. Aspose.PDF, PDF belgelerini program aracılığıyla oluşturmanıza, değiştirmenize ve dönüştürmenize izin veren güçlü bir kitaplıktır. Aspose.PDF'nin etiketli içerik yapısı özelliklerini kullanarak, etiketli metni PDF belgenize ekleyebilirsiniz.

## Önkoşullar

Başlamadan önce, aşağıdaki ön koşullara sahip olduğunuzdan emin olun:

1. .NET çerçevesiyle yüklenen Visual Studio.
2. .NET için Aspose.PDF kitaplığı.

## Adım 1: Proje Kurulumu

Başlamak için Visual Studio'da yeni bir proje oluşturun ve Aspose.PDF for .NET kitaplığına bir referans ekleyin. Kütüphaneyi Aspose resmi sitesinden indirebilir ve makinenize kurabilirsiniz.

## 2. Adım: Gerekli ad alanlarını içe aktarın

Aspose.PDF tarafından sağlanan sınıflara ve yöntemlere erişmek için gereken ad alanlarını C# kod dosyanıza aktarın:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## 3. Adım: Etiketli metin içeren PDF belgesini oluşturma

Etiketli metin içeren bir PDF belgesi oluşturmak için aşağıdaki kodu kullanın:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");

HeaderElement headerElement = taggedContent.CreateHeaderElement();
headerElement.ActualText = "Header 1";

ParagraphElement paragraphElement1 = taggedContent.CreateParagraphElement();
paragraphElement1.ActualText = "test1";

// Buraya daha fazla paragraf ekleyin

// PDF belgesini kaydedin
document.Save(dataDir + "PDFwithTagText.pdf");
```

Bu kod, boş bir PDF belgesi oluşturur ve Aspose.PDF tarafından sağlanan yöntemleri kullanarak etiketli metin ekler. Uygun yöntemleri kullanarak başlıklar ve paragraflar gibi diğer etiketli metin öğelerini ekleyebilirsiniz.

### Aspose.PDF for .NET kullanarak Etiketli Metin ile PDF Oluşturma için örnek kaynak kodu 
```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// PDF Belgesi Oluştur
Document document = new Document();
// TaggedPdf ile çalışmak için İçerik Alın
ITaggedContent taggedContent = document.TaggedContent;
// Documnet için Başlığı ve Dili Ayarlayın
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
// Metin Bloğu Düzeyinde Yapı Öğeleri Oluşturma
HeaderElement headerElement = taggedContent.CreateHeaderElement();
headerElement.ActualText = "Heading 1";
ParagraphElement paragraphElement1 = taggedContent.CreateParagraphElement();
paragraphElement1.ActualText = "test1";
ParagraphElement paragraphElement2 = taggedContent.CreateParagraphElement();
paragraphElement2.ActualText = "test 2";
ParagraphElement paragraphElement3 = taggedContent.CreateParagraphElement();
paragraphElement3.ActualText = "test 3";
ParagraphElement paragraphElement4 = taggedContent.CreateParagraphElement();
paragraphElement4.ActualText = "test 4";
ParagraphElement paragraphElement5 = taggedContent.CreateParagraphElement();
paragraphElement5.ActualText = "test 5";
ParagraphElement paragraphElement6 = taggedContent.CreateParagraphElement();
paragraphElement6.ActualText = "test 6";
ParagraphElement paragraphElement7 = taggedContent.CreateParagraphElement();
paragraphElement7.ActualText = "test 7";
// PDF Belgesini Kaydet
document.Save( dataDir + "PDFwithTaggedText.pdf");

```

## Çözüm

Bu öğreticide, Aspose.PDF for .NET kullanarak etiketli metin içeren bir PDF belgesi oluşturmayı öğrendiniz. Aspose.PDF'nin işaretli içerik yapısı özellikleri, metninizi daha iyi erişilebilirlik ve anlambilim için yapılandırmanıza ve düzenlemenize olanak tanır.
