---
title: PDF Dosyasında Yakınlaştırma Faktörünü Alın
linktitle: PDF Dosyasında Yakınlaştırma Faktörünü Alın
second_title: .NET API Referansı için Aspose.PDF
description: Bu adım adım kılavuzla PDF dosyasında yakınlaştırma faktörünü elde etmek için Aspose.PDF for .NET'i nasıl kullanacağınızı öğrenin.
type: docs
weight: 210
url: /tr/net/programming-with-document/getzoomfactor/
---
Aspose.PDF for .NET, PDF belgeleri üzerinde çeşitli işlemler gerçekleştirmek için birçok özellik sağlayan bir PDF işleme kitaplığıdır. Bu özelliklerden biri de PDF dosyasında yakınlaştırma faktörünü alabilme yeteneğidir. Bu eğitimde, C# kaynak kodunu kullanarak PDF dosyasındaki yakınlaştırma faktörünü elde etmek için Aspose.PDF for .NET'in nasıl kullanılacağını açıklayacağız.


## 1. Adım: Yeni Belge nesnesini örnekleyin

 Aspose.PDF for .NET kullanarak bir PDF dosyasının yakınlaştırma faktörünü elde etmenin ilk adımı yeni bir örnek oluşturmaktır.`Document` nesne.`Document` nesne, bir dosyadan veya akıştan yüklenebilen bir PDF belgesini temsil eder.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Yeni Belge nesnesini başlat
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");
```

 Yukarıdaki kodda bir tane oluşturduk.`Document` PDF dosyasının yolunu yapıcısına ileterek nesneyi`Document` sınıf. "BELGE DİZİNİ"ni, PDF dosyanızın bulunduğu dizinin gerçek yolu ile değiştirmeniz gerekir.

## 2. Adım: GoToAction nesnesini oluşturun

 Bir sonraki adım bir oluşturmaktır`GoToAction` nesne. A`GoToAction`nesne, bir PDF belgesinde belirli bir hedefe giden bir eylemi temsil eder. Bizim durumumuzda, PDF dosyasının yakınlaştırma faktörünü almak istiyoruz, bu nedenle`OpenAction` mülkiyeti`Document` almak için nesne`GoToAction` nesne.

```csharp
// GoToAction nesnesi oluştur
GoToAction action = doc.OpenAction as GoToAction;
```

 Yukarıdaki kodda bir tane oluşturduk.`GoToAction` döküm yaparak nesneyi`OpenAction` mülkiyeti`Document` itiraz etmek`GoToAction`.

## 3. Adım: PDF dosyasının Yakınlaştırma faktörünü alın

 Üçüncü adım, PDF dosyasının yakınlaştırma faktörünü elde etmektir. PDF dosyasının yakınlaştırma faktörünü şuraya erişerek alabiliriz:`Destination` mülkiyeti`GoToAction` nesne ve sonra onu yayına almak`XYZExplicitDestination` .`XYZExplicitDestination` sınıf, bir PDF belgesinde gidilecek koordinatları ve yakınlaştırma faktörünü belirten bir hedefi temsil eder.

```csharp
// PDF dosyasının Yakınlaştırma faktörünü alın
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Belge yakınlaştırma değeri;
```

 Yukarıdaki kodda şuraya ulaştık:`Destination` mülkiyeti`GoToAction` nesneyi seçin ve ardından onu yayınlayın`XYZExplicitDestination` . Bundan sonra şuraya eriştik:`Zoom` mülkiyeti`XYZExplicitDestination` PDF dosyasının yakınlaştırma faktörünü almak için nesneyi kullanın.

## Adım 4: Yakınlaştırma faktörünün çıktısını alın

 Son adım, PDF dosyasının yakınlaştırma faktörünün çıktısını almaktır. Şunu kullanabiliriz:`System.Console.WriteLine`

```csharp
// PDF dosyasının Yakınlaştırma faktörünü alın
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Belge yakınlaştırma değeri;
```        

### Aspose.PDF for .NET kullanarak Yakınlaştırma Faktörü Alma için Örnek Kaynak Kodu

Aspose.PDF for .NET kullanarak Get Zoom Factor'un tam örnek kaynak kodunu burada bulabilirsiniz:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Yeni Belge nesnesini başlat
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");

// GoToAction nesnesi oluştur
GoToAction action = doc.OpenAction as GoToAction;

// PDF dosyasının Yakınlaştırma faktörünü alın
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Belge yakınlaştırma değeri;
```

