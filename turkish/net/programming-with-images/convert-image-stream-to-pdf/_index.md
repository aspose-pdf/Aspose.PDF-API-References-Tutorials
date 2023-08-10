---
title: Görüntü Akışını PDF Dosyasına Dönüştür
linktitle: Görüntü Akışını PDF Dosyasına Dönüştür
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile bir görüntü akışını kolayca PDF dosyasına dönüştürün.
type: docs
weight: 70
url: /tr/net/programming-with-images/convert-image-stream-to-pdf/
---
Bu kılavuz, Aspose.PDF for .NET kullanarak bir görüntü akışının PDF dosyasına nasıl dönüştürüleceğini adım adım gösterecek. Ortamınızı zaten kurduğunuzdan emin olun ve aşağıdaki adımları izleyin:

## 1. Adım: Belge dizinini tanımlayın

 Başlamadan önce, belgeler için doğru dizini ayarladığınızdan emin olun. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` resminizin bulunduğu dizine giden yolu içeren kodda.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Bir Document nesnesinin örneğini oluşturun

 Bu adımda, bir örneği başlatacağız`Document` boş yapıcısını kullanan nesne`Aspose.Pdf.Document` sınıf.

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

## Adım 5: Görüntüyü bir bayt dizisine okuyun

 Görüntüyü akıştan okuyun ve kullanarak bir bayt dizisinde saklayın.`Read` yöntemi`fs` nesne.

```csharp
byte[] data = new byte[fs.Length];
fs.Read(data, 0, data.Length);
```

## Adım 6: Bayt dizisinden bir MemoryStream nesnesi oluşturun

 Oluşturmak`MemoryStream` görüntüyü içeren bayt dizisinden nesne.

```csharp
MemoryStream ms = new MemoryStream(data);
```

## 7. Adım: Bir Görüntü Nesnesi Oluşturun

 Bu adımda, bir oluşturacağız`Image` kullanarak nesne`Aspose.Pdf.Image` sınıf. kullanarak görüntünün akışını belirtin.`ImageStream` mülkiyet ve geçmek`ms` daha önce oluşturduğumuz nesne.

```csharp
Aspose.Pdf.Image imageht = new Aspose.Pdf.Image();
imageht. ImageStream = ms;
```

## 8. Adım: Image nesnesini Paragraphs koleksiyonuna ekleyin

 Ekle`imageht` itiraz etmek`Paragraphs` koleksiyonu`sec` bölüm.

```csharp
sec.Paragraphs.Add(imageht);
```

## 9. Adım: PDF belgesini kaydedin

 kullanarak PDF belgesini kaydedin.`Save` yöntemi`pdf1` nesne. PDF dosyasının çıktı yolunu belirtin.

```csharp
pdf1.Save(dataDir + "ConvertMemoryStreamImageToPdf_out.pdf");
```

## 10. Adım: MemoryStream nesnesini kapatın

 Kapat`ms` kullanarak nesne`Close` kaynakları serbest bırakma yöntemi.

```csharp
ms. Close();
```

### Aspose.PDF for .NET kullanarak Görüntü Akışını PDF'ye Dönüştürmek için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Boş oluşturucusunu çağırarak Belge örneğini oluşturun
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// Pdf belgesine bir Sayfa ekleyin
Aspose.Pdf.Page sec = pdf1.Pages.Add();
// İmaj dosyasını okumak için bir FileStream nesnesi oluşturun
FileStream fs = File.OpenRead(dataDir + "aspose.jpg");
// Resmi Bayt dizisine oku
byte[] data = new byte[fs.Length];
fs.Read(data, 0, data.Length);
// Görüntü Byte dizisinden bir MemoryStream nesnesi oluşturun
MemoryStream ms = new MemoryStream(data);
// Bir görüntü nesnesi oluşturun
Aspose.Pdf.Image imageht = new Aspose.Pdf.Image();
// Görüntü kaynağını MemoryStream olarak belirtin
imageht.ImageStream = ms;
// Bölümün Paragraflar koleksiyonuna resim nesnesi ekleyin
sec.Paragraphs.Add(imageht);
// Pdf'i kaydet
pdf1.Save(dataDir + "ConvertMemoryStreamImageToPdf_out.pdf");
// MemoryStream Nesnesini Kapatın
ms.Close();
```

