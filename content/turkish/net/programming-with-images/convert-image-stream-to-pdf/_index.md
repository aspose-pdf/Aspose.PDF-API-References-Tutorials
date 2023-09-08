---
title: Görüntü Akışını PDF Dosyasına Dönüştür
linktitle: Görüntü Akışını PDF Dosyasına Dönüştür
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile bir görüntü akışını kolayca PDF dosyasına dönüştürün.
type: docs
weight: 70
url: /tr/net/programming-with-images/convert-image-stream-to-pdf/
---
Bu kılavuz, Aspose.PDF for .NET kullanarak bir görüntü akışını PDF dosyasına nasıl dönüştürebileceğinizi adım adım anlatacaktır. Ortamınızı zaten kurduğunuzdan emin olun ve aşağıdaki adımları izleyin:

## 1. Adım: Belge dizinini tanımlayın

 Başlamadan önce belgeler için doğru dizini ayarladığınızdan emin olun. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` görüntünüzün bulunduğu dizinin yolunu içeren kodda.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Bir Belge nesnesinin örneğini oluşturun

 Bu adımda, bir örnek oluşturacağız`Document` boş yapıcısını kullanan nesne`Aspose.Pdf.Document` sınıf.

```csharp
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

## 3. Adım: PDF belgesine bir sayfa ekleyin

 kullanarak PDF belgesine bir sayfa ekleyin.`Add` yöntemi`Pages` Nesnesi`pdf1`.

```csharp
Aspose.Pdf.Page sec = pdf1.Pages.Add();
```

## 4. Adım: Görüntü akışını okuyun

 Bu adımda bir oluşturacağız`FileStream` görüntü dosyasını akıştan okumak için nesne.

```csharp
FileStream fs = File.OpenRead(dataDir + "aspose.jpg");
```

## Adım 5: Resmi bir bayt dizisine okuyun

 Akıştaki görüntüyü okuyun ve bunu kullanarak bir bayt dizisinde saklayın.`Read` yöntemi`fs` nesne.

```csharp
byte[] data = new byte[fs.Length];
fs.Read(data, 0, data.Length);
```

## Adım 6: Bayt dizisinden bir MemoryStream nesnesi oluşturun

 Oluşturmak`MemoryStream` görüntüyü içeren bayt dizisinden nesne.

```csharp
MemoryStream ms = new MemoryStream(data);
```

## Adım 7: Bir Görüntü Nesnesi Oluşturun

 Bu adımda bir oluşturacağız`Image` kullanarak nesne`Aspose.Pdf.Image` sınıf. kullanarak görüntünün akışını belirtin.`ImageStream` mülkiyet ve geçiş`ms` daha önce oluşturduğumuz nesne.

```csharp
Aspose.Pdf.Image imageht = new Aspose.Pdf.Image();
imageht. ImageStream = ms;
```

## Adım 8: Image nesnesini Paragraphs koleksiyonuna ekleyin

 Ekle`imageht` itiraz`Paragraphs` koleksiyonu`sec` bölüm.

```csharp
sec.Paragraphs.Add(imageht);
```

## 9. Adım: PDF belgesini kaydedin

 PDF belgesini kullanarak kaydedin.`Save` yöntemi`pdf1` nesne. PDF dosyasının çıktı yolunu belirtin.

```csharp
pdf1.Save(dataDir + "ConvertMemoryStreamImageToPdf_out.pdf");
```

## Adım 10: MemoryStream nesnesini kapatın

 Kapat`ms` kullanarak nesne`Close` Kaynakları serbest bırakma yöntemi.

```csharp
ms. Close();
```

