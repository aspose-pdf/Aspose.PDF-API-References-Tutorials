---
title: Gömülü Yazı Tiplerini Çıkarın ve PDF Dosyalarını Optimize Edin
linktitle: Gömülü Yazı Tiplerini Çıkarın ve PDF Dosyalarını Optimize Edin
second_title: .NET API Referansı için Aspose.PDF
description: Gömülü Fontları Çıkarmak ve PDF dosyalarını optimize etmek için Aspose.PDF for .NET'i nasıl kullanacağınızı öğrenin. Adım adım bir kılavuz.
type: docs
weight: 370
url: /tr/net/programming-with-document/unembedfonts/
---
Aspose.PDF for .NET, PDF belgeleriyle çalışmak için çok çeşitli özellikler sunan güçlü bir kütüphanedir. Özelliklerinden biri, bir PDF belgesinden gömülü olmayan yazı tiplerini almaktır. Bir PDF belgesinden yazı tiplerini çıkarmanız ve bunları başka uygulamalarda kullanmanız gerekiyorsa bu yararlı olabilir.

Aspose.PDF for .NET'in gömülü yazı tiplerini alma özelliğinin aşağıdaki C# kaynak kodunu açıklamak için adım adım bir kılavuz sunacağız.

## 1. Adım: Belge dizininin yolunu ayarlayın

Başlamadan önce PDF belgemizin bulunduğu dizinin yolunu ayarlamamız gerekiyor. Bu yolu "dataDir" adlı bir değişkende saklayacağız.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

"BELGE DİZİNİNİZ" ifadesini, PDF belgenizin bulunduğu dizine giden gerçek yolla değiştirin.

## Adım 2: PDF Belgesini açın

 İlk adım, bunu yapmak istediğiniz PDF belgesini yüklemek,`Document` .NET için Aspose.PDF sınıfı. Aşağıdaki kod parçacığı PDF belgesinin nasıl yükleneceğini gösterir:

```csharp
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## 3. Adım: UnembedFonts Seçeneğini Ayarlayın

 PDF belgesinden gömülü olmayan yazı tiplerini almak için,`UnembedFonts` seçeneği`true` . Bu seçenek şu adreste mevcuttur:`OptimizationOptions` sınıf. Aşağıdaki kod parçacığı, ayarın nasıl ayarlanacağını gösterir.`UnembedFonts` seçenek:

```csharp
// UnembedFonts seçeneğini ayarla
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

## Adım 4: PDF Belgesini Optimize Edin

 Ayarladıktan sonra`UnembedFonts` seçeneğini kullanarak PDF belgesini optimize edebilirsiniz.`OptimizeResources` yöntemi`Document` sınıf. Aşağıdaki kod parçacığı, PDF belgesinin nasıl optimize edileceğini gösterir:

```csharp
// OptimizationOptions'ı kullanarak PDF belgesini optimize edin
pdfDocument.OptimizeResources(optimizeOptions);
```

## Adım 5: Güncellenen Belgeyi Kaydedin

 PDF belgesi optimize edildikten sonra, güncellenen belgeyi kullanarak kaydedebilirsiniz.`Save` yöntemi`Document`sınıf. Aşağıdaki kod parçacığı güncellenen belgenin nasıl kaydedileceğini gösterir:

```csharp
// Güncellenen belgeyi kaydet
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## Adım 6: Orijinali ve Küçültülmüş Dosya Boyutunu Alın

 Son olarak, PDF belgesinin orijinal ve küçültülmüş dosya boyutunu aşağıdakileri kullanarak alabilirsiniz:`FileInfo` System.IO sınıfı. Aşağıdaki kod parçacığı, orijinal ve küçültülmüş dosya boyutunun nasıl elde edileceğini gösterir:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

### Aspose.PDF for .NET kullanarak Gömülü Fontları Almak için Örnek Kaynak Kodu

Aspose.PDF for .NET kullanarak bir PDF belgesinden gömülmemiş yazı tiplerini almak için tam örnek kaynak kodunu burada bulabilirsiniz:

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
// OptimizationOptions'ı kullanarak PDF belgesini optimize edin
pdfDocument.OptimizeResources(optimizeOptions);
// Güncellenen belgeyi kaydet
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Finished");
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

## Çözüm

Bu eğitimde, bir PDF belgesinden gömülü olmayan fontları almak için Aspose.PDF for .NET'in nasıl kullanılacağını gösterdik. Adım adım kılavuzu takip ederek bu özelliği C# uygulamalarınızda kolaylıkla uygulayabilirsiniz. Ayıklanan fontlarla ayrı ayrı çalışmanız veya çeşitli platformlarda tutarlı font kullanımı sağlamanız gerektiğinde, fontları gömmemek avantajlı olabilir.

## SSS'ler

#### S: Fontları bir PDF belgesinden çıkarmanın amacı nedir?

C: Fontları bir PDF belgesinden çıkarmak, gömülü fontları çıkarmanıza ve bunları diğer uygulamalarda kullanmanıza olanak tanır. Bu, tutarlı yazı tipi oluşturma ve belgenin görsel görünümünü koruma açısından yararlı olabilir.

#### S: C# kodundaki belge dizininin yolunu nasıl belirlerim?

 C: Belge dizininin yolunu belirtmek için değiştirin`"YOUR DOCUMENT DIRECTORY"` PDF belgenizin bulunduğu dizinin gerçek yolunu içeren kodda.

####  S: Ne işe yarar?`UnembedFonts` option do, and where is it set?

 C:`UnembedFonts` seçeneği mevcuttur`OptimizationOptions` class, yazı tiplerinin PDF belgesinden çıkarılmasını etkinleştirir veya devre dışı bırakır. Bu seçeneği ayarlamak için`true`, aşağıdaki kodu kullanın:

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

#### S: Optimizasyon işlemi sırasında yapılan değişiklikleri geri alabilir miyim?

C: Aspose.PDF for .NET, optimizasyon sırasında orijinal PDF belgesinde kalıcı değişiklikler yapmaz. Optimizasyon işlemi, orijinali olduğu gibi bırakarak belgenin bir kopyası üzerinde gerçekleştirilir.

#### S: Optimizasyondan sonra orijinal ve küçültülmüş dosya boyutunu nasıl kontrol edebilirim?

C: Kullanabilirsiniz`FileInfo` sınıfı`System.IO` orijinal ve küçültülmüş dosya boyutunu elde etmek için. Bunu başarmak için örnek bir kod pasajını burada bulabilirsiniz:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```