---
title: PDF Dosyasına Metin Damgası Ekle
linktitle: PDF Dosyasına Metin Damgası Ekle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET'i kullanarak adım adım bir PDF dosyasına metin damgası eklemeyi öğrenin ve belge sunumlarınızı bir üst seviyeye taşıyın.
type: docs
weight: 50
url: /tr/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
## giriiş

Günümüzün dijital çağında, PDF'ler belgeleri paylaşmak ve iletmek için yaygın bir formattır. İster bir geliştirici, ister bir içerik oluşturucu veya sadece PDF dosyalarını geliştirmek isteyen biri olun, PDF'leri programatik olarak nasıl düzenleyeceğinizi bilmek oyunun kurallarını değiştirebilir. Kullanmak isteyebileceğiniz kullanışlı bir özellik, PDF dosyalarınıza metin damgaları ekleme yeteneğidir. Bir metin damgası eklemek, belgelerinize profesyonel bir dokunuş katabilir veya "Örnek", "Gizli" veya hatta bir filigran gibi önemli bilgileri iletebilir.

## Ön koşullar

Koda geçmeden önce, her şeyin doğru şekilde ayarlandığından emin olmak için birkaç ön koşul var. İhtiyacınız olanlar şunlar:

1.  .NET için Aspose.PDF: Projenizde Aspose.PDF kütüphanesinin yüklü olduğundan emin olun. Bunu henüz yapmadıysanız, şuradan indirebilirsiniz:[Aspose web sitesi](https://releases.aspose.com/pdf/net/).
2. Visual Studio veya Uyumlu IDE: .NET kodunuzu yazmak ve çalıştırmak için bir geliştirme ortamına ihtiyacınız olacak. Visual Studio, geliştiriciler arasında en yaygın tercihtir.
3. Temel C# Bilgisi: C# ve nesne yönelimli programlama prensiplerine aşinalık, örnekleri daha iyi anlamanıza yardımcı olacaktır.
4. Örnek PDF Dosyası: Çalışmaya hazır bir PDF dosyanız olmalı. İşlevselliği test etmek için temel bir PDF oluşturabilir veya mevcut herhangi bir PDF'yi kullanabilirsiniz.

Bu ön koşulları hallettikten sonra kodlamaya geçebiliriz!

## Paketleri İçe Aktar

Şimdi gerekli paketleri içe aktaralım. Bu adım, Aspose kütüphanesindeki sınıfları ve yöntemleri projenizde kullanılabilir hale getirdiği için önemlidir.

### Aspose.PDF Assembly'yi içe aktar

Başlamak için Aspose.PDF ad alanını içe aktarmanız gerekir. C# dosyanızın en üstüne aşağıdaki using yönergesini ekleyin:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

Bu, PDF belgelerini oluşturmak ve düzenlemek için gerekli olan derslere erişmenizi sağlayacaktır.

Şimdi, eğitimin özüne inelim. Süreci açık ve öz adımlara böleceğiz. Her adım sizi bir PDF dosyasına metin damgası eklemek için kodda yönlendirecektir.

## Adım 1: Belge Dizinini Ayarlayın

Öncelikle PDF belgenizin saklandığı dizini belirlemeniz gerekir. Bu, kodunuzun düzenlemek istediğiniz PDF dosyasını nerede bulacağını bilmesi gerektiği anlamına gelir.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Açıklama: Değiştir`"YOUR DOCUMENT DIRECTORY"` PDF dosyanızın bulunduğu gerçek yol ile (`AddTextStamp.pdf`) saklanır. Bu yol daha sonra değiştirilen PDF'yi açmak ve kaydetmek için kullanılır.

## Adım 2: PDF Belgesini açın

 Daha sonra PDF belgesini şu şekilde açacağız:`Document` Aspose.PDF ad alanından sınıf.

```csharp
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

 Açıklama: Burada, bir örnek oluşturuyoruz`Document` sınıf ve PDF dosyamıza giden yolu geçiriyoruz. Bu, PDF'yi yükleyecek ve böylece onu düzenleyebileceğiz.

## Adım 3: Bir Metin Damgası Oluşturun

Şimdi, daha sonra PDF dokümanımıza uygulayacağımız bir metin damgası oluşturacağız.

```csharp
// Metin damgası oluştur
TextStamp textStamp = new TextStamp("Sample Stamp");
```

 Açıklama:`TextStamp` nesne, görüntülemek istediğiniz metinle oluşturulur. Bu durumda, damgamız için metin olarak "Örnek Damga"yı kullanıyoruz.

## Adım 4: Damga Özelliklerini Ayarlayın

Damganızı özelleştirmek için arka plan rengi, konum ve dönüş gibi çeşitli özellikler ayarlayabiliriz. Şimdi bunu yapalım:

```csharp
// Damganın arka plan olup olmadığını ayarlayın
textStamp.Background = true;

// Kökeni ayarla
textStamp.XIndent = 100;
textStamp.YIndent = 100;

// Pul döndür
textStamp.Rotate = Rotation.on90;
```

Açıklama:
- Arka Plan: Bunu şu şekilde ayarlayın:`true` damganın PDF içeriğinin arkasında görüneceği anlamına gelir.
- XIndent ve YIndent: Bu özellikler damganın sayfadaki konumunu belirler. Bu örnekte, damga sayfanın sol ve üst kenarlarından 100 birim uzağa yerleştirilecektir.
- Döndür: Bu, damgayı 90 derece döndürür. Tasarım gereksinimlerinize göre farklı döndürme seçenekleri seçebilirsiniz.

## Adım 5: Metin Özelliklerini Özelleştirin

Şimdi damgamızdaki metnin görünümünü özelleştirerek yaratıcı olalım:

```csharp
// Metin özelliklerini ayarla
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(Color.Aqua);
```

Açıklama:
- Yazı Tipi: Arial yazı tipini kullanıyoruz ve onu kalın ve italik yapıyoruz.
- FontSize: 14 punto olarak ayarlanmıştır.
- ForegroundColor: Metin rengini Aqua olarak ayarlamak için RGB'yi kullanın. Markanıza veya tasarım ihtiyaçlarınıza uyacak şekilde rengi değiştirmekten çekinmeyin!

## Adım 6: PDF Sayfasına Damga Ekleme

Şimdi damgayı PDF belgesinin belirli bir sayfasına ekleme zamanı.

```csharp
// Belirli bir sayfaya damga ekle
pdfDocument.Pages[1].AddStamp(textStamp);
```

Açıklama: Bu örnekte, damga PDF'nin ilk sayfasına eklenir (sayfalar 1 dizinlidir). Sayfa numarasını belgeniz için gerektiği gibi ayarlayın.

## Adım 7: Değiştirilmiş PDF'yi Kaydedin

Son olarak belgeyi yeni eklenen metin damgasıyla kaydedelim.

```csharp
dataDir = dataDir + "AddTextStamp_out.pdf";

// Çıktı belgesini kaydet
pdfDocument.Save(dataDir);
Console.WriteLine("\nText stamp added successfully.\nFile saved at " + dataDir);
```

Açıklama: Çıktı dosyası için yeni bir yol tanımlıyoruz ve ardından değiştirilen belgeyi kaydediyoruz. Kaydettikten sonra, yol konsola yazdırılır ve başarılı işlem onaylanır.

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF dosyasına başarıyla bir metin damgası eklediniz. Bu yöntem, belgelerinize etkili bir şekilde açıklama eklemenizi, hem profesyonelliklerini hem de kullanılabilirliklerini artırmanızı sağlar. Filigran, imza veya basit notlar ekliyor olun, Aspose kitaplığı PDF'lerinizi kolaylıkla düzenlemeniz için güçlü araçlar sunar.

## SSS

### PDF'de metin damgası nedir?
Metin damgası, PDF belgesine yerleştirilebilen, metin içeren grafiksel bir katmandır ve çoğunlukla açıklamalar veya filigranlar için kullanılır.

### Damgayı görsellerle özelleştirebilir miyim?
Evet, Aspose.PDF resim damgalarının eklenmesini de destekliyor ve bu da daha fazla tasarım esnekliği sağlıyor.

### Aspose.PDF ile hangi programlama dillerini kullanabilirim?
Aspose.PDF öncelikli olarak .NET'e odaklanmıştır, ancak Java ve Python gibi diğer diller için de sürümleri mevcuttur.

### Aspose.PDF için geçici lisansı nasıl alabilirim?
 Geçici lisans başvurusunu şu adresten yapabilirsiniz:[satın alma bağlantısı](https://purchase.aspose.com/temporary-license/) web sitelerinde.

### Aspose.PDF için desteği nerede bulabilirim?
 Aspose.PDF desteği şu adreste mevcuttur:[destek forumu](https://forum.aspose.com/c/pdf/10).