### Aspose.PDF for .NET kullanarak Görüntü Akışını PDF'ye Dönüştürme için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Boş yapıcısını çağırarak Belge örneğini oluşturun
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// PDF belgesine bir Sayfa ekleyin
Aspose.Pdf.Page sec = pdf1.Pages.Add();
// İmag dosyasını okumak için bir FileStream nesnesi oluşturun
FileStream fs = File.OpenRead(dataDir + "aspose.jpg");
// Görüntüyü Bayt dizisine oku
byte[] data = new byte[fs.Length];
fs.Read(data, 0, data.Length);
// Görüntü Bayt dizisinden bir MemoryStream nesnesi oluşturun
MemoryStream ms = new MemoryStream(data);
// Bir görüntü nesnesi oluşturun
Aspose.Pdf.Image imageht = new Aspose.Pdf.Image();
// Görüntü kaynağını MemoryStream olarak belirtin
imageht.ImageStream = ms;
// Bölümün Paragraf koleksiyonuna resim nesnesi ekleyin
sec.Paragraphs.Add(imageht);
// PDF'yi kaydet
pdf1.Save(dataDir + "ConvertMemoryStreamImageToPdf_out.pdf");
// MemoryStream Nesnesini kapatın
ms.Close();
```

## Çözüm

Tebrikler! Aspose.PDF for .NET'i kullanarak bir görüntü akışını başarıyla PDF dosyasına dönüştürdünüz. Oluşturulan PDF dosyası belirtilen dizine kaydedilir. Artık bu PDF dosyasını projelerinizde veya uygulamalarınızda kullanabilirsiniz.

### SSS'ler

#### S: Aspose.PDF for .NET kullanarak bir görüntü akışını PDF dosyasına dönüştürmenin amacı nedir?

C: Bir görüntü akışını PDF dosyasına dönüştürmek, görüntüleri PDF belgelerine dahil etmek, görüntü tabanlı PDF'ler oluşturmak veya görüntüleri metin içeriğine gömmek için yararlı olabilir.

#### S: Aspose.PDF for .NET, bir görüntü akışının PDF dosyasına dönüştürülmesine nasıl yardımcı olur?

C: Aspose.PDF for .NET, bir PDF belgesi oluşturmak, bir görüntü akışını okumak ve görüntüyü PDF dosyasına gömmek için kullanışlı ve adım adım bir süreç sağlar.

#### S: Görüntü akışından PDF'ye dönüştürme sürecinde belge dizinini tanımlamak neden önemlidir?

C: Belge dizininin belirtilmesi, görüntü akışının ve elde edilen PDF dosyasının istenen çıktı yolunda doğru şekilde konumlandırılmasını sağlar.

#### S: Görüntü akışından PDF'ye dönüştürme sürecinde Aspose.PDF for .NET'i kullanarak nasıl PDF belgesi oluşturabilirim?

 A: Bir örneği oluşturun`Document` kullanarak nesne`Aspose.Pdf.Document` PDF belgesini oluşturmak için sınıfın boş yapıcısını kullanın.

####  S: Rolü nedir?`Pages` object in the image stream to PDF conversion process?

 C:`Pages` nesne, PDF belgesine sayfalar eklemenize ve içeriğini yönetmenize olanak tanır.

#### S: Görüntü akışı, görüntü akışından PDF'ye dönüştürme sürecinde nasıl okunur ve işlenir?

 C: Görüntü akışı bir kullanılarak okunur`FileStream` nesne ve içeriği bir bayt dizisinde saklanır. Bayt dizisi daha sonra bir oluşturmak için kullanılır.`MemoryStream` Daha sonra bir nesne oluşturmak için kullanılan nesne`Image` nesne.

#### S: Dönüştürme işlemi sırasında görüntü PDF belgesine nasıl gömülür?

 C: Bir`Image` nesne kullanılarak oluşturulur.`Aspose.Pdf.Image` sınıfa atanır ve görüntü akışı`ImageStream` mülk.`Image` daha sonra nesne eklenir`Paragraphs` PDF belgesinin toplanması.

#### S: Ortaya çıkan PDF dosyasında görüntünün konumunu, boyutunu veya diğer özelliklerini özelleştirebilir miyim?

 C: Evet, görüntünün özelliklerini ayarlayarak görüntünün konumunu, boyutunu ve diğer niteliklerini değiştirebilirsiniz.`Image` nesneyi eklemeden önce`Paragraphs` Toplamak.

#### S: Görüntü akışından PDF'ye dönüştürme sürecinin son adımı nedir?

 C: PDF belgesi,`Save` yöntemi`Document` nesne ve`MemoryStream` nesne kullanılarak kapatılır`Close` Kaynakları serbest bırakma yöntemi.