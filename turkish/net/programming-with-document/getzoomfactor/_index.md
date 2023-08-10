---
title: PDF Dosyasında Yakınlaştırma Faktörünü Alın
linktitle: PDF Dosyasında Yakınlaştırma Faktörünü Alın
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım kılavuz ile PDF dosyasında yakınlaştırma faktörünü elde etmek için Aspose.PDF for .NET'i nasıl kullanacağınızı öğrenin.
type: docs
weight: 210
url: /tr/net/programming-with-document/getzoomfactor/
---
Aspose.PDF for .NET, PDF belgeleri üzerinde çeşitli işlemleri gerçekleştirmek için birçok özellik sağlayan bir PDF işleme kitaplığıdır. Bu özelliklerden biri, PDF dosyasında yakınlaştırma faktörünü alabilme yeteneğidir. Bu eğitimde, C# kaynak kodunu kullanarak PDF dosyasında yakınlaştırma faktörünü elde etmek için Aspose.PDF for .NET'in nasıl kullanılacağını açıklayacağız.


## 1. Adım: Yeni Document nesnesinin örneğini oluşturun

 Aspose.PDF for .NET kullanarak bir PDF dosyasının yakınlaştırma faktörünü elde etmenin ilk adımı, yeni bir yakınlaştırma faktörü oluşturmaktır.`Document` nesne. bu`Document` nesne, bir dosyadan veya akıştan yüklenebilen bir PDF belgesini temsil eder.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Yeni Document nesnesinin örneğini oluştur
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");
```

 Yukarıdaki kodda bir tane oluşturduk.`Document` oluşturucusuna PDF dosyasının yolunu ileterek nesneyi`Document` sınıf. "BELGE DİZİNİNİZİ", PDF dosyanızın bulunduğu dizinin gerçek yolu ile değiştirmeniz gerekir.

## 2. Adım: GoToAction nesnesi oluşturun

 Bir sonraki adım, bir`GoToAction` nesne. A`GoToAction`nesne, bir PDF belgesinde belirli bir hedefe giden bir eylemi temsil eder. Bizim durumumuzda, PDF dosyasının yakınlaştırma faktörünü elde etmek istiyoruz, bu yüzden kullanacağız`OpenAction` mülkiyeti`Document` almak için nesne`GoToAction` nesne.

```csharp
// GoToAction nesnesi oluştur
GoToAction action = doc.OpenAction as GoToAction;
```

 Yukarıdaki kodda bir tane oluşturduk.`GoToAction` fırlatarak nesne`OpenAction` mülkiyeti`Document` itiraz etmek`GoToAction`.

## 3. Adım: PDF dosyasının Yakınlaştırma faktörünü alın

 Üçüncü adım, PDF dosyasının yakınlaştırma faktörünü elde etmektir. PDF dosyasına erişerek yakınlaştırma faktörünü alabiliriz.`Destination` mülkiyeti`GoToAction` nesne ve sonra onu yayınlamak`XYZExplicitDestination` . bu`XYZExplicitDestination` class, gidilecek koordinatları ve yakınlaştırma faktörünü belirten bir PDF belgesindeki hedefi temsil eder.

```csharp
// PDF dosyasının Yakınlaştırma faktörünü alın
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Belge yakınlaştırma değeri;
```

 Yukarıdaki kodda, eriştik`Destination` mülkiyeti`GoToAction` nesne ve sonra onu şuraya yayın:`XYZExplicitDestination` . Bundan sonra, erişim sağladık.`Zoom` mülkiyeti`XYZExplicitDestination` PDF dosyasının yakınlaştırma faktörünü almak için nesne.

## Adım 4: Yakınlaştırma faktörünün çıktısını alın

 Son adım, PDF dosyasının yakınlaştırma faktörünü çıkarmaktır. kullanabiliriz`System.Console.WriteLine`

```csharp
// PDF dosyasının Yakınlaştırma faktörünü alın
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Belge yakınlaştırma değeri;
```        

### Aspose.PDF for .NET kullanarak Yakınlaştırma Faktörü Al için Örnek Kaynak Kodu

İşte Aspose.PDF for .NET kullanarak Get Zoom Factor için tam örnek kaynak kodu:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Yeni Document nesnesinin örneğini oluştur
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");

// GoToAction nesnesi oluştur
GoToAction action = doc.OpenAction as GoToAction;

// PDF dosyasının Yakınlaştırma faktörünü alın
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Belge yakınlaştırma değeri;
```

