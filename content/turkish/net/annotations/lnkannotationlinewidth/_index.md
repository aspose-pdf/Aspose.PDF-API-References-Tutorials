---
title: lnk Açıklama Satır Genişliği
linktitle: lnk Açıklama Satır Genişliği
second_title: Aspose.PDF for .NET API Referansı
description: .NET için Aspose.PDF kullanarak bir PDF'de mürekkep açıklama çizgisi genişliğini nasıl ayarlayacağınızı öğrenin. Bu ayrıntılı eğitim, her adımda size rehberlik ederek yüksek kaliteli çıktı sağlar.
type: docs
weight: 110
url: /tr/net/annotations/lnkannotationlinewidth/
---
## giriiş

PDF belgeleriyle çalışırken, açıklama eklemek bilgileri vurgulamak veya dosyalarınıza etkileşimli öğeler eklemek için güçlü bir yol olabilir. Bu açıklamalardan biri, PDF'nizde serbest biçimli çizgiler çizmenize olanak tanıyan Mürekkep Açıklamasıdır. Peki ya bu çizgilerin görünümünü, özellikle de çizgi genişliğini özelleştirmeniz gerekirse? Bu eğitimde, .NET için Aspose.PDF kullanarak mürekkep açıklaması çizgi genişliğini ayarlama sürecinde size yol göstereceğiz.

## Ön koşullar

Koda dalmadan önce, bu eğitimi sorunsuz bir şekilde takip edebilmeniz için her şeyin ayarlandığından emin olalım:

