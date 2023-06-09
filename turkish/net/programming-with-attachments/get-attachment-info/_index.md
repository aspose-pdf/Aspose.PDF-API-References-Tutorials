---
title: Ek Bilgilerini Alın
linktitle: Ek Bilgilerini Alın
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile bir PDF dosyasındaki belirli bir ek hakkında nasıl bilgi alacağınızı öğrenin. Adım adım rehber.
type: docs
weight: 50
url: /tr/net/programming-with-attachments/get-attachment-info/
---
Bu öğreticide, Aspose.PDF for .NET kullanarak bir PDF dosyasının belirli bir eki hakkında bilgi almak için aşağıdaki C# kaynak kodunda adım adım yol göstereceğiz.

Başlamadan önce Aspose.PDF kitaplığını kurduğunuzdan ve geliştirme ortamınızı kurduğunuzdan emin olun. Ayrıca temel C# programlama bilgisine sahip olmak.

### 1. Adım: Belge Dizini Kurulumu

Sağlanan kaynak kodunda, ek bilgilerini almak istediğiniz PDF dosyasının bulunduğu dizini belirtmeniz gerekir. "dataDir" değişkenini istenen dizine değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### 2. Adım: Mevcut PDF belgesini açın

Mevcut PDF belgesini belirtilen yolu kullanarak açıyoruz.

```csharp
Document pdfDocument = new Document(dataDir + "GetAttachmentInfo.pdf");
```

### 3. Adım: Belirli Bir Ekin Elde Edilmesi

Belgenin ekler koleksiyonundan belirli bir eki alıyoruz. Bu örnekte, dizin 1'i kullanarak ilk eki alıyoruz.

```csharp
FileSpecification fileSpecification = pdfDocument.EmbeddedFiles[1];
```

### 4. Adım: Dosya Özelliklerini Alın

Ad, açıklama, MIME türü, kontrol karması, oluşturulma tarihi, değiştirilme tarihi ve boyut gibi ek özelliklerini görüntüleriz.

```csharp
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("MIME Type: {0}", fileSpecification.MIMEType);

// Nesne parametrelerinin ek bilgi içerip içermediğini kontrol edin
if (fileSpecification.Params != null)
{
Console.WriteLine("Check Hash: {0}", fileSpecification.Params.CheckSum);
Console.WriteLine("Creation date: {0}", fileSpecification.Params.CreationDate);
Console.WriteLine("Modified date: {0}", fileSpecification.Params.ModDate);
Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}
```

### Aspose.PDF for .NET kullanarak Ek Bilgilerini Al için örnek kaynak kodu
 
```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "GetAttachmentInfo.pdf");
// Belirli gömülü dosyayı al
FileSpecification fileSpecification = pdfDocument.EmbeddedFiles[1];
// Dosya özelliklerini al
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("Mime Type: {0}", fileSpecification.MIMEType);
// Parametre nesnesinin parametreleri içerip içermediğini kontrol edin
if (fileSpecification.Params != null)
{
	Console.WriteLine("CheckSum: {0}",
	fileSpecification.Params.CheckSum);
	Console.WriteLine("Creation Date: {0}",
	fileSpecification.Params.CreationDate);
	Console.WriteLine("Modification Date: {0}",
	fileSpecification.Params.ModDate);
	Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}

```

## Çözüm

Bu eğitimde, Aspose.PDF for .NET kullanılarak bir PDF dosyasının belirli bir eki hakkında nasıl bilgi alınacağını açıkladık. Artık bu bilgiyi PDF dosyalarınızdan ek bilgileri ayıklamak ve görüntülemek için kullanabilirsiniz.
