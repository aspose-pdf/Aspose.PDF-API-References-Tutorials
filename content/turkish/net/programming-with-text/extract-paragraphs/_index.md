---
title: PDF Dosyasındaki Paragrafları Çıkar
linktitle: PDF Dosyasındaki Paragrafları Çıkar
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyasındaki paragrafların nasıl çıkarılacağını öğrenin.
type: docs
weight: 160
url: /tr/net/programming-with-text/extract-paragraphs/
---
Bu eğitim, .NET için Aspose.PDF kullanarak PDF dosyasındaki paragrafları çıkarma sürecinde size rehberlik edecektir. Sağlanan C# kaynak kodu gerekli adımları göstermektedir.

## Gereksinimler
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Bilgisayarınızda Visual Studio veya herhangi bir C# derleyicisi yüklü olmalıdır.
- Aspose.PDF for .NET kütüphanesi. Resmi Aspose web sitesinden indirebilir veya NuGet gibi bir paket yöneticisi kullanarak kurabilirsiniz.

## Adım 1: Projeyi kurun
1. Tercih ettiğiniz geliştirme ortamında yeni bir C# projesi oluşturun.
2. .NET için Aspose.PDF kitaplığına bir referans ekleyin.

## Adım 2: Gerekli ad alanlarını içe aktarın
Paragrafları çıkarmak istediğiniz kod dosyasında, dosyanın en üstüne aşağıdaki using yönergelerini ekleyin:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

## Adım 3: Belge dizinini ayarlayın
 Kodda şu satırı bulun:`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` Belgelerinizin saklandığı dizinin yolunu içeren.

## Adım 4: PDF belgesini açın
 Mevcut bir PDF belgesini şu şekilde açın:`Document` yapıcı ve giriş PDF dosyasına giden yolu geçirme.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Adım 5: Paragrafları ayıkla
 Örneklemi oluştur`ParagraphAbsorber` sınıfını kullan ve kullan`Visit` Belgeden paragrafları çıkarma yöntemi.

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
```

## Adım 6: Paragraflar arasında gezinin
Metin içeriklerine erişmek için çıkarılan paragraflar arasında döngü yapın. Her paragraftaki bölümler ve satırlar arasında gezinmek için iç içe döngüleri kullanın.

```csharp
foreach(PageMarkup markup in absorber.PageMarkups)
{
     int i = 1;
     foreach(MarkupSection section in markup.Sections)
     {
         int j = 1;
         foreach(MarkupParagraph paragraph in section.Paragraphs)
         {
             StringBuilder paragraphText = new StringBuilder();
             foreach(List<TextFragment> line in paragraph.Lines)
             {
                 foreach(TextFragment fragment in line)
                 {
                     paragraphText.Append(fragment.Text);
                 }
                 paragraphText. Append("\r\n");
             }
             paragraphText. Append("\r\n");
             Console.WriteLine("Paragraph {0} of section {1} on page {2}:", j, i, markup.Number);
             Console.WriteLine(paragraphText.ToString());
             j++;
         }
         i++;
     }
}
```

### .NET için Aspose.PDF kullanarak Paragrafları Çıkarmak için örnek kaynak kodu 
```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Mevcut bir PDF dosyasını açın
Document doc = new Document(dataDir + "input.pdf");
// ParagraphAbsorber'ı örneklendir
ParagraphAbsorber absorber = new ParagraphAbsorber();
absorber.Visit(doc);
foreach (PageMarkup markup in absorber.PageMarkups)
{
	int i = 1;
	foreach (MarkupSection section in markup.Sections)
	{
		int j = 1;
		foreach (MarkupParagraph paragraph in section.Paragraphs)
		{
			StringBuilder paragraphText = new StringBuilder();
			foreach (List<TextFragment> line in paragraph.Lines)
			{
				foreach (TextFragment fragment in line)
				{
					paragraphText.Append(fragment.Text);
				}
				paragraphText.Append("\r\n");
			}
			paragraphText.Append("\r\n");
			Console.WriteLine("Paragraph {0} of section {1} on page {2}:", j, i, markup.Number);
			Console.WriteLine(paragraphText.ToString());
			j++;
		}
		i++;
	}
}
```

## Çözüm
Aspose.PDF for .NET kullanarak bir PDF belgesinden paragrafları başarıyla çıkardınız. Çıkarılan paragraflar konsol penceresinde görüntülendi.

### SSS

#### S: Bu eğitimin amacı nedir?

A: Bu eğitim, .NET için Aspose.PDF kullanarak bir PDF dosyasından paragrafları çıkarma sürecinde size rehberlik etmeyi amaçlamaktadır. Eşlik eden C# kaynak kodu, bu görevi başarmak için pratik adımlar sağlar.

#### S: Hangi ad alanlarını içe aktarmalıyım?

A: Paragrafları çıkarmayı planladığınız kod dosyasında, dosyanın başına aşağıdaki using yönergelerini ekleyin:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

#### S: Belge dizinini nasıl belirlerim?

 A: Satırı bulun`string dataDir = "YOUR DOCUMENT DIRECTORY";` kodda ve değiştir`"YOUR DOCUMENT DIRECTORY"` belge dizininize giden gerçek yol ile.

#### S: Mevcut bir PDF belgesini nasıl açabilirim?

 A: 4. Adımda, mevcut bir PDF belgesini kullanarak açacaksınız.`Document` yapıcı ve giriş PDF dosyasına giden yolu sağlama.

#### S: Belgeden paragrafları nasıl çıkarabilirim?

 A: 5. Adım, bir örnek oluşturmayı içerir`ParagraphAbsorber` sınıf ve kullanımı`Visit` PDF belgesinden paragrafları çıkarma yöntemi.

#### S: Çıkarılan paragraflar arasında nasıl gezinebilirim?

A: 6. Adım, çıkarılan paragraflar arasında döngü yapmanıza rehberlik eder. İç içe döngüler, her paragraftaki bölümler ve satırlar arasında gezinmek, en sonunda metin içeriklerine erişmek ve bunları görüntülemek için kullanılır.

#### S: Bu eğitimden çıkarılacak en önemli ders nedir?

A: Bu öğreticiyi takip ederek, .NET için Aspose.PDF kullanarak bir PDF belgesinden paragrafların nasıl çıkarılacağını öğrendiniz. Çıkarılan paragraflar konsol penceresinde görüntülenerek, belgenin içerik yapısı hakkında size değerli bilgiler sağladı.