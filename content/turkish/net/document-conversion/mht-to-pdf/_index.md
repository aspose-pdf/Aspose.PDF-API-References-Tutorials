---
title: MHT'den PDF'ye
linktitle: MHT'den PDF'ye
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak MHT'yi PDF'ye dönüştürmek için adım adım kılavuz.
type: docs
weight: 70
url: /tr/net/document-conversion/mht-to-pdf/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak bir MHT dosyasını PDF'ye dönüştürme sürecinde size rehberlik edeceğiz. MHT (MIME HTML), resimler ve ilgili içerik de dahil olmak üzere bir web sayfasının tamamını kaydetmek için kullanılan bir formattır. Aşağıdaki adımları takip ederek MHT dosyalarını PDF formatına dönüştürebileceksiniz.

## Önkoşullar
Başlamadan önce aşağıdaki önkoşulları karşıladığınızdan emin olun:

- C# programlama dili hakkında temel bilgiler.
- Sisteminizde yüklü olan .NET için Aspose.PDF kütüphanesi.
- Visual Studio gibi bir geliştirme ortamı.

## Adım 1: MHT dosyasını yükleme
Bu adımda Aspose.PDF for .NET'i kullanarak MHT dosyasını yükleyeceğiz. Aşağıdaki kodu izleyin:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

MhtLoadOptions options = new MhtLoadOptions();

// Belgeyi yükleyin
Document document = new Document(dataDir + "test.mht", options);
```

 Değiştirdiğinizden emin olun`"YOUR DOCUMENTS DIRECTORY"` MHT dosyanızın bulunduğu gerçek dizinle.

## Adım 2: MHT'den PDF'ye dönüştürme
MHT dosyasını yükledikten sonra PDF'ye dönüştürme işlemine geçebiliriz. Aşağıdaki kodu kullanın:

```csharp
// Çıktıyı PDF belgesi olarak kaydedin
document.Save(dataDir + "MHTToPDF_out.pdf");
```

 Yukarıdaki kod MHT dosyasını PDF formatına dönüştürür ve dosya adı olarak kaydeder.`"MHTToPDF_out.pdf"`.

### Aspose.PDF for .NET kullanarak MHT'den PDF'ye dönüştürme için örnek kaynak kodu

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
Bu eğitimde, Aspose.PDF for .NET kullanarak bir MHT dosyasını PDF'ye dönüştürme işlemini adım adım ele aldık. Yukarıda özetlenen talimatları izleyerek artık MHT dosyalarını PDF formatına dönüştürebilmelisiniz. Bu özellik, web sayfalarının tamamını PDF belgelerine dönüştürmeniz gerektiğinde yararlı olabilir.

### SSS'ler

#### S: Aspose.PDF for .NET, gömülü görüntüler içeren MHT dosyalarının PDF'ye dönüştürülmesini destekliyor mu?

C: Evet, Aspose.PDF for .NET, gömülü görüntüler içeren MHT dosyalarının PDF'ye dönüştürülmesini destekler. Kitaplık, resimler ve ilgili kaynaklar da dahil olmak üzere tüm web sayfası içeriğini işleyebilir ve bunu bir PDF belgesine dönüştürebilir.

#### S: MHT'den PDF'ye dönüştürme işlemi sırasında PDF çıktısını özelleştirebilir miyim?

C: Evet, Aspose.PDF for .NET, MHT'den PDF'ye dönüştürme işlemi sırasında PDF çıktısını özelleştirmek için çeşitli seçenekler sunar. Ortaya çıkan PDF belgesinin görünümünü kontrol etmek için sayfa boyutu, yönlendirme, kenar boşlukları ve daha fazlası gibi özellikleri ayarlayabilirsiniz.

#### S: Aspose.PDF for .NET, PDF çıktısındaki orijinal MHT dosyasındaki köprüleri ve formatlamayı koruyor mu?

C: Evet, Aspose.PDF for .NET, PDF çıktısındaki orijinal MHT dosyasındaki köprüleri ve formatlamayı korur. Kitaplık, dönüştürülen PDF'nin kaynak MHT dosyasıyla aynı düzeni ve içeriği korumasını sağlar.

#### S: Aspose.PDF for .NET'i kullanarak birden fazla MHT dosyasını ayrı PDF belgelerine dönüştürebilir miyim?

C: Evet, Aspose.PDF for .NET'i kullanarak birden fazla MHT dosyasını ayrı PDF belgelerine dönüştürebilirsiniz. Her MHT dosyasını yükleyin ve benzersiz bir dosya adıyla ayrı bir PDF belgesi olarak kaydedin.