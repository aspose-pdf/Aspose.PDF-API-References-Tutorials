---
title: Yönelimi Değiştir
linktitle: Yönelimi Değiştir
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF'in sayfa yönünü değiştirmek için adım adım kılavuz. Projelerinizde takip etmesi ve uygulaması kolaydır.
type: docs
weight: 10
url: /tr/net/programming-with-pdf-pages/change-orientation/
---
## giriiş

Sayfa yönü tam olarak... kapalı olan bir PDF dosyasıyla uğraştığınız oldu mu hiç? Belki de taranmış veya yanlış oluşturulmuş bir belgeyle uğraşıyorsunuz ve sayfaların anlam kazanması için döndürülmesi gerekiyor. Neyse ki bizim için Aspose.PDF for .NET, sayfalarınızın yönünü değiştirmek de dahil olmak üzere, PDF dosyalarını akla gelebilecek her şekilde düzenlemenin kolay ve güçlü bir yolunu sunuyor. İster dikeyden yataya ister tam tersine geçmek isteyin, bu kılavuz sizi adım adım süreçte yönlendirecektir.

O halde, PDF sayfalarını kolayca döndürmeye hazırsanız, başlayalım!

## Ön koşullar

PDF'inizdeki sayfa yönünü değiştirmenin ayrıntılarına girmeden önce, neye ihtiyacınız olduğunu kısaca ele alalım:

