---
title: PDF'den SVG'ye
linktitle: PDF'den SVG'ye
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak PDF'yi SVG'ye dönüştürmek için adım adım kılavuz.
type: docs
weight: 180
url: /tr/net/document-conversion/pdf-to-svg/
---
Bu eğitimde, Aspose.PDF for .NET'i kullanarak bir PDF'yi SVG formatına dönüştürme sürecinde size yol göstereceğiz. SVG (Ölçeklenebilir Vektör Grafikleri), grafiklerin kalitesini ve ölçeklendirmesini korumaya yardımcı olan bir vektör görüntü formatıdır. Aşağıdaki adımları takip ederek bir PDF dosyasını SVG formatına dönüştürebileceksiniz.

## Önkoşullar
Başlamadan önce aşağıdaki önkoşulları karşıladığınızdan emin olun:

- C# programlama dili hakkında temel bilgiler.
- Sisteminizde yüklü olan .NET için Aspose.PDF kütüphanesi.
- Visual Studio gibi bir geliştirme ortamı.

## 1. Adım: PDF belgesini yükleme
Bu adımda kaynak PDF dosyasını Aspose.PDF for .NET kullanarak yükleyeceğiz. Aşağıdaki kodu izleyin:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// PDF belgesini yükleyin
Document doc = new Document(dataDir + "input.pdf");
```

 Değiştirdiğinizden emin olun`"YOUR DOCUMENTS DIRECTORY"` PDF dosyanızın bulunduğu gerçek dizinle.

## 2. Adım: SVG kaydetme seçeneklerinin somutlaştırılması
PDF dosyasını yükledikten sonra SVG kaydetme seçeneklerini başlatacağız. Aşağıdaki kodu kullanın:

```csharp
// Bir SvgSaveOptions nesnesinin örneğini oluşturma
SvgSaveOptions saveOptions = new SvgSaveOptions();
// Zip arşivindeki SVG görüntüsünü sıkıştırmayın
saveOptions.CompressOutputToZipArchive = false;
```

## 3. Adım: Ortaya çıkan SVG dosyasını kaydetme
Şimdi dönüştürülen PDF dosyasını SVG formatında kaydedeceğiz. Aşağıdaki kodu kullanın:

```csharp
// Çıktıyı SVG dosyalarına kaydedin
doc.Save(dataDir + "PDFToSVG_out.svg", saveOptions);
```

 Yukarıdaki kod, dönüştürülen PDF'yi dosya adıyla SVG formatına kaydeder.`"PDFToSVG_out.svg"`.

### Aspose.PDF for .NET kullanarak PDF'den SVG'ye dönüştürme için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// PDF belgesini yükle
Document doc = new Document(dataDir + "input.pdf");
// Bir SvgSaveOptions nesnesini örnekleyin
SvgSaveOptions saveOptions = new SvgSaveOptions();
// SVG görüntüsünü Zip arşivine sıkıştırmayın
saveOptions.CompressOutputToZipArchive = false;
// Çıktıyı SVG dosyalarına kaydedin
doc.Save(dataDir + "PDFToSVG_out.svg", saveOptions);
```

## Çözüm
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF dosyasını SVG formatına dönüştürme işlemini adım adım ele aldık. Yukarıda özetlenen talimatları izleyerek artık bir PDF dosyasını SVG formatına dönüştürebilmelisiniz. Bu özellik, vektör görüntülerine dönüştürürken grafik kalitesini ve ölçeklendirmeyi korumak istediğinizde kullanışlıdır.

### SSS'ler

#### S: PDF'den SVG'ye dönüştürme sırasında ortaya çıkan SVG dosyalarının çözünürlüğünü veya boyutunu kontrol edebilir miyim?

 C: Evet, Aspose.PDF for .NET'i kullanarak PDF'den SVG'ye dönüştürme sırasında ortaya çıkan SVG dosyalarının çözünürlüğünü veya boyutunu kontrol edebilirsiniz.`SvgSaveOptions` sınıf gibi özellikler sağlar`PageSavingCallback` Ve`SaveFormat` SVG çıkışıyla ilgili çözünürlüğü, sayfa boyutunu veya diğer parametreleri ayarlamanıza olanak tanır. SVG dosyalarının kalitesini ve boyutunu kontrol etmek için bu seçenekleri gereksinimlerinize göre özelleştirebilirsiniz.

#### S: Aspose.PDF for .NET, şifrelenmiş veya parola korumalı PDF'lerin SVG'ye dönüştürülmesini destekliyor mu?

C: Evet, Aspose.PDF for .NET, şifrelenmiş veya parola korumalı PDF'lerin SVG formatına dönüştürülmesini destekler. Parola korumalı bir PDF yüklediğinizde, parolayı kullanarak sağlayabilirsiniz.`Document` sınıf yapıcısı veya ayarlayarak`Password` PDF'yi yüklemeden önce özellik. Aspose.PDF for .NET, PDF'den SVG'ye dönüştürme işlemi sırasında şifre çözme işlemini gerçekleştirecektir.

#### S: Belgenin tamamı yerine PDF'nin yalnızca belirli sayfalarını SVG'ye dönüştürebilir miyim?

C: Evet, Aspose.PDF for .NET'i kullanarak belgenin tamamı yerine PDF'nin yalnızca belirli sayfalarını SVG'ye dönüştürebilirsiniz. Çıktıyı SVG dosyaları olarak kaydetmeden önce dönüştürmek istediğiniz sayfaları sayfa numaralarını veya aralıklarını belirterek seçebilirsiniz. Bu şekilde yalnızca istediğiniz sayfaları PDF'den SVG formatına çıkarabilir ve dönüştürebilirsiniz.

#### S: Aspose.PDF for .NET, SVG'nin tüm sürümleriyle uyumlu mudur?

C: Aspose.PDF for .NET, SVG 1.1 (Ölçeklenebilir Vektör Grafikleri) spesifikasyonuyla uyumlu olacak şekilde tasarlanmıştır. SVG 1.1 standardına göre SVG dosyalarının oluşturulmasını destekler. Ancak SVG 2.0'ın, SVG spesifikasyonunun en son sürümü olarak sunulduğunu lütfen unutmayın. Aspose.PDF for .NET birçok durumda hala SVG 2.0 ile iyi çalışabilse de, kullanmayı düşündüğünüz belirli SVG özellikleriyle uyumluluğu ve olası sınırlamaları kontrol etmeniz önerilir.