---
title: PDF Dosyasında Karakteri Vurgula
linktitle: PDF Dosyasında Karakteri Vurgula
second_title: Aspose.PDF for .NET API Referansı
description: Bu kapsamlı adım adım kılavuzda Aspose.PDF for .NET kullanarak bir PDF'deki karakterleri vurgulamayı öğrenin.
type: docs
weight: 240
url: /tr/net/programming-with-text/highlight-character-in-pdf/
---
## giriiş

PDF'lerle çalışmaya gelince, akademik amaçlar, düzenleme veya sadece okunabilirliği iyileştirmek için olsun, metni veya karakterleri vurgulama ihtiyacı sıklıkla ortaya çıkar. Güzel bir belgeniz olduğunu ancak belirli kısımları vurgulamak istediğinizi düşünün. Vurgulamanın devreye girdiği yer burasıdır! Bu eğitimde, güçlü Aspose.PDF for .NET kitaplığını kullanarak bir PDF dosyasındaki karakterleri nasıl vurgulayacağımıza derinlemesine ineceğiz. 

## Ön koşullar

Koda geçmeden önce ihtiyacımız olan her şeye sahip olduğumuzdan emin olalım. İhtiyacınız olanlar şunlar:

1. Geliştirme Ortamı: Bu eğitimde Visual Studio veya benzeri bir .NET IDE'de çalıştığınızı varsayıyoruz.
2.  Aspose.PDF for .NET Kütüphanesi: Eğer henüz yapmadıysanız,[buradan indirin](https://releases.aspose.com/pdf/net/) ve projenize ekleyin. 
3. C# Temel Bilgileri: C# programlamaya giriş dersi, uygulamayı kolayca anlamanıza yardımcı olacaktır.
4. PDF Belgesi: Çalışmak için hazır bir örnek PDF dosyanız olmalı. Bir tane oluşturabilir veya mevcut bir belgeyi kullanabilirsiniz.

## Paketleri İçe Aktarma

Başlamak için gerekli ad alanlarını içe aktarmamız gerekir. Bunu yapmak için bunları C# dosyanızın en üstüne eklemek isteyeceksiniz:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Devices;
using Aspose.Pdf.Text;
using System;
using System.Drawing;
```

Bu paketler, Aspose kütüphanesini kullanarak PDF belgeleri oluşturmak, düzenlemek ve işlemek için gereklidir.

Şimdi, PDF'inizdeki karakterleri vurgulamak için süreci anlaşılır adımlara bölelim. 

## Adım 1: PDF Belgesini Başlatın

İlk adım PDF belgenizi başlatmaktır. Bu, üzerinde çalışacağınız PDF dosyasını yüklemeyi içerir. İşte nasıl yapacağınız:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Doğru yolu ayarladığınızdan emin olun.
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
```
Bu kod parçacığında şunu değiştirin:`YOUR DOCUMENT DIRECTORY` makinenizde giriş PDF dosyanızın bulunduğu gerçek yol ile.`Aspose.Pdf.Document` PDF'nizi yüklemek için sınıf örnekleştirildi.

## Adım 2: İşleme Sürecini Ayarlayın

Sonra, belgemiz için işleme sürecini hazırlamamız gerekiyor. Bu, sayfadaki karakterleri doğru bir şekilde vurgulamak için önemlidir.

```csharp
int resolution = 150; // Görüntü yakalama çözünürlüğünü ayarlayın.
using (MemoryStream ms = new MemoryStream())
{
    PdfConverter conv = new PdfConverter(pdfDocument);
    conv.Resolution = new Resolution(resolution, resolution);
    conv.GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
    Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
```
 Netlik için bir çözünürlük tanımlıyoruz, bu da metnin düzgün bir şekilde işlenmesine olanak sağlıyor.`PdfConverter`PDF sayfalarını üzerine çizim yapabileceğimiz resimlere dönüştürüyor.

## Adım 3: Çizim için Grafik Nesnesi Oluşturun

Çizim işlemini ayarladıktan sonra, vurgulamamızı yapacağımız bir grafik nesnesi oluşturmamız gerekiyor:

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
{
    float scale = resolution / 72f; // Ölçek faktörü.
    gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);
```
Burada, bitmap görüntüsünden grafik nesnesini oluşturuyoruz. Dönüşüm, işlemeyi gereken çözünürlüğe doğru şekilde uyacak şekilde ayarlamaya yardımcı olur.

## Adım 4: Her Sayfada Gezinin ve Metni Vurgulayın

Şimdi PDF'deki her sayfayı dolaşalım ve vurgulamak istediğimiz metin parçalarını bulalım:

```csharp
for (int i = 0; i < pdfDocument.Pages.Count; i++)
{
    Page page = pdfDocument.Pages[i + 1]; // Sayfalar Aspose'da 1-indekslidir.
    TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
    textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
    page.Accept(textFragmentAbsorber);
```
 Her sayfaya erişiyoruz ve tüm metni arıyoruz`TextFragmentAbsorber` . Düzenli ifade deseni`@"[\S]+"` tüm boşluk olmayan karakterleri yakalar.

## Adım 5: Metin Parçalarını Çıkarın ve Vurgulayın

Şimdi metin parçalarını çıkarma ve vurgulama zamanı. Bu işlem, vurgulamak istediğimiz karakterlerin etrafına dikdörtgenler çizmeyi içerir:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

foreach (TextFragment textFragment in textFragmentCollection)
{
    // Burada mantığı vurguluyoruz
    for (int segNum = 1; segNum <= textFragment.Segments.Count; segNum++)
    {
        TextSegment segment = textFragment.Segments[segNum];
        for (int charNum = 1; charNum <= segment.Characters.Count; charNum++)
        {
            CharInfo characterInfo = segment.Characters[charNum];
            gr.DrawRectangle(Pens.Black, 
                (float)characterInfo.Rectangle.LLX, 
                (float)characterInfo.Rectangle.LLY, 
                (float)characterInfo.Rectangle.Width, 
                (float)characterInfo.Rectangle.Height);
        }
    }
}
```
Daha önce oluşturulan grafik nesnesini kullanarak her metin parçası, onun segmentleri ve tek tek karakterler arasında dolaşıp etraflarına dikdörtgenler çiziyoruz.

## Adım 6: Değiştirilen Görüntüyü Kaydedin

Vurgulama işleminden sonra ortaya çıkan görüntüyü yeni bir PNG dosyası olarak kaydetmeniz gerekecektir:

```csharp
dataDir = dataDir + "HighlightCharacterInPDF_out.png";
bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
```
Bu satır, değiştirilmiş bitmap görüntünüzü belirtilen dizine PNG dosyası olarak kaydeder. 

## Adım 7: İstisna İşleme ile Sonlandırma

Son olarak, kodunuzu bir try-catch bloğuna sarmak iyi bir uygulamadır; böylece beklenmeyen hataları zarif bir şekilde ele alabiliriz:

```csharp
catch (Exception ex)
{
    Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get a 30-day temporary license from [here](https://satın alma.aspose.com/temporary-license/).");
}
```

Bu blok, işlem sırasında oluşabilecek istisnaları yakalar ve kullanıcıya bilgilendirici geri bildirimler verir.

## Çözüm

Ve işte oldu! Aspose.PDF for .NET kullanarak bir PDF dosyasındaki karakterleri başarıyla vurguladınız. Bu güçlü kütüphane, ister açıklamalarla, ister form doldurmayla veya hatta belge dönüştürmeyle çalışıyor olun, PDF düzenlemede sonsuz olasılıklara kapı açar. Aspose ile yolculuğunuza devam ederken, pratiğin anahtar olduğunu unutmayın. Farklı özelliklerle denemeler yapmaya devam edin ve kısa sürede bir PDF uzmanı olacaksınız!

## SSS

### Aspose.PDF for .NET nedir?
Aspose.PDF for .NET, .NET uygulamalarında PDF belgelerinin programlı olarak oluşturulmasına, düzenlenmesine ve dönüştürülmesine olanak tanıyan bir kütüphanedir.

### Birden fazla metin parçasını aynı anda vurgulayabilir miyim?
Evet, verilen kod PDF içindeki tüm metinde döngü yaparak birden fazla parçayı vurgulamak için uyarlanabilir.

### Aspose.PDF'in ücretsiz bir versiyonu var mı?
Evet, Aspose ücretsiz deneme imkanı sunuyor, böylece satın almadan önce kütüphaneyi test edebilirsiniz.

### Aspose.PDF'i kullanmak için herhangi bir lisansa ihtiyacım var mı?
Evet, ticari kullanım için geçerli bir lisansa ihtiyacınız var ancak test amaçlı 30 günlük geçici lisans satın alabilirsiniz.

### Daha fazla dokümanı nerede bulabilirim?
 Şuna başvurabilirsiniz:[Aspose.PDF belgeleri](https://reference.aspose.com/pdf/net/) Uygulama ve özellikler hakkında daha detaylı bilgi için.