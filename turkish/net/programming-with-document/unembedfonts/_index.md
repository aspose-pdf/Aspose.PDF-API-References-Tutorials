---
title: Yazı Tiplerini Çıkarın ve PDF Dosyalarını Optimize Edin
linktitle: Yazı Tiplerini Çıkarın ve PDF Dosyalarını Optimize Edin
second_title: Aspose.PDF for .NET API Referansı
description: Unembed Fonts'u almak ve PDF dosyalarını optimize etmek için Aspose.PDF for .NET'i nasıl kullanacağınızı öğrenin. Adım adım kılavuz.
type: docs
weight: 370
url: /tr/net/programming-with-document/unembedfonts/
---
Aspose.PDF for .NET, PDF belgeleriyle çalışmak için çok çeşitli özellikler sağlayan güçlü bir kitaplıktır. Özelliklerinden biri, gömülmemiş yazı tiplerini bir PDF belgesinden almaktır. Bu, bir PDF belgesinden yazı tiplerini çıkarmanız ve bunları diğer uygulamalarda kullanmanız gerektiğinde faydalı olabilir.

Aspose.PDF for .NET'in aşağıdaki C# kaynak kodundaki get unembed fonts özelliğini açıklamak için adım adım bir kılavuz sağlayacağız.

## 1. Adım: Belge dizinine giden yolu ayarlayın

Başlamadan önce, PDF belgemizin bulunduğu dizinin yolunu belirlememiz gerekiyor. Bu yolu "dataDir" adlı bir değişkende saklayacağız.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

"BELGE DİZİNİNİZİ", PDF belgenizin bulunduğu dizinin gerçek yolu ile değiştirin.

## Adım 2: PDF Belgesini Açın

 İlk adım, bunu yapmak istediğiniz PDF belgesini yüklemektir,`Document` .NET için Aspose.PDF sınıfı. Aşağıdaki kod parçacığı, PDF belgesinin nasıl yükleneceğini gösterir:

```csharp
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## 3. Adım: UnembedFonts Seçeneğini Ayarlayın

 Gömülü olmayan yazı tiplerini PDF belgesinden almak için,`UnembedFonts` seçeneği`true` . Bu seçenek şu adreste mevcuttur:`OptimizationOptions` sınıf. Aşağıdaki kod parçacığı, nasıl ayarlanacağını gösterir.`UnembedFonts` seçenek:

```csharp
// UnembedFonts seçeneğini ayarla
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

## 4. Adım: PDF Belgesini Optimize Edin

 ayarladıktan sonra`UnembedFonts` seçeneğini kullanarak PDF belgesini optimize edebilirsiniz.`OptimizeResources` yöntemi`Document` sınıf. Aşağıdaki kod parçacığı, PDF belgesinin nasıl optimize edileceğini gösterir:

```csharp
// OptimizationOptions kullanarak PDF belgesini optimize edin
pdfDocument.OptimizeResources(optimizeOptions);
```

## 5. Adım: Güncellenen Belgeyi Kaydedin

 PDF belgesi optimize edildikten sonra, güncellenen belgeyi`Save` yöntemi`Document`sınıf. Aşağıdaki kod parçacığı, güncellenen belgenin nasıl kaydedileceğini gösterir:

```csharp
// Güncellenen belgeyi kaydet
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## 6. Adım: Orijinali ve Küçültülmüş Dosya Boyutunu Alın

 Son olarak, PDF belgesinin orijinal ve küçültülmüş dosya boyutunu elde edebilirsiniz.`FileInfo` System.IO sınıfı. Aşağıdaki kod parçacığı, orijinal ve küçültülmüş dosya boyutunun nasıl alınacağını gösterir:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

### Aspose.PDF for .NET kullanarak Get Unembed Fonts için Örnek Kaynak Kodu

Aspose.PDF for .NET kullanarak bir PDF belgesinden gömülmemiş yazı tiplerini almak için eksiksiz örnek kaynak kodu:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// UnembedFonts seçeneğini ayarla
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
Console.WriteLine("Start");
// OptimizationOptions kullanarak PDF belgesini optimize edin
pdfDocument.OptimizeResources(optimizeOptions);
// Güncellenen belgeyi kaydet
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Finished");
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

## Çözüm

Bu eğitimde, bir PDF belgesinden gömülü olmayan yazı tiplerini almak için Aspose.PDF for .NET'in nasıl kullanılacağını gösterdik. Adım adım kılavuzu izleyerek, bu özelliği C# uygulamalarınızda kolayca uygulayabilirsiniz. Ayıklanan yazı tipleriyle ayrı ayrı çalışmanız veya çeşitli platformlarda tutarlı yazı tipi kullanımı sağlamanız gerektiğinde, yazı tiplerinin gömülmesi avantajlı olabilir.

## SSS

#### S: Bir PDF belgesinden yazı tiplerini çıkarmanın amacı nedir?

Y: Bir PDF belgesinden yazı tiplerini çıkarmak, gömülü yazı tiplerini çıkarmanıza ve bunları diğer uygulamalarda kullanmanıza olanak tanır. Bu, tutarlı yazı tipi oluşturmayı sağlamak ve belgenin görsel görünümünü korumak için yararlı olabilir.

#### S: C# kodunda belge dizininin yolunu nasıl belirtebilirim?

 A: Belge dizininin yolunu belirtmek için değiştirin`"YOUR DOCUMENT DIRECTORY"` PDF belgenizin bulunduğu dizine giden gerçek yolu içeren kodda.

####  S: ne yapar`UnembedFonts` option do, and where is it set?

 C:`UnembedFonts` seçeneği, şu adreste mevcuttur:`OptimizationOptions` class, yazı tiplerinin PDF belgesinden çıkarılmasını etkinleştirir veya devre dışı bırakır. Bu seçeneği ayarlamak için`true`, aşağıdaki kodu kullanın:

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

#### S: Optimizasyon sürecinde yapılan değişiklikleri geri alabilir miyim?

Y: Aspose.PDF for .NET, optimizasyon sırasında orijinal PDF belgesinde kalıcı değişiklikler yapmaz. Optimizasyon işlemi, orijinali olduğu gibi bırakarak belgenin bir kopyası üzerinde gerçekleştirilir.

#### S: Optimizasyondan sonra orijinal ve küçültülmüş dosya boyutunu nasıl kontrol edebilirim?

C: Şunu kullanabilirsiniz:`FileInfo` sınıfı`System.IO` orijinal ve küçültülmüş dosya boyutunu elde etmek için. İşte bunu başarmak için örnek bir kod parçacığı:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```