---
title: Yazı Tiplerini Kaldırın ve PDF Dosyalarını Optimize Edin
linktitle: Yazı Tiplerini Kaldırın ve PDF Dosyalarını Optimize Edin
second_title: Aspose.PDF for .NET API Referansı
description: .NET için Aspose.PDF'yi kullanarak Unembed Fonts'u nasıl alacağınızı ve PDF dosyalarını nasıl optimize edeceğinizi öğrenin. Adım adım bir kılavuz.
type: docs
weight: 370
url: /tr/net/programming-with-document/unembedfonts/
---
Aspose.PDF for .NET, PDF belgeleriyle çalışmak için geniş bir özellik yelpazesi sunan güçlü bir kütüphanedir. Özelliklerinden biri de PDF belgesinden gömülü fontları çıkarmaktır. Bu, bir PDF belgesinden fontları çıkarmanız ve bunları diğer uygulamalarda kullanmanız gerektiğinde yararlı olabilir.

.NET için Aspose.PDF'nin gömülü yazı tiplerini kaldırma özelliğinin C# kaynak kodunu açıklamak için adım adım bir kılavuz sağlayacağız.

## Adım 1: Belge dizinine giden yolu ayarlayın

Başlamadan önce, PDF belgemizin bulunduğu dizine giden yolu ayarlamamız gerekiyor. Bu yolu "dataDir" adlı bir değişkende saklayacağız.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

"BELGE DİZİNİNİZ" ifadesini PDF belgenizin bulunduğu dizinin gerçek yoluyla değiştirin.

## Adım 2: PDF Belgesini açın

 İlk adım, bunu yapmak istediğiniz PDF belgesini yüklemektir,`Document` .NET için Aspose.PDF sınıfı. Aşağıdaki kod parçacığı PDF belgesinin nasıl yükleneceğini gösterir:

```csharp
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Adım3: UnembedFonts Seçeneğini Ayarlayın

 PDF belgesinden gömülü yazı tiplerini kaldırmak için, şunu ayarlamanız gerekir:`UnembedFonts` seçeneği`true` Bu seçenek şurada mevcuttur:`OptimizationOptions` Aşağıdaki kod parçacığı, sınıfın nasıl ayarlanacağını gösterir.`UnembedFonts` seçenek:

```csharp
// UnembedFonts seçeneğini ayarlayın
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

## Adım 4: PDF Belgesini Optimize Edin

 Ayarladıktan sonra`UnembedFonts` seçeneğiyle PDF belgesini optimize edebilirsiniz`OptimizeResources` yöntemi`Document` sınıf. Aşağıdaki kod parçacığı PDF belgesinin nasıl optimize edileceğini gösterir:

```csharp
// OptimizationOptions kullanarak PDF belgesini optimize edin
pdfDocument.OptimizeResources(optimizeOptions);
```

## Adım 5: Güncellenen Belgeyi Kaydedin

 PDF belgesi optimize edildikten sonra, güncellenen belgeyi kullanarak kaydedebilirsiniz.`Save` yöntemi`Document`Aşağıdaki kod parçacığı güncellenen belgenin nasıl kaydedileceğini gösterir:

```csharp
// Güncellenen belgeyi kaydet
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## Adım 6: Orijinal ve Küçültülmüş Dosya Boyutunu Alın

 Son olarak, PDF belgesinin orijinal ve küçültülmüş dosya boyutunu şu şekilde elde edebilirsiniz:`FileInfo` System.IO sınıfı. Aşağıdaki kod parçası orijinal ve küçültülmüş dosya boyutunun nasıl alınacağını gösterir:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

### .NET için Aspose.PDF kullanarak Gömülü Yazı Tiplerini Kaldırmak için Örnek Kaynak Kodu

İşte Aspose.PDF for .NET kullanarak bir PDF belgesinden gömülü yazı tiplerini almaya yönelik tam örnek kaynak kodu:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// UnembedFonts seçeneğini ayarlayın
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

Bu eğitimde, bir PDF belgesinden gömülü olmayan fontları almak için Aspose.PDF for .NET'in nasıl kullanılacağını gösterdik. Adım adım kılavuzu izleyerek, bu özelliği C# uygulamalarınızda kolayca uygulayabilirsiniz. Çıkarılan fontlarla ayrı ayrı çalışmanız veya çeşitli platformlarda tutarlı font kullanımı sağlamanız gerektiğinde, gömülü olmayan fontlar avantajlı olabilir.

## SSS

#### S: PDF belgesinden yazı tiplerinin kaldırılmasının amacı nedir?

A: Bir PDF belgesinden fontları gömmeyi kaldırmak, gömülü fontları çıkarmanıza ve bunları diğer uygulamalarda kullanmanıza olanak tanır. Bu, tutarlı font oluşturmayı sağlamak ve belgenin görsel görünümünü korumak için yararlı olabilir.

#### S: C# kodunda belge dizinine giden yolu nasıl belirtirim?

 A: Belge dizinine giden yolu belirtmek için şunu değiştirin:`"YOUR DOCUMENT DIRECTORY"` PDF belgenizin bulunduğu dizinin gerçek yolunu içeren kodda.

####  S: Ne anlama geliyor?`UnembedFonts` option do, and where is it set?

 A:`UnembedFonts` seçeneği, mevcuttur`OptimizationOptions` sınıf, PDF belgesinden yazı tiplerinin gömülmesini kaldırır veya devre dışı bırakır. Bu seçeneği ayarlamak için`true`, aşağıdaki kodu kullanın:

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

#### S: Optimizasyon sürecinde yapılan değişiklikleri geri alabilir miyim?

A: Aspose.PDF for .NET, optimizasyon sırasında orijinal PDF belgesinde kalıcı değişiklikler yapmaz. Optimizasyon işlemi, orijinali bozulmadan bırakarak belgenin bir kopyası üzerinde gerçekleştirilir.

#### S: Optimizasyondan sonra orijinal ve küçültülmüş dosya boyutunu nasıl kontrol edebilirim?

 A: Kullanabilirsiniz`FileInfo` sınıfı`System.IO` orijinal ve küçültülmüş dosya boyutunu elde etmek için. Bunu başarmak için örnek bir kod parçası:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```