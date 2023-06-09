---
title: Açık İşlemi Kaldır
linktitle: Açık İşlemi Kaldır
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF'den açık eylemi nasıl kaldıracağınızı öğrenin.
type: docs
weight: 80
url: /tr/net/programming-with-links-and-actions/remove-open-action/
---

Bu adım adım kılavuz ile Aspose.PDF for .NET kullanarak bir PDF dosyasından açık eylemi nasıl kaldıracağınızı öğrenin.

## 1. Adım: Ortamı ayarlama

Geliştirme ortamınızı bir C# projesi ve uygun Aspose.PDF referansları ile kurduğunuzdan emin olun.

## 2. Adım: PDF dosyasını yükleme

Belgelerinizin dizin yolunu ayarlayın ve aşağıdaki kodu kullanarak PDF dosyasını yükleyin:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// belgeyi aç
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
```

## 3. Adım: Açık eylemi silme

 ayarlayarak açık eylemi belgeden kaldırın.`OpenAction` null için özellik:

```csharp
document. OpenAction = null;
```

## 4. Adım: Güncellenen belgeyi kaydedin

 kullanarak güncellenen belgeyi kaydedin.`Save` yöntem:

```csharp
dataDir = dataDir + "RemoveOpenAction_out.pdf";
document. Save(dataDir);
```

## 5. Adım: Sonucun görüntülenmesi

Açma eyleminin başarıyla kaldırıldığını belirten bir mesaj görüntüleyin ve kaydedilen dosyanın konumunu belirtin:

```csharp
Console.WriteLine("\nOpen action deleted successfully.\nFile saved to location: " + dataDir);
```

### Aspose.PDF for .NET kullanarak Open Action'ı Kaldır için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
// Belge açma eylemini kaldır
document.OpenAction = null;
dataDir = dataDir + "RemoveOpenAction_out.pdf";
// Güncellenen belgeyi kaydet
document.Save(dataDir);
Console.WriteLine("\nOpen action removed successfully.\nFile saved at " + dataDir); 
```

## Çözüm

Tebrikler! Artık Aspose.PDF for .NET kullanarak bir PDF'den açık eylemi nasıl kaldıracağınızı biliyorsunuz. Projelerinizdeki PDF dosyalarının özelliklerini ve davranışını özelleştirmek için bu bilgiyi kullanın.

Artık bu kılavuzu tamamladığınıza göre, bu kavramları kendi projelerinize uygulayabilir ve Aspose.PDF for .NET tarafından sunulan özellikleri daha fazla keşfedebilirsiniz.