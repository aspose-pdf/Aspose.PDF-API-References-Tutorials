---
title: PDF Dosyasına Resim Ekle
linktitle: PDF Dosyasına Resim Ekle
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET'i kullanarak PDF dosyasına kolayca resim ekleyin.
type: docs
weight: 10
url: /tr/net/programming-with-images/add-image/
---
Bu kılavuz, Aspose.PDF for .NET kullanarak PDF dosyasına nasıl resim ekleyeceğinizi adım adım anlatacaktır. Ortamınızı zaten kurduğunuzdan emin olun ve aşağıdaki adımları izleyin:

## 1. Adım: Belge dizinini tanımlayın

 Başlamadan önce belgeler için doğru dizini ayarladığınızdan emin olun. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` PDF belgenizin bulunduğu dizinin yolunu içeren kodda.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Belgeyi açın

Bu adımda PDF belgesini aşağıdaki komutu kullanarak açacağız:`Document` Aspose.PDF sınıfı. Kullan`Document` yapıcıya gidin ve yolu PDF belgesine iletin.

```csharp
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
```

## 3. Adım: Görüntü Koordinatlarını Ayarlayın

 Eklemek istediğiniz görselin koordinatlarını ayarlayın. Değişkenler`lowerLeftX`, `lowerLeftY`, `upperRightX` Ve`upperRightY` sırasıyla görüntünün sol alt köşesinin ve sağ üst köşesinin koordinatlarını temsil eder.

```csharp
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
```

## 4. Adım: Resmin eklenmesi gereken sayfayı alın

Görüntüyü PDF belgesinin belirli bir sayfasına eklemek için önce o sayfayı almamız gerekir. Bu örnekte görseli belgenin ikinci sayfasına (indeks 1) ekliyoruz.

```csharp
Page page = pdfDocument.Pages[1];
```

## 5. Adım: Görüntüyü bir akıştan yükleyin

 Artık PDF belgesine eklemek istediğimiz görseli yükleyeceğiz. Bu örnekte, adında bir görüntü dosyanız olduğu varsayılmaktadır.`aspose-logo.jpg` belgenizle aynı dizinde. Gerekirse dosya adını değiştirin.

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
```

## 6. Adım: Resmi Sayfa Varlıklarına Ekleme

Resmi PDF belgesinde kullanmak için onu sayfanın kaynak resim koleksiyonuna eklememiz gerekir.

```csharp
page.Resources.Images.Add(imageStream);
```

## 7. Adım: Mevcut grafik durumunu kaydedin

 Resmi çizmeden önce mevcut grafik durumunu aşağıdaki komutu kullanarak kaydetmemiz gerekir:`GSave` Şebeke. Bu, grafik durumundaki değişikliklerin daha sonra geri alınabilmesini sağlar.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
```

## Adım 8: Rectangle ve Matrix nesneleri oluşturun

 Şimdi bir oluşturacağız`Rectangle` nesne ve bir`Matrix`nesne. Dikdörtgen görüntünün konumunu ve boyutunu temsil ederken matris görüntünün nasıl yerleştirilmesi gerektiğini tanımlar.

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lower

LeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
```

## Adım 9: Görüntü yerleştirme için matrisi birleştirin

 Resmin dikdörtgene nasıl yerleştirileceğini belirtmek için şunu kullanırız:`ConcatenateMatrix` Şebeke. Bu operatör, görüntünün koordinat alanını sayfanın koordinat alanına eşleyen dönüşüm matrisini tanımlar.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
```

## Adım 10: Resmi çizin

 Bu adımda sayfadaki resmi aşağıdaki komutu kullanarak çizeceğiz:`Do` Şebeke.`Do` operatör görsel adını kaynaklardan alır ve sayfaya çizer.

```csharp
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
```

## 11. Adım: Grafik durumunu geri yükleyin

 Görüntüyü çizdikten sonra, aşağıdaki grafik durumunu kullanarak önceki grafik durumunu geri yüklememiz gerekir:`GRestore` Şebeke.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
```

