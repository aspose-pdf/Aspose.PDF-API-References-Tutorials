---
title: Sütun Metnini PDF Dosyasından Çıkartın
linktitle: Sütun Metnini PDF Dosyasından Çıkartın
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak PDF dosyasındaki sütun metinlerini nasıl çıkaracağınızı öğrenin.
type: docs
weight: 150
url: /tr/net/programming-with-text/extract-columns-text/
---
Bu eğitim, Aspose.PDF for .NET'i kullanarak PDF dosyasındaki sütun metnini çıkarma sürecinde size rehberlik edecektir. Sağlanan C# kaynak kodu gerekli adımları gösterir.

## Gereksinimler
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Makinenizde kurulu Visual Studio veya başka herhangi bir C# derleyicisi.
- Aspose.PDF for .NET kitaplığı. Resmi Aspose web sitesinden indirebilir veya yüklemek için NuGet gibi bir paket yöneticisi kullanabilirsiniz.

## 1. Adım: Projeyi ayarlayın
1. Tercih ettiğiniz geliştirme ortamında yeni bir C# projesi oluşturun.
2. Aspose.PDF for .NET kitaplığına bir referans ekleyin.

## 2. Adım: Gerekli ad alanlarını içe aktarın
Sütun metnini çıkarmak istediğiniz kod dosyasında, dosyanın en üstüne aşağıdaki kullanma yönergelerini ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

## 3. Adım: Belge dizinini ayarlayın
 Kodda yazan satırı bulun`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` belgelerinizin saklandığı dizinin yolu ile birlikte.

## 4. Adım: PDF belgesini açın
 Mevcut bir PDF belgesini kullanarak açın.`Document`yapıcı ve yolu giriş PDF dosyasına geçirme.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## 5. Adım: Yazı tipi boyutunu ayarlayın
Okunabilirliği artırmak ve sütunlu metni daha iyi temsil etmek için metin parçalarının yazı tipi boyutunu 0,7 kat azaltın.

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach(TextFragment tf in tfc)
{
     tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
```

## 6. Adım: Sütunlardan metni çıkarın
 Değiştirilen PDF belgesini bir bellek akışına kaydedin ve yeni bir belge olarak yeniden yükleyin. Daha sonra şunu kullanın:`TextAbsorber` Sütunlardan metin çıkarmak için sınıf.

```csharp
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument);
```

## 7. Adım: Çıkarılan metni kaydedin
Çıkarılan metni belirtilen çıktı dosyası yolundaki bir metin dosyasına kaydedin.

```csharp
dataDir = dataDir + "ExtractColumnsText_out.txt";
File.WriteAllText(dataDir, extractedText);
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

### Aspose.PDF for .NET kullanarak Sütun Metnini Çıkart için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
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
Aspose.PDF for .NET'i kullanarak bir PDF belgesinden sütun metinlerini başarıyla çıkardınız. Çıkarılan metin belirtilen çıktı dosyasına kaydedildi.

### SSS'ler

#### S: Bu eğitimin amacı nedir?

C: Bu eğitim, Aspose.PDF for .NET kullanarak bir PDF dosyasından metin sütunlarının çıkarılması konusunda adım adım bir kılavuz sunar. Ekteki C# kaynak kodu, gerekli prosedürlerin pratik bir gösterimini sağlar.

#### S: Hangi ad alanlarını içe aktarmalıyım?

C: Metin sütunlarını çıkarmayı planladığınız kod dosyasında, dosyanın başına aşağıdaki kullanma yönergelerini ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

#### S: Belge dizinini nasıl belirlerim?

 A: Çizgiyi bulun`string dataDir = "YOUR DOCUMENT DIRECTORY";` kodda ve değiştirin`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

#### S: Mevcut bir PDF belgesini nasıl açarım?

 C: 4. Adımda, mevcut bir PDF belgesini aşağıdaki komutu kullanarak açacaksınız:`Document` yapıcı ve giriş PDF dosyasının yolunu sağlama.

#### S: Yazı tipi boyutu neden ayarlandı?

C: Adım 5, metin parçalarının yazı tipi boyutunun 0,7 kat azaltılmasını içerir. Bu ayarlama okunabilirliği artırır ve sütunlu metni daha doğru şekilde temsil eder.

#### S: Sütunlardan metni nasıl ayıklayabilirim?

 C: Adım 6, değiştirilmiş PDF belgesinin bir bellek akışına kaydedilmesini, yeni bir belge olarak yeniden yüklenmesini ve ardından`TextAbsorber` Sütunlardan metin çıkarmak için sınıf.

#### S: Çıkarılan metni kaydetmenin amacı nedir?

C: 7. Adımda, çıkarılan metni belirtilen çıktı dosyası yolundaki bir metin dosyasına kaydedeceksiniz.

#### S: Çıkartmadan önce neden yazı tipi boyutunu küçültmelisiniz?

C: Yazı tipi boyutunun küçültülmesi, çıkarılan metnin sütunlar içinde düzgün şekilde hizalanmasını sağlayarak orijinal düzenin daha doğru bir temsilini sağlar.

#### S: Bu eğitimden çıkarılacak önemli sonuç nedir?

C: Bu eğitimi takip ederek Aspose.PDF for .NET kullanarak bir PDF belgesinden metin sütunları çıkarmak için gereken bilgi ve becerileri edindiniz. Ortaya çıkan metin belirtilen çıktı dosyasına kaydedildi.