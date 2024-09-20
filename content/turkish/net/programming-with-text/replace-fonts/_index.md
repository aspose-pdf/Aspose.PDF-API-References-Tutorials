---
title: PDF Dosyasındaki Yazı Tiplerini Değiştir
linktitle: PDF Dosyasındaki Yazı Tiplerini Değiştir
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyalarındaki yazı tiplerini kolayca değiştirin. Yazı tiplerini değiştirmek için kod örnekleriyle adım adım kılavuz.
type: docs
weight: 340
url: /tr/net/programming-with-text/replace-fonts/
---
## giriiş

Dijital çağda, PDF'ler her yerdedir; iş raporlarından kişisel belgelere. Peki bir PDF'de kullanılan yazı tipi gereksinimlerinizi karşılamadığında ne olur? Belki tutarsızdır, güncelliğini yitirmiştir veya markanızla uyuşmamaktadır. .NET için Aspose.PDF ile bir PDF dosyasındaki yazı tiplerini kolayca değiştirebilirsiniz. Bu eğitimde, PDF dosyalarınızdaki yazı tipiyle ilgili ayarlamaları iyi bir şekilde halletmenizi sağlayacak şekilde bunu adım adım nasıl başaracağınızı inceleyeceğiz.

## Ön koşullar

Aspose.PDF for .NET kullanarak bir PDF'deki yazı tiplerini değiştirme sürecine geçmeden önce, yerinde olması gereken birkaç şey vardır:

1.  Aspose.PDF for .NET Kütüphanesi: Aspose.PDF for .NET kütüphanesinin en son sürümünü indirin ve yükleyin. Bunu şuradan edinebilirsiniz:[Burada](https://releases.aspose.com/pdf/net/).
2. Geliştirme Ortamı: Visual Studio gibi bir C# geliştirme ortamının kurulu olduğundan emin olun.
3.  Geçerli Lisans: Aspose.PDF ücretsiz deneme sunarken, bazı gelişmiş özellikler lisans gerektirebilir. Bir lisans alabilirsiniz.[geçici lisans](https://purchase.aspose.com/temporary-license/) veya[tam lisans satın al](https://purchase.aspose.com/buy).
4. Temel C# Bilgisi: C# programlama ve harici kütüphanelerle çalışma konusunda bilgili olmalısınız.

## Ad Alanlarını İçe Aktar

Yazı tiplerini değiştirmeye başlamadan önce, C# projenize aşağıdaki ad alanlarını içe aktardığınızdan emin olun:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

Bu ad alanları, PDF dosyalarını yüklemek, düzenlemek ve kaydetmek için kullanılan sınıflara ve yöntemlere erişime izin verdikleri için önemlidir.

Şimdi, bir PDF dosyasındaki yazı tiplerini değiştirme adımlarını inceleyelim. Arial,Bold adlı bir yazı tipinin tüm örneklerini Arial ile değiştirdiğimiz bir örnek kullanacağız. Bunu nasıl yapacağınız aşağıda açıklanmıştır:

## Adım 1: Projenizi Kurun

Bir PDF dosyasını düzenlemeye başlamadan önce yeni bir proje oluşturmalı ve Aspose.PDF for .NET kütüphanesini yüklemelisiniz.

1. Yeni Bir Proje Oluşturun: Visual Studio'yu (veya herhangi bir IDE'yi) açın ve yeni bir C# Konsol Uygulaması oluşturun.
2.  .NET için Aspose.PDF'yi yükleyin: NuGet Paket Yöneticisi'nde Aspose.PDF'yi arayın ve projenize yükleyin. Alternatif olarak, şuradan indirebilirsiniz:[Burada](https://releases.aspose.com/pdf/net/) ve manuel olarak referans alın.

```bash
Install-Package Aspose.PDF
```

## Adım 2: Kaynak PDF Dosyasını Yükleyin

Bir sonraki adım, yazı tiplerini değiştirmek istediğiniz PDF dosyasını yüklemektir.`Document` Bunu yapmak için sınıf.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

1. Yolu Belirleyin: PDF dosyanızın bulunduğu yolu tanımlayın (`dataDir`).
2.  PDF'yi yükle: Şunu kullanın:`Document` PDF'yi belleğe yükleyerek işleme hazır hale getiren sınıf.

## Adım 3: Metin Parçası Emicisini Ayarlayın

 Belirli metin parçalarındaki yazı tiplerini bulmak ve değiştirmek için şunu kullanacağız:`TextFragmentAbsorber` class. Bu sınıf, belirli metin parçalarını aramanızı ve yazı tipi değiştirme gibi değişiklikleri uygulamanızı sağlar.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
pdfDocument.Pages.Accept(absorber);
```

1.  TextFragmentAbsorber'ı Oluştur: Başlat`TextFragmentAbsorber` ile`TextEditOptions` kullanılmayan yazı tiplerinin kaldırılması da buna dahildir.
2.  Metni Em: Emiciyi belgedeki tüm sayfalara uygulayın.`Accept` Yöntem.

## Adım 4: Metin Parçaları Arasında Gezinme

Metin parçalarını özümsedikten sonra, her parçayı dolaşıp yazı tipini kontrol etmemiz gerekir. Yazı tipi Arial,Bold ise, onu Arial ile değiştireceğiz.

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    if (textFragment.TextState.Font.FontName == "Arial,Bold")
    {
        textFragment.TextState.Font = FontRepository.FindFont("Arial");
    }
}
```

1.  Parçalar Arasında Döngü: Bir`foreach` Her metin parçasında yineleme yapmak için döngü.
2. Yazı Tipini Kontrol Et: Her metin parçası için yazı tipinin Arial,Bold olup olmadığını kontrol edin.
3.  Yazı Tipini Değiştir: Koşul karşılanırsa, şunu kullanın:`FontRepository.FindFont` Arial,Bold'u Arial ile değiştirme yöntemi.

## Adım 5: Güncellenen PDF'yi Kaydedin

Yazı tipi değiştirme işlemi tamamlandıktan sonra güncellenen PDF dosyasını kaydedin.

```csharp
dataDir = dataDir + "ReplaceFonts_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nFonts replaced successfully in pdf document.\nFile saved at " + dataDir);
```

1.  Çıktı Yolunu Tanımla: Güncelle`dataDir` yeni dosya adını içerecek değişken (örneğin,`ReplaceFonts_out.pdf`).
2.  PDF'yi kaydet: Şunu kullan:`Save` Değiştirilen PDF dosyasını kaydetme yöntemi.
3. Başarı Mesajı: PDF'nin kaydedildiğini belirten bir başarı mesajını konsola yazdırın.

## Adım 6: İstisnaları Yönetin

 Programınızın çökmesini önlemek için kodu bir`try-catch` PDF dosyasındaki sorunlar veya eksik yazı tipleri gibi olası hataları ele almak için blok.

```csharp
catch (Exception ex)
{
    Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get a 30 day temporary license.");
}
```

1.  Try-Catch'e sarın: Yazı tipi değiştirme kodunuzu bir`try` engellemek.
2.  İstisnaları Yakala:`catch` Blok, oluşan herhangi bir istisnayı günlüğe kaydeder.

## Çözüm

Aspose.PDF for .NET ile bir PDF dosyasındaki yazı tiplerini değiştirmek hem basit hem de güçlüdür. İster markalamayı güncelleyin ister belgeler arasında tutarlılığı sağlayın, bu işlem size çok zaman kazandırabilir. Yukarıdaki adım adım kılavuzu izleyerek artık C# kullanarak PDF dosyalarınızdaki yazı tiplerini etkili bir şekilde değiştirmek için araçlara sahipsiniz.

## SSS

### Tek bir PDF'deki birden fazla yazı tipini değiştirebilir miyim?
 Evet, yapabilirsiniz. Değiştirebilirsiniz.`if` döngüde birden fazla yazı tipini hedeflemek için koşullar.

### Aspose.PDF for .NET'i kullanmak için lisansa ihtiyacım var mı?
 Evet, bazı özellikler lisans gerektirir. Bir lisans kullanabilirsiniz.[geçici lisans](https://purchase.aspose.com/temporary-license/) veya bir tane satın alın[Burada](https://purchase.aspose.com/buy).

### Fontun sistemime kurulması gerekiyor mu?
Evet, orijinalini değiştireceğiniz fontun sisteminizde mevcut olması gerekir.

### Şifrelenmiş PDF'lerdeki yazı tiplerini değiştirebilir miyim?
 Evet, ancak öncelikle PDF'yi şifresini çözmeniz gerekecek`Document.Decrypt` Yöntem.

### Sorun yaşarsam nasıl yardım alabilirim?
 Şunu kontrol edebilirsiniz:[destek forumu](https://forum.aspose.com/c/pdf/10) yardım için.