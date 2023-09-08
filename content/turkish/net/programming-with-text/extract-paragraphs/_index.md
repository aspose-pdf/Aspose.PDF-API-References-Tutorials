---
title: PDF Dosyasındaki Paragrafları Çıkart
linktitle: PDF Dosyasındaki Paragrafları Çıkart
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak PDF dosyasındaki paragrafları nasıl çıkaracağınızı öğrenin.
type: docs
weight: 160
url: /tr/net/programming-with-text/extract-paragraphs/
---
Bu eğitim, Aspose.PDF for .NET'i kullanarak PDF dosyasındaki paragrafları çıkarma sürecinde size rehberlik edecektir. Sağlanan C# kaynak kodu gerekli adımları gösterir.

## Gereksinimler
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Makinenizde kurulu Visual Studio veya başka herhangi bir C# derleyicisi.
- Aspose.PDF for .NET kitaplığı. Resmi Aspose web sitesinden indirebilir veya yüklemek için NuGet gibi bir paket yöneticisi kullanabilirsiniz.

## 1. Adım: Projeyi ayarlayın
1. Tercih ettiğiniz geliştirme ortamında yeni bir C# projesi oluşturun.
2. Aspose.PDF for .NET kitaplığına bir referans ekleyin.

## 2. Adım: Gerekli ad alanlarını içe aktarın
Paragrafları çıkarmak istediğiniz kod dosyasında, dosyanın en üstüne aşağıdaki kullanma yönergelerini ekleyin:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

## 3. Adım: Belge dizinini ayarlayın
 Kodda yazan satırı bulun`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` belgelerinizin saklandığı dizinin yolu ile birlikte.

## 4. Adım: PDF belgesini açın
 Mevcut bir PDF belgesini kullanarak açın.`Document`yapıcı ve yolu giriş PDF dosyasına geçirme.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## 5. Adım: Paragrafları çıkarın
 Örnekleyin`ParagraphAbsorber` sınıf ve onu kullanın`Visit` Belgeden paragrafları çıkarma yöntemi.

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
```

## Adım 6: Paragrafları yineleyin
Metin içeriğine erişmek için çıkarılan paragraflar arasında dolaşın. Her paragraftaki bölümler ve çizgiler arasında geçiş yapmak için iç içe geçmiş döngüleri kullanın.

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

### Aspose.PDF for .NET kullanarak Paragraf Çıkarma için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Mevcut bir PDF dosyasını açın
Document doc = new Document(dataDir + "input.pdf");
// Paragraf Emiciyi Örneklendir
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
Aspose.PDF for .NET'i kullanarak bir PDF belgesinden paragrafları başarıyla çıkardınız. Çıkarılan paragraflar konsol penceresinde görüntülendi.

### SSS'ler

#### S: Bu eğitimin amacı nedir?

C: Bu eğitimin amacı, Aspose.PDF for .NET kullanarak bir PDF dosyasından paragraf çıkarma sürecinde size rehberlik etmektir. Ekteki C# kaynak kodu, bu görevi gerçekleştirmek için pratik adımlar sağlar.

#### S: Hangi ad alanlarını içe aktarmalıyım?

C: Paragrafları çıkarmak istediğiniz kod dosyasında, dosyanın başına aşağıdaki kullanma yönergelerini ekleyin:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

#### S: Belge dizinini nasıl belirlerim?

 A: Çizgiyi bulun`string dataDir = "YOUR DOCUMENT DIRECTORY";` kodda ve değiştirin`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

#### S: Mevcut bir PDF belgesini nasıl açarım?

 C: 4. Adımda, mevcut bir PDF belgesini aşağıdaki komutu kullanarak açacaksınız:`Document` yapıcı ve giriş PDF dosyasının yolunu sağlama.

#### S: Belgeden paragrafları nasıl çıkarabilirim?

 C: Adım 5, bir örneğinin oluşturulmasını içerir.`ParagraphAbsorber` sınıf ve onu kullanma`Visit` PDF belgesinden paragrafları çıkarma yöntemi.

#### S: Çıkarılan paragraflar arasında nasıl yineleme yaparım?

C: Adım 6, çıkarılan paragraflar arasında geçiş yapmanızda size rehberlik eder. İç içe döngüler, her paragraf içindeki bölümleri ve satırları geçmek, sonuçta metin içeriğine erişmek ve görüntülemek için kullanılır.

#### S: Bu eğitimden çıkarılacak önemli sonuç nedir?

C: Bu eğitimi takip ederek Aspose.PDF for .NET kullanarak bir PDF belgesinden paragrafların nasıl çıkarılacağını öğrendiniz. Çıkarılan paragraflar konsol penceresinde görüntülenerek belgenin içerik yapısına ilişkin değerli bilgiler sağlanmıştır.