## Adım 12: Güncellenen belgeyi kaydedin

 Son olarak güncellenen belgeyi yeni bir dosyaya kaydedeceğiz. Güncelleme`dataDir` İstenilen çıktı dizini ve dosya adı ile değişken.

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
//Resmin eklenmesi gereken sayfayı alın
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
// ConcatenateMatrix (birleştirme matrisi) operatörünü kullanma: görüntünün nasıl yerleştirilmesi gerektiğini tanımlar
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
// Do operatörünü kullanma: Bu operatör görüntüyü çizer
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
// GRestore operatörünü kullanma: bu operatör grafik durumunu geri yükler
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
dataDir = dataDir + "AddImage_out.pdf";
// Güncellenen belgeyi kaydet
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage added successfully.\nFile saved at " + dataDir); 
```

## Çözüm

Bu eğitimde Aspose.PDF for .NET kullanarak bir PDF belgesine nasıl resim ekleneceğini öğrendik. Belgeyi açmaktan güncellenmiş sürümü kaydetmeye kadar her adımı ayrıntılı olarak ele aldık. Bu kılavuzu takip ederek artık C# ve Aspose.PDF kullanarak görüntüleri programlı olarak PDF dosyalarınıza gömebilirsiniz.

### PDF dosyasına resim eklemek için SSS

#### S: Neden bir PDF belgesine resim eklemek isteyeyim?

C: Bir PDF belgesine resim eklemek, görsel içeriği geliştirebilir, ek bağlam sağlayabilir veya PDF dosyalarınıza logo ve grafikler ekleyebilir.

#### S: Bir PDF belgesindeki belirli sayfalara resim ekleyebilir miyim?

C: Evet, görseli eklemek istediğiniz sayfayı belirtebilirsiniz. Sağlanan kodda görsel, PDF belgesinin ikinci sayfasına eklenir.

#### S: Eklenen görüntünün konumunu ve boyutunu nasıl ayarlayabilirim?

 C: Değiştirebilirsiniz`lowerLeftX`, `lowerLeftY`, `upperRightX` , Ve`upperRightY` Görüntünün koordinatlarını ayarlamak ve boyutunu ve sayfadaki konumunu kontrol etmek için koddaki değişkenler.

#### S: Bu yöntemi kullanarak ne tür görüntü formatlarını ekleyebilirim?

C: Sağlanan kod örneği, bir JPG resmi yüklediğinizi varsayar (`aspose-logo.jpg`). Aspose.PDF for .NET PNG, BMP, GIF ve daha fazlası dahil olmak üzere çeşitli görüntü formatlarını destekler.

#### S: Eklenen görüntünün belirtilen koordinatlara uyduğundan nasıl emin olabilirim?

 C: Koordinatları ve boyutu ayarladığınızdan emin olun.`Rectangle` nesne (`rectangle`görüntünün boyutlarına ve sayfadaki istenen yerleşimine uyacak şekilde.

#### S: Tek bir PDF sayfasına birden fazla resim ekleyebilir miyim?

C: Evet, her görüntü için işlemi tekrarlayarak ve koordinatları ve diğer parametreleri buna göre ayarlayarak tek bir PDF sayfasına birden fazla görüntü ekleyebilirsiniz.

####  S: Nasıl`GSave` and `GRestore` operator work in the code?

 C:`GSave` operatörü mevcut grafik durumunu kaydederek genel grafik bağlamını etkilemeden değişiklik yapmanıza olanak tanır.`GRestore` operatör, değişiklikler yapıldıktan sonra önceki grafik durumunu geri yükler.

#### S: Görüntü dosyası belirtilen yolda bulunamazsa ne olur?

C: Görüntü dosyası belirtilen yolda bulunamazsa, görüntü akışını yüklemeye çalışırken kod bir istisna oluşturacaktır. Görüntü dosyasının doğru dizinde bulunduğundan emin olun.

#### S: Görüntü yerleşimini ve görünümünü daha da özelleştirebilir miyim?

 C: Evet, resmin görünümünü değiştirerek özelleştirebilirsiniz.`Matrix`nesne ve kod içindeki diğer operatörlerin ayarlanması. Gelişmiş özelleştirme için Aspose.PDF belgelerine bakın.

#### S: Görüntünün PDF'ye başarıyla eklenip eklenmediğini nasıl test edebilirim?

C: Görüntüyü eklemek için sağlanan kodu uyguladıktan sonra, değiştirilen PDF dosyasını açın ve görüntünün belirtilen sayfada doğru yerleşimle görüntülendiğini doğrulayın.

#### S: Resim eklemek PDF belgesinin orijinal içeriğini etkiler mi?

C: Resim eklemek PDF belgesinin orijinal içeriğini etkilemez. Görsel öğeler ekleyerek belgeyi zenginleştirir.