---
title: Dosya Sıkıştırmayı Devre Dışı Bırak
linktitle: Dosya Sıkıştırmayı Devre Dışı Bırak
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile bir PDF dosyasında dosya sıkıştırmayı nasıl devre dışı bırakacağınızı öğrenin. Kolay kullanım için adım adım kılavuz.
type: docs
weight: 30
url: /tr/net/programming-with-attachments/disable-files-compression/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF'de dosya sıkıştırmayı devre dışı bırakmak için aşağıdaki C# kaynak kodunda adım adım yol göstereceğiz.

Başlamadan önce Aspose.PDF kitaplığını kurduğunuzdan ve geliştirme ortamınızı kurduğunuzdan emin olun. Ayrıca temel C# programlama bilgisine sahip olmak.

### 1. Adım: Belge Dizini Kurulumu

Sağlanan kaynak kodunda, dosya sıkıştırmayı devre dışı bırakmak istediğiniz PDF dosyasının bulunduğu dizini belirtmeniz gerekir. "dataDir" değişkenini istenen dizine değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### 2. Adım: Mevcut PDF belgesini açın

Mevcut PDF belgesini belirtilen yolu kullanarak açıyoruz.

```csharp
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
```

### 3. Adım: Ek olarak eklenecek yeni dosyayı ayarlama

Ek olarak eklemek istediğimiz yeni dosyayı yapılandırıyoruz. Bu örnekte, "test_out.txt" adına ve "Örnek metin dosyası" açıklamasına sahip bir metin dosyası ekliyoruz.

```csharp
FileSpecification fileSpecification = new FileSpecification("test_out.txt", "Sample text file");
```

### 4. Adım: Dosya Sıkıştırmayı Devre Dışı Bırakın

FileSpecification nesnesinin Encoding özelliğini FileEncoding.None olarak ayarlayarak dosya sıkıştırmayı devre dışı bırakıyoruz.

```csharp
fileSpecification.Encoding = FileEncoding.None;
```

### Adım 5: Ekin belgenin ekler koleksiyonuna eklenmesi

Eki, belgenin ekler koleksiyonuna ekliyoruz.

```csharp
pdfDocument.EmbeddedFiles.Add(fileSpecification);
```

### 6. Adım: Yeni çıktı dosyasını kaydedin

Son olarak ortaya çıkan yeni PDF dosyasını belirtilen dizine "DisableFilesCompression_out.pdf" adıyla kaydediyoruz.

```csharp
pdfDocument.Save(dataDir + "DisableFilesCompression_out.pdf");
```


### Aspose.PDF for .NET kullanarak Dosya Sıkıştırmayı Devre Dışı Bırakmak için örnek kaynak kodu 

```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
// Ek olarak eklenecek yeni dosyayı ayarlayın
FileSpecification fileSpecification = new FileSpecification("test_out.txt", "Sample text file");
// Encoding proparty'yi FileEncoding.None olarak ayarlayarak belirtin
fileSpecification.Encoding = FileEncoding.None;
// Belgenin ek koleksiyonuna ek ekleyin
pdfDocument.EmbeddedFiles.Add(fileSpecification);
dataDir = dataDir + "DisableFilesCompression_out.pdf";
// Yeni çıktıyı kaydet
pdfDocument.Save(dataDir);
Console.WriteLine("\nFile compression disabled successfully.\nFile saved at " + dataDir);

```

## Çözüm

Bu eğitimde, Aspose.PDF for .NET kullanılarak bir PDF'de dosya sıkıştırmanın nasıl devre dışı bırakılacağını açıkladık. Artık bu bilgiyi, ekli dosyaların bütünlüğünü sıkıştırma olmadan korumak için kullanabilirsiniz.