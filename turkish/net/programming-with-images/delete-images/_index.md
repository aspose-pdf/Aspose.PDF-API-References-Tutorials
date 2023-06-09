---
title: Resimleri Sil
linktitle: Resimleri Sil
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile bir PDF dosyasındaki görüntüleri kolayca silin.
type: docs
weight: 110
url: /tr/net/programming-with-images/delete-images/
---

Bu kılavuz, Aspose.PDF for .NET kullanarak bir PDF dosyasından görüntülerin nasıl silineceğini adım adım gösterecek. Ortamınızı zaten kurduğunuzdan emin olun ve aşağıdaki adımları izleyin:

## 1. Adım: Belge dizinini tanımlayın

 Başlamadan önce, belgeler için doğru dizini ayarladığınızdan emin olun. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` PDF belgenizin bulunduğu dizinin yolunu içeren kodda.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: PDF belgesini açın

 Bu adımda, PDF belgesini kullanarak açacağız.`Document` Aspose.PDF sınıfı. Kullan`Document` yapıcı ve yolu PDF belgesine iletin.

```csharp
Document pdfDocument = new Document(dataDir + "DeleteImages.pdf");

```

## 3. Adım: Belirli bir resmi silin

 Bu adımda, belirli bir sayfadan belirli bir görüntüyü sileceğiz. Kullan`Delete` sayfa kaynağı yöntemi`Images` görüntüyü silmek için nesne. Aşağıdaki örnekte index 1 olan görseli ilk sayfadan siliyoruz.

```csharp
pdfDocument.Pages[1].Resources.Images.Delete(1);
```

## 4. Adım: Güncellenmiş PDF dosyasını kaydedin

 Güncellenmiş PDF dosyasını kullanarak kaydedin.`Save` yöntemi`pdfDocument` nesne. PDF dosyası için çıktı yolunu belirtin.

```csharp
dataDir = dataDir + "DeleteImages_out.pdf";
pdfDocument.Save(dataDir);
```

### Aspose.PDF for .NET kullanarak Resimleri Sil için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir+ "DeleteImages.pdf");
//Belirli bir görüntüyü silin
pdfDocument.Pages[1].Resources.Images.Delete(1);
dataDir = dataDir + "DeleteImages_out.pdf";
// Güncellenmiş PDF dosyasını kaydet
pdfDocument.Save(dataDir);
Console.WriteLine("\nImages deleted successfully.\nFile saved at " + dataDir); 
```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF dosyasındaki resimleri başarıyla sildiniz. Güncellenen PDF dosyası belirtilen dizine kaydedilir. Artık bu PDF dosyasını silinen resimler olmadan kullanabilirsiniz.