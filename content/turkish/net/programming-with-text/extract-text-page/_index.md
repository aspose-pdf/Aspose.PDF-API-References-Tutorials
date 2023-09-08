---
title: PDF Dosyasındaki Metin Sayfasını Çıkart
linktitle: PDF Dosyasındaki Metin Sayfasını Çıkart
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET'i kullanarak PDF dosyasındaki belirli bir sayfadan metni nasıl çıkaracağınızı öğrenin.
type: docs
weight: 200
url: /tr/net/programming-with-text/extract-text-page/
---
Bu eğitim, Aspose.PDF for .NET'i kullanarak PDF dosyasındaki belirli bir sayfadan metin çıkarma sürecinde size rehberlik edecektir. Sağlanan C# kaynak kodu gerekli adımları gösterir.

## Gereksinimler
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Makinenizde kurulu Visual Studio veya başka herhangi bir C# derleyicisi.
- Aspose.PDF for .NET kitaplığı. Resmi Aspose web sitesinden indirebilir veya yüklemek için NuGet gibi bir paket yöneticisi kullanabilirsiniz.

## 1. Adım: Projeyi ayarlayın
1. Tercih ettiğiniz geliştirme ortamında yeni bir C# projesi oluşturun.
2. Aspose.PDF for .NET kitaplığına bir referans ekleyin.

## 2. Adım: Gerekli ad alanlarını içe aktarın
Metni çıkarmak istediğiniz kod dosyasında, dosyanın en üstüne aşağıdaki kullanma yönergelerini ekleyin:

```csharp
using Aspose.Pdf;
using System.IO;
```

## 3. Adım: Belge dizinini ayarlayın
 Kodda yazan satırı bulun`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` belgelerinizin saklandığı dizinin yolu ile birlikte.

## 4. Adım: PDF belgesini açın
 Mevcut bir PDF belgesini kullanarak açın.`Document`yapıcı ve yolu giriş PDF dosyasına geçirme.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## Adım 5: Belirli bir sayfadaki metni çıkarın
 Oluşturmak`TextAbsorber` Belgeden metin çıkarmak için nesne. İstenilen sayfanın emicisini, şu adresten erişerek kabul edin:`Pages` koleksiyonu`pdfDocument`.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages[1].Accept(textAbsorber);
```

## 6. Adım: Çıkarılan metni alın
 Çıkarılan metne erişin`TextAbsorber` nesne.

```csharp
string extractedText = textAbsorber.Text;
```

## 7. Adım: Çıkarılan metni kaydedin
 Oluşturmak`TextWriter` ve çıkarılan metni kaydetmek istediğiniz dosyayı açın. Çıkarılan metni dosyaya yazın ve akışı kapatın.

```csharp
dataDir = dataDir + "extracted-text_out.txt";
TextWriter tw = new StreamWriter(dataDir);
tw.WriteLine(extractedText);
tw. Close();
```

### Aspose.PDF for .NET kullanarak Metin Sayfasını Çıkart için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
// Metni ayıklamak için TextAbsorber nesnesi oluşturun
TextAbsorber textAbsorber = new TextAbsorber();
//Belirli bir sayfa için emiciyi kabul edin
pdfDocument.Pages[1].Accept(textAbsorber);
// Çıkarılan metni alın
string extractedText = textAbsorber.Text;
dataDir = dataDir + "extracted-text_out.txt";
// Bir yazar oluşturun ve dosyayı açın
TextWriter tw = new StreamWriter(dataDir);
// Dosyaya bir satır metin yazın
tw.WriteLine(extractedText);
// Akışı kapat
tw.Close();
Console.WriteLine("\nText extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

## Çözüm
Aspose.PDF for .NET'i kullanarak bir PDF belgesinin belirli bir sayfasından metni başarıyla çıkardınız. Çıkarılan metin belirtilen çıktı dosyasına kaydedildi.

### SSS'ler

#### S: Bu eğitimin amacı nedir?

C: Bu eğitim, Aspose.PDF for .NET'i kullanarak bir PDF dosyasındaki belirli bir sayfadan metin çıkarma sürecinde size rehberlik eder. Ekteki C# kaynak kodu, bu görevi gerçekleştirmek için gerekli adımları gösterir.

#### S: Hangi ad alanlarını içe aktarmalıyım?

C: Metni çıkarmayı planladığınız kod dosyasında, dosyanın başına aşağıdaki kullanma yönergelerini ekleyin:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### S: Belge dizinini nasıl belirlerim?

 C: Kodda şunu yazan satırı bulun:`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

#### S: Mevcut bir PDF belgesini nasıl açarım?

 C: 4. Adımda, mevcut bir PDF belgesini aşağıdaki komutu kullanarak açacaksınız:`Document` yapıcı ve giriş PDF dosyasının yolunu sağlama.

#### S: Belirli bir sayfadan metni nasıl ayıklayabilirim?

 C: Adım 5, bir`TextAbsorber` PDF belgesinden metin çıkarmak için nesne. Daha sonra istediğiniz sayfaya yönelik emiciyi, bu sayfaya erişerek kabul edeceksiniz.`Pages` koleksiyonu`pdfDocument`.

#### S: Çıkarılan metne nasıl erişebilirim?

 C: 6. Adım, dosyadan çıkarılan metne erişim konusunda size rehberlik eder.`TextAbsorber` nesne.

#### S: Çıkarılan metni bir dosyaya nasıl kaydederim?

 C: 7. Adımda bir`TextWriter`, ayıklanan metni kaydetmek istediğiniz dosyayı açın, ayıklanan metni dosyaya yazın ve ardından akışı kapatın.

#### S: Bu eğitimden çıkarılacak önemli sonuç nedir?

C: Bu eğitimi takip ederek Aspose.PDF for .NET kullanarak bir PDF belgesinin belirli bir sayfasından nasıl metin çıkaracağınızı öğrendiniz. Çıkarılan metin belirli bir çıktı dosyasına kaydedilerek belirli sayfalardaki metin içeriğini hedeflemenize ve analiz etmenize olanak sağlar.