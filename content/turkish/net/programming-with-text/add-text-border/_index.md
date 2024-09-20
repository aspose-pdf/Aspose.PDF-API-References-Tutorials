---
title: PDF Dosyasına Metin Kenarlığı Ekle
linktitle: PDF Dosyasına Metin Kenarlığı Ekle
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım kılavuzla Aspose.PDF for .NET kullanarak bir PDF dosyasına metin kenarlığı eklemeyi öğrenin. PDF belgelerinizi geliştirin.
type: docs
weight: 70
url: /tr/net/programming-with-text/add-text-border/
---
## giriiş

PDF belgeleri oluşturmak ve düzenlemek günümüzün dijital dünyasında olmazsa olmaz bir beceri haline geldi. İster raporlar, ister faturalar veya başka bir tür belge üretiyor olun, metninizin nasıl göründüğü üzerinde kontrol sahibi olmak önemli bir fark yaratabilir. Uygulamak isteyebileceğiniz bu tür geliştirmelerden biri, bir PDF dosyasındaki metninizin etrafına bir kenarlık eklemektir. Bu kılavuzda, .NET için Aspose.PDF kitaplığını kullanarak bir PDF dosyasına metin kenarlığı ekleme adımlarında size yol göstereceğiz. Hadi, hemen başlayalım!

## Ön koşullar

Başlamadan önce, yerinde olması gereken birkaç şey var. Endişelenmeyin, oldukça basit!

