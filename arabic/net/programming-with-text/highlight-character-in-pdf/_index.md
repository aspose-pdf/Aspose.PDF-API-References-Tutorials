---
title: قم بتمييز الحرف في PDF
linktitle: قم بتمييز الحرف في PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تمييز الأحرف في مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 240
url: /ar/net/programming-with-text/highlight-character-in-pdf/
---

في هذا البرنامج التعليمي ، سنشرح كيفية تمييز الأحرف في مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. سنمر بعملية تمييز الأحرف في ملف PDF خطوة بخطوة باستخدام كود المصدر C # المقدم.

## متطلبات

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- تثبيت Aspose.PDF لمكتبة .NET.
- فهم أساسي لبرمجة C #.

## الخطوة 1: قم بإعداد دليل المستندات

 أولاً ، تحتاج إلى تعيين المسار إلى الدليل حيث يوجد ملف PDF الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` في ال`dataDir` متغير مع المسار إلى ملف PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل مستند PDF

 بعد ذلك ، نقوم بتحميل مستند PDF المدخل باستخدام ملف`Aspose.Pdf.Document` فصل.

```csharp
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
```

## الخطوة الثالثة: تحويل ملفات PDF إلى صورة

 لتمييز الأحرف ، نقوم بتحويل مستند PDF إلى صورة باستخدام امتداد`PdfConverter` فصل. قمنا بتعيين دقة التحويل واسترداد الصورة كملف`Bitmap` هدف.

```csharp
int resolution = 150;
using (MemoryStream ms = new MemoryStream())
{
     PdfConverter conv = new PdfConverter(pdfDocument);
     conv. Resolution = new Resolution(resolution, resolution);
     conv. GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
     Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
```

## الخطوة 4: تسليط الضوء على الشخصيات

 نحن نمرّر كل صفحة من صفحات مستند PDF ونستخدم ملف`TextFragmentAbsorber` كائن للعثور على جميع الكلمات في الصفحة. ثم نقوم بتكرار أجزاء النص ، والمقاطع ، والشخصيات لتمييزها باستخدام المستطيلات.

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
{
     // ضبط الحجم والتحويل
     float scale = resolution / 72f;
     gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);

     // تكرار الصفحات
     for (int i = 0; i < pdfDocument.Pages.Count; i++)
     {
         Page page = pdfDocument.Pages[1];

         // البحث عن كل الكلمات في الصفحة
         TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
         textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
         page. Accept(textFragmentAbsorber);
         TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

         // حلقة خلال أجزاء النص
         foreach(TextFragment textFragment in textFragmentCollection)
         {
             if (i == 0)
             {
                 //تسليط الضوء على الشخصيات
                 gr.DrawRectangle(
                     Think.Yellow,
                     (float)textFragment.Position.XIndent,
                     (float)textFragment.Position.YIndent,
                     (float)textFragment.Rectangle.Width,
                     (float)textFragment.Rectangle.Height);

                 // حلقة خلال المقاطع
                 foreach(TextSegment segment in textFragment.Segments)
                 {
                     // تسليط الضوء على الجزء
                     gr.DrawRectangle(
                         Think Green,
                         (float)segment.Rectangle.LLX,
                         (float)segment.Rectangle.LLY,
                         (float)segment.Rectangle.Width,
                         (float)segment.Rectangle.Height);

                     // حلقة من خلال الشخصيات
                     foreach(CharInfo characterInfo in segment.Characters)
                     {
                         // تمييز الحرف
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

## الخطوة 5: احفظ صورة الإخراج

أخيرًا ، نحفظ الصورة المعدلة بالأحرف المميزة في ملف الإخراج المحدد.

```csharp
dataDir = dataDir + "HighlightCharacterInPDF_out.png";
bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
```

### عينة من التعليمات البرمجية المصدر لـ Highlight Character In PDF باستخدام Aspose.PDF for .NET 
```csharp
try
{
	// المسار إلى دليل المستندات.
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
				// إنشاء كائن TextAbsorber للعثور على كل الكلمات
				TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
				textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
				page.Accept(textFragmentAbsorber);
				// احصل على أجزاء النص المستخرجة
				TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
				// حلقة من خلال الأجزاء
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
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx. ") ؛
}
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمت كيفية تمييز الأحرف في مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. باتباع الدليل المفصل خطوة بخطوة وتنفيذ كود C # المقدم ، يمكنك تمييز الأحرف في ملف PDF وحفظ المخرجات كصورة.