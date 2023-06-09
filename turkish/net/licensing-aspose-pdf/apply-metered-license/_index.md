---
title: Tarifeli Lisansı Yapılandır
linktitle: Tarifeli Lisansı Yapılandır
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile ölçülü bir lisans oluşturmak ve gelişmiş özelliklerden yararlanmak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/licensing-aspose-pdf/configure-metered-license/
---

Bu eğitimde, Aspose.PDF for .NET ile tarifeli bir lisansı nasıl kuracağınızı adım adım anlatacağız. Tarifeli lisans, Aspose.PDF'nin gelişmiş özelliklerini gerçek tüketiminize göre kullanmanızı sağlar.

### 1. Adım: Lisans Anahtarlarını Yapılandırma

Sağlanan kaynak kodunda, ölçülü lisansın genel ve özel anahtarlarını belirtmeniz gerekir. "*****" değerleri kendi anahtarlarınızla. Aspose'dan ölçülü bir lisans satın aldığınızda bu anahtarlar size sağlanacaktır.

```csharp
Aspose.Pdf.Metered metered = new Aspose.Pdf.Metered();
metered.SetMeteredKey("PUBLIC_KEY", "PRIVATE_KEY");
```

### 2. Adım: Belgeyi yükleme

 kullanarak PDF belgesini diskten yükleyin.`Document`Aspose.PDF sınıfı.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

### 3. Adım: Belge Sayfa Sayısını Alın

 Kullan`Count` mülkiyeti`Pages` koleksiyon, belgedeki toplam sayfa sayısını almak için.

```csharp
Console.WriteLine(doc.Pages.Count);
```

### Aspose.PDF for .NET kullanarak Ölçülü Lisansı Yapılandırmak için örnek kaynak kodu 

```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// ölçülü genel ve özel anahtarları ayarla
Aspose.Pdf.Metered metered = new Aspose.Pdf.Metered();
// setMeteredKey özelliğine erişin ve ortak ve özel anahtarları parametre olarak iletin
metered.SetMeteredKey("*****", "*****");
// Belgeyi diskten yükleyin.
Document doc = new Document(dataDir + "input.pdf");
//Belgenin sayfa sayısını alın
Console.WriteLine(doc.Pages.Count);

```

## Çözüm

Bu eğitimde, Aspose.PDF for .NET ile ölçülü bir lisansın nasıl kurulacağını açıkladık. Ölçülü bir lisans kullanarak, Aspose.PDF'nin gelişmiş özelliklerinden gerçek kullanımınıza göre yararlanabilirsiniz. Aspose.PDF'yi tüm özellikleriyle kullanmak için geçerli lisans anahtarları sağladığınızdan emin olun.
