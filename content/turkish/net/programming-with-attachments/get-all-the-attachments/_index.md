---
title: Tüm Ekleri PDF Dosyasında Alın
linktitle: Tüm Ekleri PDF Dosyasında Alın
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile tüm ekleri PDF dosyasına nasıl alacağınızı öğrenin. Kolay kullanım için adım adım kılavuz.
type: docs
weight: 40
url: /tr/net/programming-with-attachments/get-all-the-attachments/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak PDF dosyasındaki tüm ekleri almak için aşağıdaki C# kaynak kodunu adım adım anlatacağız.

Başlamadan önce Aspose.PDF kütüphanesini kurduğunuzdan ve geliştirme ortamınızı kurduğunuzdan emin olun. Ayrıca temel C# programlama bilgisine sahip olmak.

### Adım 1: Belge Dizini Kurulumu

Sağlanan kaynak kodunda, ekleri almak istediğiniz PDF dosyasının bulunduğu dizini belirtmeniz gerekir. "dataDir" değişkenini istediğiniz dizine değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### 2. Adım: Mevcut PDF belgesini açın

Mevcut PDF belgesini belirtilen yolu kullanarak açıyoruz.

```csharp
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
```

### Adım 3: Ek Koleksiyonunun Edinilmesi

Eklerin koleksiyonunu belgeden alıyoruz.

```csharp
EmbeddedFileCollection embeddedFiles = pdfDocument.EmbeddedFiles;
```

### 4. Adım: Ekleri alma

Tüm ekleri almak ve bilgilerini görüntülemek için koleksiyona göz atıyoruz. Ekleri ayrı ayrı dosyalara da kaydediyoruz.

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


### Aspose.PDF for .NET kullanarak Tüm Ekleri Al için örnek kaynak kodu 

```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
// Gömülü dosya koleksiyonunu edinin
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

Bu eğitimde Aspose.PDF for .NET kullanarak bir PDF dosyasındaki tüm eklerin nasıl alınacağını açıkladık. Artık bu bilgiyi PDF dosyalarınızdaki ekleri ayıklamak ve değiştirmek için kullanabilirsiniz.

## Tüm ekleri PDF dosyasına almak için SSS

#### S: Neden bir PDF belgesindeki tüm ekleri almam gerekiyor?

C: Ekleri almak, PDF'ye gömülü ek dosyalara erişmenize ve bunları değiştirmenize olanak tanır; bunlar, arşivleme, paylaşma veya daha ileri işlemler için yararlı olabilir.

#### S: Bir PDF belgesine ne tür dosyalar eklenebilir?

C: PDF belgeleri; resimler, belgeler, e-tablolar, ses dosyaları ve daha fazlasını içeren çok çeşitli ekli dosyalar içerebilir.

#### S: Bu eğitim Aspose.PDF for .NET kullanarak bir PDF'den ekleri almama nasıl yardımcı olacak?

C: Bu eğitimde, bir PDF belgesindeki tüm eklere erişmek ve bunları almak için adım adım talimatlar ve C# kaynak kodu sağlanır.

#### S: Bu öğreticiyi kullanarak tüm ekler yerine belirli ekleri alabilir miyim?

C: Evet, gereksinimlerinize göre ekleri seçerek almak için sağlanan kodu değiştirebilirsiniz.

#### S: Bu öğreticiyi kullanarak her bir ek hakkında hangi bilgileri edinebilirim?

C: Bu eğitimde, ekin adı, açıklaması, MIME türü, oluşturulma tarihi, değiştirilme tarihi ve boyutu gibi ayrıntıların nasıl alınacağı ve görüntüleneceği gösterilmektedir.

#### S: Alınan ekler bu eğitim kullanılarak nasıl kaydedilir?

C: Eğitim, alınan her eki belirtilen dizinde ayrı bir dosya olarak kaydetme konusunda size yol gösterir.

#### S: Bu bilgiyi parola korumalı PDF dosyalarından ekleri çıkarmak için kullanabilir miyim?

C: Evet, Aspose.PDF for .NET'i kullanarak parola korumalı PDF dosyalarından ekleri almak için benzer ilkeleri uygulayabilirsiniz.

#### S: Aspose.PDF for .NET eklerin alınmasını nasıl kolaylaştırır?

C: Aspose.PDF for .NET, PDF belgelerindeki eklere kolayca erişmenizi ve bunları değiştirmenizi sağlayan sezgisel bir API sağlar.

#### S: Eklerin alınmasının önerildiği belirli senaryolar var mı?

C: Ekleri almak, görüntüleri, ses dosyalarını veya ek belgeleri ayıklamak gibi bir PDF'ye gömülü dosyalara erişmeniz gerektiğinde kullanışlıdır.