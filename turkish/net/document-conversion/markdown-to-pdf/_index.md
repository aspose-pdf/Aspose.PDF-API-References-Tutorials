---
title: PDF'e İşaretleme
linktitle: PDF'e İşaretleme
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak Markdown'ı PDF'e dönüştürmek için adım adım kılavuz.
type: docs
weight: 60
url: /tr/net/document-conversion/markdown-to-pdf/
---

Bu eğitimde, Aspose.PDF for .NET kullanarak bir Markdown dosyasını PDF'ye dönüştürme sürecinde size yol göstereceğiz. Markdown, düz metni yapılandırılmış bir şekilde biçimlendirmek için kullanılan hafif bir biçimlendirme dilidir. Aşağıdaki adımları izleyerek Markdown dosyalarını PDF formatına dönüştürebileceksiniz.

## Önkoşullar
Başlamadan önce, aşağıdaki ön koşulları karşıladığınızdan emin olun:

- C# programlama dili hakkında temel bilgi.
- Sisteminizde kurulu .NET için Aspose.PDF kitaplığı.
- Visual Studio gibi bir geliştirme ortamı.

## 1. Adım: Markdown dosyasını yükleme
Bu adımda Aspose.PDF for .NET kullanarak Markdown dosyasını yükleyeceğiz. Aşağıdaki kodu izleyin:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Markdown belgesini aç
Document doc = new Document(dataDir + "sample.md", new MdLoadOptions());
```

 değiştirdiğinizden emin olun`"YOUR DOCUMENTS DIRECTORY"`Markdown dosyanızın bulunduğu gerçek dizinle.

## Adım 2: Markdown'dan PDF'e dönüştürme
Markdown dosyasını yükledikten sonra PDF'e dönüştürme işlemine geçebiliriz. Aşağıdaki kodu kullanın:

```csharp
// Belgeyi PDF biçiminde kaydedin
doc.Save(dataDir + "MarkdownToPDF.pdf");
```

 Yukarıdaki kod, Markdown dosyasını PDF formatına dönüştürür ve dosya adı olarak kaydeder.`"MarkdownToPDF.pdf"`.

### Aspose.Words for .NET kullanarak Markdown to PDF için örnek kaynak kodu


```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Markdown belgesini aç
Document doc = new Document(dataDir + "sample.md", new MdLoadOptions());
// Belgeyi PDF biçiminde kaydet
doc.Save(dataDir + "MarkdownToPDF.pdf");
```

## Çözüm
Bu eğitimde, Aspose.PDF for .NET kullanarak bir Markdown dosyasını PDF'ye dönüştürme sürecini adım adım ele aldık. Yukarıda özetlenen talimatları izleyerek, artık Markdown dosyalarını PDF formatına dönüştürebilmelisiniz. Bu özellik, Markdown içeriğinden PDF belgeleri oluşturmanız gerektiğinde yararlı olabilir.