## Çözüm

Tebrikler! Aspose.PDF for .NET'i kullanarak bir görüntü akışını başarıyla bir PDF dosyasına dönüştürdünüz. Oluşturulan PDF dosyası belirtilen dizine kaydedilir. Artık bu PDF dosyasını projelerinizde veya uygulamalarınızda kullanabilirsiniz.

### SSS

#### S: Aspose.PDF for .NET kullanarak bir görüntü akışını bir PDF dosyasına dönüştürmenin amacı nedir?

Y: Bir görüntü akışını bir PDF dosyasına dönüştürmek, görüntüleri PDF belgelerine dahil etmek, görüntü tabanlı PDF'ler oluşturmak veya görüntüleri metin içeriğine gömmek için yararlı olabilir.

#### S: Aspose.PDF for .NET, bir görüntü akışının bir PDF dosyasına dönüştürülmesine nasıl yardımcı olur?

C: Aspose.PDF for .NET, bir PDF belgesi oluşturmak, bir görüntü akışını okumak ve görüntüyü PDF dosyasına gömmek için kullanışlı ve adım adım ilerleyen bir süreç sağlar.

#### S: Görüntü akışından PDF'e dönüştürme işleminde belge dizinini tanımlamak neden önemlidir?

C: Belge dizininin belirtilmesi, görüntü akışının ve ortaya çıkan PDF dosyasının istenen çıktı yolunda doğru bir şekilde konumlandırılmasını sağlar.

#### S: Görüntü akışından PDF'e dönüştürme sürecinde Aspose.PDF for .NET'i kullanarak bir PDF belgesini nasıl oluştururum?

 A: Bir örneğini oluşturun`Document` kullanarak nesne`Aspose.Pdf.Document` PDF belgesini oluşturmak için sınıfın boş kurucusu.

####  S: Rolü nedir?`Pages` object in the image stream to PDF conversion process?

 C:`Pages` nesne, PDF belgesine sayfalar eklemenize ve içeriğini yönetmenize olanak tanır.

#### S: Görüntü akışı, görüntü akışında PDF dönüştürme işleminde nasıl okunur ve işlenir?

 A: Görüntü akışı bir`FileStream` nesne ve içeriği bir bayt dizisinde saklanır. Bayt dizisi daha sonra oluşturmak için kullanılır.`MemoryStream` daha sonra oluşturmak için kullanılan nesne`Image` nesne.

#### S: Görüntü, dönüştürme işlemi sırasında PDF belgesine nasıl gömülür?

 bir: bir`Image` nesne kullanılarak oluşturulur`Aspose.Pdf.Image` sınıf ve görüntü akışı şuna atanır:`ImageStream` mülk. bu`Image` nesne daha sonra eklenir`Paragraphs` PDF belgesinin toplanması.

#### S: Ortaya çıkan PDF dosyasında görüntünün konumunu, boyutunu veya diğer niteliklerini özelleştirebilir miyim?

 C: Evet, görüntünün konumunu, boyutunu ve diğer niteliklerini, özelliklerini ayarlayarak değiştirebilirsiniz.`Image` eklemeden önce nesne`Paragraphs` Toplamak.

#### S: Görüntü akışından PDF'e dönüştürme sürecindeki son adım nedir?

 A: PDF belgesi kullanılarak kaydedilir.`Save` yöntemi`Document` nesne ve`MemoryStream` nesne kullanılarak kapatılır`Close` kaynakları serbest bırakma yöntemi.