---
title: Tüm Ekleri Sil
linktitle: Tüm Ekleri Sil
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF dosyasındaki tüm ekleri nasıl kaldıracağınızı öğrenin. Kolay kullanım için adım adım kılavuz.
type: docs
weight: 20
url: /tr/net/programming-with-attachments/delete-all-attachments/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF dosyasındaki tüm ekleri kaldırmak için aşağıdaki C# kaynak kodunda adım adım yol göstereceğiz.

Başlamadan önce Aspose.PDF kitaplığını kurduğunuzdan ve geliştirme ortamınızı kurduğunuzdan emin olun. Ayrıca temel C# programlama bilgisine sahip olmak.

### 1. Adım: Belge Dizini Kurulumu

Sağlanan kaynak kodunda, ekleri kaldırmak istediğiniz PDF dosyasının bulunduğu dizini belirtmeniz gerekir. "dataDir" değişkenini istenen dizine değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### 2. Adım: Mevcut PDF belgesini açın

Mevcut PDF belgesini belirtilen yolu kullanarak açıyoruz.

```csharp
Document pdfDocument = new Document(dataDir + "DeleteAllAttachments.pdf");
```

### 3. Adım: Tüm ekleri kaldırın

Tüm ekleri belgeden kaldırıyoruz.

```csharp
pdfDocument.EmbeddedFiles.Delete();
```

### 4. Adım: Güncellenen Dosyayı Kaydedin

Son olarak güncellenmiş PDF dosyasını belirtilen dizine "DeleteAllAttachments_out.pdf" adıyla kaydediyoruz.

```csharp
pdfDocument.Save(dataDir + "DeleteAllAttachments_out.pdf");
```

### Aspose.PDF for .NET kullanarak Tüm Ekleri Sil için örnek kaynak kodu 

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "DeleteAllAttachments.pdf");
// Tüm ekleri sil
pdfDocument.EmbeddedFiles.Delete();
dataDir = dataDir + "DeleteAllAttachments_out.pdf";
// Güncellenen dosyayı kaydet
pdfDocument.Save(dataDir);
Console.WriteLine("\nAll attachments deleted successfully.\nFile saved at " + dataDir);

```

## Çözüm

Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF dosyasındaki tüm eklerin nasıl kaldırılacağını açıkladık. Artık tüm istenmeyen ekleri kaldırarak PDF belgelerinizi temizlemek için bu bilgiyi kullanabilirsiniz.
