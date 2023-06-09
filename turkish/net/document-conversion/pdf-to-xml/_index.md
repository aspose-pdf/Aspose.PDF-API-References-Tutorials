---
title: PDF'den XML'e
linktitle: PDF'den XML'e
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF'yi XML'e dönüştürmek için adım adım kılavuz.
type: docs
weight: 210
url: /tr/net/document-conversion/pdf-to-xml/
---

Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF dosyasını XML formatına dönüştürme sürecinde size yol göstereceğiz. XML (eXtensible Markup Language), yapılandırılmış bilgileri depolamak ve değiş tokuş etmek için kullanılan bir veri formatıdır. Aşağıdaki adımları izleyerek, bir PDF dosyasını XML formatına dönüştürebileceksiniz.

## Önkoşullar
Başlamadan önce, aşağıdaki ön koşulları karşıladığınızdan emin olun:

- C# programlama dili hakkında temel bilgi.
- Sisteminizde kurulu .NET için Aspose.PDF kitaplığı.
- Visual Studio gibi bir geliştirme ortamı.

## 1. Adım: PDF belgesini yükleme
Bu adımda, Aspose.PDF for .NET kullanarak kaynak PDF dosyasını yükleyeceğiz. Aşağıdaki kodu izleyin:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// PDF belgesini yükleyin
Document doc = new Document(dataDir + "input.pdf");
```

 değiştirdiğinizden emin olun`"YOUR DOCUMENTS DIRECTORY"` PDF dosyanızın bulunduğu gerçek dizinle.

## 2. Adım: Ortaya çıkan XML dosyasını kaydetme
Şimdi dönüştürülen PDF dosyasını XML formatında kaydedeceğiz. Aşağıdaki kodu kullanın:

```csharp
// Çıktıyı XML olarak kaydet
doc.Save(dataDir + "PDFToXML_out.xml", SaveFormat.MobiXml);
```

 Yukarıdaki kod, dönüştürülen PDF dosyasını dosya adıyla XML biçiminde kaydeder.`"PDFToXML_out.xml"`.

### Aspose.PDF for .NET kullanarak PDF to XML için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";            
// Kaynak PDF dosyasını yükle
Document doc = new Document(dataDir + "input.pdf");
// Çıktıyı XML biçiminde kaydet
doc.Save(dataDir + "PDFToXML_out.xml", SaveFormat.MobiXml);
```

## Çözüm
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF dosyasını XML'e dönüştürme sürecini adım adım ele aldık. Yukarıda özetlenen talimatları izleyerek, artık bir PDF dosyasını XML formatına dönüştürebilmelisiniz. Bu özellik, bir PDF dosyasından yapılandırılmış içeriği ayıklamak ve daha sonra kullanmak üzere bir XML biçiminde işlemek istediğinizde kullanışlıdır.