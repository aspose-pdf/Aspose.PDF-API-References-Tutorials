---
title: Tüm Ekleri PDF Dosyasında Alın
linktitle: Tüm Ekleri PDF Dosyasında Alın
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım eğitimde Aspose.PDF for .NET kullanarak bir PDF dosyasından tüm ekleri nasıl çıkaracağınızı öğrenin.
type: docs
weight: 40
url: /tr/net/programming-with-attachments/get-all-the-attachments/
---
## giriiş

Dijital çağda, PDF'ler belgeleri paylaşmak için olmazsa olmaz bir araç haline geldi. Çok yönlüdürler, güvenlidirler ve ekler de dahil olmak üzere çok sayıda bilgi içerebilirler. Bir PDF dosyasından tüm bu gizli hazineleri nasıl çıkaracağınızı hiç merak ettiniz mi? Şanslısınız! Bu eğitimde, bir PDF dosyasındaki tüm ekleri almak için Aspose.PDF for .NET'i kullanmaya dalacağız. İster deneyimli bir geliştirici olun ister yeni başlıyor olun, bu kılavuz sizi adım adım süreçte yönlendirecektir.

## Ön koşullar

Koda geçmeden önce, başlamak için ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım:

1. Visual Studio: Makinenizde Visual Studio'nun yüklü olduğundan emin olun. .NET geliştirme için başvurulacak IDE'dir.
2.  .NET için Aspose.PDF: Aspose.PDF kütüphanesini indirip yüklemeniz gerekecek. Bunu bulabilirsiniz[Burada](https://releases.aspose.com/pdf/net/).
3. Temel C# Bilgisi: C# programlamaya aşina olmak, kod parçacıklarını daha iyi anlamanıza yardımcı olacaktır.

## Paketleri İçe Aktar

Başlamak için, C# projenize gerekli paketleri içe aktarmanız gerekir. Bunu nasıl yapacağınız aşağıda açıklanmıştır:

### Yeni Bir Proje Oluştur

Visual Studio'yu açın ve yeni bir C# projesi oluşturun. Basitlik için bir Konsol Uygulaması seçin.

### Aspose.PDF Referansını Ekle

1. Çözüm Gezgini’nde projenizin üzerine sağ tıklayın.
2. “NuGet Paketlerini Yönet” seçeneğini seçin.
3. “Aspose.PDF” dosyasını arayın ve en son sürümü yükleyin.

### Ad Alanını İçe Aktar

C# dosyanızın en üstüne Aspose.PDF ad alanını içe aktarın

```csharp
using System.IO;
using Aspose.Pdf;
using System;
```

Artık ortamımızı kurduğumuza göre, bir PDF dosyasından ekleri çıkarmanın inceliklerine geçelim.

## Adım 1: Belge Dizininizi Ayarlayın

İlk önce, belgeler dizininize giden yolu belirtmeniz gerekir. PDF dosyanız burada bulunacaktır.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`YOUR DOCUMENT DIRECTORY` PDF dosyanızın saklandığı gerçek yol ile. Bu önemlidir çünkü programın dosyayı nerede arayacağını bilmesi gerekir.

## Adım 2: PDF Belgesini açın

Sonra, Aspose.PDF kütüphanesini kullanarak PDF belgesini açacağız. Sihir burada başlıyor!

```csharp
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
```

 Burada yeni bir tane yaratıyoruz`Document` nesne ve PDF dosyasının yolunu geçirin. Dosya adının, uzantı dahil, tam olarak eşleştiğinden emin olun.

## Adım 3: Gömülü Dosyalar Koleksiyonuna Erişim

Artık belgeyi açtığımıza göre, gömülü dosyalar koleksiyonuna erişelim. Tüm ekler burada saklanır.

```csharp
EmbeddedFileCollection embeddedFiles = pdfDocument.EmbeddedFiles;
```

Bu satırla, tüm gömülü dosyaları kolayca döngüye alabileceğimiz bir koleksiyona çekiyoruz.

## Adım 4: Gömülü Dosyaları Say

Kaç tane ek ile uğraştığınızı bilmek her zaman iyidir. Gömülü dosyaların toplam sayısını yazdıralım.

```csharp
Console.WriteLine("Total files : {0}", embeddedFiles.Count);
```

Bu size PDF'inizde kaç tane ek olduğunu gösteren hızlı bir genel bakış sunacaktır.

## Adım 5: Ekler Arasında Döngü Oluşturun

Şimdi eğlenceli kısma geliyoruz! Gömülü dosyalar koleksiyonundaki her dosya spesifikasyonunu dolaşacağız ve ayrıntıları çıkaracağız.

```csharp
int count = 1;

foreach (FileSpecification fileSpecification in embeddedFiles)
{
    Console.WriteLine("Name: {0}", fileSpecification.Name);
    Console.WriteLine("Description: {0}", fileSpecification.Description);
    Console.WriteLine("Mime Type: {0}", fileSpecification.MIMEType);
```

Bu döngüde, her bir ekin adını, açıklamasını ve MIME türünü yazdırıyoruz. Bu, PDF'nizin içinde ne olduğuna dair net bir resim sunar.

## Adım 6: Ek Parametreleri Kontrol Edin

Bazı ekler ek parametrelere sahip olabilir. Bunların var olup olmadığını kontrol edelim ve yazdıralım.

```csharp
if (fileSpecification.Params != null)
{
    Console.WriteLine("CheckSum: {0}", fileSpecification.Params.CheckSum);
    Console.WriteLine("Creation Date: {0}", fileSpecification.Params.CreationDate);
    Console.WriteLine("Modification Date: {0}", fileSpecification.Params.ModDate);
    Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}
```

Bu adım, eklerle ilgili önemli ayrıntıları kaçırmamanızı sağlar.

## Adım 7: Ekleri Çıkarın ve Kaydedin

Son olarak, her bir ekin içeriğini çıkartalım ve bir dosyaya kaydedelim. İşte sıkı çalışmanızın sonuçlarını burada göreceksiniz!

```csharp
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + count + "_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();
count += 1;
```

 Bu kodda, her bir ekin içeriğini bir bayt dizisine okuruz ve sonra onu yeni bir dosyaya yazarız. Dosyalar sırayla adlandırılır (örneğin,`1_out.txt`, `2_out.txt`, vesaire.).

## Çözüm

Ve işte oldu! Aspose.PDF for .NET kullanarak bir PDF dosyasından tüm ekleri başarıyla çıkardınız. Bu güçlü kütüphane, PDF belgelerini düzenlemeyi ve gizli hazinelerine erişmeyi kolaylaştırır. İster kişisel bir proje ister profesyonel bir uygulama üzerinde çalışıyor olun, ekleri nasıl çıkaracağınızı bilmek inanılmaz derecede faydalı olabilir.

## SSS

### Aspose.PDF for .NET nedir?
Aspose.PDF for .NET, geliştiricilerin PDF belgelerini programlı bir şekilde oluşturmalarına, düzenlemelerine ve dönüştürmelerine olanak tanıyan bir kütüphanedir.

### Aspose.PDF'yi ücretsiz kullanabilir miyim?
 Evet, Aspose kütüphanenin özelliklerini keşfetmek için kullanabileceğiniz ücretsiz bir deneme sürümü sunuyor. Kontrol edin[Burada](https://releases.aspose.com/).

### Aspose.PDF için nasıl destek alabilirim?
 Aspose forumundan destek alabilirsiniz[Burada](https://forum.aspose.com/c/pdf/10).

### Geçici lisans var mı?
Evet, Aspose.PDF için geçici bir lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).

### Dokümantasyonu nerede bulabilirim?
 .NET için Aspose.PDF'nin belgeleri şurada bulunabilir:[Burada](https://reference.aspose.com/pdf/net/).