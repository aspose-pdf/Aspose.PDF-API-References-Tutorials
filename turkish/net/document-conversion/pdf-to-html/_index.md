---
title: PDF'den HTML'ye
linktitle: PDF'den HTML'ye
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF'yi HTML'ye dönüştürmek için adım adım kılavuz.
type: docs
weight: 130
url: /tr/net/document-conversion/pdf-to-html/
---

Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF dosyasını HTML formatına dönüştürme sürecinde size yol göstereceğiz. PDF formatı genellikle belgeleri görüntülemek ve paylaşmak için kullanılırken, HTML formatı web sayfaları oluşturmak için kullanılır. Aşağıdaki adımları izleyerek, PDF dosyalarını HTML formatına dönüştürebileceksiniz.

## Önkoşullar
Başlamadan önce, aşağıdaki ön koşulları karşıladığınızdan emin olun:

- C# programlama dili hakkında temel bilgi.
- Sisteminizde kurulu .NET için Aspose.PDF kitaplığı.
- Visual Studio gibi bir geliştirme ortamı.

## 1. Adım: Kaynak PDF belgesini açma
Bu adımda, Aspose.PDF for .NET kullanarak kaynak PDF dosyasını açacağız. Aşağıdaki kodu izleyin:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Kaynak PDF belgesini aç
Document pdfDocument = new Document(dataDir + "PDFToHTML.pdf");
```

 değiştirdiğinizden emin olun`"YOUR DOCUMENTS DIRECTORY"` PDF dosyanızın bulunduğu gerçek dizinle.

## 2. Adım: PDF'den HTML'ye dönüştürme
PDF dosyasını açtıktan sonra HTML formatına dönüştürme işlemine geçebiliriz. Aşağıdaki kodu kullanın:

```csharp
// Dosyayı HTML biçiminde kaydedin
pdfDocument.Save(dataDir + "output_out.html", SaveFormat.Html);
```

 Yukarıdaki kod, PDF dosyasını HTML formatına dönüştürür ve şu şekilde kaydeder:`"output_out.html"` dosya.

 Yer değiştirmek`"YOUR DOCUMENTS DIRECTORY"`Çıktı HTML dosyasını kaydetmek istediğiniz istediğiniz dizin ile.

### Aspose.Words for .NET kullanarak PDF'den HTML'ye dönüştürme için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Kaynak PDF belgesini aç
Document pdfDocument = new Document(dataDir + "PDFToHTML.pdf");

//Dosyayı MS belge biçiminde kaydedin
pdfDocument.Save(dataDir + "output_out.html", SaveFormat.Html);
```

## Çözüm
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF dosyasını HTML formatına dönüştürme sürecini adım adım ele aldık. Yukarıda özetlenen talimatları izleyerek, artık PDF dosyalarını HTML biçimine dönüştürebilmelisiniz. Bu özellik, PDF içeriğini web sayfalarına veya HTML formatını destekleyen diğer uygulamalara gömmek istediğinizde kullanışlıdır.

