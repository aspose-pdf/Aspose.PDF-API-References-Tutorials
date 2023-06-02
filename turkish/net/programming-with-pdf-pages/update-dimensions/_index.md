---
title: Boyutları Güncelle
linktitle: Boyutları Güncelle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF sayfa boyutlarını güncellemek için adım adım kılavuz. İhtiyaçlarınıza göre boyutları kontrol edin.
type: docs
weight: 150
url: /tr/net/programming-with-pdf-pages/update-dimensions/
---
Bu öğreticide, Aspose.PDF for .NET kullanarak bir PDF belgesindeki sayfa boyutlarını güncelleme sürecini adım adım anlatacağız. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği anlamanıza ve kendi projelerinizde uygulamanıza yardımcı olacak kapsamlı bir kılavuz sağlayacağız. Bu eğitimin sonunda, Aspose.PDF for .NET kullanarak bir PDF belgesindeki sayfa boyutlarını nasıl değiştireceğinizi öğreneceksiniz.

## Önkoşullar
Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- C# programlama dili hakkında temel bilgi
- Aspose.PDF for .NET geliştirme ortamınızda yüklü

## 1. Adım: Belge dizinini tanımlayın
Öncelikle, belgeler dizininize giden yolu ayarlamanız gerekir. Bu, düzenlenmiş PDF belgenizi kaydetmek istediğiniz konumdur. "BELGELER DİZİNİNİZİ" uygun yolla değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: PDF belgesini açın
 Ardından mevcut PDF belgesini kullanarak açabilirsiniz.`Document` Aspose.PDF sınıfı. Doğru belge yolunu belirttiğinizden emin olun.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## 3. Adım: Sayfa Koleksiyonunu Alın
 Artık PDF belgesinin sayfalar koleksiyonuna aşağıdakileri kullanarak erişebilirsiniz:`Pages` mülkiyeti`Document` sınıf.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## 4. Adım: Belirli bir sayfa edinin
Ardından, koleksiyondaki sayfanın dizinini kullanarak belgenin belirli bir sayfasını seçebilirsiniz. Bu örnekte ikinci sayfayı (dizin 1) kullanıyoruz.

```csharp
Page pdfPage = pageCollection[1];
```

## 5. Adım: Yeni sayfa boyutlarını tanımlayın
 Artık yeni sayfa boyutunu kullanarak ayarlayabilirsiniz.`SetPageSize()` yöntemi`Page` nesne. Bu örnekte, sayfa boyutlarını A4 (11,7 x 8,3 inç) olarak ayarlıyoruz ve puntoya çeviriyoruz (1 inç = 72 punto).

```csharp
pdfPage.SetPageSize(597.6, 842.4);
```

## 6. Adım: Güncellenen belgeyi kaydedin
Son olarak, güncellenmiş PDF belgesini kullanarak bir dosyaya kaydedebilirsiniz.`Save()` yöntemi`Document` sınıf. Doğru yolu ve dosya adını belirttiğinizden emin olun.

```csharp
dataDir = dataDir + "UpdateDimensions_out.pdf";
pdfDocument.Save(dataDir);
```

### Aspose.PDF for .NET kullanarak Update Dimensions için örnek kaynak kodu 

```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// Sayfa koleksiyonunu al
PageCollection pageCollection = pdfDocument.Pages;
// Belirli bir sayfayı al
Page pdfPage = pageCollection[1];
// Sayfa boyutunu A4 (11,7 x 8,3 inç) olarak ayarlayın ve Aspose.Pdf'te 1 inç = 72 punto
// Yani punto cinsinden A4 boyutları (842.4, 597.6) olacaktır.
pdfPage.SetPageSize(597.6, 842.4);
dataDir = dataDir + "UpdateDimensions_out.pdf";
// Güncellenen belgeyi kaydedin
pdfDocument.Save(dataDir);
System.Console.WriteLine("\nPage dimensions updated successfully.\nFile saved at " + dataDir);

```

## Çözüm
Bu öğreticide, Aspose.PDF for .NET kullanarak bir PDF belgesindeki sayfanın boyutlarının nasıl güncelleneceğini öğrendik. Bu adım adım kılavuzu izleyerek, bir PDF belgesindeki sayfanın boyutlarını gerektiği gibi kolayca değiştirebilirsiniz. Aspose.PDF, PDF dosyalarıyla çalışmak ve sayfa boyutlarını değiştirmek de dahil olmak üzere çeşitli manipülasyonlar gerçekleştirmek için güçlü ve esnek bir API sunar. Bu bilgiyle, özel ihtiyaçlarınızı karşılamak için PDF sayfalarınızın boyutlarını kontrol edebilir ve özelleştirebilirsiniz.