1.  .NET için Aspose.PDF: .NET için Aspose.PDF kütüphanesinin yüklü olduğundan emin olun. Bunu şuradan indirebilirsiniz:[indirme sayfası](https://releases.aspose.com/pdf/net/) veya Visual Studio'daki NuGet Paket Yöneticisi aracılığıyla yükleyebilirsiniz.
2. Geliştirme Ortamı: Bu eğitimde, Visual Studio gibi bir .NET geliştirme ortamında çalıştığınızı varsayıyoruz.
3. Temel C# Bilgisi: C# hakkında temel bir anlayışa sahip olmak, kodlama adımlarını takip etmenize yardımcı olacaktır.
4. PDF Belgesi: Bu eğitim için mevcut bir PDF belgesini kullanın veya yeni bir tane oluşturun.

## Gerekli Ad Alanlarını İçe Aktarma

Kodlamaya başlamadan önce projenize gerekli ad alanlarını aktardığınızdan emin olun:

```csharp
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using System;
using System.Collections;
using System.Collections.Generic;
```

Bu ad alanları, PDF belgelerini düzenlemek, açıklamalarla çalışmak ve grafik öğelerini işlemek için gereken sınıfları ve yöntemleri sağlar.

Artık ön koşullarımız hazır olduğuna göre, mürekkep ek açıklama satırı genişliğini ayarlama sürecini açık ve yönetilebilir adımlara bölelim.

## Adım 1: PDF Belgesini Başlatın

Öncelikle bir PDF belgesi oluşturmamız veya açmamız gerekiyor. Bu eğitim için sıfırdan yeni bir PDF belgesi oluşturacağız.

```csharp
// PDF Belgesini Başlat
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Belge dizininizi belirtin
Document doc = new Document();
doc.Pages.Add(); // Belgeye boş bir sayfa ekleyin
```

 Burada yeni bir tane başlatıyoruz`Document` nesne, PDF dosyamızı temsil eder. Daha sonra bu belgeye çalışmak için boş bir sayfa ekleriz.

## Adım 2: Mürekkep Açıklamasını Oluşturun

Sonra, mürekkep açıklamasını kendisi oluşturacağız. Bu, mürekkep vuruşlarını oluşturan noktaları tanımlamayı içerir.

```csharp
// Mürekkep Açıklamasını Oluşturun
IList<Point[]> inkList = new List<Point[]>();
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = Color.Red;
lineInfo.LineWidth = 2;
```

 Bu adımda, şunu tanımlıyoruz:`LineInfo` mürekkep vuruşlarının koordinatlarını, görünürlüğünü, rengini ve başlangıç çizgi genişliğini tutan nesne.`VerticeCoordinate` dizi, vuruştaki her noktanın X ve Y koordinatlarını içerir.

## Adım 3: Koordinatları Noktalara Dönüştürün

Şimdi bu koordinatları Ink Annotation'ın kullanabileceği noktalara dönüştürmemiz gerekiyor.

```csharp
// Koordinatları Noktalara Dönüştür
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
    gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}

inkList.Add(gesture);
```

 Bu döngü, koordinat dizisini işler ve her bir koordinat çiftini bir`Point` daha sonra bizimkine eklenen nesne`inkList`.

## Adım 4: PDF Sayfasına Mürekkep Açıklaması Ekleyin

Noktalar hazır olduğuna göre artık mürekkep açıklamasını oluşturabilir ve PDF sayfasına ekleyebiliriz.

```csharp
// PDF Sayfasına Mürekkep Açıklaması Ekleyin
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
a1.Subject = "Test";
a1.Title = "Title";
a1.Color = Aspose.Pdf.Color.FromRgb(Color.Green);
```

 Bu adımda bir`InkAnnotation`nesne, sayfayı, sınırlayıcı bir dikdörtgeni ve nokta listemizi belirtir. Ayrıca açıklamanın konusunu, başlığını ve rengini de ayarlarız.

## Adım 5: Açıklamanın Kenarlığını Özelleştirin

Açıklamamızın görünümünü daha da özelleştirmek için kenarlık özelliklerini değiştireceğiz.

```csharp
// Açıklamanın Kenarlığını Özelleştir
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
doc.Pages[1].Annotations.Add(a1);
```

 Burada bir tane yaratıyoruz`Border` açıklamamız için nesne, genişliğini, efektini, çizgi desenini ve stilini ayarlayarak. Bu adım, açıklamanın PDF sayfasında görsel olarak öne çıkmasını sağlar.

## Adım 6: PDF Belgesini Kaydedin

Son olarak gerekli tüm değişiklikleri yaptıktan sonra belgeyi kaydetmenin zamanı geldi.

```csharp
// PDF Belgesini Kaydet
dataDir = dataDir + "lnkAnnotationLineWidth_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nInk annotation line width setup successfully.\nFile saved at " + dataDir);
```

 Bu kod, değiştirilen PDF belgesini mürekkep açıklamasıyla belirtilen dizine kaydeder.`Console.WriteLine` ifadesi kodun başarılı bir şekilde yürütüldüğünü doğrular.

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesinde mürekkep notu oluşturmayı ve özelleştirmeyi başarıyla gerçekleştirdiniz. Bu eğitim, belgenin başlatılmasından son dosyanın kaydedilmesine kadar tüm süreci kapsıyordu. Bu bilgiyle, Aspose.PDF for .NET'in geniş yeteneklerini daha fazla keşfedebilir ve benzer teknikleri diğer not türlerine veya PDF düzenlemelerine uygulayabilirsiniz.

## SSS

### Mürekkep açıklamasının farklı bölümleri için farklı renkler kullanabilir miyim?  
 Evet, birden fazla oluşturabilirsiniz`InkAnnotation` Farklı renklerdeki nesneleri PDF'nizin aynı veya farklı sayfalarına ekleyin.

### Çizgi genişliğini dinamik olarak nasıl değiştirebilirim?  
 Ayarlayabilirsiniz`LineWidth` mülkiyeti`LineInfo` Koordinatları noktalara dönüştürmeden önce nesne.

### Mürekkep açıklamasını şeffaf yapmak mümkün mü?  
 Evet, değiştirebilirsiniz`Opacity` mülkiyeti`InkAnnotation` şeffaf hale getirmek için nesne.

### Aynı sayfaya birden fazla mürekkep açıklaması ekleyebilir miyim?  
Kesinlikle! İşlemi tekrarlayarak tek bir sayfaya istediğiniz kadar mürekkep notu ekleyebilirsiniz.

### PDF'den mürekkep açıklamasını nasıl kaldırabilirim?  
 Bir açıklamayı kullanarak kaldırabilirsiniz`doc.Pages[1].Annotations.Delete(a1)` yöntem, nerede`a1` sizin açıklama nesnenizdir.