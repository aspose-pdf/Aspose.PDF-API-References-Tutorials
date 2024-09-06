---
title: PDF Dosyasına Resim Ekle
linktitle: PDF Dosyasına Resim Ekle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyasına kolayca resim ekleyin.
type: docs
weight: 10
url: /tr/net/programming-with-images/add-image/
---
Bu kılavuz, Aspose.PDF for .NET kullanarak PDF dosyasına nasıl resim ekleyeceğinizi adım adım gösterecektir. Ortamınızı önceden ayarladığınızdan emin olun ve aşağıdaki adımları izleyin:

## Adım 1: Belge dizinini tanımlayın

Başlamadan önce, belgeler için doğru dizini ayarladığınızdan emin olun. Değiştir`"YOUR DOCUMENT DIRECTORY"` PDF belgenizin bulunduğu dizinin yolunu içeren kodda.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Belgeyi açın

 Bu adımda PDF belgesini şu şekilde açacağız:`Document` Aspose.PDF sınıfı. Kullanın`Document` oluşturucuyu kullanın ve PDF belgesinin yolunu geçirin.

```csharp
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
```

## Adım 3: Görüntü Koordinatlarını Ayarlayın

 Eklemek istediğiniz resmin koordinatlarını ayarlayın. Değişkenler`lowerLeftX`, `lowerLeftY`, `upperRightX` Ve`upperRightY` sırasıyla görüntünün sol alt köşesinin ve sağ üst köşesinin koordinatlarını temsil eder.

```csharp
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
```

## Adım 4: Resmin eklenmesi gereken sayfayı alın

Görüntüyü PDF belgesinin belirli bir sayfasına eklemek için, önce o sayfayı almamız gerekir. Bu örnekte, görüntüyü belgenin ikinci sayfasına (indeks 1) ekliyoruz.

```csharp
Page page = pdfDocument.Pages[1];
```

## Adım 5: Görüntüyü bir akıştan yükleyin

 Şimdi PDF belgesine eklemek istediğimiz resmi yükleyeceğiz. Bu örnek, adında bir resim dosyanız olduğunu varsayar.`aspose-logo.jpg` belgenizle aynı dizinde. Gerekirse dosya adını değiştirin.

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
```

## Adım 6: Görüntüyü Sayfa Varlıklarına Ekleyin

PDF belgesinde yer alan görseli kullanabilmek için, onu sayfanın kaynak görsel koleksiyonuna eklememiz gerekmektedir.

```csharp
page.Resources.Images.Add(imageStream);
```

## Adım 7: Mevcut grafik durumunu kaydedin

 Resmi çizmeden önce, mevcut grafik durumunu kullanarak kaydetmemiz gerekir.`GSave` operatörü. Bu, grafik durumunda yapılan değişikliklerin daha sonra geri alınabilmesini sağlar.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
```

## Adım 8: Dikdörtgen ve Matris nesneleri oluşturun

 Şimdi bir tane yaratacağız`Rectangle` nesne ve bir`Matrix` nesne. Dikdörtgen, görüntünün konumunu ve boyutunu temsil ederken, matris görüntünün nasıl yerleştirileceğini tanımlar.

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lower

LeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
```

## Adım 9: Görüntü yerleştirme için matrisi birleştirin

 Resmin dikdörtgene nasıl yerleştirileceğini belirtmek için şunu kullanırız:`ConcatenateMatrix` operatörü. Bu operatör, görüntünün koordinat alanını sayfanın koordinat alanına eşleyen dönüşüm matrisini tanımlar.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
```

## Adım 10: Resmi çizin

 Bu adımda sayfadaki resmi şu şekilde çizeceğiz:`Do` operatör.`Do`operatörü kaynaklardan resim adını alır ve sayfaya çizer.

```csharp
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
```

## Adım 11: Grafik durumunu geri yükleyin

 Resmi çizdikten sonra, önceki grafik durumunu kullanarak geri yüklememiz gerekiyor.`GRestore` operatör.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
