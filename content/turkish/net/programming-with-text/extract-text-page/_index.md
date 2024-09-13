---
title: PDF Dosyasındaki Metin Sayfasını Çıkar
linktitle: PDF Dosyasındaki Metin Sayfasını Çıkar
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyasındaki belirli bir sayfadan metnin nasıl çıkarılacağını öğrenin.
type: docs
weight: 200
url: /tr/net/programming-with-text/extract-text-page/
---
Bu eğitim, .NET için Aspose.PDF kullanarak PDF dosyasındaki belirli bir sayfadan metin çıkarma sürecinde size rehberlik edecektir. Sağlanan C# kaynak kodu gerekli adımları göstermektedir.

## Gereksinimler
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Bilgisayarınızda Visual Studio veya herhangi bir C# derleyicisi yüklü olmalıdır.
- Aspose.PDF for .NET kütüphanesi. Resmi Aspose web sitesinden indirebilir veya NuGet gibi bir paket yöneticisi kullanarak kurabilirsiniz.

## Adım 1: Projeyi kurun
1. Tercih ettiğiniz geliştirme ortamında yeni bir C# projesi oluşturun.
2. .NET için Aspose.PDF kitaplığına bir referans ekleyin.

## Adım 2: Gerekli ad alanlarını içe aktarın
Metni çıkarmak istediğiniz kod dosyasında, dosyanın en üstüne aşağıdaki using yönergelerini ekleyin:

```csharp
using Aspose.Pdf;
using System.IO;
```

## Adım 3: Belge dizinini ayarlayın
 Kodda şu satırı bulun:`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` Belgelerinizin saklandığı dizinin yolunu içeren.

## Adım 4: PDF belgesini açın
 Mevcut bir PDF belgesini şu şekilde açın:`Document`yapıcı ve giriş PDF dosyasına giden yolu geçirme.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## Adım 5: Belirli bir sayfadan metin çıkarın
 Bir tane oluştur`TextAbsorber` belgeden metin çıkarmak için nesne. İstenilen sayfa için emiciyi, ona erişerek kabul edin`Pages` koleksiyonu`pdfDocument`.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages[1].Accept(textAbsorber);
```

## Adım 6: Çıkarılan metni alın
 Çıkarılan metne şuradan erişin:`TextAbsorber` nesne.

```csharp
string extractedText = textAbsorber.Text;
```

## Adım 7: Çıkarılan metni kaydedin
 Bir tane oluştur`TextWriter` ve çıkarılan metni kaydetmek istediğiniz dosyayı açın. Çıkarılan metni dosyaya yazın ve akışı kapatın.

```csharp
dataDir = dataDir + "extracted-text_out.txt";
TextWriter tw = new StreamWriter(dataDir);
tw.WriteLine(extractedText);
tw. Close();
```

### .NET için Aspose.PDF kullanarak Metin Sayfası Çıkarma için örnek kaynak kodu 
```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
// Metni çıkarmak için TextAbsorber nesnesi oluşturun
TextAbsorber textAbsorber = new TextAbsorber();
//Belirli bir sayfa için emiciyi kabul et
pdfDocument.Pages[1].Accept(textAbsorber);
// Çıkarılan metni alın
string extractedText = textAbsorber.Text;
dataDir = dataDir + "extracted-text_out.txt";
// Bir yazar oluşturun ve dosyayı açın
TextWriter tw = new StreamWriter(dataDir);
// Dosyaya bir satır metin yaz
tw.WriteLine(extractedText);
// Akışı kapat
tw.Close();
Console.WriteLine("\nText extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

## Çözüm
Aspose.PDF for .NET kullanarak bir PDF belgesinin belirli bir sayfasından metni başarıyla çıkardınız. Çıkarılan metin belirtilen çıktı dosyasına kaydedildi.

### SSS

#### S: Bu eğitimin amacı nedir?

A: Bu eğitim, .NET için Aspose.PDF kullanarak bir PDF dosyasındaki belirli bir sayfadan metin çıkarma sürecinde size rehberlik eder. Eşlik eden C# kaynak kodu, bu görevi başarmak için gereken adımları gösterir.

#### S: Hangi ad alanlarını içe aktarmalıyım?

A: Metni çıkarmayı planladığınız kod dosyasında, dosyanın başına aşağıdaki using yönergelerini ekleyin:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### S: Belge dizinini nasıl belirlerim?

 A: Kodda şunu söyleyen satırı bulun:`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` belge dizininize giden gerçek yol ile.

#### S: Mevcut bir PDF belgesini nasıl açabilirim?

 A: 4. Adımda, mevcut bir PDF belgesini kullanarak açacaksınız.`Document` yapıcı ve giriş PDF dosyasına giden yolu sağlama.

#### S: Belirli bir sayfadan metni nasıl çıkarabilirim?

 A: 5. Adım, bir`TextAbsorber` PDF belgesinden metin çıkarmak için nesne. Daha sonra, istediğiniz sayfa için emiciyi, ona erişerek kabul edeceksiniz`Pages` koleksiyonu`pdfDocument`.

#### S: Çıkarılan metne nasıl ulaşabilirim?

 A: 6. Adım, çıkarılan metne erişmenizde size rehberlik eder`TextAbsorber` nesne.

#### S: Çıkarılan metni bir dosyaya nasıl kaydederim?

 A: 7. Adımda bir tane oluşturacaksınız`TextWriter`, çıkarılan metni kaydetmek istediğiniz dosyayı açın, çıkarılan metni dosyaya yazın ve ardından akışı kapatın.

#### S: Bu eğitimden çıkarılacak en önemli ders nedir?

A: Bu öğreticiyi takip ederek, .NET için Aspose.PDF kullanarak bir PDF belgesinin belirli bir sayfasından metin çıkarmayı öğrendiniz. Çıkarılan metin, belirli sayfalardaki metin içeriğini hedeflemenizi ve analiz etmenizi sağlayan belirli bir çıktı dosyasına kaydedildi.