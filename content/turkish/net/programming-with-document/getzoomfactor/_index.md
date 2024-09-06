---
title: PDF Dosyasında Yakınlaştırma Faktörünü Alın
linktitle: PDF Dosyasında Yakınlaştırma Faktörünü Alın
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım kılavuzla PDF dosyasında yakınlaştırma faktörünü elde etmek için Aspose.PDF for .NET'in nasıl kullanılacağını öğrenin.
type: docs
weight: 210
url: /tr/net/programming-with-document/getzoomfactor/
---
Aspose.PDF for .NET, PDF belgelerinde çeşitli işlemler gerçekleştirmek için birçok özellik sağlayan bir PDF düzenleme kütüphanesidir. Bu özelliklerden biri de PDF dosyasında yakınlaştırma faktörünü elde etme yeteneğidir. Bu eğitimde, C# kaynak kodunu kullanarak PDF dosyasında yakınlaştırma faktörünü elde etmek için Aspose.PDF for .NET'in nasıl kullanılacağını açıklayacağız.


## Adım 1: Yeni Belge nesnesi örneği oluşturun

 Aspose.PDF for .NET kullanarak bir PDF dosyasının yakınlaştırma faktörünü elde etmenin ilk adımı, yeni bir örnek oluşturmaktır.`Document` nesne.`Document` nesne, bir dosyadan veya akıştan yüklenebilen bir PDF belgesini temsil eder.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Yeni Belge nesnesi örneği oluştur
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");
```

 Yukarıdaki kodda bir tane oluşturduk`Document` PDF dosyasının yolunu oluşturucuya geçirerek nesne`Document` sınıf. "YOUR DOCUMENT DIRECTORY" ifadesini PDF dosyanızın bulunduğu dizinin gerçek yoluyla değiştirmeniz gerekir.

## Adım 2: GoToAction nesnesi oluşturun

 Bir sonraki adım, bir tane oluşturmaktır`GoToAction` nesne. Bir`GoToAction`nesne, bir PDF belgesinde belirli bir hedefe giden bir eylemi temsil eder. Bizim durumumuzda, PDF dosyasının yakınlaştırma faktörünü elde etmek istiyoruz, bu nedenle`OpenAction` mülkiyeti`Document` nesneyi elde etmek için`GoToAction` nesne.

```csharp
// GoToAction nesnesi oluştur
GoToAction action = doc.OpenAction as GoToAction;
```

 Yukarıdaki kodda bir tane oluşturduk`GoToAction` nesneyi dökerek`OpenAction` mülkiyeti`Document` itiraz etmek`GoToAction`.

## Adım 3: PDF dosyasının Yakınlaştırma faktörünü alın

 Üçüncü adım PDF dosyasının yakınlaştırma faktörünü elde etmektir. PDF dosyasının yakınlaştırma faktörünü şuraya erişerek elde edebiliriz:`Destination` mülkiyeti`GoToAction` nesne ve ardından onu döküm`XYZExplicitDestination` .`XYZExplicitDestination` sınıf, PDF belgesinde gidilecek koordinatları ve yakınlaştırma faktörünü belirten bir hedefi temsil eder.

```csharp
// PDF dosyasının Yakınlaştırma faktörünü alın
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Belge yakınlaştırma değeri;
```

 Yukarıdaki kodda, şuna eriştik:`Destination` mülkiyeti`GoToAction` nesneyi ve sonra onu şuraya at`XYZExplicitDestination` . Bundan sonra, şuraya eriştik:`Zoom` mülkiyeti`XYZExplicitDestination` PDF dosyasının yakınlaştırma faktörünü almak için nesne.

## Adım 4: Yakınlaştırma faktörünü çıktı olarak alın

 Son adım PDF dosyasının yakınlaştırma faktörünü çıktı olarak vermektir. Şunu kullanabiliriz:`System.Console.WriteLine`

```csharp
// PDF dosyasının Yakınlaştırma faktörünü alın
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Belge yakınlaştırma değeri;
```        

### .NET için Aspose.PDF kullanarak Yakınlaştırma Faktörünü Almak için Örnek Kaynak Kodu

İşte .NET için Aspose.PDF kullanarak Yakınlaştırma Faktörünü Elde Etmenin tam örnek kaynak kodu:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Yeni Belge nesnesi örneği oluştur
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");

// GoToAction nesnesi oluştur
GoToAction action = doc.OpenAction as GoToAction;

// PDF dosyasının Yakınlaştırma faktörünü alın
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Belge yakınlaştırma değeri;
```

