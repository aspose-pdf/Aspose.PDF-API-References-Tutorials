---
title: PDF Dosyasındaki Tüm Ekleri Alın
linktitle: PDF Dosyasındaki Tüm Ekleri Alın
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF dosyasındaki tüm ekleri nasıl alacağınızı öğrenin. Kolay kullanım için adım adım kılavuz.
type: docs
weight: 40
url: /tr/net/programming-with-attachments/get-all-the-attachments/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak PDF dosyasındaki tüm ekleri almak için aşağıdaki C# kaynak kodunda adım adım yol göstereceğiz.

Başlamadan önce Aspose.PDF kitaplığını kurduğunuzdan ve geliştirme ortamınızı kurduğunuzdan emin olun. Ayrıca temel C# programlama bilgisine sahip olmak.

### 1. Adım: Belge Dizini Kurulumu

Sağlanan kaynak kodunda, ekleri almak istediğiniz PDF dosyasının bulunduğu dizini belirtmeniz gerekir. "dataDir" değişkenini istenen dizine değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### 2. Adım: Mevcut PDF belgesini açın

Mevcut PDF belgesini belirtilen yolu kullanarak açıyoruz.

```csharp
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
```

### 3. Adım: Ekler Koleksiyonunu Elde Etme

Eklerin koleksiyonunu belgeden alıyoruz.

```csharp
EmbeddedFileCollection embeddedFiles = pdfDocument.EmbeddedFiles;
```

### 4. Adım: Ekleri alma

Tüm ekleri almak ve bilgilerini görüntülemek için koleksiyonu gözden geçiriyoruz. Ekleri ayrı ayrı dosyalara da kaydederiz.

```csharp
int count = 1;
foreach(FileSpecification fileSpecification in embeddedFiles)
{
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("MIME Type: {0}", fileSpecification.MIMEType);

// Nesne parametrelerinin ek bilgi içerip içermediğini kontrol edin
if (fileSpecification.Params != null)
{
Console.WriteLine("CheckSum: {0}", fileSpecification.Params.CheckSum);
Console.WriteLine("Creation date: {0}", fileSpecification.Params.CreationDate);
Console.WriteLine("Modified date: {0}", fileSpecification.Params.ModDate);
Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}

// Eki alın ve bir dosyaya kaydedin
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + count + "_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();

count += 1;
}
```


### Aspose.PDF for .NET kullanarak Tüm Ekleri Getir için örnek kaynak kodu 

```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
// Katıştırılmış dosya koleksiyonunu alın
EmbeddedFileCollection embeddedFiles = pdfDocument.EmbeddedFiles;
// Gömülü dosyaların sayısını alın
Console.WriteLine("Total files : {0}", embeddedFiles.Count);
int count = 1;
// Tüm ekleri almak için koleksiyonda dolaşın
foreach (FileSpecification fileSpecification in embeddedFiles)
{
	Console.WriteLine("Name: {0}", fileSpecification.Name);
	Console.WriteLine("Description: {0}",
	fileSpecification.Description);
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
	fileSpecification.Contents.Read(fileContent, 0,
	fileContent.Length);
	FileStream fileStream = new FileStream(dataDir + count + "_out" + ".txt",
	FileMode.Create);
	fileStream.Write(fileContent, 0, fileContent.Length);
	fileStream.Close();
	count+=1;
}

```

## Çözüm

Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF dosyasından tüm eklerin nasıl alınacağını açıkladık. Artık bu bilgiyi PDF dosyalarınızdan ekleri ayıklamak ve değiştirmek için kullanabilirsiniz.

## PDF dosyasındaki tüm ekleri almak için SSS

#### S: Neden bir PDF belgesindeki tüm ekleri almam gerekiyor?

Y: Ekleri almak, bir PDF'ye gömülü ek dosyalara erişmenizi ve bunları değiştirmenizi sağlar; bu, arşivleme, paylaşma veya daha fazla işleme için yararlı olabilir.

#### S: Bir PDF belgesine ne tür dosyalar eklenebilir?

Y: PDF belgeleri, resimler, belgeler, elektronik tablolar, ses dosyaları ve daha fazlası dahil olmak üzere çok çeşitli ekli dosyalar içerebilir.

#### S: Bu eğitim, Aspose.PDF for .NET kullanarak bir PDF'den ekleri almama nasıl yardımcı oluyor?

A: Bu öğretici, bir PDF belgesindeki tüm eklere erişmek ve bunları almak için adım adım talimatlar ve C# kaynak kodu sağlar.

#### S: Bu öğreticiyi kullanarak tüm ekler yerine belirli ekleri alabilir miyim?

C: Evet, gereksinimlerinize göre ekleri seçerek almak için sağlanan kodu değiştirebilirsiniz.

#### S: Bu öğreticiyi kullanarak her ek hakkında hangi bilgileri edinebilirim?

A: Bu öğretici, ekin adı, açıklaması, MIME türü, oluşturma tarihi, değiştirme tarihi ve boyutu gibi ayrıntıların nasıl alınacağını ve görüntüleneceğini gösterir.

#### S: Bu eğitim kullanılarak alınan ekler nasıl kaydedilir?

C: Eğitim, alınan her eki belirtilen dizinde ayrı bir dosya olarak kaydetme konusunda size rehberlik eder.

#### S: Bu bilgiyi parola korumalı PDF dosyalarından ekleri çıkarmak için kullanabilir miyim?

C: Evet, Aspose.PDF for .NET kullanarak parola korumalı PDF dosyalarından ekleri almak için benzer ilkeleri uygulayabilirsiniz.

#### S: Aspose.PDF for .NET, ek almayı nasıl kolaylaştırır?

Y: Aspose.PDF for .NET, PDF belgelerindeki eklere kolayca erişmenizi ve bunları değiştirmenizi sağlayan sezgisel bir API sağlar.

#### S: Ekleri almanın önerildiği belirli senaryolar var mı?

C: Ekleri almak, görüntüleri, ses dosyalarını veya ek belgeleri ayıklamak gibi bir PDF'ye katıştırılmış dosyalara erişmeniz gerektiğinde kullanışlıdır.