---
title: Resim Boyutlarına Göre Sayfa Yönü
linktitle: Resim Boyutlarına Göre Sayfa Yönü
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile görüntü boyutlarına göre sayfa yönünü ayarlamak için adım adım kılavuz.
type: docs
weight: 80
url: /tr/net/document-conversion/page-orientation-according-image-dimensions/
---
Bu eğitimde, Aspose.PDF for .NET'i kullanarak görüntünün boyutlarına göre sayfa yönünü ayarlama sürecinde size yol göstereceğiz. Belirli bir dizindeki JPG görsellerinin listesi boyunca dolaşacağız ve her görselin genişliğine göre sayfa yönünü otomatik olarak ayarlayacağız. Bunu başarmak için aşağıdaki adımları izleyin.

## Önkoşullar
Başlamadan önce aşağıdaki önkoşulları karşıladığınızdan emin olun:

- C# programlama dili hakkında temel bilgiler.
- Sisteminizde yüklü olan .NET için Aspose.PDF kütüphanesi.
- Visual Studio gibi bir geliştirme ortamı.

## 1. Adım: JPG görsellerine göz atın
Bu adımda belirli bir dizindeki tüm JPG görsellerine göz atacağız. Aşağıdaki kodu izleyin:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Yeni bir PDF belgesi oluştur
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Belirli bir dizindeki tüm JPG dosyalarının adlarını alın
string[] fileEntries = Directory.GetFiles(dataDir, "*.JPG");
```

 Değiştirdiğinizden emin olun`"YOUR DOCUMENTS DIRECTORY"` JPG resimlerinizin bulunduğu gerçek dizinle.

## Adım 2: Sayfanın ve görselin oluşturulması
JPG dosyalarına göz attıktan sonra her dosya için bir sayfa ve görsel oluşturacağız. Aşağıdaki kodu kullanın:

```csharp
int counter;
for (counter = 0; counter < fileEntries.Length - 1; counter++)
{
// Sayfa nesnesi oluşturma
Aspose.Pdf.Page page = doc.Pages.Add();

// Bir Görüntü nesnesi oluşturma
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = fileEntries[counter];
```

## 3. Adım: Görüntü boyutlarını kontrol etme
Şimdi sayfa yönünü belirlemek için her görselin boyutlarını kontrol edelim. Aşağıdaki kodu kullanın:

```csharp
// Görüntü dosyasından bilgi almak için bir BitMap nesnesi oluşturun
Bitmap myimage = new Bitmap(fileEntries[counter]);

// Resmin genişliğinin sayfa genişliğinden büyük olup olmadığını kontrol edin
if (myimage.Width > page.PageInfo.Width)
//

  If the width of the image is greater than the width of the page, set the page orientation to landscape
page.PageInfo.IsLandscape = true;
else
// Resmin genişliği sayfa genişliğinden azsa sayfanın yönünü dikey olarak ayarlayın
page.PageInfo.IsLandscape = false;
```

## Adım 4: Görüntüyü PDF belgesine ekleme
Görselin boyutlarını kontrol ettikten sonra görseli PDF belgesinin paragraf koleksiyonuna ekleyeceğiz. Aşağıdaki kodu kullanın:

```csharp
// Görüntüyü PDF belgesinin paragraf koleksiyonuna ekleyin
page.Paragraphs.Add(image1);
```

## Adım 5: PDF dosyasını kaydetme
Tüm görselleri PDF belgesine ekledikten sonra artık ortaya çıkan PDF dosyasını kaydedebiliriz. İşte son adım:

```csharp
// PDF dosyasını kaydedin
doc.Save(dataDir + "SetPageOrientation_out.pdf");
```

 Yer değiştirmek`"YOUR DOCUMENTS DIRECTORY"` Çıktı PDF dosyasını kaydetmek istediğiniz dizini seçin.

### Aspose.PDF for .NET kullanarak Görüntü Boyutlarına Göre Sayfa Yönlendirmesi için örnek kaynak kodu

```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Belirli bir Dizindeki tüm JPG dosyalarının adlarını alın
string[] fileEntries = Directory.GetFiles(dataDir, "*.JPG");

int counter;
for (counter = 0; counter < fileEntries.Length - 1; counter++)
{
	// Sayfa nesnesi oluşturma
	Aspose.Pdf.Page page = doc.Pages.Add();

	// Bir görüntü nesnesi oluşturun
	Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
	image1.File = fileEntries[counter];

	// Görüntü dosyasının bilgilerini almak için bir BitMap nesnesi oluşturun
	Bitmap myimage = new Bitmap(fileEntries[counter]);
	// Resim dosyasının genişliğinin Sayfa genişliğinden büyük olup olmadığını kontrol edin
	if (myimage.Width > page.PageInfo.Width)
		// Görüntü genişliği sayfa genişliğinden büyükse sayfa yönünü Yatay olarak ayarlayın
		page.PageInfo.IsLandscape = true;
	else
		// Görüntü genişliği sayfa genişliğinden azsa sayfa yönünü Dikey olarak ayarlayın
		page.PageInfo.IsLandscape = false;
	// Görüntüyü PDF belgesinin paragraf koleksiyonuna ekleyin
	page.Paragraphs.Add(image1);
}
// Pdf dosyasını kaydedin
doc.Save(dataDir + "SetPageOrientation_out.pdf");
```

## Çözüm
Bu eğitimde, Aspose.PDF for .NET'i kullanarak görüntünün boyutlarına göre sayfa yönlendirmesini adım adım ayarlama sürecini ele aldık. Yukarıda özetlenen talimatları izleyerek artık her görüntü için doğru sayfa yönüne sahip bir PDF belgesi oluşturabilmeniz gerekir. Bu özellik, farklı boyutlarda resimleriniz olduğunda ve bunları bir PDF belgesine gömmek istediğinizde kullanışlıdır.

### SSS'ler

#### S: Sayfa yönünü görsel boyutlarına göre ayarlamak için JPG yerine başka görsel formatlarını kullanabilir miyim?

C: Evet, görüntü boyutlarına göre sayfa yönünü ayarlamak için JPG'nin yanı sıra PNG, BMP veya GIF gibi diğer görüntü formatlarını da kullanabilirsiniz. Sağlanan kod, ".JPG" uzantılı tüm resim dosyalarında döngü yapar, ancak onu diğer resim formatlarını da içerecek şekilde değiştirebilirsiniz.

#### S: Bir görselin boyutları sayfa genişliğine tam olarak eşitse ne olur?

C: Bir görselin genişliği sayfa genişliğine tam olarak eşitse sayfa yönü dikey olarak ayarlanacaktır. Sağlanan kodda, sayfa yönü yalnızca görüntünün genişliği sayfa genişliğinden büyükse yatay olarak ayarlanır.

#### S: Sayfa yönlendirme mantığını belirli gereksinimlere göre özelleştirebilir miyim?

C: Evet, sayfa yönlendirme mantığını belirli gereksinimlere göre özelleştirebilirsiniz. Örneğin, sayfa yönlendirmesinin ne zaman yatay veya dikey olarak ayarlanması gerektiğini belirlemek için bir eşik değeri ayarlayabilirsiniz. Ayrıca sayfa yönünü belirlemek için görüntü yüksekliği veya en boy oranı gibi faktörleri de göz önünde bulundurabilirsiniz.

#### S: PDF belgesine görsellerin yanı sıra metin veya tablolar gibi başka içerikler de ekleyebilir miyim?

C: Evet, PDF belgesine görsellerin yanı sıra metin veya tablolar gibi başka içerikler de ekleyebilirsiniz. Aspose.PDF for .NET, PDF belgelerini yönetmek için sayfalara metin, resim, tablo ve diğer öğelerin eklenmesi de dahil olmak üzere zengin özellikler sunar.