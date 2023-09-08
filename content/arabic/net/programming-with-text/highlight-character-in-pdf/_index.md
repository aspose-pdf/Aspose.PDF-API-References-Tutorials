---
title: تسليط الضوء على الحرف في ملف PDF
linktitle: تسليط الضوء على الحرف في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تمييز الأحرف في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 240
url: /ar/net/programming-with-text/highlight-character-in-pdf/
---
سنشرح في هذا البرنامج التعليمي كيفية تمييز الأحرف في ملف PDF باستخدام مكتبة Aspose.PDF لـ .NET. سنتابع عملية تمييز الأحرف خطوة بخطوة في ملف PDF باستخدام كود مصدر C# المقدم.

## متطلبات

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- تم تثبيت Aspose.PDF لمكتبة .NET.
- فهم أساسي للبرمجة C#.

## الخطوة 1: إعداد دليل المستندات

 أولاً، تحتاج إلى تعيين المسار إلى الدليل الذي يوجد به ملف PDF الذي قمت بإدخاله. يستبدل`"YOUR DOCUMENT DIRECTORY"` في ال`dataDir` متغير مع المسار إلى ملف PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل مستند PDF

 بعد ذلك، نقوم بتحميل مستند PDF المدخل باستخدام ملف`Aspose.Pdf.Document` فصل.

```csharp
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
```

## الخطوة 3: تحويل PDF إلى صورة

 لتسليط الضوء على الحروف، نقوم بتحويل وثيقة PDF إلى صورة باستخدام`PdfConverter` فصل. قمنا بتعيين دقة التحويل واسترجاع الصورة كملف`Bitmap` هدف.

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

 نقوم بالتكرار خلال كل صفحة من مستند PDF ونستخدم ملف`TextFragmentAbsorber` كائن للعثور على جميع الكلمات في الصفحة. نقوم بعد ذلك بالتكرار على أجزاء النص والأجزاء والأحرف لتمييزها باستخدام المستطيلات.

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
{
     //ضبط الحجم والتحويل
     float scale = resolution / 72f;
     gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);

     // حلقة من خلال الصفحات
     for (int i = 0; i < pdfDocument.Pages.Count; i++)
     {
         Page page = pdfDocument.Pages[1];

         // البحث عن جميع الكلمات في الصفحة
         TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
         textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
         page. Accept(textFragmentAbsorber);
         TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

         // حلقة من خلال أجزاء النص
         foreach(TextFragment textFragment in textFragmentCollection)
         {
             if (i == 0)
             {
                 // تسليط الضوء على الشخصيات
                 gr.DrawRectangle(
                     Think.Yellow,
                     (float)textFragment.Position.XIndent,
                     (float)textFragment.Position.YIndent,
                     (float)textFragment.Rectangle.Width,
                     (float)textFragment.Rectangle.Height);

                 // حلقة من خلال القطاعات
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
                         // تسليط الضوء على الحرف
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

وأخيرًا، نقوم بحفظ الصورة المعدلة بالأحرف المميزة في ملف الإخراج المحدد.

```csharp
dataDir = dataDir + "HighlightCharacterInPDF_out.png";
bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
```

### نموذج التعليمات البرمجية المصدر لـ Highlight Character In PDF باستخدام Aspose.PDF لـ .NET 
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
				// قم بإنشاء كائن TextAbsorter للعثور على جميع الكلمات
				TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
				textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
				page.Accept(textFragmentAbsorber);
				// احصل على أجزاء النص المستخرجة
				TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
				// حلقة من خلال الشظايا
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

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية تمييز الأحرف في مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. باتباع الدليل الموضح خطوة بخطوة وتنفيذ كود C# المقدم، يمكنك تمييز الأحرف في ملف PDF وحفظ الإخراج كصورة.

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "تمييز الأحرف في ملف PDF"؟

ج: يشرح البرنامج التعليمي "Highlight Character In PDF File" كيفية استخدام مكتبة Aspose.PDF لـ .NET لتمييز الأحرف داخل مستند PDF. يوفر البرنامج التعليمي دليلاً خطوة بخطوة وكود مصدر C# لتحقيق ذلك.

#### س: لماذا أرغب في تمييز الأحرف في مستند PDF؟

ج: يمكن أن يكون تمييز الأحرف في مستند PDF مفيدًا لأغراض متعددة، مثل إبراز محتوى معين أو جعل نص معين أكثر وضوحًا وتمييزًا.

#### س: كيف أقوم بإعداد دليل المستندات؟

ج: لإعداد دليل المستندات:

1.  يستبدل`"YOUR DOCUMENT DIRECTORY"` في ال`dataDir` متغير مع المسار إلى الدليل حيث يوجد ملف PDF المدخل الخاص بك.

#### س: كيف يمكنني تحميل مستند PDF وتحويله إلى صورة؟

 ج: في البرنامج التعليمي،`Aspose.Pdf.Document` يتم استخدام الفئة لتحميل مستند PDF الإدخال. ثم،`PdfConverter` يتم استخدام الفصل لتحويل مستند PDF إلى صورة. يتم تعيين دقة الصورة، ويتم استرداد الصورة كملف`Bitmap` هدف.

#### س: كيف يمكنني تمييز الأحرف في صورة مستند PDF؟

ج: يرشدك البرنامج التعليمي خلال عملية التكرار خلال كل صفحة من مستند PDF، والبحث عن الكلمات باستخدام ملف`TextFragmentAbsorber`، والتكرار عبر أجزاء النص والأجزاء والأحرف لتمييزها باستخدام المستطيلات.

#### س: هل يمكنني تخصيص مظهر الشخصيات والمقاطع المميزة؟

ج: نعم، يمكنك تخصيص مظهر الأحرف والمقاطع المميزة عن طريق تعديل الألوان والأنماط المستخدمة في عمليات الرسم.

#### س: كيف أحفظ الصورة المعدلة بالأحرف المميزة؟

 ج: يوضح البرنامج التعليمي كيفية حفظ الصورة المعدلة بالأحرف المميزة في ملف الإخراج المحدد باستخدام ملف`Save` طريقة`Bitmap` فصل.

#### س: هل يلزم وجود ترخيص Aspose صالح لهذا البرنامج التعليمي؟

ج: نعم، يلزم وجود ترخيص Aspose صالح حتى يعمل هذا البرنامج التعليمي بشكل صحيح. يمكنك شراء ترخيص كامل أو الحصول على ترخيص مؤقت لمدة 30 يومًا من موقع Aspose.