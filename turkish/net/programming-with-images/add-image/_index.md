---
title: Resim eklemek
linktitle: Resim eklemek
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesine kolayca görüntü ekleyin.
type: docs
weight: 10
url: /tr/net/programming-with-images/add-image/
---

Bu kılavuz, Aspose.PDF for .NET kullanarak bir PDF belgesine nasıl resim ekleyeceğinizi adım adım gösterecek. Ortamınızı zaten kurduğunuzdan emin olun ve aşağıdaki adımları izleyin:

## 1. Adım: Belge dizinini tanımlayın

 Başlamadan önce, belgeler için doğru dizini ayarladığınızdan emin olun. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` PDF belgenizin bulunduğu dizinin yolunu içeren kodda.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Belgeyi açın

 Bu adımda, PDF belgesini kullanarak açacağız.`Document` Aspose.PDF sınıfı. Kullan`Document` yapıcı ve yolu PDF belgesine iletin.

```csharp
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
```

## 3. Adım: Görüntü Koordinatlarını Ayarlayın

 Eklemek istediğiniz görüntünün koordinatlarını ayarlayın. değişkenler`lowerLeftX`, `lowerLeftY`, `upperRightX` Ve`upperRightY` sırasıyla görüntünün sol alt köşesinin ve sağ üst köşesinin koordinatlarını temsil eder.

```csharp
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
```

## 4. Adım: Resmin eklenmesi gereken sayfayı alın

Görüntüyü PDF belgesinin belirli bir sayfasına eklemek için önce o sayfayı almamız gerekir. Bu örnekte, görüntüyü belgenin ikinci sayfasına (dizin 1) ekliyoruz.

```csharp
Page page = pdfDocument.Pages[1];
```

## 5. Adım: Görüntüyü bir akıştan yükleyin

Şimdi PDF belgesine eklemek istediğimiz görseli yükleyeceğiz. Bu örnek, adında bir görüntü dosyanız olduğunu varsayar.`aspose-logo.jpg` belgenizle aynı dizinde. Gerekirse dosya adını değiştirin.

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
```

## 6. Adım: Resmi Sayfa Varlıklarına Ekleyin

Görüntüyü PDF belgesinde kullanmak için, onu sayfanın kaynak görüntü koleksiyonuna eklememiz gerekir.

```csharp
page.Resources.Images.Add(imageStream);
```

## 7. Adım: Geçerli grafik durumunu kaydedin

 Görüntüyü çizmeden önce, mevcut grafik durumunu kullanarak kaydetmemiz gerekir.`GSave` Şebeke. Bu, grafik durumundaki değişikliklerin daha sonra geri alınabilmesini sağlar.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
```

## 8. Adım: Dikdörtgen ve Matris nesneleri oluşturun

 Şimdi bir oluşturacağız`Rectangle` nesne ve bir`Matrix` nesne. Dikdörtgen görüntünün konumunu ve boyutunu temsil ederken, matris görüntünün nasıl yerleştirilmesi gerektiğini tanımlar.

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lower

LeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
```

## 9. Adım: Görüntü yerleşimi için matrisi birleştirin

 Resmin dikdörtgene nasıl yerleştirilmesi gerektiğini belirtmek için`ConcatenateMatrix`Şebeke. Bu operatör, görüntünün koordinat uzayını sayfanın koordinat uzayına eşleyen dönüşüm matrisini tanımlar.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
```

## Adım 10: Resmi çizin

 Bu adımda, görüntüyü kullanarak sayfadaki resmi çizeceğiz.`Do` Şebeke. bu`Do` operatör görüntü adını kaynaklardan alır ve sayfaya çizer.

```csharp
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
```

## 11. Adım: Grafik durumunu geri yükleyin

 Resmi çizdikten sonra, önceki grafik durumunu kullanarak geri yüklememiz gerekiyor.`GRestore` Şebeke.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
```

## 12. Adım: Güncellenen belgeyi kaydedin

 Son olarak, güncellenen belgeyi yeni bir dosyaya kaydedeceğiz. güncelle`dataDir` istenen çıktı dizini ve dosya adı ile değişken.

```csharp
dataDir = dataDir + "AddImage_out.pdf";
pdfDocument.Save(dataDir);
```

### Aspose.PDF for .NET kullanarak Resim Ekleme için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir+ "AddImage.pdf");
// Koordinatları ayarla
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
// Resmin eklenmesi gereken sayfayı alın
Page page = pdfDocument.Pages[1];
// Görüntüyü akışa yükle
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
// Sayfa Kaynaklarının Görseller koleksiyonuna resim ekleyin
page.Resources.Images.Add(imageStream);
// GSave operatörünü kullanma: bu operatör mevcut grafik durumunu kaydeder
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
// Dikdörtgen ve Matris nesneleri oluşturma
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
//ConcatenateMatrix (concatenate matrix) operatörünü kullanma: görüntünün nasıl yerleştirilmesi gerektiğini tanımlar
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
// Do işlecini kullanma: bu işleç görüntüyü çizer
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
// GRestore operatörünü kullanma: bu operatör grafik durumunu geri yükler
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
dataDir = dataDir + "AddImage_out.pdf";
// Güncellenen belgeyi kaydet
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage added successfully.\nFile saved at " + dataDir); 
```

## Çözüm

Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesine nasıl resim ekleyeceğimizi öğrendik. Belgeyi açmaktan güncellenmiş sürümü kaydetmeye kadar her adımı ayrıntılı olarak ele aldık. Bu kılavuzu takip ederek, artık görüntüleri C# ve Aspose.PDF kullanarak programlı olarak PDF dosyalarınıza gömebilmelisiniz.