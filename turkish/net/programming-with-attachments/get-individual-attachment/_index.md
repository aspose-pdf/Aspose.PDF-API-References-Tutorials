---
title: Bireysel Ek Alın
linktitle: Bireysel Ek Alın
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile bir PDF dosyasında ayrı bir eki nasıl alacağınızı öğrenin.
type: docs
weight: 60
url: /tr/net/programming-with-attachments/get-individual-attachment/
---
Bu öğreticide, Aspose.PDF for .NET kullanarak bir PDF dosyasının ayrı bir ekini almak için aşağıdaki C# kaynak kodunda size adım adım yol göstereceğiz.

Başlamadan önce Aspose.PDF kitaplığını kurduğunuzdan ve geliştirme ortamınızı kurduğunuzdan emin olun. Ayrıca temel C# programlama bilgisine sahip olmak.

### 1. Adım: Belge Dizini Kurulumu

Sağlanan kaynak kodunda, bağımsız eki almak istediğiniz PDF dosyasının bulunduğu dizini belirtmeniz gerekir. "dataDir" değişkenini istenen dizine değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### 2. Adım: Mevcut PDF belgesini açın

Mevcut PDF belgesini belirtilen yolu kullanarak açıyoruz.

```csharp
Document pdfDocument = new Document(dataDir + "GetIndividualAttachment.pdf");
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

### 5. Adım: Eki alın ve dosyaya kaydedin

Ekin içeriğini alıp bir metin dosyasına kaydediyoruz. Bu örnekte, dosya "test_out.txt" adıyla kaydedilmiştir.

```csharp
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + "test_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();
```

### Aspose.PDF for .NET kullanarak Get Individual Attachment için örnek kaynak kodu 

```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "GetIndividualAttachment.pdf");
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
// Eki alın ve dosyaya veya akışa yazın
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + "test_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();

```

## Çözüm

Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF dosyasından nasıl ayrı bir ek alınacağını açıkladık. Artık bu bilgiyi PDF dosyalarınızdan ekleri ayıklamak ve kaydetmek için kullanabilirsiniz.
