---
title: PDF Dosyasında Karakteri Vurgula
linktitle: PDF Dosyasında Karakteri Vurgula
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyasındaki karakterlerin nasıl vurgulanacağını öğrenin.
type: docs
weight: 240
url: /tr/net/programming-with-text/highlight-character-in-pdf/
---
Bu eğitimde, .NET için Aspose.PDF kütüphanesini kullanarak bir PDF dosyasındaki karakterlerin nasıl vurgulanacağını açıklayacağız. Sağlanan C# kaynak kodunu kullanarak bir PDF dosyasındaki karakterleri vurgulamanın adım adım sürecini ele alacağız.

## Gereksinimler

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Aspose.PDF for .NET kütüphanesi kuruldu.
- C# programlamanın temellerini anlamak.

## Adım 1: Belge Dizinini Ayarlayın

 İlk olarak, giriş PDF dosyanızın bulunduğu dizine giden yolu ayarlamanız gerekir. Değiştir`"YOUR DOCUMENT DIRECTORY"` içinde`dataDir` PDF dosyanızın yolunu içeren değişken.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: PDF Belgesini Yükleyin

 Daha sonra, giriş PDF belgesini kullanarak yüklüyoruz`Aspose.Pdf.Document` sınıf.

```csharp
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
```

## Adım 3: PDF'yi Görüntüye Dönüştür

 Karakterleri vurgulamak için PDF belgesini bir görüntüye dönüştürüyoruz`PdfConverter` sınıf. Dönüştürme için çözünürlüğü ayarlıyoruz ve görüntüyü bir`Bitmap` nesne.

```csharp
int resolution = 150;
using (MemoryStream ms = new MemoryStream())
{
     PdfConverter conv = new PdfConverter(pdfDocument);
     conv. Resolution = new Resolution(resolution, resolution);
     conv. GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
     Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
```

