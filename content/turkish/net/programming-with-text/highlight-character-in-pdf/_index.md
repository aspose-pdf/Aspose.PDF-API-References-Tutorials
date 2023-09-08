---
title: PDF Dosyasındaki Karakteri Vurgula
linktitle: PDF Dosyasındaki Karakteri Vurgula
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak PDF dosyasındaki karakterleri nasıl vurgulayacağınızı öğrenin.
type: docs
weight: 240
url: /tr/net/programming-with-text/highlight-character-in-pdf/
---
Bu eğitimde, .NET için Aspose.PDF kütüphanesini kullanarak bir PDF dosyasındaki karakterlerin nasıl vurgulanacağını açıklayacağız. Sağlanan C# kaynak kodunu kullanarak bir PDF'deki karakterleri vurgulama işlemini adım adım gerçekleştireceğiz.

## Gereksinimler

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Aspose.PDF for .NET kütüphanesi kuruldu.
- C# programlamanın temel anlayışı.

## 1. Adım: Belge Dizinini Ayarlayın

 Öncelikle, giriş PDF dosyanızın bulunduğu dizinin yolunu ayarlamanız gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` içinde`dataDir` PDF dosyanızın yolunu içeren değişken.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: PDF Belgesini Yükleyin

 Daha sonra, giriş PDF belgesini kullanarak yükleriz.`Aspose.Pdf.Document` sınıf.

```csharp
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
```

## 3. Adım: PDF'yi Görüntüye Dönüştürün

 Karakterleri vurgulamak için PDF belgesini,`PdfConverter` sınıf. Dönüşümün çözünürlüğünü ayarlıyoruz ve görüntüyü bir`Bitmap` nesne.

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

 PDF belgesinin her sayfasında döngü yaparız ve`TextFragmentAbsorber` sayfadaki tüm kelimeleri bulmak için nesne. Daha sonra dikdörtgenler kullanarak bunları vurgulamak için metin parçalarını, bölümleri ve karakterleri yineliyoruz.

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
{
     //Ölçeği ayarlayın ve dönüştürün
     float scale = resolution / 72f;
     gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);

     // Sayfalar arasında dolaş
     for (int i = 0; i < pdfDocument.Pages.Count; i++)
     {
         Page page = pdfDocument.Pages[1];

         // Sayfadaki tüm kelimeleri bulun
         TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
         textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
         page. Accept(textFragmentAbsorber);
         TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

         // Metin parçaları arasında döngü yapın
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

                 // Segmentler arasında döngü yapın
                 foreach(TextSegment segment in textFragment.Segments)
                 {
                     // Segmenti vurgula
                     gr.DrawRectangle(
                         Think Green,
                         (float)segment.Rectangle.LLX,
                         (float)segment.Rectangle.LLY,
                         (float)segment.Rectangle.Width,
                         (float)segment.Rectangle.Height);

                     // Karakterler arasında döngü yap
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

Son olarak, vurgulanan karakterlerle değiştirilen görüntüyü belirtilen çıktı dosyasına kaydediyoruz.

```csharp
dataDir = dataDir + "HighlightCharacterInPDF_out.png";
bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
```

### Aspose.PDF for .NET kullanarak PDF'de Karakteri Vurgulama için örnek kaynak kodu 
```csharp
try
{
	// Belgeler dizininin yolu.
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
				// Parçalar arasında döngü yapın
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

Bu eğitimde, .NET için Aspose.PDF kütüphanesini kullanarak bir PDF belgesindeki karakterleri nasıl vurgulayacağınızı öğrendiniz. Adım adım kılavuzu izleyerek ve verilen C# kodunu çalıştırarak, PDF'deki karakterleri vurgulayabilir ve çıktıyı resim olarak kaydedebilirsiniz.

### SSS'ler

#### S: "PDF Dosyasındaki Karakteri Vurgula" eğitiminin amacı nedir?

C: "PDF Dosyasındaki Karakteri Vurgula" eğitimi, bir PDF belgesindeki karakterleri vurgulamak için .NET için Aspose.PDF kütüphanesinin nasıl kullanılacağını açıklar. Öğreticide bunu başarmak için adım adım kılavuz ve C# kaynak kodu sağlanır.

#### S: Bir PDF belgesindeki karakterleri neden vurgulamak isteyeyim?

C: Bir PDF belgesindeki karakterleri vurgulamak, belirli içeriği vurgulamak veya belirli metni daha görünür ve ayırt edilebilir kılmak gibi çeşitli amaçlar için yararlı olabilir.

#### S: Belge dizinini nasıl ayarlarım?

C: Belge dizinini ayarlamak için:

1.  Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` içinde`dataDir` giriş PDF dosyanızın bulunduğu dizinin yolunu içeren değişken.

#### S: PDF belgesini nasıl yükleyebilirim ve onu bir görüntüye nasıl dönüştürebilirim?

 C: Eğitimde,`Aspose.Pdf.Document` sınıfı, giriş PDF belgesini yüklemek için kullanılır. Sonra`PdfConverter` PDF belgesini bir görüntüye dönüştürmek için sınıf kullanılır. Görüntünün çözünürlüğü ayarlanır ve görüntü bir`Bitmap` nesne.

#### S: PDF belge görüntüsündeki karakterleri nasıl vurgularım?

C: Eğitim, PDF belgesinin her sayfasında döngü yaparak kelimeleri bulma sürecinde size rehberlik eder.`TextFragmentAbsorber`ve metin parçalarını, bölümleri ve karakterleri yineleyerek dikdörtgenler kullanarak bunları vurgulayın.

#### S: Vurgulanan karakterlerin ve bölümlerin görünümünü özelleştirebilir miyim?

C: Evet, çizim işlemlerinde kullanılan renkleri ve stilleri değiştirerek vurgulanan karakterlerin ve bölümlerin görünümünü özelleştirebilirsiniz.

#### S: Değiştirilen görüntüyü vurgulanan karakterlerle nasıl kaydederim?

 C: Eğitimde, vurgulanan karakterlerle değiştirilen görüntünün belirtilen çıktı dosyasına nasıl kaydedileceği gösterilmektedir.`Save` yöntemi`Bitmap` sınıf.

#### S: Bu eğitim için geçerli bir Aspose Lisansı gerekli mi?

C: Evet, bu eğitimin düzgün çalışması için geçerli bir Aspose Lisansı gereklidir. Aspose web sitesinden tam lisans satın alabilir veya 30 günlük geçici lisans alabilirsiniz.