---
title: PDF Dosyasında Dosya Sıkıştırmayı Devre Dışı Bırak
linktitle: PDF Dosyasında Dosya Sıkıştırmayı Devre Dışı Bırak
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile PDF dosyasında dosya sıkıştırmasını nasıl devre dışı bırakacağınızı öğrenin. Kolay kullanım için adım adım kılavuz.
type: docs
weight: 30
url: /tr/net/programming-with-attachments/disable-files-compression/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak PDF'de dosya sıkıştırmayı devre dışı bırakmak için aşağıdaki C# kaynak kodunu adım adım anlatacağız.

Başlamadan önce Aspose.PDF kütüphanesini kurduğunuzdan ve geliştirme ortamınızı kurduğunuzdan emin olun. Ayrıca temel C# programlama bilgisine sahip olmak.

### Adım 1: Belge Dizini Kurulumu

Sağlanan kaynak kodunda, dosya sıkıştırmasını devre dışı bırakmak istediğiniz PDF dosyasının bulunduğu dizini belirtmeniz gerekir. "dataDir" değişkenini istediğiniz dizine değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### 2. Adım: Mevcut PDF belgesini açın

Mevcut PDF belgesini belirtilen yolu kullanarak açıyoruz.

```csharp
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
```

### 3. Adım: Yeni dosyayı ek olarak eklenecek şekilde ayarlama

Ek olarak eklemek istediğimiz yeni dosyayı yapılandırıyoruz. Bu örnekte "test_out.txt" adında ve "Örnek metin dosyası" açıklamasına sahip bir metin dosyası ekliyoruz.

```csharp
FileSpecification fileSpecification = new FileSpecification("test_out.txt", "Sample text file");
```

### Adım 4: Dosya Sıkıştırmayı Devre Dışı Bırakın

FileSpecification nesnesinin Encoding özelliğini FileEncoding.None olarak ayarlayarak dosya sıkıştırmayı devre dışı bırakıyoruz.

```csharp
fileSpecification.Encoding = FileEncoding.None;
```

### 5. Adım: Eki belgenin ekler koleksiyonuna ekleme

Eki, belgenin ekler koleksiyonuna ekliyoruz.

```csharp
pdfDocument.EmbeddedFiles.Add(fileSpecification);
```

### Adım 6: Yeni çıktı dosyasını kaydedin

Son olarak ortaya çıkan yeni PDF dosyasını "DisableFilesCompression_out.pdf" ismiyle belirtilen dizine kaydediyoruz.

```csharp
pdfDocument.Save(dataDir + "DisableFilesCompression_out.pdf");
```


### Aspose.PDF for .NET kullanarak Dosya Sıkıştırmayı Devre Dışı Bırakma için örnek kaynak kodu 

```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
// Ek olarak eklenecek yeni dosyayı ayarlayın
FileSpecification fileSpecification = new FileSpecification("test_out.txt", "Sample text file");
// Kodlama proparty'sini FileEncoding.None olarak ayarlayarak belirtin
fileSpecification.Encoding = FileEncoding.None;
//Belgenin ek koleksiyonuna ek ekleyin
pdfDocument.EmbeddedFiles.Add(fileSpecification);
dataDir = dataDir + "DisableFilesCompression_out.pdf";
// Yeni çıktıyı kaydet
pdfDocument.Save(dataDir);
Console.WriteLine("\nFile compression disabled successfully.\nFile saved at " + dataDir);

```

## Çözüm

Bu eğitimde Aspose.PDF for .NET kullanarak bir PDF'de dosya sıkıştırmanın nasıl devre dışı bırakılacağını açıkladık. Artık bu bilgiyi, sıkıştırılmadan ekli dosyaların bütünlüğünü korumak için kullanabilirsiniz.

## PDF dosyasında dosya sıkıştırmayı devre dışı bırakmak için SSS

#### S: Bir PDF belgesinde dosya sıkıştırmasını neden devre dışı bırakmak isteyeyim?

C: Dosya sıkıştırmasını devre dışı bırakmak, PDF belgesindeki ekli dosyaların sıkıştırılmamış kalmasını ve orijinal kalitelerini ve içeriklerini korumalarını sağlar.

#### S: Dosya sıkıştırmasını devre dışı bırakmanın PDF eklerine nasıl faydası olur?

C: Sıkıştırmayı devre dışı bırakmak, sıkıştırma işlemi sırasında oluşabilecek veri veya kalite kaybını önleyerek ekli dosyaların olduğu gibi sunulmasını sağlar.

#### S: Bu öğreticiyi kullanarak belirli ekler için sıkıştırmayı seçerek devre dışı bırakabilir miyim?

C: Evet, bu eğitim, bir PDF belgesindeki tek tek ekler için dosya sıkıştırmasını devre dışı bırakma konusunda size rehberlik ederek ayrıntılı kontrol sağlar.

#### S: Hangi tür eklerde sıkıştırmayı devre dışı bırakabilirim?

C: Görüntüler, belgeler, e-tablolar ve daha fazlası gibi her türlü ek için sıkıştırmayı devre dışı bırakarak bunların bütünlüğünün korunmasını sağlayabilirsiniz.

#### S: Sıkıştırmayı devre dışı bırakmak PDF belgesinin genel dosya boyutunu etkiler mi?

C: Ekler için sıkıştırmanın devre dışı bırakılması, sıkıştırılmamış dosyalar daha fazla yer kaplayacağından PDF belgesinin genel dosya boyutunda hafif bir artışa neden olabilir.

#### S: Aspose.PDF for .NET, dosya sıkıştırmasını devre dışı bırakma sürecini nasıl kolaylaştırır?

C: Aspose.PDF for .NET, sağlanan kaynak kodunda gösterildiği gibi, ekler için dosya sıkıştırmayı devre dışı bırakmanıza olanak tanıyan, kullanımı kolay bir API sağlar.

#### S: Daha sonra gerekirse ekler için sıkıştırmayı yeniden etkinleştirebilir miyim?

C: Evet, gerekirse sıkıştırmayı tekrar etkinleştirmek için ekin ayarlarını değiştirebilirsiniz.

#### S: PDF'yi sıkıştırmayı destekleyen bir aygıtta veya yazılımda açarsam ne olur?

C: PDF'yi sıkıştırmayı destekleyen bir aygıtta veya yazılımda açarsanız, ek sıkıştırılmamış olarak görüntülenebilir ve bu durum dosya boyutunu ve oluşturma performansını etkileyebilir.

#### S: Sıkıştırmanın devre dışı bırakılmasının önerildiği belirli senaryolar var mı?

C: Yüksek çözünürlüklü görüntüler veya hassas belgeler gibi orijinal kalitenin ve veri bütünlüğünün korunmasının öncelikli olduğu ekler için sıkıştırmanın devre dışı bırakılması önerilir.