## Çözüm

Bu eğitimde, bir PDF dosyasının yakınlaştırma faktörünü elde etmek için Aspose.PDF for .NET'in nasıl kullanılacağını araştırdık. Yakınlaştırma faktörü, bir görüntüleyicide açıldığında ilk görüntü boyutunu belirlediği için PDF belgesinin çok önemli bir özelliğidir. Geliştiriciler, yakınlaştırma faktörüne erişerek ve onu kullanarak, son kullanıcılar için görüntüleme deneyimini özelleştirebilir. Aspose.PDF for .NET, yakınlaştırma faktörünü ve gezinmeyle ilgili diğer bilgileri bir PDF belgesinden almak için basit ve etkili bir API sağlayarak geliştiricilerin zengin özelliklere sahip ve etkileşimli PDF uygulamaları oluşturmasına olanak tanır.

### PDF dosyasında yakınlaştırma faktörünü almak için SSS

#### S: Bir PDF dosyasındaki yakınlaştırma faktörü nedir?

C: Bir PDF dosyasındaki yakınlaştırma faktörü, görüntülendiğinde belgeye uygulanan büyütme düzeyini ifade eder. PDF dosyasının ekranda ilk görüntülenme boyutunu belirler. 1,0'lık bir yakınlaştırma faktörü gerçek boyutu temsil eder (%100 yakınlaştırma), 1,0'dan büyük bir yakınlaştırma faktörü bir büyütmeyi temsil eder ve 1,0'dan küçük bir yakınlaştırma faktörü bir küçültmeyi temsil eder.

#### S: Yakınlaştırma faktörü bilgisini uygulamamda nasıl kullanabilirim?

C: Bir PDF belgesinin görüntüleyicide açıldığında ilk görüntülenme boyutunu özelleştirmek için yakınlaştırma faktörü bilgisini kullanabilirsiniz. Örneğin, PDF'nin belirli bir boyutta görüntülenmesini sağlamak veya sayfanın tamamını izleyicinin penceresine sığdırmak için belirli bir yakınlaştırma faktörü ayarlayabilirsiniz.

#### S: Aspose.PDF for .NET'i kullanarak bir PDF belgesinin yakınlaştırma faktörünü programlı olarak değiştirebilir miyim?

 C: Evet, Aspose.PDF for .NET'i kullanarak bir PDF belgesinin yakınlaştırma faktörünü programlı olarak değiştirebilirsiniz. Aşağıdakiler gibi belirli eylemler için yakınlaştırma faktörünü ayarlayabilirsiniz:`GoToAction` veya`GoToRemoteAction`Kullanıcı bağlantılar veya yer imleriyle etkileşimde bulunduğunda belgenin nasıl görüntüleneceğini kontrol etmek için.

#### S: Aspose.PDF for .NET kullanarak bir PDF belgesinde belirli konumlara gitmenin başka yolları var mı?

 C: Evet, Aspose.PDF for .NET, bir PDF belgesindeki belirli konumlara gitmek için çeşitli özellikler sağlar. Kullanmanın yanı sıra`GoToAction` gibi diğer eylemleri kullanabilirsiniz.`GoToURIAction` bir URL'yi açmak için,`GoToEmbeddedAction` katıştırılmış dosyalara gitmek için ve`GoToNamedAction` PDF belgesindeki adlandırılmış hedeflere gitmek için.