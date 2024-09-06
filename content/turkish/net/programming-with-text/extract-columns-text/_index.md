---
title: PDF Dosyasındaki Sütun Metnini Çıkar
linktitle: PDF Dosyasındaki Sütun Metnini Çıkar
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyasındaki sütun metinlerinin nasıl çıkarılacağını öğrenin.
type: docs
weight: 150
url: /tr/net/programming-with-text/extract-columns-text/
---
Bu eğitim, .NET için Aspose.PDF kullanarak PDF dosyasındaki sütun metinlerini çıkarma sürecinde size rehberlik edecektir. Sağlanan C# kaynak kodu gerekli adımları göstermektedir.

## Gereksinimler
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Bilgisayarınızda Visual Studio veya herhangi bir C# derleyicisi yüklü olmalıdır.
- Aspose.PDF for .NET kütüphanesi. Resmi Aspose web sitesinden indirebilir veya NuGet gibi bir paket yöneticisi kullanarak kurabilirsiniz.

## Adım 1: Projeyi kurun
1. Tercih ettiğiniz geliştirme ortamında yeni bir C# projesi oluşturun.
2. .NET için Aspose.PDF kitaplığına bir referans ekleyin.

## Adım 2: Gerekli ad alanlarını içe aktarın
Sütun metinlerini çıkarmak istediğiniz kod dosyasında, dosyanın en üstüne aşağıdaki using yönergelerini ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

## Adım 3: Belge dizinini ayarlayın
 Kodda şu satırı bulun:`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` Belgelerinizin saklandığı dizinin yolunu içeren.

## Adım 4: PDF belgesini açın
 Mevcut bir PDF belgesini şu şekilde açın:`Document` yapıcı ve giriş PDF dosyasına giden yolu geçirme.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## Adım 5: Yazı tipi boyutunu ayarlayın
Okunabilirliği artırmak ve sütunlu metni daha iyi temsil etmek için metin parçalarının yazı tipi boyutunu 0,7 oranında azaltın.

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach(TextFragment tf in tfc)
{
     tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
```

## Adım 6: Sütunlardan metin çıkarın
 Değiştirilen PDF belgesini bir bellek akışına kaydedin ve yeni bir belge olarak yeniden yükleyin. Ardından, şunu kullanın:`TextAbsorber` Sütunlardan metin çıkarmak için sınıf.

```csharp
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument);
```

## Adım 7: Çıkarılan metni kaydedin
Çıkarılan metni belirtilen çıktı dosyası yolundaki bir metin dosyasına kaydedin.

```csharp
dataDir = dataDir + "ExtractColumnsText_out.txt";
File.WriteAllText(dataDir, extractedText);
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

### .NET için Aspose.PDF kullanarak Sütun Metnini Çıkarmak için örnek kaynak kodu 
```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");                
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach (TextFragment tf in tfc)
{
	// Yazı tipi boyutunu en az %70 oranında küçültmeniz gerekiyor
	tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument); 
dataDir = dataDir + "ExtractColumnsText_out.txt";
System.IO.File.WriteAllText(dataDir, extractedText);           
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

## Çözüm
Aspose.PDF for .NET kullanarak bir PDF belgesinden sütun metinlerini başarıyla çıkardınız. Çıkarılan metin belirtilen çıktı dosyasına kaydedildi.

### SSS

#### S: Bu eğitimin amacı nedir?

A: Bu eğitim, .NET için Aspose.PDF kullanarak bir PDF dosyasından metin sütunlarını çıkarmak için adım adım bir kılavuz sunar. Eşlik eden C# kaynak kodu, gerekli prosedürlerin pratik bir gösterimini sağlar.

#### S: Hangi ad alanlarını içe aktarmalıyım?

A: Metin sütunlarını çıkarmayı planladığınız kod dosyasında, dosyanın başına aşağıdaki using yönergelerini ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

#### S: Belge dizinini nasıl belirlerim?

 A: Satırı bulun`string dataDir = "YOUR DOCUMENT DIRECTORY";` kodda ve değiştir`"YOUR DOCUMENT DIRECTORY"` belge dizininize giden gerçek yol ile.

#### S: Mevcut bir PDF belgesini nasıl açabilirim?

 A: 4. Adımda, mevcut bir PDF belgesini kullanarak açacaksınız.`Document` yapıcı ve giriş PDF dosyasına giden yolu sağlama.

#### S: Yazı tipi boyutu neden ayarlanıyor?

A: Adım 5, metin parçalarının yazı tipi boyutunu 0,7 faktörüyle azaltmayı içerir. Bu ayarlama okunabilirliği artırır ve sütunlu metni daha doğru bir şekilde temsil eder.

#### S: Sütunlardan metni nasıl çıkarabilirim?

 A: 6. Adım, değiştirilen PDF belgesini bir bellek akışına kaydetmek, yeni bir belge olarak yeniden yüklemek ve ardından`TextAbsorber` Sütunlardan metin çıkarmak için sınıf.

#### S: Çıkarılan metnin kaydedilmesinin amacı nedir?

A: 7. Adımda, çıkarılan metni belirtilen çıktı dosyası yolundaki bir metin dosyasına kaydedeceksiniz.

#### S: Çıkarmadan önce yazı tipi boyutunu neden küçültmek gerekiyor?

A: Yazı tipi boyutunu küçültmek, çıkarılan metnin sütunlar içinde düzgün bir şekilde hizalanmasını sağlayarak, orijinal düzenin daha doğru bir şekilde gösterilmesini sağlar.

#### S: Bu eğitimden çıkarılacak en önemli ders nedir?

A: Bu öğreticiyi takip ederek, .NET için Aspose.PDF kullanarak bir PDF belgesinden metin sütunlarını çıkarmak için gereken bilgi ve becerileri edindiniz. Ortaya çıkan metin belirtilen çıktı dosyasına kaydedildi.