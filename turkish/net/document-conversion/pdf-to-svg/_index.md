---
title: PDF'den SVG'ye
linktitle: PDF'den SVG'ye
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF'yi SVG'ye dönüştürmek için adım adım kılavuz.
type: docs
weight: 180
url: /tr/net/document-conversion/pdf-to-svg/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF'yi SVG formatına dönüştürme sürecinde size yol göstereceğiz. SVG (Scalable Vector Graphics), grafiklerin kalitesini ve ölçeklemesini korumaya yardımcı olan bir vektör görüntü formatıdır. Aşağıdaki adımları izleyerek, bir PDF dosyasını SVG formatına dönüştürebileceksiniz.

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

## 2. Adım: SVG kaydetme seçeneklerinin somutlaştırılması
PDF dosyasını yükledikten sonra, SVG kaydetme seçeneklerini başlatacağız. Aşağıdaki kodu kullanın:

```csharp
// Bir SvgSaveOptions nesnesinin örneğini oluşturun
SvgSaveOptions saveOptions = new SvgSaveOptions();
// SVG görüntüsünü bir Zip arşivinde sıkıştırmayın
saveOptions.CompressOutputToZipArchive = false;
```

## 3. Adım: Ortaya çıkan SVG dosyasını kaydetme
Şimdi dönüştürülen PDF dosyasını SVG formatında kaydedeceğiz. Aşağıdaki kodu kullanın:

```csharp
// Çıktıyı SVG dosyalarına kaydet
doc.Save(dataDir + "PDFToSVG_out.svg", saveOptions);
```

 Yukarıdaki kod, dönüştürülen PDF'yi dosya adıyla SVG formatına kaydeder`"PDFToSVG_out.svg"`.

### Aspose.PDF for .NET kullanarak PDF to SVG için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// PDF belgesini yükle
Document doc = new Document(dataDir + "input.pdf");
// Bir SvgSaveOptions nesnesinin örneğini oluşturun
SvgSaveOptions saveOptions = new SvgSaveOptions();
// SVG görüntüsünü Zip arşivine sıkıştırma
saveOptions.CompressOutputToZipArchive = false;
// Çıktıyı SVG dosyalarına kaydedin
doc.Save(dataDir + "PDFToSVG_out.svg", saveOptions);
```

## Çözüm
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF dosyasını SVG formatına dönüştürme sürecini adım adım ele aldık. Yukarıda özetlenen talimatları izleyerek, artık bir PDF dosyasını SVG formatına dönüştürebilmelisiniz. Bu özellik, vektör görüntülere dönüştürürken grafik kalitesini ve ölçeklendirmeyi korumak istediğinizde kullanışlıdır.

### SSS

#### S: PDF'den SVG'ye dönüştürme sırasında ortaya çıkan SVG dosyalarının çözünürlüğünü veya boyutunu kontrol edebilir miyim?

 C: Evet, Aspose.PDF for .NET kullanarak PDF'den SVG'ye dönüştürme sırasında ortaya çıkan SVG dosyalarının çözünürlüğünü veya boyutunu kontrol edebilirsiniz. bu`SvgSaveOptions` sınıf gibi özellikler sağlar`PageSavingCallback` Ve`SaveFormat` Çözünürlüğü, sayfa boyutunu veya SVG çıktısıyla ilgili diğer parametreleri ayarlamanıza izin verir. SVG dosyalarının kalitesini ve boyutunu kontrol etmek için bu seçenekleri gereksinimlerinize göre özelleştirebilirsiniz.

#### S: Aspose.PDF for .NET, şifreli veya parola korumalı PDF'leri SVG'ye dönüştürmeyi destekliyor mu?

C: Evet, Aspose.PDF for .NET, şifreli veya parola korumalı PDF'lerin SVG formatına dönüştürülmesini destekler. Parola korumalı bir PDF yüklediğinizde, parolayı`Document` sınıf yapıcı veya ayarlayarak`Password` özelliği PDF'i yüklemeden önce. Aspose.PDF for .NET, PDF'den SVG'ye dönüştürme işlemi sırasında şifre çözme işlemini gerçekleştirir.

#### S: Tüm belge yerine PDF'nin yalnızca belirli sayfalarını SVG'ye dönüştürebilir miyim?

C: Evet, Aspose.PDF for .NET kullanarak belgenin tamamı yerine yalnızca belirli sayfalarını SVG'ye dönüştürebilirsiniz. Çıktıyı SVG dosyaları olarak kaydetmeden önce, dönüştürmek istediğiniz sayfaları sayfa numaralarını veya aralıklarını belirterek seçebilirsiniz. Bu şekilde, yalnızca istediğiniz sayfaları ayıklayabilir ve PDF'den SVG formatına dönüştürebilirsiniz.

#### S: Aspose.PDF for .NET, SVG'nin tüm sürümleriyle uyumlu mu?

Y: Aspose.PDF for .NET, SVG 1.1 (Ölçeklenebilir Vektör Grafikleri) özelliği ile uyumlu olacak şekilde tasarlanmıştır. SVG 1.1 standardına göre SVG dosyaları oluşturmayı destekler. Ancak, SVG 2.0'ın SVG spesifikasyonunun en son sürümü olarak tanıtıldığını lütfen unutmayın. Aspose.PDF for .NET birçok durumda SVG 2.0 ile iyi çalışsa da, kullanmayı düşündüğünüz belirli SVG özellikleriyle uyumluluğu ve olası sınırlamaları kontrol etmeniz önerilir.