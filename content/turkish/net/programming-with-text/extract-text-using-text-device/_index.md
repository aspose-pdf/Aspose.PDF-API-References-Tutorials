---
title: Metin Aygıtını Kullanarak Metni Çıkarın
linktitle: Metin Aygıtını Kullanarak Metni Çıkarın
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET'teki Metin Aygıtını kullanarak bir PDF belgesinden metnin nasıl çıkarılacağını öğrenin.
type: docs
weight: 210
url: /tr/net/programming-with-text/extract-text-using-text-device/
---
Bu eğitim, .NET için Aspose.PDF'deki Metin Aygıtını kullanarak bir PDF belgesinden metin çıkarma sürecinde size rehberlik edecektir. Sağlanan C# kaynak kodu gerekli adımları göstermektedir.

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
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

## Adım 3: Belge dizinini ayarlayın
 Kodda şu satırı bulun:`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` Belgelerinizin saklandığı dizinin yolunu içeren.

## Adım 4: PDF belgesini açın
 Mevcut bir PDF belgesini şu şekilde açın:`Document`yapıcı ve giriş PDF dosyasına giden yolu geçirme.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## Adım 5: Metin Aygıtını kullanarak metni çıkarın
 Bir tane oluştur`StringBuilder` Çıkarılan metni tutmak için nesne. Belgenin her sayfasını yineleyin ve bir`TextDevice` her sayfadan metni çıkarmak için.

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

## Adım 6: Çıkarılan metni kaydedin
 Çıktı dosyası yolunu belirtin ve çıkarılan metni bir metin dosyasına kaydedin`File.WriteAllText` Yöntem.

```csharp
dataDir = dataDir + "input_Text_Extracted_out.txt";
File.WriteAllText(dataDir, builder.ToString());
```

### .NET için Aspose.PDF kullanarak Metin Aygıtı Kullanarak Metin Çıkarma için örnek kaynak kodu 
```csharp
// Belgeler dizinine giden yol.
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
		// Metin aygıtı oluştur
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
		// Bellek akışından metin al
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

### SSS

#### S: Bu eğitimin amacı nedir?

A: Bu eğitim, .NET için Aspose.PDF'deki Metin Aygıtı özelliğini kullanarak bir PDF belgesinden metin çıkarma konusunda rehberlik sağlar. Eşlik eden C# kaynak kodu, bu görevi başarmak için gerekli adımları gösterir.

#### S: Hangi ad alanlarını içe aktarmalıyım?

A: Metni çıkarmayı planladığınız kod dosyasında, dosyanın başına aşağıdaki using yönergelerini ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

#### S: Belge dizinini nasıl belirlerim?

 A: Kodda şunu söyleyen satırı bulun:`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` belge dizininize giden gerçek yol ile.

#### S: Mevcut bir PDF belgesini nasıl açabilirim?

 A: 4. Adımda, mevcut bir PDF belgesini kullanarak açacaksınız.`Document` yapıcı ve giriş PDF dosyasına giden yolu sağlama.

#### S: Metin Aygıtını kullanarak metni nasıl çıkarabilirim?

 A: 5. Adım, bir`StringBuilder` Çıkarılan metni tutacak nesne. Daha sonra belgenin her sayfasında yineleme yapacaksınız ve bir`TextDevice` ile birlikte`TextExtractionOptions` her sayfadan metin çıkarmak için.

#### S: Çıkarılan metni bir dosyaya nasıl kaydederim?

 A: 6. Adımda çıktı dosyası yolunu belirtecek ve`File.WriteAllText`Çıkarılan metni bir metin dosyasına kaydetme yöntemi.

#### S: Bu eğitimden çıkarılacak en önemli ders nedir?

A: Bu öğreticiyi takip ederek, .NET için Aspose.PDF'deki Metin Aygıtı özelliğinden yararlanarak bir PDF belgesinden metin çıkarmayı öğrendiniz. Çıkarılan metin, belirtilen bir çıktı dosyasına kaydedildi ve bu sayede çıkarılan içeriği gerektiği gibi düzenleyip kullanabilirsiniz.