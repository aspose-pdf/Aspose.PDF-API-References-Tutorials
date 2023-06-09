---
title: Resmi Değiştir
linktitle: Resmi Değiştir
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesindeki bir görüntüyü değiştirmek için adım adım kılavuz.
type: docs
weight: 240
url: /tr/net/programming-with-images/replace-image/
---

Bu öğreticide, Aspose.PDF for .NET kullanarak bir PDF belgesindeki bir görüntüyü nasıl değiştireceğinizi size göstereceğiz. Bu işlemi kolayca gerçekleştirmek için aşağıdaki adımları izleyin.

## 1. Adım: Önkoşullar

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Visual Studio veya kurulu ve yapılandırılmış başka bir geliştirme ortamı.
- C# programlama dili hakkında temel bilgi.
- Aspose.PDF kitaplığı for .NET kurulu. Aspose resmi sitesinden indirebilirsiniz.

## 2. Adım: PDF belgesini yükleme

Başlamak için, PDF belgesini yüklemek üzere aşağıdaki kodu kullanın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// belgeyi aç
Document pdfDocument = new Document(dataDir + "ReplaceImage.pdf");
```

PDF belgenize giden doğru yolu sağladığınızdan emin olun.

## 3. Adım: Belirli bir görüntünün değiştirilmesi

PDF belgesindeki belirli bir görüntüyü değiştirmek için aşağıdaki kodu kullanın:

```csharp
// Belirli bir resmi değiştir
pdfDocument.Pages[1].Resources.Images.Replace(1, new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open));
```

Bu örnekte, PDF belgesinin 1. sayfasında bulunan görüntüyü değiştiriyoruz. Kullanmak istediğiniz yeni görüntünün doğru yolunu sağladığınızdan emin olun.

## 4. Adım: Güncellenmiş PDF dosyasını kaydetme

Görüntü değiştirmeyi gerçekleştirdikten sonra, aşağıdaki kodu kullanarak güncellenmiş PDF dosyasını kaydedin:

```csharp
dataDir = dataDir + "ReplaceImage_out.pdf";
// Güncellenmiş PDF dosyasını kaydedin
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage replaced successfully.\nFile saved as: " + dataDir);
```

Güncellenmiş PDF dosyası için istenen yolu ve dosya adını sağladığınızdan emin olun.

### Aspose.PDF for .NET kullanarak Görüntü Değiştir için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir+ "ReplaceImage.pdf");
// Belirli bir resmi değiştir
pdfDocument.Pages[1].Resources.Images.Replace(1, new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open));
dataDir = dataDir + "ReplaceImage_out.pdf";
// Güncellenmiş PDF dosyasını kaydet
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage replaced successfully.\nFile saved at " + dataDir); 
```

## Çözüm

Tebrikler! Aspose.PDF for .NET'i kullanarak bir PDF belgesindeki görüntüyü başarıyla değiştirdiniz. Artık PDF dosyalarındaki görüntüleri düzenlemek için bu yöntemi kendi projelerinize uygulayabilirsiniz.