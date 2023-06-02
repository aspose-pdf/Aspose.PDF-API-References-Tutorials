---
title: Yakınlaştırma Faktörünü Alın
linktitle: Yakınlaştırma Faktörünü Alın
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım kılavuz ile bir PDF dosyasının yakınlaştırma faktörünü elde etmek için Aspose.PDF for .NET'i nasıl kullanacağınızı öğrenin.
type: docs
weight: 210
url: /tr/net/programming-with-document/getzoomfactor/
---
Aspose.PDF for .NET, PDF belgeleri üzerinde çeşitli işlemleri gerçekleştirmek için birçok özellik sağlayan bir PDF işleme kitaplığıdır. Bu özelliklerden biri, bir PDF dosyasının yakınlaştırma faktörünü elde etme yeteneğidir. Bu eğitimde, C# kaynak kodunu kullanarak bir PDF dosyasının yakınlaştırma faktörünü elde etmek için Aspose.PDF for .NET'in nasıl kullanılacağını açıklayacağız.


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

 Bir sonraki adım, bir`GoToAction` nesne. A`GoToAction` nesne, bir PDF belgesinde belirli bir hedefe giden bir eylemi temsil eder. Bizim durumumuzda, PDF dosyasının yakınlaştırma faktörünü elde etmek istiyoruz, bu yüzden kullanacağız`OpenAction` mülkiyeti`Document` almak için nesne`GoToAction` nesne.

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
