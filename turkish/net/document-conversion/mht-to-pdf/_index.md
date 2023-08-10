---
title: MHT'den PDF'ye
linktitle: MHT'den PDF'ye
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak MHT'yi PDF'ye dönüştürmek için adım adım kılavuz.
type: docs
weight: 70
url: /tr/net/document-conversion/mht-to-pdf/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak bir MHT dosyasını PDF'ye dönüştürme sürecinde size rehberlik edeceğiz. MHT (MIME HTML), resimler ve ilişkili içerik dahil olmak üzere eksiksiz bir web sayfasını kaydetmek için kullanılan bir biçimdir. Aşağıdaki adımları izleyerek MHT dosyalarını PDF formatına dönüştürebileceksiniz.

## Önkoşullar
Başlamadan önce, aşağıdaki ön koşulları karşıladığınızdan emin olun:

- C# programlama dili hakkında temel bilgi.
- Sisteminizde kurulu .NET için Aspose.PDF kitaplığı.
- Visual Studio gibi bir geliştirme ortamı.

## 1. Adım: MHT dosyasını yükleme
Bu adımda Aspose.PDF for .NET kullanarak MHT dosyasını yükleyeceğiz. Aşağıdaki kodu izleyin:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

MhtLoadOptions options = new MhtLoadOptions();

// belgeyi yükle
Document document = new Document(dataDir + "test.mht", options);
```

 değiştirdiğinizden emin olun`"YOUR DOCUMENTS DIRECTORY"` MHT dosyanızın bulunduğu gerçek dizinle.

## 2. Adım: MHT'den PDF'e dönüştürme
MHT dosyasını yükledikten sonra PDF'e dönüştürme işlemine geçebiliriz. Aşağıdaki kodu kullanın:

```csharp
// Çıktıyı bir PDF belgesi olarak kaydedin
document.Save(dataDir + "MHTToPDF_out.pdf");
```

 Yukarıdaki kod, MHT dosyasını PDF formatına dönüştürür ve dosya adı olarak kaydeder.`"MHTToPDF_out.pdf"`.

### Aspose.PDF for .NET kullanılarak MHT'den PDF'e dönüştürme için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
MhtLoadOptions options = new MhtLoadOptions();
// Belgeyi yükle
Document document = new Document(dataDir  + "test.mht", options);
// Çıktıyı PDF belgesi olarak kaydedin
document.Save(dataDir + "MHTToPDF_out.pdf");
```

## Çözüm
Bu eğitimde, Aspose.PDF for .NET kullanarak bir MHT dosyasını PDF'ye dönüştürme sürecini adım adım ele aldık. Yukarıda özetlenen talimatları izleyerek, artık MHT dosyalarını PDF formatına dönüştürebilmelisiniz. Bu özellik, tüm web sayfalarını PDF belgelerine dönüştürmeniz gerektiğinde yararlı olabilir.

### SSS

#### S: Aspose.PDF for .NET, gömülü görüntüler içeren MHT dosyalarının PDF'ye dönüştürülmesini destekliyor mu?

C: Evet, Aspose.PDF for .NET, gömülü görüntüler içeren MHT dosyalarının PDF'ye dönüştürülmesini destekler. Kitaplık, resimler ve ilgili kaynaklar da dahil olmak üzere tüm web sayfası içeriğini işleyebilir ve bunu bir PDF belgesine dönüştürebilir.

#### S: MHT'den PDF'e dönüştürme işlemi sırasında PDF çıktısını özelleştirebilir miyim?

C: Evet, Aspose.PDF for .NET, MHT'den PDF'e dönüştürme işlemi sırasında PDF çıktısını özelleştirmek için çeşitli seçenekler sunar. Ortaya çıkan PDF belgesinin görünümünü kontrol etmek için sayfa boyutu, yönlendirme, kenar boşlukları ve daha fazlası gibi özellikleri ayarlayabilirsiniz.

#### S: Aspose.PDF for .NET, PDF çıktısında orijinal MHT dosyasındaki köprüleri ve biçimlendirmeyi koruyor mu?

C: Evet, Aspose.PDF for .NET, PDF çıktısında orijinal MHT dosyasındaki köprüleri ve biçimlendirmeyi korur. Kitaplık, dönüştürülen PDF'nin kaynak MHT dosyasıyla aynı düzeni ve içeriği korumasını sağlar.

#### S: Aspose.PDF for .NET kullanarak birden çok MHT dosyasını ayrı PDF belgelerine dönüştürebilir miyim?

C: Evet, Aspose.PDF for .NET kullanarak birden çok MHT dosyasını ayrı PDF belgelerine dönüştürebilirsiniz. Her bir MHT dosyasını yükleyin ve benzersiz bir dosya adına sahip ayrı bir PDF belgesi olarak kaydedin.