## Çözüm

Bu eğitimde, bir PDF dosyasının yakınlaştırma faktörünü elde etmek için Aspose.PDF for .NET'in nasıl kullanılacağını inceledik. Yakınlaştırma faktörü, bir görüntüleyicide açıldığında ilk ekran boyutunu belirlediğinden, bir PDF belgesinin çok önemli bir yönüdür. Geliştiriciler, yakınlaştırma faktörüne erişip bunu kullanarak son kullanıcılar için görüntüleme deneyimini özelleştirebilir. Aspose.PDF for .NET, bir PDF belgesinden yakınlaştırma faktörü ve navigasyonla ilgili diğer bilgileri almak için basit ve etkili bir API sağlayarak, geliştiricilerin zengin özelliklere sahip ve etkileşimli PDF uygulamaları oluşturmasına olanak tanır.

### PDF dosyasında yakınlaştırma faktörü almak için SSS

#### S: Bir PDF dosyasındaki yakınlaştırma faktörü nedir?

Y: Bir PDF dosyasındaki yakınlaştırma faktörü, görüntülendiğinde belgeye uygulanan büyütme düzeyini ifade eder. PDF dosyasının ekranda ilk görüntülenme boyutunu belirler. 1,0'lık bir yakınlaştırma faktörü gerçek boyutu (%100 yakınlaştırma) temsil ederken, 1,0'dan büyük bir yakınlaştırma faktörü bir büyütmeyi ve 1,0'dan küçük bir yakınlaştırma faktörü bir küçülmeyi temsil eder.

#### S: Yakınlaştırma faktörü bilgisini uygulamamda nasıl kullanabilirim?

Y: Bir görüntüleyicide açıldığında bir PDF belgesinin ilk görüntü boyutunu özelleştirmek için yakınlaştırma faktörü bilgisini kullanabilirsiniz. Örneğin, PDF'nin belirli bir boyutta görüntülenmesini sağlamak veya tüm sayfayı görüntüleyen kişinin penceresine sığdırmak için belirli bir yakınlaştırma faktörü ayarlayabilirsiniz.

#### S: Aspose.PDF for .NET kullanarak bir PDF belgesinin yakınlaştırma faktörünü programlı olarak değiştirebilir miyim?

 C: Evet, Aspose.PDF for .NET kullanarak bir PDF belgesinin yakınlaştırma faktörünü programlı olarak değiştirebilirsiniz. gibi belirli eylemler için yakınlaştırma faktörünü ayarlayabilirsiniz.`GoToAction` veya`GoToRemoteAction`kullanıcı bağlantılar veya yer imleriyle etkileşime girdiğinde belgenin nasıl görüntüleneceğini kontrol etmek için.

#### S: Aspose.PDF for .NET kullanarak bir PDF belgesinde belirli konumlara gitmenin başka yolları var mı?

 C: Evet, Aspose.PDF for .NET, bir PDF belgesinde belirli konumlara gitmek için çeşitli özellikler sağlar. kullanmanın yanı sıra`GoToAction` gibi diğer işlemleri kullanabilirsiniz.`GoToURIAction` URL açmak için,`GoToEmbeddedAction` katıştırılmış dosyalara gitmek için ve`GoToNamedAction` PDF belgesindeki adlandırılmış hedeflere gitmek için.