```

## Adım 12: Güncellenen belgeyi kaydedin

 Son olarak, güncellenen belgeyi yeni bir dosyaya kaydedeceğiz.`dataDir` İstenilen çıktı dizini ve dosya adı ile değişken.

```csharp
dataDir = dataDir + "AddImage_out.pdf";
pdfDocument.Save(dataDir);
```

### .NET için Aspose.PDF kullanarak Resim Ekleme için örnek kaynak kodu 
```csharp
// Belgeler dizinine giden yol.
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
// Sayfa Kaynaklarının Resimler koleksiyonuna resim ekle
page.Resources.Images.Add(imageStream);
// GSave operatörünü kullanma: bu operatör geçerli grafik durumunu kaydeder
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
// Dikdörtgen ve Matris nesneleri oluşturun
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
// ConcatenateMatrix (matrisi birleştir) operatörünü kullanma: görüntünün nasıl yerleştirileceğini tanımlar
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
// Do operatörünü kullanma: bu operatör görüntü çizer
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
// GRestore operatörünü kullanma: bu operatör grafik durumunu geri yükler
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
dataDir = dataDir + "AddImage_out.pdf";
// Güncellenen belgeyi kaydet
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage added successfully.\nFile saved at " + dataDir); 
```

## Çözüm

Bu eğitimde, .NET için Aspose.PDF kullanarak bir PDF belgesine nasıl resim ekleneceğini öğrendik. Belgeyi açmaktan güncellenmiş sürümü kaydetmeye kadar her adımı ayrıntılı olarak ele aldık. Bu kılavuzu izleyerek artık C# ve Aspose.PDF kullanarak PDF dosyalarınıza programatik olarak resim gömebilmeniz gerekir.

### PDF dosyasına resim eklemeyle ilgili SSS

#### S: Neden bir PDF belgesine resim eklemek isteyeyim?

A: PDF belgesine resim eklemek görsel içeriği geliştirebilir, ek bağlam sağlayabilir veya PDF dosyalarınıza logo ve grafikler ekleyebilir.

#### S: PDF belgesinin belirli sayfalarına resim ekleyebilir miyim?

A: Evet, resmi eklemek istediğiniz sayfayı belirtebilirsiniz. Sağlanan kodda resim, PDF belgesinin ikinci sayfasına eklenir.

#### S: Eklenen görselin konumunu ve boyutunu nasıl ayarlarım?

 A: Değiştirebilirsiniz`lowerLeftX`, `lowerLeftY`, `upperRightX` , Ve`upperRightY` Resmin koordinatlarını ayarlamak ve sayfadaki boyutunu ve konumunu kontrol etmek için koddaki değişkenler.

#### S: Bu yöntemi kullanarak hangi tür resim formatlarını ekleyebilirim?

A: Sağlanan kod örneği, bir JPG resmi yüklediğinizi varsayar (`aspose-logo.jpg`). Aspose.PDF for .NET, PNG, BMP, GIF ve daha fazlası dahil olmak üzere çeşitli resim formatlarını destekler.

#### S: Eklenen görselin belirtilen koordinatlara uyduğundan nasıl emin olabilirim?

 A: Koordinatları ve boyutunu ayarladığınızdan emin olun.`Rectangle` nesne (`rectangle`) resmin boyutlarına ve sayfadaki istenilen yerleşimine uyacak şekilde ayarlanmalıdır.

#### S: Tek bir PDF sayfasına birden fazla resim ekleyebilir miyim?

C: Evet, her resim için işlemi tekrarlayarak ve koordinatları ve diğer parametreleri buna göre ayarlayarak tek bir PDF sayfasına birden fazla resim ekleyebilirsiniz.

####  S: Nasıl?`GSave` and `GRestore` operator work in the code?

 A:`GSave` operatör geçerli grafik durumunu kaydeder ve genel grafik bağlamını etkilemeden değişiklikler yapmanıza olanak tanır.`GRestore` operatör değişiklikler yapıldıktan sonra önceki grafik durumuna geri döner.

#### S: Resim dosyası belirtilen yolda bulunmazsa ne olur?

A: Görüntü dosyası belirtilen yolda bulunmazsa, kod görüntü akışını yüklemeye çalışırken bir istisna atar. Görüntü dosyasının doğru dizinde bulunduğundan emin olun.

#### S: Görüntü yerleşimini ve görünümünü daha da özelleştirebilir miyim?

 A: Evet, görüntüyü değiştirerek görüntü görünümünü özelleştirebilirsiniz.`Matrix` nesne ve kod içindeki diğer operatörleri ayarlama. Gelişmiş özelleştirme için Aspose.PDF belgelerine bakın.

#### S: Görüntünün PDF'e başarıyla eklendiğini nasıl test edebilirim?

A: Sağlanan kodu uygulayarak görseli ekledikten sonra, değiştirilmiş PDF dosyasını açın ve görselin belirtilen sayfada doğru yerleşimle görüntülendiğini doğrulayın.

#### S: Resim eklemek PDF belgesinin orijinal içeriğini etkiler mi?

A: Resim eklemek PDF belgesinin orijinal içeriğini etkilemez. Görsel öğeler ekleyerek belgeyi geliştirir.