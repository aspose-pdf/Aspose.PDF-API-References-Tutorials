---
title: Etiketli Görüntü ile PDF Oluşturun
linktitle: Etiketli Görüntü ile PDF Oluşturun
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak etiketli görüntü ile PDF oluşturmak için adım adım kılavuz.
type: docs
weight: 40
url: /tr/net/programming-with-tagged-pdf/create-pdf-with-tagged-image/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak etiketli bir görüntü ile bir PDF belgesinin nasıl oluşturulacağına dair adım adım bir kılavuz sağlayacağız. Aspose.PDF, PDF belgelerini program aracılığıyla oluşturmanıza, değiştirmenize ve dönüştürmenize izin veren güçlü bir kitaplıktır. Aspose.PDF'nin etiketli içerik yapısı özelliklerini kullanarak, etiketli görselleri PDF belgenize ekleyebilirsiniz.

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

## 3. Adım: Etiketli bir görselle PDF belgesi oluşturma

Etiketli bir görüntü ile bir PDF belgesi oluşturmak için aşağıdaki kodu kullanın:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Creating a PDF with a tagged image");
taggedContent.SetLanguage("fr-FR");

IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Picture 1";
figure1.SetTag("Fig");
figure1.SetImage(dataDir + @"aspose-logo.jpg");
```

Bu kod, boş bir PDF belgesi oluşturur ve Aspose.PDF tarafından sağlanan yöntemleri kullanarak etiketlenmiş bir görüntü ekler. Resim alternatif metin, başlık ve etiket ile belirtilir.

## 4. Adım: PDF Belgesini Kaydetme

PDF belgesini kaydetmek için aşağıdaki kodu kullanın:

```csharp
document.Save(dataDir + "PDFwithTaggedImage.pdf");
```

Bu kod, etiketli görüntü içeren PDF belgesini belirtilen bir dosyaya kaydeder.

### Aspose.PDF for .NET kullanarak Etiketli Görüntü ile PDF Oluşturma için örnek kaynak kodu 
```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("CreatePDFwithTaggedImage");
taggedContent.SetLanguage("en-US");
IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Image 1";
figure1.SetTag("Fig");
// 300 DPI çözünürlüklü görüntü ekleyin (varsayılan olarak)
figure1.SetImage(dataDir + @"aspose-logo.jpg");
// PDF Belgesini Kaydet
document.Save(dataDir + "PDFwithTaggedImage.pdf");

```

## Çözüm

Bu öğreticide, Aspose.PDF for .NET kullanarak etiketli bir görüntü ile PDF belgesi oluşturmayı öğrendiniz. Etiketli görüntüler, PDF belgenize ek, yapılandırılmış bilgiler ekler.
