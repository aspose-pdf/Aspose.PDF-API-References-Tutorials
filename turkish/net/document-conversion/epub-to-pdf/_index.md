---
title: EPUB'u PDF'ye dönüştürme
linktitle: EPUB'u PDF'ye dönüştürme
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak EPUB'u PDF'ye dönüştürmek için adım adım kılavuz.
type: docs
weight: 30
url: /tr/net/document-conversion/epub-to-pdf/
---

Bu eğitimde, Aspose.PDF kitaplığını .NET kullanarak bir EPUB dosyasını PDF'ye dönüştürme sürecinde size rehberlik edeceğiz. EPUB (Elektronik Yayın) elektronik kitaplar için yaygın olarak kullanılan bir formatken, PDF (Taşınabilir Belge Formatı) bir belge değişim standardıdır. Aşağıda verilen adımları izleyerek, EPUB dosyalarını zahmetsizce PDF formatına dönüştürebileceksiniz.

## Önkoşullar
Başlamadan önce, aşağıdaki ön koşulları karşıladığınızdan emin olun:

- C# programlama dili hakkında temel bilgi.
- Sisteminizde kurulu .NET için Aspose.PDF kitaplığı.
- Visual Studio gibi bir geliştirme ortamı.

## 1. Adım: EPUB dosyasını yükleyin
Bu adımda, EPUB dosyasını Aspose.PDF for .NET kullanarak yükleyeceğiz. Aşağıdaki kodu izleyin:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// EPUB yükleme seçeneğini kullanarak LoadOption nesnesini somutlaştırın
EpubLoadOptions epubload = new EpubLoadOptions();

// Belge nesnesi oluşturma
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document(dataDir + "EPUBToPDF.epub", epubload);
```

 değiştirdiğinizden emin olun`"YOUR DOCUMENTS DIRECTORY"` EPUB dosyanızın bulunduğu gerçek dizinle.

## 2. Adım: EPUB'dan PDF'e dönüştürme
Artık EPUB dosyasını yüklediğimize göre, PDF'ye dönüştürme işlemine geçebiliriz. Aşağıdaki kodu kullanın:

```csharp
// Ortaya çıkan PDF belgesini kaydedin
pdf. Save(dataDir + "EPUBToPDF_out.pdf");
```

 Yukarıdaki kod, PDF biçiminde yüklenen EP dosyasını EPUB'a dönüştürür ve dosya adı olarak kaydeder`"EPUBToPDF_out.pdf"`. Çıktı PDF dosyası için doğru yolu ve dosya adını sağladığınızdan emin olun.


 Yer değiştirmek`"YOUR DOCUMENTS DIRECTORY"` Çıktı PDF dosyasını kaydetmek istediğiniz istediğiniz dizinle.

### Aspose.Words for .NET kullanarak EPUB'dan PDF'e örnek kaynak kodu

```csharp
try
{
	
	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// EPUB yükleme seçeneğini kullanarak LoadOption nesnesini oluşturun
	EpubLoadOptions epubload = new EpubLoadOptions();

	// Belge nesnesi oluştur
	Aspose.Pdf.Document pdf = new Aspose.Pdf.Document(dataDir + "EPUBToPDF.epub", epubload);

	// Ortaya çıkan PDF belgesini kaydedin
	pdf.Save(dataDir + "EPUBToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}

```

## Çözüm
Bu eğitimde, Aspose.PDF kitaplığını .NET kullanarak bir EPUB dosyasını PDF'ye dönüştürme sürecini adım adım ele aldık. Yukarıda özetlenen talimatları izleyerek, artık EPUB dosyalarını zahmetsizce PDF formatına dönüştürebilmelisiniz. Bu dönüştürme, belgelerinizi paylaşmak, yazdırmak ve arşivlemek için olanaklar sunar.

