---
title: PDF Dosyasındaki Sayfa Bölgesinden Metni Çıkar
linktitle: PDF Dosyasındaki Sayfa Bölgesinden Metni Çıkar
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyasındaki bir sayfanın belirli bir bölgesinden metnin nasıl çıkarılacağını öğrenin.
type: docs
weight: 190
url: /tr/net/programming-with-text/extract-text-from-page-region/
---
Bu eğitim, .NET için Aspose.PDF kullanarak PDF dosyasındaki bir sayfadaki belirli bir bölgeden metin çıkarma sürecinde size rehberlik edecektir. Sağlanan C# kaynak kodu gerekli adımları göstermektedir.

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
 Mevcut bir PDF belgesini şu şekilde açın:`Document` yapıcı ve giriş PDF dosyasına giden yolu geçirme.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

## Adım 5: Bir sayfa bölgesinden metni çıkarın
 Bir tane oluştur`TextAbsorber` belgeden metin çıkarmak için nesne. Yapılandır`TextSearchOptions` Aramayı bir dikdörtgenle tanımlanan belirli bir sayfa bölgesiyle sınırlamak için.

```csharp
TextAbsorber absorb = new TextAbsorber();
absorb.TextSearchOptions.LimitToPageBounds = true;
absorb.TextSearchOptions.Rectangle = new Aspose.Pdf.Rectangle(100, 200, 250, 350);
pdfDocument.Pages[1].Accept(absorb);
```

## Adım 6: Çıkarılan metni alın
 Çıkarılan metne şuradan erişin:`TextAbsorber` nesne.

```csharp
string extractedText = absorb.Text;
```

## Adım 7: Çıkarılan metni kaydedin
 Bir tane oluştur`TextWriter` ve çıkarılan metni kaydetmek istediğiniz dosyayı açın. Çıkarılan metni dosyaya yazın ve akışı kapatın.

```csharp
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
tw.WriteLine(extractedText);
tw. Close();
```

### .NET için Aspose.PDF kullanarak Sayfa Bölgesinden Metin Çıkarma için örnek kaynak kodu 
```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
// Metni çıkarmak için TextAbsorber nesnesi oluşturun
TextAbsorber absorber = new TextAbsorber();
absorber.TextSearchOptions.LimitToPageBounds = true;
absorber.TextSearchOptions.Rectangle = new Aspose.Pdf.Rectangle(100, 200, 250, 350);
// İlk sayfa için emiciyi kabul et
pdfDocument.Pages[1].Accept(absorber);
// Çıkarılan metni alın
string extractedText = absorber.Text;
// Bir yazar oluşturun ve dosyayı açın
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
// Dosyaya bir satır metin yaz
tw.WriteLine(extractedText);
// Akışı kapat
tw.Close();
```

## Çözüm
Aspose.PDF for .NET kullanarak bir PDF belgesinin bir sayfasındaki belirli bir bölgeden metni başarıyla çıkardınız. Çıkarılan metin belirtilen çıktı dosyasına kaydedildi.

### SSS

#### S: Bu eğitimin amacı nedir?

A: Bu eğitim, .NET için Aspose.PDF kullanarak bir PDF dosyasındaki bir sayfadaki belirli bir bölgeden metin çıkarma sürecinde size rehberlik etmeyi amaçlamaktadır. Eşlik eden C# kaynak kodu, bu görevi gerçekleştirmek için adım adım talimatlar sağlar.

#### S: Hangi ad alanlarını içe aktarmalıyım?

A: Metni çıkarmayı planladığınız kod dosyasında, dosyanın başına aşağıdaki using yönergelerini ekleyin:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### S: Belge dizinini nasıl belirlerim?

 A: Satırı bulun`string dataDir = "YOUR DOCUMENT DIRECTORY";` kodda ve değiştir`"YOUR DOCUMENT DIRECTORY"` belge dizininize giden gerçek yol ile.

#### S: Mevcut bir PDF belgesini nasıl açabilirim?

 A: 4. Adımda, mevcut bir PDF belgesini kullanarak açacaksınız.`Document` yapıcı ve giriş PDF dosyasına giden yolu sağlama.

#### S: Belirli bir sayfa bölgesinden metni nasıl çıkarabilirim?

 A: 5. Adım, bir`TextAbsorber`PDF belgesinden metin çıkarmak için nesne. Daha sonra yapılandıracaksınız`TextSearchOptions` Sayfada koordinatları kullanarak belirli bir dikdörtgen bölge tanımlamak.

#### S: Çıkarılan metne nasıl ulaşabilirim?

 A: 6. Adım, çıkarılan metne erişmenizde size rehberlik eder`TextAbsorber` nesne.

#### S: Çıkarılan metni bir dosyaya nasıl kaydederim?

 A: 7. Adımda bir tane oluşturacaksınız`TextWriter`, çıkarılan metni kaydetmek istediğiniz dosyayı açın, çıkarılan metni dosyaya yazın ve ardından akışı kapatın.

#### S: Bu eğitimden çıkarılacak en önemli ders nedir?

A: Bu öğreticiyi takip ederek, .NET için Aspose.PDF kullanarak bir PDF belgesinin bir sayfasındaki belirli bir bölgeden metni nasıl çıkaracağınızı öğrendiniz. Çıkarılan metin, belirtilen bir çıktı dosyasına kaydedildi ve bu da istenen metin içeriğini hassas bir şekilde hedeflemenize ve analiz etmenize olanak tanır.