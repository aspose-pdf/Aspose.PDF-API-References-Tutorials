---
title: Görüntü Boyutlarına Göre Sayfa Yönü
linktitle: Görüntü Boyutlarına Göre Sayfa Yönü
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile görüntü boyutlarına göre sayfa yönünü ayarlamak için adım adım kılavuz.
type: docs
weight: 80
url: /tr/net/document-conversion/page-orientation-according-image-dimensions/
---
Bu öğreticide, Aspose.PDF for .NET kullanarak bir görüntünün boyutlarına göre sayfa yönünü ayarlama sürecinde size yol göstereceğiz. Belirli bir dizindeki JPG görüntüleri listesinde dolaşacağız ve her görüntünün genişliğine göre sayfa yönünü otomatik olarak ayarlayacağız. Bunu başarmak için aşağıdaki adımları izleyin.

## Önkoşullar
Başlamadan önce, aşağıdaki ön koşulları karşıladığınızdan emin olun:

- C# programlama dili hakkında temel bilgi.
- Sisteminizde kurulu .NET için Aspose.PDF kitaplığı.
- Visual Studio gibi bir geliştirme ortamı.

## 1. Adım: JPG resimlerine göz atın
Bu adımda, belirli bir dizindeki tüm JPG resimlerine göz atacağız. Aşağıdaki kodu izleyin:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Yeni bir PDF belgesi oluştur
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Belirli bir dizindeki tüm JPG dosyalarının adlarını alın
string[] fileEntries = Directory.GetFiles(dataDir, "*.JPG");
```

 değiştirdiğinizden emin olun`"YOUR DOCUMENTS DIRECTORY"` JPG resimlerinizin bulunduğu gerçek dizinle.

## 2. Adım: Sayfanın ve görselin oluşturulması
JPG dosyalarına göz attıktan sonra her dosya için bir sayfa ve bir görsel oluşturacağız. Aşağıdaki kodu kullanın:

```csharp
int counter;
for (counter = 0; counter < fileEntries.Length - 1; counter++)
{
// Bir Sayfa nesnesi oluşturun
Aspose.Pdf.Page page = doc.Pages.Add();

// Bir Görüntü nesnesi oluşturun
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = fileEntries[counter];
```

## 3. Adım: Görüntü boyutlarını kontrol etme
Şimdi sayfa yönünü belirlemek için her görüntünün boyutlarını kontrol edelim. Aşağıdaki kodu kullanın:

```csharp
// Görüntü dosyasından bilgi almak için bir BitMap nesnesi oluşturun
Bitmap myimage = new Bitmap(fileEntries[counter]);

// Resmin genişliğinin sayfanın genişliğinden büyük olup olmadığını kontrol edin
if (myimage.Width > page.PageInfo.Width)
//

  If the width of the image is greater than the width of the page, set the page orientation to landscape
page.PageInfo.IsLandscape = true;
else
// Görüntünün genişliği sayfanın genişliğinden azsa, sayfanın yönünü dikey olarak ayarlayın.
page.PageInfo.IsLandscape = false;
```

## 4. Adım: Görüntüyü PDF belgesine ekleme
Resmin boyutlarını kontrol ettikten sonra, resmi PDF belgesinin paragraf koleksiyonuna ekleyeceğiz. Aşağıdaki kodu kullanın:

```csharp
// Görüntüyü PDF belgesinin paragraf koleksiyonuna ekleyin
page.Paragraphs.Add(image1);
```

## 5. Adım: PDF dosyasını kaydetme
Tüm görüntüleri PDF belgesine ekledikten sonra, artık ortaya çıkan PDF dosyasını kaydedebiliriz. İşte son adım:

```csharp
//PDF dosyasını kaydedin
doc.Save(dataDir + "SetPageOrientation_out.pdf");
```

 Yer değiştirmek`"YOUR DOCUMENTS DIRECTORY"` Çıktı PDF dosyasını kaydetmek istediğiniz istediğiniz dizinle.

### Aspose.PDF for .NET kullanan Görüntü Boyutlarına Göre Sayfa Yönlendirme için örnek kaynak kodu

```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Belirli bir Dizindeki tüm JPG dosyalarının adlarını alın
string[] fileEntries = Directory.GetFiles(dataDir, "*.JPG");

int counter;
for (counter = 0; counter < fileEntries.Length - 1; counter++)
{
	// Bir sayfa nesnesi oluşturun
	Aspose.Pdf.Page page = doc.Pages.Add();

	// Bir resim nesnesi oluşturun
	Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
	image1.File = fileEntries[counter];

	// Görüntü dosyasının bilgilerini almak için bir BitMap nesnesi oluşturun
	Bitmap myimage = new Bitmap(fileEntries[counter]);
	// Görüntü dosyasının genişliğinin Sayfa genişliğinden büyük olup olmadığını kontrol edin
	if (myimage.Width > page.PageInfo.Width)
		// Görüntü genişliği sayfa genişliğinden büyükse sayfa yönünü Yatay olarak ayarlayın
		page.PageInfo.IsLandscape = true;
	else
		// Görüntü genişliği sayfa genişliğinden küçükse, sayfa yönünü Dikey olarak ayarlayın
		page.PageInfo.IsLandscape = false;
	// Görüntüyü PDF belgesinin paragraflar koleksiyonuna ekleyin
	page.Paragraphs.Add(image1);
}
// Pdf dosyasını kaydedin
doc.Save(dataDir + "SetPageOrientation_out.pdf");
```

## Çözüm
Bu öğreticide, Aspose.PDF for .NET kullanarak bir görüntünün boyutlarına göre sayfa yönünü ayarlama sürecini adım adım ele aldık. Yukarıda özetlenen talimatları izleyerek, artık her görüntü için doğru sayfa yönüne sahip bir PDF belgesi oluşturabilmelisiniz. Bu özellik, farklı boyutlarda resimleriniz olduğunda ve bunları bir PDF belgesine gömmek istediğinizde kullanışlıdır.

### SSS

#### S: Resim boyutlarına göre sayfa yönünü ayarlamak için JPG yerine başka resim formatları kullanabilir miyim?

C: Evet, resim boyutlarına göre sayfa yönünü ayarlamak için JPG'ye ek olarak PNG, BMP veya GIF gibi diğer resim formatlarını kullanabilirsiniz. Sağlanan kod, ".JPG" uzantılı tüm görüntü dosyaları arasında dolaşır, ancak diğer görüntü formatlarını da içerecek şekilde değiştirebilirsiniz.

#### S: Bir resmin boyutları tam olarak sayfa genişliğine eşitse ne olur?

A: Bir görüntünün genişliği tam olarak sayfa genişliğine eşitse, sayfa yönü dikey olarak ayarlanacaktır. Sağlanan kodda, sayfa yönü yalnızca görüntünün genişliği sayfa genişliğinden büyükse yatay olarak ayarlanır.

#### S: Sayfa yönlendirme mantığını belirli gereksinimlere göre özelleştirebilir miyim?

C: Evet, sayfa yönlendirme mantığını belirli gereksinimlere göre özelleştirebilirsiniz. Örneğin, sayfa yönünün ne zaman yatay veya dikey olarak ayarlanması gerektiğini belirlemek için bir eşik değeri belirleyebilirsiniz. Ek olarak, sayfa yönünü belirlemek için görüntü yüksekliği veya en boy oranı gibi faktörleri de göz önünde bulundurabilirsiniz.

#### S: PDF belgesine resimlerle birlikte metin veya tablolar gibi başka içerikler ekleyebilir miyim?

Y: Evet, resimlerle birlikte PDF belgesine metin veya tablolar gibi başka içerikler de ekleyebilirsiniz. Aspose.PDF for .NET, PDF belgelerini işlemek için sayfalara metin, resim, tablo ve diğer öğeler eklemek dahil olmak üzere zengin bir dizi özellik sağlar.