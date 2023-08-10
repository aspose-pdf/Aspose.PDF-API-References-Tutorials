---
title: Metin Aygıtını Kullanarak Metin Çıkarın
linktitle: Metin Aygıtını Kullanarak Metin Çıkarın
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET'te Metin Aygıtını kullanarak bir PDF belgesinden nasıl metin çıkaracağınızı öğrenin.
type: docs
weight: 210
url: /tr/net/programming-with-text/extract-text-using-text-device/
---

Bu eğitim, Aspose.PDF for .NET'te Metin Aygıtını kullanarak bir PDF belgesinden metin çıkarma sürecinde size rehberlik edecektir. Sağlanan C# kaynak kodu, gerekli adımları gösterir.

## Gereksinimler
Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Visual Studio veya makinenizde kurulu başka bir C# derleyicisi.
- Aspose.PDF for .NET kitaplığı. Resmi Aspose web sitesinden indirebilir veya yüklemek için NuGet gibi bir paket yöneticisi kullanabilirsiniz.

## 1. Adım: Projeyi kurun
1. Tercih ettiğiniz geliştirme ortamında yeni bir C# projesi oluşturun.
2. Aspose.PDF for .NET kitaplığına bir referans ekleyin.

## 2. Adım: Gerekli ad alanlarını içe aktarın
Metni çıkarmak istediğiniz kod dosyasında, dosyanın en üstüne aşağıdaki using yönergelerini ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

## 3. Adım: Belge dizinini ayarlayın
 Kodda yazan satırı bulun`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` belgelerinizin saklandığı dizinin yolu ile.

## 4. Adım: PDF belgesini açın
 kullanarak mevcut bir PDF belgesini açın.`Document` yapıcı ve yolu giriş PDF dosyasına geçirme.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## 5. Adım: Metin Aygıtını kullanarak metni ayıklayın
 Oluşturmak`StringBuilder` ayıklanan metni tutmak için nesne. Belgenin her sayfasını yineleyin ve bir`TextDevice` her sayfadan metni çıkarmak için.

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

## 6. Adım: Ayıklanan metni kaydedin
 Çıktı dosyası yolunu belirtin ve ayıklanan metni kullanarak bir metin dosyasına kaydedin.`File.WriteAllText` yöntem.

```csharp
dataDir = dataDir + "input_Text_Extracted_out.txt";
File.WriteAllText(dataDir, builder.ToString());
```

### Aspose.PDF for .NET kullanarak Text Device Kullanarak Metin Çıkarma için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document( dataDir + "input.pdf");
System.Text.StringBuilder builder = new System.Text.StringBuilder();
// Ayıklanan metni tutmak için dize
string extractedText = "";
foreach (Page pdfPage in pdfDocument.Pages)
{
	using (MemoryStream textStream = new MemoryStream())
	{
		// Metin cihazı oluştur
		TextDevice textDevice = new TextDevice();
		//Metin çıkarma seçeneklerini ayarlayın - metin çıkarma modunu ayarlayın (Ham veya Saf)
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
// Ayıklanan metni metin dosyasına kaydedin
File.WriteAllText(dataDir, builder.ToString());
Console.WriteLine("\nText extracted successfully using text device from page of PDF Document.\nFile saved at " + dataDir);
```

## Çözüm
Aspose.PDF for .NET'teki Metin Aygıtını kullanarak bir PDF belgesinden başarıyla metin çıkardınız. Ayıklanan metin, belirtilen çıktı dosyasına kaydedildi.