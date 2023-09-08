---
title: Metin Aygıtını Kullanarak Metni Çıkarma
linktitle: Metin Aygıtını Kullanarak Metni Çıkarma
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET'teki Metin Aygıtını kullanarak bir PDF belgesinden nasıl metin çıkaracağınızı öğrenin.
type: docs
weight: 210
url: /tr/net/programming-with-text/extract-text-using-text-device/
---
Bu eğitim, Aspose.PDF for .NET'teki Metin Aygıtını kullanarak bir PDF belgesinden metin çıkarma sürecinde size rehberlik edecektir. Sağlanan C# kaynak kodu gerekli adımları gösterir.

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
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

## 3. Adım: Belge dizinini ayarlayın
 Kodda yazan satırı bulun`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` belgelerinizin saklandığı dizinin yolu ile birlikte.

## 4. Adım: PDF belgesini açın
 Mevcut bir PDF belgesini kullanarak açın.`Document`yapıcı ve yolu giriş PDF dosyasına geçirme.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## Adım 5: Metin Aygıtını kullanarak metni çıkarın
 Oluşturmak`StringBuilder` Çıkarılan metni tutacak nesne. Belgenin her sayfasını yineleyin ve bir`TextDevice` Metni her sayfadan çıkarmak için.

```csharp
StringBuilder builder = new StringBuilder();
string extractedText = "";
foreach(Page pdfPage in pdfDocument.Pages)
{
using (MemoryStream textStream = new MemoryStream())
{
TextDevice textDevice = new TextDevice();
TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
textDevice.ExtractionOptions = textExtOptions;
textDevice.Process(pdfPage, textStream);
textStream. Close();
extractedText = Encoding.Unicode.GetString(textStream.ToArray());
}
builder. Append(extractedText);
}
```

## 6. Adım: Çıkarılan metni kaydedin
 Çıktı dosyası yolunu belirtin ve çıkartılan metni kullanarak bir metin dosyasına kaydedin.`File.WriteAllText` yöntem.

```csharp
dataDir = dataDir + "input_Text_Extracted_out.txt";
File.WriteAllText(dataDir, builder.ToString());
```

### Aspose.PDF for .NET kullanarak Metin Aygıtını Kullanarak Metin Çıkarma için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document( dataDir + "input.pdf");
System.Text.StringBuilder builder = new System.Text.StringBuilder();
//Çıkarılan metni tutacak dize
string extractedText = "";
foreach (Page pdfPage in pdfDocument.Pages)
{
	using (MemoryStream textStream = new MemoryStream())
	{
		// Metin cihazı oluştur
		TextDevice textDevice = new TextDevice();
		// Metin çıkarma seçeneklerini ayarlayın - metin çıkarma modunu ayarlayın (Ham veya Saf)
		TextExtractionOptions textExtOptions = new
		TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
		textDevice.ExtractionOptions = textExtOptions;
		// Belirli bir sayfayı dönüştürün ve metni akışa kaydedin
		textDevice.Process(pdfPage, textStream);
		// Belirli bir sayfayı dönüştürün ve metni akışa kaydedin
		textDevice.Process(pdfDocument.Pages[1], textStream);
		// Bellek akışını kapat
		textStream.Close();
		// Bellek akışından metin alın
		extractedText = Encoding.Unicode.GetString(textStream.ToArray());
	}
	builder.Append(extractedText);
}
dataDir = dataDir + "input_Text_Extracted_out.txt";
// Çıkarılan metni metin dosyasına kaydedin
File.WriteAllText(dataDir, builder.ToString());
Console.WriteLine("\nText extracted successfully using text device from page of PDF Document.\nFile saved at " + dataDir);
```

## Çözüm
Aspose.PDF for .NET'teki Metin Aygıtını kullanarak bir PDF belgesinden metni başarıyla çıkardınız. Çıkarılan metin belirtilen çıktı dosyasına kaydedildi.

### SSS'ler

#### S: Bu eğitimin amacı nedir?

C: Bu eğitim, Aspose.PDF for .NET'teki Metin Aygıtı özelliğini kullanarak bir PDF belgesinden metin çıkarma konusunda rehberlik sağlar. Ekteki C# kaynak kodu, bu görevi gerçekleştirmek için gerekli adımları gösterir.

#### S: Hangi ad alanlarını içe aktarmalıyım?

C: Metni çıkarmayı planladığınız kod dosyasında, dosyanın başına aşağıdaki kullanma yönergelerini ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

#### S: Belge dizinini nasıl belirlerim?

 C: Kodda şunu yazan satırı bulun:`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

#### S: Mevcut bir PDF belgesini nasıl açarım?

 C: 4. Adımda, mevcut bir PDF belgesini aşağıdaki komutu kullanarak açacaksınız:`Document` yapıcı ve giriş PDF dosyasının yolunu sağlama.

#### S: Metin Aygıtını kullanarak nasıl metin ayıklayabilirim?

 C: Adım 5, bir`StringBuilder` Çıkarılan metni tutacak nesne. Daha sonra belgenin her sayfasını yineleyecek ve bir`TextDevice` ile birlikte`TextExtractionOptions` Her sayfadan metin çıkarmak için.

#### S: Çıkarılan metni bir dosyaya nasıl kaydederim?

 C: 6. Adımda çıktı dosyasının yolunu belirleyecek ve`File.WriteAllText`Çıkarılan metni bir metin dosyasına kaydetme yöntemi.

#### S: Bu eğitimden çıkarılacak önemli sonuç nedir?

C: Bu eğitimi takip ederek Aspose.PDF for .NET'teki Metin Aygıtı özelliğini kullanarak bir PDF belgesinden metin çıkarmayı öğrendiniz. Çıkarılan metin, belirtilen çıktı dosyasına kaydedilerek, çıkarılan içeriği gerektiği gibi değiştirmenize ve kullanmanıza olanak tanır.