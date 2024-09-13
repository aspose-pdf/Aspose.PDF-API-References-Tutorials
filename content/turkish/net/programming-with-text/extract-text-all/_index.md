---
title: PDF Dosyasındaki Tüm Metni Çıkar
linktitle: Metni AllIn PDF Dosyasından Çıkar
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyasındaki tüm metinlerin nasıl çıkarılacağını öğrenin.
type: docs
weight: 180
url: /tr/net/programming-with-text/extract-text-all/
---
Bu eğitim, .NET için Aspose.PDF kullanarak PDF dosyasındaki tüm metni çıkarma sürecinde size rehberlik edecektir. Sağlanan C# kaynak kodu gerekli adımları göstermektedir.

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
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

## Adım 5: Tüm metni çıkarın
 Bir tane oluştur`TextAbsorber`Belgeden metin çıkarmak için nesne. Sonra, tüm sayfalar için emiciyi kabul edin.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
```

## Adım 6: Çıkarılan metni alın
 Çıkarılan metne şuradan erişin:`TextAbsorber` nesne.

```csharp
string extractedText = textAbsorber.Text;
```

## Adım 7: Çıkarılan metni kaydedin
 Bir tane oluştur`TextWriter` ve çıkarılan metni kaydetmek istediğiniz dosyayı açın. Çıkarılan metni dosyaya yazın ve akışı kapatın.

```csharp
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
tw.WriteLine(extractedText);
tw. Close();
```

### .NET için Aspose.PDF kullanarak Metnin Tamamını Çıkarma için örnek kaynak kodu 
```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
// Metni çıkarmak için TextAbsorber nesnesi oluşturun
TextAbsorber textAbsorber = new TextAbsorber();
// Tüm sayfalar için emiciyi kabul et
pdfDocument.Pages.Accept(textAbsorber);
// Çıkarılan metni alın
string extractedText = textAbsorber.Text;
// Bir yazar oluşturun ve dosyayı açın
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
// Dosyaya bir satır metin yaz
tw.WriteLine(extractedText);
// Akışı kapat
tw.Close();
```

## Çözüm
Aspose.PDF for .NET kullanarak bir PDF belgesinden tüm metni başarıyla çıkardınız. Çıkarılan metin belirtilen çıktı dosyasına kaydedildi.

### SSS

#### S: Bu eğitimin amacı nedir?

A: Bu eğitim, .NET için Aspose.PDF kullanarak bir PDF dosyasından tüm metni çıkarmanıza yardımcı olacak bir kılavuz görevi görür. Eşlik eden C# kaynak kodu, bu görevi başarmak için adım adım talimatlar sağlar.

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

#### S: Belgedeki tüm metni nasıl çıkarabilirim?

 A: 5. Adım, bir`TextAbsorber` PDF belgesinden metin çıkarmak için nesne. Sonra, tüm sayfalar için emiciyi kabul edeceksiniz.

#### S: Çıkarılan metne nasıl ulaşabilirim?

 A: 6. Adım, çıkarılan metne erişmenizde size rehberlik eder`TextAbsorber` nesne.

#### S: Çıkarılan metni bir dosyaya nasıl kaydederim?

 A: 7. Adımda bir tane oluşturacaksınız`TextWriter`, çıkarılan metni kaydetmek istediğiniz dosyayı açın, çıkarılan metni dosyaya yazın ve ardından akışı kapatın.

#### S: Bu eğitimden çıkarılacak en önemli ders nedir?

A: Bu öğreticiyi takip ederek, .NET için Aspose.PDF kullanarak bir PDF belgesinden tüm metni nasıl çıkaracağınızı öğrendiniz. Çıkarılan metin, belirtilen bir çıktı dosyasına kaydedildi ve bu da belgenin metinsel içeriğini analiz etmenizi ve düzenlemenizi sağlar.