## Çözüm

Bu eğitimde, bir PDF dosyasının yakınlaştırma faktörünü almak için Aspose.PDF for .NET'in nasıl kullanılacağını inceledik. Yakınlaştırma faktörü, bir PDF belgesinin önemli bir yönüdür, çünkü bir görüntüleyicide açıldığında ilk görüntüleme boyutunu belirler. Yakınlaştırma faktörüne erişerek ve onu kullanarak, geliştiriciler son kullanıcılar için görüntüleme deneyimini özelleştirebilir. Aspose.PDF for .NET, bir PDF belgesinden yakınlaştırma faktörünü ve diğer gezinmeyle ilgili bilgileri almak için basit ve etkili bir API sağlar ve geliştiricilerin özellik açısından zengin ve etkileşimli PDF uygulamaları oluşturmasını sağlar.

### PDF dosyasında yakınlaştırma faktörünü elde etmek için SSS

#### S: PDF dosyasında yakınlaştırma faktörü nedir?

A: Bir PDF dosyasındaki yakınlaştırma faktörü, belge görüntülendiğinde uygulanan büyütme seviyesini ifade eder. PDF dosyasının ekranda ilk görüntülenme boyutunu belirler. 1,0'lık bir yakınlaştırma faktörü gerçek boyutu (yüzde 100 yakınlaştırma) temsil ederken, 1,0'dan büyük bir yakınlaştırma faktörü bir büyütmeyi, 1,0'dan küçük bir yakınlaştırma faktörü ise bir küçültmeyi temsil eder.

#### S: Uygulamamda yakınlaştırma faktörü bilgisini nasıl kullanabilirim?

A: Bir PDF belgesi görüntüleyicide açıldığında ilk görüntüleme boyutunu özelleştirmek için yakınlaştırma faktörü bilgilerini kullanabilirsiniz. Örneğin, PDF'nin belirli bir boyutta görüntülenmesini veya tüm sayfanın görüntüleyicinin penceresine sığmasını sağlamak için belirli bir yakınlaştırma faktörü ayarlayabilirsiniz.

#### S: Aspose.PDF for .NET kullanarak bir PDF belgesinin yakınlaştırma faktörünü program aracılığıyla değiştirebilir miyim?

 A: Evet, Aspose.PDF for .NET kullanarak bir PDF belgesinin yakınlaştırma faktörünü programatik olarak değiştirebilirsiniz. Yakınlaştırma faktörünü belirli eylemler için ayarlayabilirsiniz, örneğin:`GoToAction` veya`GoToRemoteAction`Kullanıcının bağlantılarla veya yer imleriyle etkileşime girdiğinde belgenin nasıl görüntüleneceğini kontrol etmek için.

#### S: Aspose.PDF for .NET kullanarak bir PDF belgesinde belirli konumlara gitmenin başka yolları var mı?

 A: Evet, Aspose.PDF for .NET, bir PDF belgesindeki belirli konumlara gitmek için çeşitli özellikler sunar.`GoToAction` , diğer eylemleri de kullanabilirsiniz`GoToURIAction` Bir URL'yi açmak için,`GoToEmbeddedAction` gömülü dosyalara gitmek için ve`GoToNamedAction` PDF belgesindeki belirtilen hedeflere gitmek için.