## Adım 4: Karakterleri Vurgulayın

 PDF belgesinin her sayfasında dolaşıyoruz ve bir`TextFragmentAbsorber` sayfadaki tüm kelimeleri bulmak için nesne. Daha sonra dikdörtgenler kullanarak vurgulamak için metin parçaları, segmentler ve karakterler üzerinde yineleme yaparız.

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
{
     // Ölçeği ayarlayın ve dönüştürün
     float scale = resolution / 72f;
     gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);

     // Sayfalar arasında dolaş
     for (int i = 0; i < pdfDocument.Pages.Count; i++)
     {
         Page page = pdfDocument.Pages[1];

         //Sayfadaki tüm kelimeleri bul
         TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
         textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
         page. Accept(textFragmentAbsorber);
         TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

         // Metin parçaları arasında döngü
         foreach(TextFragment textFragment in textFragmentCollection)
         {
             if (i == 0)
             {
                 // Karakterleri vurgula
                 gr.DrawRectangle(
                     Think.Yellow,
                     (float)textFragment.Position.XIndent,
                     (float)textFragment.Position.YIndent,
                     (float)textFragment.Rectangle.Width,
                     (float)textFragment.Rectangle.Height);

                 // Segmentler arasında döngü
                 foreach(TextSegment segment in textFragment.Segments)
                 {
                     // Öne çıkan bölüm
                     gr.DrawRectangle(
                         Think Green,
                         (float)segment.Rectangle.LLX,
                         (float)segment.Rectangle.LLY,
                         (float)segment.Rectangle.Width,
                         (float)segment.Rectangle.Height);

                     // Karakterler arasında döngü
                     foreach(CharInfo characterInfo in segment.Characters)
                     {
                         // Karakteri vurgula
                         gr.DrawRectangle(
                             Think.Black,
                             (float)characterInfo.Rectangle.LLx,
                             (float)characterInfo.Rectangle.LLY,
                             (float)characterInfo.Rectangle.Width,
                             (float)characterInfo.Rectangle.Height);
                     }
                 }
             }
         }
     }
}
```

## Adım 5: Çıktı Görüntüsünü Kaydedin

Son olarak vurgulanan karakterlerle değiştirilmiş görüntüyü belirtilen çıktı dosyasına kaydediyoruz.

```csharp
dataDir = dataDir + "HighlightCharacterInPDF_out.png";
bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
```

### .NET için Aspose.PDF kullanarak PDF'de Karakteri Vurgulamak için örnek kaynak kodu 
```csharp
try
{
	// Belgeler dizinine giden yol.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	int resolution = 150;
	Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
	using (MemoryStream ms = new MemoryStream())
	{
		PdfConverter conv = new PdfConverter(pdfDocument);
		conv.Resolution = new Resolution(resolution, resolution);
		conv.GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
		Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
		using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
		{
			float scale = resolution / 72f;
			gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);
			for (int i = 0; i < pdfDocument.Pages.Count; i++)
			{
				Page page = pdfDocument.Pages[1];
				// Tüm kelimeleri bulmak için TextAbsorber nesnesi oluşturun
				TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
				textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
				page.Accept(textFragmentAbsorber);
				// Çıkarılan metin parçalarını alın
				TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
				// Parçalar arasında döngü
				foreach (TextFragment textFragment in textFragmentCollection)
				{
					if (i == 0)
					{
						gr.DrawRectangle(
						Pens.Yellow,
						(float)textFragment.Position.XIndent,
						(float)textFragment.Position.YIndent,
						(float)textFragment.Rectangle.Width,
						(float)textFragment.Rectangle.Height);
						for (int segNum = 1; segNum <= textFragment.Segments.Count; segNum++)
						{
							TextSegment segment = textFragment.Segments[segNum];
							for (int charNum = 1; charNum <= segment.Characters.Count; charNum++)
							{
								CharInfo characterInfo = segment.Characters[charNum];
								Aspose.Pdf.Rectangle rect = page.GetPageRect(true);
								Console.WriteLine("TextFragment = " + textFragment.Text + "    Page URY = " + rect.URY +
												  "   TextFragment URY = " + textFragment.Rectangle.URY);
								gr.DrawRectangle(
								Pens.Black,
								(float)characterInfo.Rectangle.LLX,
								(float)characterInfo.Rectangle.LLY,
								(float)characterInfo.Rectangle.Width,
								(float)characterInfo.Rectangle.Height);
							}
							gr.DrawRectangle(
							Pens.Green,
							(float)segment.Rectangle.LLX,
							(float)segment.Rectangle.LLY,
							(float)segment.Rectangle.Width,
							(float)segment.Rectangle.Height);
						}
					}
				}
			}
		}
		dataDir = dataDir + "HighlightCharacterInPDF_out.png";
		bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
	}
	Console.WriteLine("\nCharacters highlighted successfully in pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## Çözüm

Bu eğitimde, .NET için Aspose.PDF kütüphanesini kullanarak bir PDF belgesindeki karakterleri nasıl vurgulayacağınızı öğrendiniz. Adım adım kılavuzu takip ederek ve sağlanan C# kodunu çalıştırarak, bir PDF'deki karakterleri vurgulayabilir ve çıktıyı bir resim olarak kaydedebilirsiniz.

### SSS

#### S: "PDF Dosyasında Karakter Vurgulama" eğitiminin amacı nedir?

A: "PDF Dosyasında Karakter Vurgulama" öğreticisi, .NET için Aspose.PDF kütüphanesinin bir PDF belgesindeki karakterleri vurgulamak için nasıl kullanılacağını açıklar. Öğretici, bunu başarmak için adım adım bir kılavuz ve C# kaynak kodu sağlar.

#### S: Neden bir PDF belgesindeki karakterleri vurgulamak isterim?

A: PDF belgesinde karakterleri vurgulamak çeşitli amaçlar için yararlı olabilir. Örneğin belirli bir içeriği vurgulamak veya belirli bir metni daha görünür ve ayırt edilebilir hale getirmek gibi.

#### S: Belge dizinini nasıl ayarlarım?

A: Belge dizinini ayarlamak için:

1.  Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` içinde`dataDir` Girdi PDF dosyanızın bulunduğu dizinin yolunu içeren değişken.

#### S: PDF belgesini nasıl yükleyip görüntüye dönüştürebilirim?

 A: Eğitimde,`Aspose.Pdf.Document` sınıfı, giriş PDF belgesini yüklemek için kullanılır. Ardından,`PdfConverter` sınıf, PDF belgesini bir görüntüye dönüştürmek için kullanılır. Görüntünün çözünürlüğü ayarlanır ve görüntü bir`Bitmap` nesne.

#### S: PDF belge görüntüsündeki karakterleri nasıl vurgularım?

A: Eğitim, PDF belgesinin her sayfasında dolaşarak kelimeleri bulma sürecinde size rehberlik eder.`TextFragmentAbsorber`ve dikdörtgenler kullanarak metin parçaları, segmentler ve karakterler arasında yineleme yaparak bunları vurgulamak.

#### S: Vurgulanan karakterlerin ve bölümlerin görünümünü özelleştirebilir miyim?

C: Evet, çizim işlemlerinde kullanılan renkleri ve stilleri değiştirerek vurgulanan karakterlerin ve segmentlerin görünümünü özelleştirebilirsiniz.

#### S: Vurgulanan karakterlerle değiştirilen resmi nasıl kaydederim?

 A: Bu eğitimde, vurgulanan karakterlerle değiştirilmiş görüntünün belirtilen çıktı dosyasına nasıl kaydedileceği gösterilmektedir.`Save` yöntemi`Bitmap` sınıf.

#### S: Bu eğitim için geçerli bir Aspose Lisansı gerekli mi?

C: Evet, bu eğitimin doğru çalışması için geçerli bir Aspose Lisansı gereklidir. Aspose web sitesinden tam lisans satın alabilir veya 30 günlük geçici lisans edinebilirsiniz.