---
title: Ek Ekle
linktitle: Ek Ekle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyalarınıza nasıl ek ekleyeceğinizi öğrenin. Kolay kullanım için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-attachments/add-attachment/
---

Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF dosyasına ek eklemek için aşağıdaki C# kaynak kodunda adım adım yol göstereceğiz.

Başlamadan önce Aspose.PDF kitaplığını kurduğunuzdan ve geliştirme ortamınızı kurduğunuzdan emin olun. Ayrıca temel C# programlama bilgisine sahip olmak.

### 1. Adım: Belge Dizini Kurulumu

Sağlanan kaynak kodunda, eki eklemek istediğiniz PDF dosyasının bulunduğu dizini belirtmeniz gerekir. "dataDir" değişkenini istenen dizine değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### 2. Adım: Mevcut PDF belgesini açın

Mevcut PDF belgesini belirtilen yolu kullanarak açıyoruz.

```csharp
Document pdfDocument = new Document(dataDir + "AddAttachment.pdf");
```

### 3. Adım: Ek olarak eklenecek yeni dosyayı ayarlama

Ek olarak eklemek istediğimiz yeni dosyayı yapılandırıyoruz. Bu örnekte, "test.txt" adına ve "Örnek metin dosyası" açıklamasına sahip bir metin dosyası ekliyoruz.

```csharp
FileSpecification fileSpecification = new FileSpecification(dataDir + "test.txt", "Sample text file");
```

### 4. Adım: Eki belgenin ek koleksiyonuna ekleme

Eki, belgenin ekler koleksiyonuna ekliyoruz.

```csharp
pdfDocument.EmbeddedFiles.Add(fileSpecification);
```

### Adım 5: Yeni çıktı dosyasının kaydedilmesi

Son olarak ortaya çıkan yeni PDF dosyasını "AddAttachment_out.pdf" adıyla belirtilen dizine kaydediyoruz.

```csharp
pdfDocument.Save(dataDir + "AddAttachment_out.pdf");
```

### Aspose.PDF for .NET kullanarak Eklenti Ekleme için örnek kaynak kodu
 
```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "AddAttachment.pdf");
// Ek olarak eklenecek yeni dosyayı ayarlayın
FileSpecification fileSpecification = new FileSpecification(dataDir + "test.txt", "Sample text file");
// Belgenin ek koleksiyonuna ek ekleyin
pdfDocument.EmbeddedFiles.Add(fileSpecification);
dataDir = dataDir + "AddAttachment_out.pdf";
// Yeni çıktıyı kaydet
pdfDocument.Save(dataDir);
Console.WriteLine("\nSample text file attached successfully.\nFile saved at " + dataDir);

```

## Çözüm

Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF dosyasına nasıl ek ekleneceğini açıkladık. Artık bu bilgiyi PDF belgelerinize ek olarak ek dosyalar eklemek için kullanabilirsiniz.