1. Visual Studio: Makinenizde Visual Studio'nun yüklü olduğundan emin olun. Bu, kodunuzu yazıp çalıştıracağınız geliştirme ortamınız olacaktır.
2.  .NET için Aspose.PDF: Aspose.PDF kütüphanesini indirip yüklemeniz gerekecek. Bunu şuradan edinebilirsiniz:[Aspose PDF for .NET indirme sayfası](https://releases.aspose.com/pdf/net/) Eğer önce denemek isterseniz, ayrıca bir tane alabilirsiniz[ücretsiz deneme burada](https://releases.aspose.com/).
3. Temel C# Bilgisi: C# programlama dilinin temellerini anlamak, örnekleri kolayca takip etmenize yardımcı olacaktır.
4. .NET Framework: Projenizde .NET Framework'ün yüklü ve ayarlanmış olduğundan emin olun.

Bu ön koşulları sağladıktan sonra kodlamaya başlamaya hazırsınız!

## Paketleri İçe Aktar

Artık her şeyi ayarladığımıza göre, projemizde Aspose.PDF kullanmak için gerekli paketleri içe aktaralım. Bunu, C# dosyanızın en üstüne aşağıdaki using yönergelerini ekleyerek yapabilirsiniz:

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;

```

Bu ad alanları PDF belgeleri ve metin parçalarıyla etkili bir şekilde çalışmanıza olanak tanır. 

Şimdi, metin kenarlığı ekleme sürecini ayrıntılı adımlara ayıralım. Her adımı ele alacağız, böylece perde arkasında tam olarak neler olduğunu anlayabilirsiniz.

## Adım 1: Belgeyi Ayarlayın

İlk önce, yeni bir PDF belgesi oluşturmamız gerekiyor. Tüm sihrimiz burada gerçekleşecek.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Yeni belge nesnesi oluştur
Document pdfDocument = new Document();
```

 Bu adımda, PDF dosyamızı kaydetmek istediğimiz dizini belirtiyoruz. Ardından, yeni bir örnek oluşturuyoruz`Document` PDF dokümanımızı temsil eden sınıf.

## Adım 2: Yeni Bir Sayfa Ekleyin

Sonra, belgemize bir sayfa eklememiz gerekiyor. Bunu, metnimizi yerleştireceğimiz boş bir tuval eklemek olarak düşünün.

```csharp
// Belirli sayfayı al
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

 Burada şunu diyoruz:`Add()` yöntem üzerinde`Pages` koleksiyonumuz`pdfDocument` nesne. Bu, belgeye yeni bir sayfa ekler ve buna bir referansı şurada saklarız:`pdfPage` değişken.

## Adım 3: Bir Metin Parçası Oluşturun

Şimdi PDF'imizde görüntülemek istediğimiz metni oluşturalım. Burada metin parçamızın içeriğini tanımlıyoruz.

```csharp
// Metin parçası oluştur
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

 Bu kodda yeni bir tane oluşturuyoruz`TextFragment` "ana metin" metni olan nesne. Ayrıca sayfadaki konumunu da kullanarak ayarladık`Position` sınıf. (100, 600) koordinatları metnin sayfada nereye yerleştirileceğini belirtir.

## Adım 4: Metin Özelliklerini Ayarlayın

Sonra, metin parçamızı görsel olarak çekici hale getirmek için özelleştireceğiz. Bu, yazı tipi boyutunu, yazı tipini, arka plan rengini ve ön plan rengini ayarlamayı içerir.

```csharp
// Metin özelliklerini ayarla
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
```

Burada, yazı tipi boyutunu 12'ye ayarlıyoruz, yazı tipi olarak "Times New Roman" kullanıyoruz ve kırmızı metinle açık gri bir arka plan rengi uyguluyoruz. Bu özellikler metnin görünürlüğünü artırmaya yardımcı olur.

## Adım 5: Kenarlık için Kontur Rengini Ayarlayın

Şimdi heyecan verici kısma geliyoruz: Metnimizin etrafına bir kenarlık ekleme!

```csharp
// Metin dikdörtgeni etrafına kenarlık (vuruş) çizmek için StrokingColor özelliğini ayarlayın
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

Bu adımda metnimizin etrafına çizmek istediğimiz kenarlığın rengini belirtiyoruz. Burada koyu kırmızı bir renk seçtik.

## Adım 6: Metin Dikdörtgen Kenarlığını Etkinleştirin

 Metnimizin etrafına sınır çizmek için,`DrawTextRectangleBorder` mülk.

```csharp
// DrawTextRectangleBorder özelliğinin değerini true olarak ayarlayın
textFragment.TextState.DrawTextRectangleBorder = true;
```

 Bu özelliği şu şekilde ayarlayarak:`true`, Aspose.PDF'e, belirtilen vuruş rengine göre metin dikdörtgeninin etrafına kenarlık çizmesini söylüyoruz.

## Adım 7: Metin Parçasını Sayfaya Ekleyin

Artık metin parçacığımız tüm özellikleri ayarlanmış şekilde hazır olduğuna göre, onu sayfaya eklemenin zamanı geldi.

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

 Burada bir tane yaratıyoruz`TextBuilder` Bizimle ilişkili olan nesne`pdfPage` Daha sonra şunu kullanırız:`AppendText` yöntemimizi eklemek için`textFragment` sayfaya. 

## Adım 8: Belgeyi Kaydedin

Son olarak, PDF belgemizi belirtilen dizine kaydetmemiz gerekiyor. İşte gerçek an!

```csharp
// Belgeyi kaydet
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

Bu adımda şunu çağırıyoruz:`Save` yöntemimiz`pdfDocument` nesne, dosyayı kaydetmek istediğimiz yolu sağlar. Kodu çalıştırdığınızda, belirtilen dizinde metin kenarlığıyla yeni oluşturduğunuz PDF'yi bulmalısınız!

## Çözüm

İşte oldu! Aspose.PDF for .NET kullanarak bir PDF dosyasına başarıyla bir metin kenarlığı eklediniz. Bu basit ama güçlü özellik, PDF belgelerinizin okunabilirliğini ve estetiğini önemli ölçüde artırabilir. İster raporlar, ister broşürler veya başka herhangi bir tür belge oluşturuyor olun, metin biçimlendirmesini nasıl değiştireceğinizi bilmek işinize yarayabilir.

## SSS

### Aspose.PDF for .NET nedir?
Aspose.PDF for .NET, geliştiricilerin .NET çerçevesini kullanarak PDF belgelerini programlı bir şekilde oluşturmalarına, düzenlemelerine ve işlemelerine olanak tanıyan güçlü bir kütüphanedir.

### Aspose.PDF'yi ücretsiz deneyebilir miyim?
 Evet! Aspose bir teklif sunuyor[ücretsiz deneme](https://releases.aspose.com/) PDF kütüphanesini kullanarak satın alma işlemi yapmadan önce özelliklerini test edebilirsiniz.

### Aspose.PDF for .NET'i nasıl satın alabilirim?
 Aspose.PDF for .NET'i doğrudan şu adresten satın alabilirsiniz:[satın alma sayfası](https://purchase.aspose.com/buy).

### Aspose.PDF için destek mevcut mu?
 Kesinlikle! Ziyaret ederek destek alabilirsiniz.[Aspose destek forumu](https://forum.aspose.com/c/pdf/10).

### Geçici lisansa ihtiyacım olursa ne olur?
 Aspose bir sağlar[geçici lisans](https://purchase.aspose.com/temporary-license/) Kütüphaneyi sınırlı bir süre için değerlendirmesi gereken geliştiriciler için bir seçenek.