-  .NET için Aspose.PDF: .NET için Aspose.PDF kütüphanesini yüklediğinizden emin olun. Yüklemediyseniz,[buradan indirin](https://releases.aspose.com/pdf/net/).
- .NET Geliştirme Ortamı: .NET ile çalışmak için Visual Studio, JetBrains Rider veya tercih ettiğiniz herhangi bir IDE'yi kullanabilirsiniz.
- Temel C# Bilgisi: Bu rehber basit olmasına rağmen, C# hakkında temel bir anlayışa sahip olmak takip etmeyi daha da kolaylaştıracaktır.
- Bir PDF Dosyası: Aşağıdaki örnek, birden fazla sayfadan oluşan bir PDF dosyanız olduğunu varsayar. Elinizde yoksa, çalışmak için bir örnek PDF oluşturun veya indirin.

 Ayrıca, yeni başlıyorsanız, Aspose.PDF'yi deneyebilirsiniz[ücretsiz geçici lisans](https://purchase.aspose.com/temporary-license/) karar vermeden önce[tam sürümü satın al](https://purchase.aspose.com/buy).

## Ad Alanlarını İçe Aktar

PDF'nizdeki sayfaların yönünü değiştirebilmeniz için, C# projenize gerekli ad alanlarını içe aktarmanız gerekir. Aşağıdakilere sahip olduğunuzdan emin olun:

```csharp
using System.IO;
using Aspose.Pdf;
```

Bunu da aktardıktan sonra artık eğitimin asıl kısmına geçelim.

## Adım 1: PDF Belgesini Yükleyin

 Yapmamız gereken ilk şey, değiştirmek istediğiniz PDF dosyasını yüklemektir.`Document` PDF'nizi açmak için Aspose.PDF ad alanından sınıf.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
```

 Bu satır PDF'yi belirtilen dizinden yükler. Değiştirdiğinizden emin olun`"YOUR DOCUMENT DIRECTORY"` dosyanızın gerçek yolu ile.`"input.pdf"` Yönlendirmesini değiştirmek istediğiniz PDF'dir.

## Adım 2: Her Sayfada Döngü Yapın

 Artık belgeyi yüklediğimize göre, PDF'deki her sayfada dolaşalım. Bir`foreach` Her sayfayı dolaşacak bir döngü oluşturarak, yönelim değişikliğini hepsine uygulayabiliriz.

```csharp
foreach (Page page in doc.Pages)
{
    // Her sayfayı düzenleyin
}
```

Bu döngü belgedeki tüm sayfaları yineleyecektir.

## Adım 3: Sayfanın MediaBox'ını edinin

 PDF'deki her sayfanın bir`MediaBox` sayfanın sınırlarını tanımlayan. Mevcut yönelimi belirlemek ve değiştirmek için buna erişmemiz gerekiyor.

```csharp
Aspose.Pdf.Rectangle r = page.MediaBox;
```

 The`MediaBox` bize sayfanın genişlik, yükseklik ve konumlandırma gibi boyutlarını verir.

## Adım 4: Genişlik ve Yüksekliği Değiştirin

Sayfa yönünü dikeyden yataya veya yataydan dikeye değiştirmek için, genişlik ve yükseklik değerlerini değiştirmemiz yeterlidir. Bu adım sayfanın boyutlarını ayarlayacaktır.

```csharp
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
```

Bu kod yüksekliği ve genişliği değiştirir ve sol alt köşeyi yeniden konumlandırır (`LLY`) böylece döndürme işleminden sonra içerik düzgün bir şekilde yerleşir.

## Adım 5: MediaBox ve CropBox'ı güncelleyin

Artık yeni yükseklik ve genişliğe sahip olduğumuza göre, değişiklikleri sayfanın`MediaBox` Ve`CropBox` .`CropBox` Orijinal belgede bir ayar varsa, tüm sayfanın doğru şekilde görüntülenmesini sağlamak önemlidir.

```csharp
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
```

Bu adım, sayfayı az önce hesapladığımız yeni boyutlara göre yeniden boyutlandırır.

## Adım 6: Sayfayı Döndürün

Son olarak, sayfanın dönüş açısını ayarlıyoruz. Aspose.PDF bunu çok basit hale getiriyor. Sayfayı 90 derece döndürerek portreden manzaraya veya tam tersine geçebiliriz.

```csharp
page.Rotate = Rotation.on90;
```

Bu kod sayfayı 90 derece döndürerek istenilen yöne çevirir.

## Adım 7: Çıktı PDF'ini Kaydedin

Yönlendirme değişikliklerini tüm sayfalara uyguladıktan sonra, değiştirilen belgeyi yeni bir dosyaya kaydediyoruz. 

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);
```

 Yeni bir dosya adı sağladığınızdan emin olun (bu durumda,`ChangeOrientation_out.pdf`) çıktıyı kaydetmek için. Bu şekilde, orijinal dosyanızın üzerine yazmazsınız.

### Çözüm

Ve işte karşınızda! Aspose.PDF for .NET kullanarak bir PDF dosyasının sayfa yönünü değiştirmek, belgeyi yüklemek, sayfalar arasında dolaşmak, MediaBox'ı ayarlamak ve güncellenen dosyayı kaydetmek kadar basittir. Kötü taranmış bir belgeyle uğraşıyor olun veya biçimlendirme ihtiyaçlarınıza uyması için sayfaları döndürmeniz gereksin, bu adım adım kılavuz size yardımcı olacaktır.

## SSS

### PDF'deki tüm sayfalar yerine belirli sayfaları döndürebilir miyim?  
Evet, tüm sayfalarda döngü yapmak yerine, belirli sayfaları hedeflemek için döngüyü, o sayfaların dizinlerini kullanarak değiştirebilirsiniz.

###  Nedir?`MediaBox`?  
 The`MediaBox` PDF dosyasındaki sayfanın boyutunu ve şeklini tanımlar. Sayfanın içeriğinin yerleştirildiği yerdir.

### Aspose.PDF for .NET diğer dosya formatlarıyla çalışır mı?  
Evet, Aspose.PDF HTML, XML, XPS ve daha fazlası gibi çeşitli dosya biçimlerini işleyebilir.

### Aspose.PDF'in .NET için ücretsiz bir sürümü var mı?  
 Evet, bir başlangıç yapabilirsiniz[ücretsiz deneme](https://releases.aspose.com/) veya bir talepte bulunun[geçici lisans](https://purchase.aspose.com/temporary-license/).

### Kaydettiğim değişiklikleri geri alabilir miyim?  
Belgeyi kaydettiğinizde değişiklikler kalıcı olur. Orijinal dosyanın bir kopyası üzerinde çalıştığınızdan veya yedeğini sakladığınızdan emin olun.