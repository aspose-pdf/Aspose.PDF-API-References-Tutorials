---
title: Yatay ve Dikey Radyo Düğmeleri
linktitle: Yatay ve Dikey Radyo Düğmeleri
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım eğitimle Aspose.PDF for .NET kullanarak PDF'te yatay ve dikey hizalanmış radyo düğmelerinin nasıl oluşturulacağını öğrenin.
type: docs
weight: 180
url: /tr/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---
## giriiş

Etkileşimli PDF formları oluşturmak, özellikle bilgi toplama söz konusu olduğunda kullanıcı deneyimini önemli ölçüde iyileştirebilir. En yaygın form öğelerinden biri, kullanıcıların bir dizi seçenekten birini seçmesine olanak tanıyan radyo düğmesidir. Bu eğitimde, .NET için Aspose.PDF kullanarak yatay ve dikey hizalanmış radyo düğmelerinin nasıl oluşturulacağını inceleyeceğiz. İster deneyimli bir geliştirici olun ister yeni başlıyor olun, bu kılavuz sizi adım adım süreçte yönlendirecek ve her bir parçayı net bir şekilde anlamanızı sağlayacaktır.

## Ön koşullar

Koda dalmadan önce, yerine getirmeniz gereken birkaç ön koşul vardır:

1.  .NET için Aspose.PDF: Aspose.PDF kütüphanesinin yüklü olduğundan emin olun. Bunu şuradan indirebilirsiniz:[alan](https://releases.aspose.com/pdf/net/).
2. Visual Studio: Kodunuzu yazıp test edebileceğiniz bir geliştirme ortamı.
3. Temel C# Bilgisi: C# programlamaya aşina olmak, kod parçacıklarını daha iyi anlamanıza yardımcı olacaktır.

## Paketleri İçe Aktar

Başlamak için, C# projenize gerekli paketleri içe aktarmanız gerekir. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:

### Yeni Bir Proje Oluştur

Visual Studio'yu açın ve yeni bir C# projesi oluşturun. Basitlik için bir Konsol Uygulaması seçebilirsiniz.

### Aspose.PDF Referansını Ekle

1. Çözüm Gezgini’nde projenizin üzerine sağ tıklayın.
2. "NuGet Paketlerini Yönet" seçeneğini seçin.
3. "Aspose.PDF" dosyasını arayın ve en son sürümü yükleyin.

```csharp
using System;
using System.IO;
using Aspose.Pdf.Facades;
using Aspose.Pdf;
using Aspose.Pdf.Forms;
```

Artık her şeyi ayarladığınıza göre, yatay ve dikey hizalanmış radyo düğmeleri oluşturmak için kodu parçalara ayıralım.

## Adım 1: Belge Dizinini Ayarlayın

Bu adımda PDF belgelerinizin saklanacağı dizinin yolunu tanımlayacağız.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` PDF dosyanızı kaydetmek istediğiniz gerçek yol ile. Bu önemlidir çünkü programa girdi dosyalarını nerede arayacağını ve çıktıyı nerede kaydedeceğini söyler.

## Adım 2: Mevcut PDF Belgesini Yükleyin

 Sonra, üzerinde çalışacağımız PDF belgesini yüklememiz gerekiyor. Bu, şu şekilde yapılır:`FormEditor` sınıf.

```csharp
FormEditor formEditor = new FormEditor();
formEditor.BindPdf(dataDir + "input.pdf");
```

Burada, bir örnek oluşturuyoruz`FormEditor` ve onu mevcut bir PDF dosyasına bağlayın`input.pdf`Bu dosyanın belirttiğiniz dizinde bulunduğundan emin olun.

## Adım 3: Radyo Düğmesi Özelliklerini Yapılandırın

Şimdi, radyo düğmelerimiz için bazı özellikler ayarlayalım. Bunlara düğmeler arasındaki boşluk, yönlendirmeleri ve boyutları dahildir.

```csharp
formEditor.RadioGap = 4; // Radyo düğmesi seçenekleri arasındaki mesafe
formEditor.RadioHoriz = true; // Yatay hizalama için doğru olarak ayarlayın
formEditor.RadioButtonItemSize = 20; // Radyo düğmesinin boyutu
formEditor.Facade.BorderWidth = 1; // Sınır genişliği
formEditor.Facade.BorderColor = System.Drawing.Color.Black; // Sınır rengi
```

 Bu özellikler, radyo düğmelerinin PDF'de nasıl görüneceğini tanımlamaya yardımcı olacaktır.`RadioGap` özellik, düğmeler arasındaki boşluğu kontrol ederken`RadioHoriz` düzenlerini belirler.

## Adım 4: Yatay Radyo Düğmeleri Ekleyin

Şimdi PDF'e yatay radyo düğmelerini ekleyelim.

```csharp
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
```

 Bu kodda, radyo düğmeleri için öğeleri tanımlıyoruz ve bunları PDF'e ekliyoruz.`AddField`yöntem, alan türü, alan adı ve yerleştirme koordinatları da dahil olmak üzere çeşitli parametreler alır.

## Adım 5: Dikey Radyo Düğmeleri Ekleyin

Sonra, dikey radyo düğmelerini ekleyeceğiz. Bunu yapmak için, yönelimi tekrar dikey olarak değiştirmemiz gerekiyor.

```csharp
formEditor.RadioHoriz = false; // Dikey hizalama için false olarak ayarlayın
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
```

Daha önce olduğu gibi öğeleri tanımlayıp PDF'e ekliyoruz, ancak bu sefer öğeler dikey olarak hizalanacak.

## Adım 6: PDF Belgesini Kaydedin

Son olarak değiştirdiğimiz PDF belgesini kaydetmemiz gerekiyor.

```csharp
dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
formEditor.Save(dataDir);
Console.WriteLine("\nHorizontally and vertically laid out radio buttons successfully.\nFile saved at " + dataDir);
```

Bu kod PDF'yi yeni eklenen radyo düğmeleriyle kaydeder. Çıktı dosyası için belirtilen dizini kontrol ettiğinizden emin olun.

## Çözüm

Aspose.PDF for .NET kullanarak bir PDF'de radyo düğmeleri oluşturmak basit bir işlemdir. Bu eğitimde özetlenen adımları izleyerek, PDF formlarınıza hem yatay hem de dikey olarak hizalanmış radyo düğmeleri kolayca ekleyebilirsiniz. Bu yalnızca belgelerinizin etkileşimini geliştirmekle kalmaz, aynı zamanda genel kullanıcı deneyimini de iyileştirir. O halde devam edin ve deneyin!

## SSS

### Aspose.PDF for .NET nedir?
Aspose.PDF for .NET, geliştiricilerin PDF belgelerini programlı bir şekilde oluşturmalarına, düzenlemelerine ve dönüştürmelerine olanak tanıyan güçlü bir kütüphanedir.

### Aspose.PDF'yi ücretsiz kullanabilir miyim?
 Evet, Aspose kütüphaneyi değerlendirmek için kullanabileceğiniz ücretsiz bir deneme sürümü sunuyor. İndirebilirsiniz[Burada](https://releases.aspose.com/).

### Aspose.PDF için nasıl destek alabilirim?
 Destek almak için şu adresi ziyaret edebilirsiniz:[Aspose forumu](https://forum.aspose.com/c/pdf/10).

### Aspose.PDF ile başka form elemanları oluşturmak mümkün müdür?
Kesinlikle! Aspose.PDF, metin alanları, onay kutuları ve açılır listeler dahil olmak üzere çeşitli form öğelerini destekler.

### Aspose.PDF for .NET'i nereden satın alabilirim?
 Aspose.PDF for .NET'i şu adresten satın alabilirsiniz:[satın alma sayfası](https://purchase.aspose.com/buy).