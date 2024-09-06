---
title: Görüntü Boyutlarına Göre Sayfa Yönlendirmesi
linktitle: Görüntü Boyutlarına Göre Sayfa Yönlendirmesi
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım kılavuzda, Aspose.PDF for .NET ile PDF'lerin nasıl oluşturulacağını ve sayfa yönünün görüntü boyutlarına göre nasıl ayarlanacağını öğrenin.
type: docs
weight: 80
url: /tr/net/document-conversion/page-orientation-according-image-dimensions/
---
## giriiş

.NET için Aspose.PDF dünyasına hoş geldiniz! PDF belgelerini programatik olarak oluşturmak, düzenlemek veya dönüştürmek istiyorsanız doğru yerdesiniz. Aspose.PDF, geliştiricilerin PDF dosyalarıyla sorunsuz bir şekilde çalışmasını sağlayan güçlü bir kütüphanedir. Bu kılavuzda, resim boyutlarına göre sayfa yönlendirmelerini ayarlama sürecinde size yol göstereceğiz. İster deneyimli bir geliştirici olun ister yeni başlıyor olun, bu eğitim size Aspose.PDF ile başlamak için ihtiyaç duyduğunuz bilgiyi sağlayacaktır.

## Ön koşullar

Koda dalmadan önce, takip etmeniz gereken her şeye sahip olduğunuzdan emin olalım:

1. Visual Studio: Makinenizde Visual Studio'nun yüklü olduğundan emin olun. .NET geliştirme için en iyi IDE'dir.
2. .NET Framework: Bu kılavuz .NET Framework kullandığınızı varsayar. Uygun sürümün yüklü olduğundan emin olun.
3.  .NET için Aspose.PDF: Kütüphaneyi şu adresten indirebilirsiniz:[Aspose web sitesi](https://releases.aspose.com/pdf/net/) Eğer önce denemek isterseniz, bir tane alabilirsiniz[ücretsiz deneme](https://releases.aspose.com/).
4. Temel C# Bilgisi: C# programlamaya aşina olmak örnekleri daha iyi anlamanıza yardımcı olacaktır.

## Paketleri İçe Aktar

Başlamak için gerekli paketleri içe aktarmanız gerekir. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:

1. Visual Studio projenizi açın.
2. Çözüm Gezgini'nde projenize sağ tıklayın ve "NuGet Paketlerini Yönet" seçeneğini seçin.
3.  Arama`Aspose.PDF` ve kurun.

Artık her şeyi ayarladığımıza göre, örneği adım adım inceleyelim.

## Adım 1: Belge Dizininizi Ayarlayın

İlk önce, resimlerinizin depolandığı belgeler dizininize giden yolu belirtmeniz gerekir. Aspose'un JPG dosyalarını arayacağı yer burasıdır.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` Resimlerinizin bulunduğu gerçek yol ile. Bu önemlidir çünkü Aspose resimlerinizi bulamazsa, PDF'yi oluşturamayacaktır.

## Adım 2: Yeni bir PDF Belgesi Oluşturun

Sonra, yeni bir PDF belge nesnesi oluşturacaksınız. Tüm görsellerinizin ekleneceği yer burasıdır.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

 Bu satır, yeni bir örneğini başlatır`Document` PDF dosyanızı temsil eden sınıf.

## Adım 3: Görüntü Dosyalarını Alın

 Şimdi belirtilen dizinden tüm JPG dosyalarını alalım. Bu, şu şekilde yapılır:`Directory.GetFiles` Yöntem.

```csharp
string[] fileEntries = Directory.GetFiles(dataDir, "*.JPG");
```

Bu satır size JPG formatıyla eşleşen bir dosya adı dizisi verecektir. Bunun işe yaraması için dizininizin bazı JPG görüntüleri içerdiğinden emin olun!

## Adım 4: Her Görüntüyü Döngüye Alın

Her resim dosyasında döngüye girmeniz ve onu PDF belgesine eklemeniz gerekecek. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:

```csharp
int counter;
for (counter = 0; counter < fileEntries.Length - 1; counter++)
{
    // Bir sayfa nesnesi oluşturun
    Aspose.Pdf.Page page = doc.Pages.Add();
```

 Bu döngüde, her resim için yeni bir sayfa oluşturuyorsunuz.`doc.Pages.Add()` yöntemi PDF belgenize yeni bir sayfa ekler.

## Adım 5: Bir Görüntü Nesnesi Oluşturun

 Her bir görüntü için bir tane oluşturmanız gerekir`Image` Görüntü verilerini tutacak nesne.

```csharp
    Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
    image1.File = fileEntries[counter];
```

 Burada, geçerli görüntü dosyasını şuraya atıyorsunuz:`Image` nesne. Bu, PDF'e resim eklemek için önemlidir.

## Adım 6: Görüntü Boyutlarını Kontrol Edin

Resmi PDF'e eklemeden önce sayfa yönünü belirlemek için boyutlarını kontrol etmeniz gerekir.

```csharp
    Bitmap myimage = new Bitmap(fileEntries[counter]);
    if (myimage.Width > page.PageInfo.Width)
        page.PageInfo.IsLandscape = true;
    else
        page.PageInfo.IsLandscape = false;
```

Bu kod parçacığı, görüntünün genişliğinin sayfa genişliğinden büyük olup olmadığını kontrol eder. Büyükse, sayfa yönü yatay olarak ayarlanır; aksi takdirde, dikey modda kalır.

## Adım 7: Resmi PDF'e Ekleyin

Artık yönlendirmeyi ayarladığınıza göre, resmi PDF belgesine eklemenin zamanı geldi.

```csharp
    page.Paragraphs.Add(image1);
}
```

Bu satır, resmi geçerli sayfanın paragraf koleksiyonuna ekler. Bir resmi çerçeveye yerleştirmek gibidir!

## Adım 8: PDF Belgesini Kaydedin

Son olarak PDF belgenizi belirttiğiniz dizine kaydetmeniz gerekmektedir.

```csharp
doc.Save(dataDir + "SetPageOrientation_out.pdf");
```

 Bu satır belgeyi şu adla kaydeder:`SetPageOrientation_out.pdf`Yeni oluşturulan PDF'i belgeler dizininizde kontrol ettiğinizden emin olun!

## Çözüm

Ve işte karşınızda! Aspose.PDF for .NET kullanarak, sayfa yönünü resimlerin boyutlarına göre ayarlayarak bir PDF belgesini başarıyla oluşturdunuz. Bu güçlü kütüphane, uygulamalarınızda PDF dosyalarıyla çalışmak için bir olasılıklar dünyasının kapılarını açar. İster raporlar, ister faturalar veya başka herhangi bir tür belge üretiyor olun, Aspose.PDF sizin için her şeyi yapar.

## SSS

### Aspose.PDF for .NET nedir?
Aspose.PDF for .NET, geliştiricilerin PDF belgelerini programlı bir şekilde oluşturmalarına, düzenlemelerine ve dönüştürmelerine olanak tanıyan bir kütüphanedir.

### Aspose.PDF'yi nasıl yüklerim?
 Aspose.PDF'yi Visual Studio'daki NuGet Paket Yöneticisi aracılığıyla yükleyebilir veya şu adresten indirebilirsiniz:[Aspose web sitesi](https://releases.aspose.com/pdf/net/).

### Aspose.PDF'yi ücretsiz kullanabilir miyim?
 Evet, Aspose bir[ücretsiz deneme](https://releases.aspose.com/) satın almadan önce kütüphaneyi test etmeniz için.

### Aspose.PDF için desteği nerede bulabilirim?
Destek için buraya tıklayabilirsiniz.[Aspose forumu](https://forum.aspose.com/c/pdf/10).

### Aspose kullanarak hangi dosya türlerini PDF'ye dönüştürebilirim?
Aspose.PDF, resimler, Word belgeleri, Excel elektronik tabloları ve daha fazlası dahil olmak üzere çok çeşitli dosya biçimlerini destekler.