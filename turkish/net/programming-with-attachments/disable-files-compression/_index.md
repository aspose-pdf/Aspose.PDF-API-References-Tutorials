---
title: PDF Dosyasında Dosya Sıkıştırmayı Devre Dışı Bırak
linktitle: PDF Dosyasında Dosya Sıkıştırmayı Devre Dışı Bırak
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF dosyasında dosya sıkıştırmayı nasıl devre dışı bırakacağınızı öğrenin. Kolay kullanım için adım adım kılavuz.
type: docs
weight: 30
url: /tr/net/programming-with-attachments/disable-files-compression/
---
Bu öğreticide, Aspose.PDF for .NET kullanarak PDF'de dosya sıkıştırmayı devre dışı bırakmak için aşağıdaki C# kaynak kodunda adım adım yol göstereceğiz.

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
//Belgenin ek koleksiyonuna ek ekleyin
pdfDocument.EmbeddedFiles.Add(fileSpecification);
dataDir = dataDir + "DisableFilesCompression_out.pdf";
// Yeni çıktıyı kaydet
pdfDocument.Save(dataDir);
Console.WriteLine("\nFile compression disabled successfully.\nFile saved at " + dataDir);

```

## Çözüm

Bu eğitimde, Aspose.PDF for .NET kullanılarak bir PDF'de dosya sıkıştırmanın nasıl devre dışı bırakılacağını açıkladık. Artık bu bilgiyi, ekli dosyaların bütünlüğünü sıkıştırma olmadan korumak için kullanabilirsiniz.

## PDF dosyasında dosya sıkıştırmayı devre dışı bırakmak için SSS

#### S: Neden bir PDF belgesinde dosya sıkıştırmayı devre dışı bırakmak isteyeyim?

C: Dosya sıkıştırmayı devre dışı bırakmak, bir PDF belgesindeki ekli dosyaların sıkıştırılmamış olarak kalmasını ve orijinal kalitelerini ve içeriklerini korumasını sağlar.

#### S: Dosya sıkıştırmayı devre dışı bırakmak PDF eklerine nasıl yarar sağlar?

C: Sıkıştırmayı devre dışı bırakmak, sıkıştırma işlemi sırasında oluşabilecek herhangi bir veri veya kalite kaybını önleyerek, ekli dosyaların olduğu gibi sunulmasını sağlar.

#### S: Bu öğreticiyi kullanarak belirli ekler için sıkıştırmayı seçerek devre dışı bırakabilir miyim?

C: Evet, bu eğitim, bir PDF belgesindeki tek tek ekler için dosya sıkıştırmayı devre dışı bırakma konusunda size rehberlik ederek hassas kontrol sağlar.

#### S: Ne tür ekler için sıkıştırmayı devre dışı bırakabilirim?

C: Görüntüler, belgeler, elektronik tablolar ve daha fazlası gibi her türlü ek için sıkıştırmayı devre dışı bırakarak bütünlüklerinin korunmasını sağlayabilirsiniz.

#### S: Sıkıştırmayı devre dışı bırakmak, PDF belgesinin genel dosya boyutunu etkiler mi?

C: Ekler için sıkıştırmayı devre dışı bırakmak, sıkıştırılmamış dosyalar daha fazla yer kapladığından, PDF belgesinin genel dosya boyutunda küçük bir artışa neden olabilir.

#### S: Aspose.PDF for .NET, dosya sıkıştırmayı devre dışı bırakma sürecini nasıl kolaylaştırır?

Y: Aspose.PDF for .NET, sağlanan kaynak kodunda gösterildiği gibi, ekler için dosya sıkıştırmayı devre dışı bırakmanıza izin veren, kullanımı kolay bir API sağlar.

#### S: Gerekirse ekler için sıkıştırmayı daha sonra yeniden etkinleştirebilir miyim?

C: Evet, gerekirse sıkıştırmayı yeniden etkinleştirmek için ekin ayarlarını değiştirebilirsiniz.

#### S: PDF'yi sıkıştırmayı destekleyen bir aygıtta veya yazılımda açarsam ne olur?

Y: PDF'yi sıkıştırmayı destekleyen bir aygıtta veya yazılımda açarsanız, ek sıkıştırılmamış olarak görüntülenebilir ve bu da dosya boyutunu ve işleme performansını etkileyebilir.

#### S: Sıkıştırmayı devre dışı bırakmanın önerildiği belirli senaryolar var mı?

Y: Yüksek çözünürlüklü resimler veya hassas belgeler gibi orijinal kalite ve veri bütünlüğünün korunmasının öncelikli olduğu ekler için sıkıştırmanın devre dışı bırakılması önerilir.