---
title: إبراز الحرف في ملف PDF
linktitle: إبراز الحرف في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية تمييز الأحرف في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 240
url: /ar/net/programming-with-text/highlight-character-in-pdf/
---
في هذا البرنامج التعليمي، سنشرح كيفية تمييز الأحرف في ملف PDF باستخدام مكتبة Aspose.PDF لـ .NET. سنتناول عملية تمييز الأحرف في ملف PDF خطوة بخطوة باستخدام كود المصدر C# المقدم.

## متطلبات

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- تم تثبيت مكتبة Aspose.PDF لـ .NET.
- فهم أساسي لبرمجة C#.

## الخطوة 1: إعداد دليل المستندات

 أولاً، تحتاج إلى تعيين المسار إلى الدليل الذي يوجد به ملف PDF المدخل. استبدل`"YOUR DOCUMENT DIRECTORY"` في`dataDir` متغير يحتوي على المسار إلى ملف PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: تحميل مستند PDF

 بعد ذلك، نقوم بتحميل مستند PDF المدخل باستخدام`Aspose.Pdf.Document` فصل.

```csharp
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
```

## الخطوة 3: تحويل PDF إلى صورة

 لتسليط الضوء على الأحرف، نقوم بتحويل مستند PDF إلى صورة باستخدام`PdfConverter` الصف. نقوم بتعيين الدقة للتحويل واسترداد الصورة كملف`Bitmap` هدف.

```csharp
int resolution = 150;
using (MemoryStream ms = new MemoryStream())
{
     PdfConverter conv = new PdfConverter(pdfDocument);
     conv. Resolution = new Resolution(resolution, resolution);
     conv. GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
     Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
```

## الخطوة 4: إبراز الشخصيات

 نقوم بالتنقل عبر كل صفحة من مستند PDF واستخدام`TextFragmentAbsorber` نستخدم كائنًا للعثور على جميع الكلمات الموجودة في الصفحة. ثم نكرر البحث على أجزاء النص والمقاطع والأحرف لتسليط الضوء عليها باستخدام المستطيلات.

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
{
     // تعيين المقياس والتحويل
     float scale = resolution / 72f;
     gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);

     // التنقل عبر الصفحات
     for (int i = 0; i < pdfDocument.Pages.Count; i++)
     {
         Page page = pdfDocument.Pages[1];

         //ابحث عن جميع الكلمات في الصفحة
         TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
         textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
         page. Accept(textFragmentAbsorber);
         TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

         // التنقل عبر أجزاء النص
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

                 // التكرار خلال المقاطع
                 foreach(TextSegment segment in textFragment.Segments)
                 {
                     // تسليط الضوء على الجزء
                     gr.DrawRectangle(
                         Think Green,
                         (float)segment.Rectangle.LLX,
                         (float)segment.Rectangle.LLY,
                         (float)segment.Rectangle.Width,
                         (float)segment.Rectangle.Height);

                     // التنقل بين الشخصيات
                     foreach(CharInfo characterInfo in segment.Characters)
                     {
                         // إبراز الحرف
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

## الخطوة 5: احفظ الصورة الناتجة

وأخيرًا، نقوم بحفظ الصورة المعدلة مع الأحرف المميزة في ملف الإخراج المحدد.

```csharp
dataDir = dataDir + "HighlightCharacterInPDF_out.png";
bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
```

### عينة من كود المصدر لتمييز الأحرف في PDF باستخدام Aspose.PDF لـ .NET 
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
				// إنشاء كائن TextAbsorber للبحث عن جميع الكلمات
				TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
				textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
				page.Accept(textFragmentAbsorber);
				// احصل على أجزاء النص المستخرجة
				TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
				// التنقل عبر الشظايا
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

في هذا البرنامج التعليمي، تعلمت كيفية تمييز الأحرف في مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. باتباع الدليل خطوة بخطوة وتنفيذ التعليمات البرمجية C# المقدمة، يمكنك تمييز الأحرف في ملف PDF وحفظ الناتج كصورة.

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "تمييز الحرف في ملف PDF"؟

ج: يوضح البرنامج التعليمي "تمييز الأحرف في ملف PDF" كيفية استخدام مكتبة Aspose.PDF لـ .NET لتمييز الأحرف داخل مستند PDF. يوفر البرنامج التعليمي دليلاً خطوة بخطوة وكود مصدر C# لتحقيق ذلك.

#### س: لماذا أرغب في تسليط الضوء على الأحرف في مستند PDF؟

أ: يمكن أن يكون تمييز الأحرف في مستند PDF مفيدًا لأغراض مختلفة، مثل التأكيد على محتوى معين أو جعل نص معين أكثر وضوحًا وقابلية للتمييز.

#### س: كيف أقوم بإعداد دليل المستندات؟

أ: لإعداد دليل المستندات:

1.  يستبدل`"YOUR DOCUMENT DIRECTORY"` في`dataDir` متغير يحتوي على المسار إلى الدليل الذي يوجد به ملف PDF المدخل الخاص بك.

#### س: كيف أقوم بتحميل مستند PDF وتحويله إلى صورة؟

 أ: في البرنامج التعليمي،`Aspose.Pdf.Document` يتم استخدام الفئة لتحميل مستند PDF المدخل. بعد ذلك،`PdfConverter` يتم استخدام الفئة لتحويل مستند PDF إلى صورة. يتم تعيين دقة الصورة، ويتم استرداد الصورة كملف PDF.`Bitmap` هدف.

#### س: كيف أقوم بتسليط الضوء على الأحرف في صورة مستند PDF؟

أ: يرشدك البرنامج التعليمي خلال عملية التنقل عبر كل صفحة من مستند PDF، والبحث عن الكلمات باستخدام`TextFragmentAbsorber`، والتكرار عبر أجزاء النص والأجزاء والأحرف لتسليط الضوء عليها باستخدام المستطيلات.

#### س: هل يمكنني تخصيص مظهر الشخصيات والأجزاء المميزة؟

ج: نعم، يمكنك تخصيص مظهر الأحرف والأجزاء المميزة عن طريق تعديل الألوان والأنماط المستخدمة في عمليات الرسم.

#### س: كيف أحفظ الصورة المعدلة مع الأحرف المميزة؟

 أ: يوضح البرنامج التعليمي كيفية حفظ الصورة المعدلة بالأحرف المميزة في ملف الإخراج المحدد باستخدام`Save` طريقة`Bitmap` فصل.

#### س: هل يلزم الحصول على ترخيص Aspose صالح لهذا البرنامج التعليمي؟

ج: نعم، يلزم الحصول على ترخيص Aspose صالح حتى يعمل هذا البرنامج التعليمي بشكل صحيح. يمكنك شراء ترخيص كامل أو الحصول على ترخيص مؤقت لمدة 30 يومًا من موقع Aspose على الويب.