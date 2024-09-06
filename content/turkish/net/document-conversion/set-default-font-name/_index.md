---
title: Varsayılan Yazı Tipi Adını Ayarla
linktitle: Varsayılan Yazı Tipi Adını Ayarla
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF'leri görüntülere dönüştürürken varsayılan yazı tipi adının nasıl ayarlanacağını öğrenin. Bu kılavuz ön koşulları, adım adım talimatları ve SSS'leri kapsar.
type: docs
weight: 270
url: /tr/net/document-conversion/set-default-font-name/
---
## giriiş

Hiç bir PDF belgesini bir görüntüye dönüştürmeyi denediniz ancak yazı tiplerinin doğru görünmediğini mi gördünüz? Belki metin bozuk görünüyor veya belki de orijinal yazı tipi desteklenmiyor. İşte tam bu noktada varsayılan bir yazı tipi belirlemek günü kurtarabilir! .NET için Aspose.PDF'yi kullanarak, PDF oluşturmanız için kolayca varsayılan bir yazı tipi belirleyebilir ve belgenizin net ve profesyonel görünmesini sağlayabilirsiniz. Bu eğitimde, bir PDF'yi bir görüntüye dönüştürürken varsayılan yazı tipi adını nasıl ayarlayacağınızı göstereceğiz. Bu kılavuzun sonunda, karşınıza çıkan tüm PDF oluşturma zorluklarının üstesinden gelmek için gereken becerilere sahip olacaksınız. Hazır mısınız? Hadi başlayalım!

## Ön koşullar

Koda geçmeden önce, yerinde olması gereken birkaç şey var:

- .NET için Aspose.PDF: Bu güçlü kütüphane, PDF belgemizi düzenlemek için kullanacağımız şeydir. Bunu şuradan indirebilirsiniz:[Aspose web sitesi](https://releases.aspose.com/pdf/net/).
- Visual Studio: Makinenizde Visual Studio'nun yüklü olduğundan emin olun. Bu bizim geliştirme ortamımız olacak.
- .NET Framework: .NET Framework'ün yüklü olduğundan emin olun. .NET için Aspose.PDF çeşitli sürümleri destekler, bu nedenle ihtiyaçlarınıza uygun belgeleri kontrol edin.
- PDF Belgesi: Çalışmak için bir örnek PDF belgesine ihtiyacınız olacak. Eğer yoksa, basit bir PDF oluşturun veya çevrimiçi bir örnek indirin.

Her şeyi ayarladıktan sonra kodlamaya başlamaya hazırız!

## Paketleri İçe Aktar

Koda dalmadan önce, gerekli paketleri içe aktarmak önemlidir. Bu, projemiz için ihtiyaç duyduğumuz tüm sınıflara ve yöntemlere erişimimiz olduğundan emin olmamızı sağlar.

```csharp
using Aspose.Pdf.Devices;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

Bu içe aktarımlar, PDF düzenleme, görüntü oluşturma ve dosya akışı işlemlerini yönetmek için gerekli ad alanlarını sağladıkları için hayati önem taşımaktadır.

## Adım 1: Projenizi ve Belge Yolunuzu Ayarlayın

İlk önce, PDF belgenizin bulunduğu dizin yolunu ayarlayalım. Bu, PDF dosyasını düzenlemeniz için başlangıç noktanız olacak.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
 Burada,`dataDir` PDF belgenizin bulunduğu dizindir. Değiştirdiğinizden emin olun`"YOUR DOCUMENT DIRECTORY"` Belgenizin gerçek yolu ile. Bu önemlidir çünkü kodun PDF dosyasını nereden alacağını bilmesi gerekir.

## Adım 2: PDF Belgesini Yükleyin

Artık belge yoluna sahip olduğumuza göre, bir sonraki adım PDF belgesini belleğe yüklemek ve üzerinde çalışmaya başlamaktır.

```csharp
using (Document pdfDocument = new Document(dataDir + "input.pdf"))
```
 Biz kullanıyoruz`Document` PDF dosyamızı yüklemek için Aspose.PDF kütüphanesinden sınıf. Bu sınıf, PDF belgesiyle çalışmak için çeşitli yöntemler ve özellikler sağlar.`"input.pdf"` PDF'nizin gerçek dosya adıyla değiştirilmelidir. Bu dosya, işleme için girdi olarak kullanılacaktır.

## Adım 3: Çıktı için bir Görüntü Akışı Oluşturun

Belge yüklendikten sonra, işlenmiş görüntüyü kaydetmek için bir akış ayarlamamız gerekir. Çıktı görüntüsünün saklanacağı yer burasıdır.

```csharp
using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
```
 The`FileStream`sınıf, işlenen görüntünün kaydedileceği yeni bir dosya oluşturmak için kullanılır. Bu örnekte, görüntüyü şu şekilde kaydediyoruz`"SetDefaultFontName.png"` .`FileMode.Create` yeni bir dosyanın oluşturulmasını veya var olan bir dosyanın üzerine yazılmasını sağlar.

## Adım 4: Görüntü için Çözünürlüğü Ayarlayın

PDF'yi bir görüntüye dönüştürmeden önce çözünürlüğü ayarlamak çok önemlidir. Bu, çıktı görüntüsünün kalitesini ve netliğini belirler.

```csharp
Resolution resolution = new Resolution(300);
```
 The`Resolution` sınıf, çıktı görüntüsünün çözünürlüğünü ayarlar. Burada, yüksek kaliteli görüntüler için standart olan 300 DPI (inç başına nokta) çözünürlüğünü seçtik. Bu, PDF'nizdeki metin ve grafiklerin ayrıntı kaybı olmadan net bir şekilde görüntülenmesini sağlar.

## Adım 5: PNG Aygıtını Yapılandırın

Daha sonra, PDF'yi PNG görüntüsüne dönüştürecek cihazı yapılandırmamız gerekiyor.

```csharp
PngDevice pngDevice = new PngDevice(resolution);
```
 The`PngDevice` sınıf, PDF belgesini PNG görüntüsüne dönüştürmekten sorumludur.`resolution` Buna itiraz etmeden önce, görüntünün belirtilen DPI ile oluşturulmasını sağlıyoruz.

## Adım 6: Varsayılan Yazı Tipi Adını Ayarlayın

İşte kritik kısım - varsayılan yazı tipi adını ayarlamak. Bu, PDF'deki orijinal yazı tipi mevcut olmadığında yedek yazı tipi olacaktır.

```csharp
RenderingOptions ro = new RenderingOptions();
ro.DefaultFontName = "Arial";
pngDevice.RenderingOptions = ro;
```
 Bir örnek oluşturuyoruz`RenderingOptions` ve ayarla`DefaultFontName` mülk`"Arial"`. Bu, PDF'deki orijinal yazı tipi bulunamazsa, bunun yerine Arial'in kullanılacağı anlamına gelir. Bu adım, işlenmiş görüntüdeki metnin okunabilirliğini ve görünümünü korumak için çok önemlidir.

## Adım 7: PDF Sayfasını Bir Görüntüye Dönüştürün

Son olarak, her şey ayarlandığına göre, artık PDF belgesinin ilk sayfasını bir görüntüye dönüştürebilir ve daha önce oluşturduğumuz dosya akışını kullanarak kaydedebiliriz.

```csharp
pngDevice.Process(pdfDocument.Pages[1], imageStream);
```
 The`Process` yöntemi`PngDevice` sınıfı belirtilen PDF sayfasını (bu durumda ilk sayfa) bir görüntüye dönüştürmek için kullanılır. Çıktı daha sonra şuraya kaydedilir:`imageStream`Bu adım PDF sayfasını belirtilen çözünürlük ve varsayılan yazı tipiyle PNG resmine dönüştürür.

## Adım 8: Dosya Akışını ve PDF Belgesini Kapatın

Görüntüyü oluşturduktan sonra, kaynakları serbest bırakmak için dosya akışını ve PDF belgesini kapatmak önemlidir.

```csharp
imageStream.Close();
pdfDocument.Dispose();
```
Kapatma`imageStream` dosyanın düzgün bir şekilde kaydedilmesini ve hiçbir verinin kaybolmamasını sağlar.`pdfDocument` belleği ve kaynakları serbest bırakarak olası bellek sızıntılarını önler.

## Çözüm

Ve işte oldu! Sadece birkaç satır kodla, .NET için Aspose.PDF kullanarak bir PDF'yi bir görüntüye dönüştürürken varsayılan bir yazı tipi adını nasıl ayarlayacağınızı öğrendiniz. Bu beceri inanılmaz derecede kullanışlıdır, özellikle de desteklenmeyen yazı tipleri içerebilen PDF'lerle uğraşırken. Varsayılan bir yazı tipi ayarlayarak, oluşturulan görüntülerinizin okunabilirliğini ve profesyonel görünümünü korumasını sağlarsınız.

## SSS

### Belirtilen varsayılan yazı tipi sistemde yüklü değilse ne olur?
 Varsayılan yazı tipi belirtilen ise`RenderingOptions` sistemde yüklü değilse, Aspose.PDF sistem tarafından tanımlanan bir yedek yazı tipini kullanacaktır.

### Varsayılan yazı tipi olarak Arial dışındaki yazı tiplerini kullanabilir miyim?
Kesinlikle! Sisteminizde yüklü olan herhangi bir yazı tipini varsayılan yazı tipi olarak ayarlayabilirsiniz.

### Bir PDF'in birden fazla sayfasını tek seferde resim olarak işlemek mümkün müdür?
Evet, PDF'inizin sayfaları arasında dolaşabilir ve aynı işlemi kullanarak her sayfayı ayrı ayrı işleyebilirsiniz.

### Çözünürlüğü yüksek ayarlamak PDF oluşturma performansını etkiler mi?
Evet, daha yüksek çözünürlükler daha büyük görüntü dosyalarıyla sonuçlanacak ve işleme süresini uzatabilir, ancak aynı zamanda daha net görüntüler de üretecektir.

### PDF'i PNG dışında başka resim formatlarına dönüştürebilir miyim?
Evet, Aspose.PDF JPEG, BMP ve TIFF gibi çeşitli görüntü formatlarına dönüştürmeyi destekler.