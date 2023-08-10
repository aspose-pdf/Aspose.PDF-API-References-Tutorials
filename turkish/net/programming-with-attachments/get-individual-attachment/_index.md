---
title: PDF Dosyasında Bireysel Ek Alın
linktitle: PDF Dosyasında Bireysel Ek Alın
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF dosyasında ayrı bir eki nasıl alacağınızı öğrenin.
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
//Parametre nesnesinin parametreleri içerip içermediğini kontrol edin
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

### PDF dosyasında bireysel ek almayla ilgili SSS

#### S: Bir PDF belgesinden ayrı bir ek almanın amacı nedir?

C: Bireysel bir ek almak, daha fazla analiz veya düzenleme için yararlı olabilecek belirli bir katıştırılmış dosyayı bir PDF'ye ayıklamanıza ve kaydetmenize olanak tanır.

#### S: PDF ile ilgili görevlerimde bu eğitimden nasıl yararlanabilirim?

C: Bu öğretici, Aspose.PDF for .NET kullanarak bir PDF belgesinden belirli bir eki almak ve kaydetmek için adım adım talimatlar ve C# kaynak kodu sağlar.

#### S: Bu öğreticiyi kullanarak hangi ek özelliklerine erişebilirim?

C: Belirli bir ekin adı, açıklaması, MIME türü, kontrol karması, oluşturma tarihi, değiştirilme tarihi ve boyutu gibi ek özelliklerine erişebilirsiniz.

#### S: İlk ek dışındaki ekleri almak için kodu değiştirebilir miyim?

 A: Kesinlikle, dizini ayarlayabilirsiniz (örn.`pdfDocument.EmbeddedFiles[1]`) PDF içindeki farklı dizinlerdeki ekleri almak için.

#### S: Alınan eki bir dosyaya nasıl kaydederim?

A: Bu öğretici, ekin içeriğini almak ve onu belirli bir ada sahip bir metin dosyasına kaydetmek için kod sağlar.

#### S: Ek bilgisindeki "Karmayı Kontrol Et" özelliğinin önemi nedir?

Y: "Karmayı Kontrol Et" özelliği, ekin bütünlüğünü doğrulamak için kullanılabilen ekin kontrol karma değerini temsil eder.

#### S: Bu bilgiyi, dosya türü gibi belirli ölçütlere sahip ekleri ayıklamak için genişletebilir miyim?

C: Evet, ekleri dosya türü veya diğer özellikler gibi belirli ölçütlere göre filtrelemek için kodu geliştirebilirsiniz.

#### S: Aspose.PDF for .NET, tek tek eklerin çıkarılması sürecini nasıl basitleştiriyor?

Y: Aspose.PDF for .NET, PDF belgeleri içindeki eklerin çıkarılmasını ve değiştirilmesini kolaylaştıran kullanıcı dostu bir API sağlar.

#### S: Bu eğitim, parola korumalı PDF dosyaları için de geçerli mi?

C: Evet, Aspose.PDF for .NET kullanarak parola korumalı PDF dosyalarından tek tek ekleri almak için benzer teknikleri uyarlayabilirsiniz.
