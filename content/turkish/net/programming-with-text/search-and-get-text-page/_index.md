---
title: PDF Dosyasında Metin Sayfasını Ara ve Al
linktitle: PDF Dosyasında Metin Sayfasını Ara ve Al
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyasındaki belirli bir sayfadaki metni nasıl arayacağınızı ve alacağınızı öğrenin.
type: docs
weight: 430
url: /tr/net/programming-with-text/search-and-get-text-page/
---
## giriiş

Hiç bir PDF belgesinde belirli bir metni aramanız ve daha sonra kullanmak üzere çıkarmanız gerektiğini fark ettiniz mi? Belki de belgeleri işleyen ve hassas veri çıkarma gerektiren bir uygulama oluşturuyorsunuz veya belki de sadece PDF'leri verimli bir şekilde ayrıştırmanız gerekiyor. Durumunuz ne olursa olsun, doğru yerdesiniz! Bu eğitimde, .NET için Aspose.PDF kullanarak bir PDF dosyasındaki bir sayfadan metin arama ve alma konusuna derinlemesine ineceğiz. İster yeni başlayan ister deneyimli bir geliştirici olun, bu kılavuz sizi her adımda sohbet tarzında ve ilgi çekici bir şekilde yönlendirecektir. Başlamaya hazır mısınız? Hadi başlayalım!

## Ön koşullar

Kodlamaya başlamadan önce ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım:

1.  Aspose.PDF for .NET Kütüphanesi: Buradan indirebilirsiniz[Burada](https://releases.aspose.com/pdf/net/) veya aynı bağlantıdan ücretsiz deneme sürümünü edinin. Satın almak için şuraya gidin:[Aspose mağazası](https://purchase.aspose.com/buy).
2. .NET Framework: Visual Studio gibi çalışan bir .NET geliştirme ortamına ihtiyacınız olacak.
3. Bir PDF dosyası: Metni arayıp çıkarabileceğimiz bir örnek PDF dosyasına ihtiyacınız olacak. Bu eğitim için dosyanın adının şu olduğunu varsayalım:`SearchAndGetTextPage.pdf`.

## Paketleri İçe Aktar

İlk önce, Aspose.PDF for .NET ile çalışmak için gerekli ad alanlarını içe aktarmamız gerekiyor. Bunların kodunuzun en üstüne eklendiğinden emin olun.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System
```

Artık ön koşulları ele aldığımıza göre, kodu adım adım parçalara ayıralım. Her adım, takip etmeyi kolaylaştırmak için açıkça belirtilmiştir.

## Adım 1: Belgeler Dizininize Giden Yolu Ayarlayın

PDF'nizle etkileşime girmeden önce, PDF belgenizin depolandığı yolu tanımlamanız gerekir. Bu, programın dosyaya erişebilmesini sağlar.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

-  dataDir: Bu, PDF dosyalarınızın saklandığı klasörün yoludur. Değiştir`"YOUR DOCUMENT DIRECTORY"` PDF'nin bulunduğu gerçek yol ile.

## Adım 2: PDF Belgesini Yükleyin

Bir sonraki adım, PDF belgesini belleğe yüklemek ve onunla çalışmaktır. İşte nasıl:

```csharp
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

- Belge: Bu, PDF dosyasını yükleyen Aspose.PDF sınıfıdır.
- pdfDocument: PDF dosyanızın yüklendikten sonra saklandığı değişken.

## Adım 3: Bir Metin Emici Nesne Oluşturun

 The`TextFragmentAbsorber`class, PDF içinde belirli bir metni aramanıza olanak tanır. Belirli bir arama ifadesinin tüm örneklerini bulmak için bu sınıfın bir örneğini oluşturalım.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

- TextFragmentAbsorber: Bu sınıf PDF'den metin bulup çıkarmaktan sorumludur.
- "Şekil": Bunu PDF içinde aramak istediğiniz herhangi bir metinle değiştirin.

## Adım 4: Metin Emiciyi Tüm PDF'ye Uygulayın

Metin emici ayarlandıktan sonra, programa PDF'in tüm sayfalarını aramasını söylemeniz gerekir.

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

- Accept(): Bu metot, metin emiciyi PDF'e uygular ve belirttiğiniz metni bulmak için her sayfayı tarar.

## Adım 5: Çıkarılan Metni Alın ve Üzerinde Yineleme Yapın

Artık PDF'yi taradığımıza göre, sonuçları alma ve görüntüleme zamanı geldi. Çıkarılan metin parçaları arasında döngü yapacağız.

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

- TextFragmentCollection: Bu koleksiyon, metin emici tarafından bulunan metin parçalarının tüm örneklerini tutar.

## Adım 6: Her Parçayı Döngüye Alın ve Verileri Çıkarın

Şimdi döngüye gireceğiz`textFragmentCollection` ve her metin parçasının konumu, yazı tipi ayrıntıları ve rengi gibi çeşitli özelliklerini çıkarın.

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

- TextFragment: Her parça bulunan metnin bölümlerini içerir.
- TextSegment: Her parça, metnin farklı kısımlarını temsil eden birden fazla parçaya sahip olabilir.
- TextState: Metnin yazı tipi, boyutu ve rengi hakkında ayrıntılı bilgi sağlar.

Bu döngüde, gerçek metin, konumu (X ve Y koordinatları), yazı tipi, yazı tipinin PDF'e gömülü olup olmadığı ve metnin ön plan rengi gibi ayrıntıları yazdırıyoruz.

## Çözüm

Ve işte oldu! Artık Aspose.PDF for .NET kullanarak bir PDF dosyasından metni başarıyla aradınız ve çıkardınız. Bu kütüphaneyle ne kadar esnekliğe sahip olduğunuz inanılmaz. Büyük bir belgede belirli bir metni aramanız, çıkarmanız veya özelliklerini analiz etmeniz gerekip gerekmediğine bakılmaksızın Aspose.PDF bunu kolaylaştırır. Ayrıca, ele aldığımız kodla, onu ihtiyaçlarınıza göre uyarlamak için iyi bir donanıma sahipsiniz. 

## SSS

### Birden fazla ifadeyi aynı anda arayabilir miyim?  
 Evet, birden fazla ifadeyi aramak için kodu birden fazla ifade oluşturarak değiştirebilirsiniz.`TextFragmentAbsorber` nesneler.

### Belirli bir sayfadan metni nasıl çıkarabilirim?  
 Belirli bir sayfayı hedefleyebilirsiniz.`TextFragmentAbsorber` tüm belge yerine tek bir sayfaya. Örneğin:`pdfDocument.Pages[1].Accept(textFragmentAbsorber);`.

### Aspose.PDF for .NET ücretsiz mi?  
 Aspose.PDF ticari bir üründür, ancak bunu bir[ücretsiz deneme](https://releases.aspose.com/).

### Aspose.PDF kullanarak PDF'den resim çıkarabilir miyim?  
 Evet, Aspose.PDF metne ek olarak görselleri de çıkarmanıza olanak tanır.[belgeleme](https://reference.aspose.com/pdf/net/) Daha detaylı bilgi için.

### Daha fazla yardıma veya desteğe ihtiyacım olursa ne olacak?  
 Her zaman yardım alabilirsiniz[Aspose Destek Forumu](https://forum.aspose.com/c/pdf/10).