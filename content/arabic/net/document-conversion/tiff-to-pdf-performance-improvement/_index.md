---
title: تحسين أداء TIFF إلى PDF
linktitle: تحسين أداء TIFF إلى PDF
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لتحسين أداء تحويل TIFF إلى PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 310
url: /ar/net/document-conversion/tiff-to-pdf-performance-improvement/
---
في هذا البرنامج التعليمي، سنرشدك خطوة بخطوة حول كيفية تحسين أداء تحويل ملفات TIFF إلى PDF باستخدام مكتبة Aspose.PDF لـ .NET. سنقوم بتفصيل كود مصدر C# المقدم ونوضح لك كيفية تنفيذه في مشاريعك الخاصة. بحلول نهاية هذا البرنامج التعليمي، ستكون قادرًا على إجراء تحويلات أسرع وأكثر كفاءة لملفات TIFF إلى PDF.

## الخطوة 1: قم بتعيين دليل المستندات
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```
 يستبدل`"YOUR DOCUMENTS DIRECTORY"` بالمسار الذي قمت بحفظ ملفاتك فيه.

## الخطوة 2: احصل على قائمة ملفات TIFF
```csharp
string[] files = System.IO.Directory.GetFiles(dataDir, "*.tif");
```
احصل على قائمة بملفات TIFF الموجودة في الدليل المحدد.

## الخطوة 3: إنشاء كائن مستند
```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```
قم بإنشاء مثيل لكائن المستند.

## الخطوة 4: تصفح الملفات وأضفها إلى مستند PDF
```csharp
foreach (string myFile in files)
{
     FileStream fs = new FileStream(myFile, FileMode.Open, FileAccess.Read);
     byte[] tmpBytes = new byte[fs.Length];
     fs.Read(tmpBytes, 0, Convert.ToInt32(fs.Length));

     MemoryStream mystream = new MemoryStream(tmpBytes);
     Bitmap b = new Bitmap(mystream);
     Aspose.Pdf.Page currpage = doc.Pages.Add();

     currpage.PageInfo.Margin.Top = 5;
     currpage.PageInfo.Margin.Bottom = 5;
     currpage.PageInfo.Margin.Left = 5;
     currpage.PageInfo.Margin.Right = 5;

     currpage.PageInfo.Width = (b.Width / b.HorizontalResolution) * 72;
     currpage.PageInfo.Height = (b.Height / b.VerticalResolution) * 72;

     Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

     currpage.Paragraphs.Add(image1);

     image1.IsBlackWhite = true;
     image1.ImageStream = mystream;
     image1.ImageScale = 0.95F;
}
```
 انتقل إلى كل ملف TIFF، وقم بتحميله كملف`Bitmap` الكائن، ثم قم بإضافته إلى مستند PDF. يتم أيضًا تكوين المعلمات مثل الهوامش والدقة وحجم الصورة.

## الخطوة 5: احفظ ملف PDF الناتج
```csharp
doc.Save(dataDir + "PerformaceImprovement_out.pdf");
```
احفظ مستند PDF الناتج في الدليل المحدد.

### مثال على التعليمات البرمجية المصدر لتحسين أداء TIFF إلى PDF باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// احصل على قائمة بملفات صور tiff
string[] files = System.IO.Directory.GetFiles(dataDir, "*.tif");

// إنشاء مثيل لكائن المستند
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// التنقل بين الملفات وفي ملف pdf
foreach (string myFile in files)
{

	// قم بتحميل جميع ملفات tiff في صفيف بايت
	FileStream fs = new FileStream(myFile, FileMode.Open, FileAccess.Read);
	byte[] tmpBytes = new byte[fs.Length];
	fs.Read(tmpBytes, 0, Convert.ToInt32(fs.Length));

	MemoryStream mystream = new MemoryStream(tmpBytes);
	Bitmap b = new Bitmap(mystream);
	// قم بإنشاء صفحة جديدة في مستند Pdf
	Aspose.Pdf.Page currpage = doc.Pages.Add();

	// قم بتعيين الهوامش بحيث تناسب الصورة، وما إلى ذلك.
	currpage.PageInfo.Margin.Top = 5;
	currpage.PageInfo.Margin.Bottom = 5;
	currpage.PageInfo.Margin.Left = 5;
	currpage.PageInfo.Margin.Right = 5;

	currpage.PageInfo.Width = (b.Width / b.HorizontalResolution) * 72;
	currpage.PageInfo.Height = (b.Height / b.VerticalResolution) * 72;

	// إنشاء كائن الصورة
	Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

	// إضافة الصورة إلى مجموعة فقرات الصفحة
	currpage.Paragraphs.Add(image1);

	// اضبط الخاصية IsBlackWhite على القيمة true لتحسين الأداء
	image1.IsBlackWhite = true;
	// قم بتعيين ImageStream إلى كائن MemoryStream
	image1.ImageStream = mystream;
	// ضبط مقياس الصورة المطلوب
	image1.ImageScale = 0.95F;
}

// احفظ ملف PDF
doc.Save(dataDir + "PerformaceImprovement_out.pdf");
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية تحسين أداء تحويل ملفات TIFF إلى PDF باستخدام مكتبة Aspose.PDF لـ .NET. باتباع الخطوات المقدمة، ستتمكن من تحقيق تحويلات أسرع وأكثر كفاءة لملفات TIFF إلى PDF. احصل على نتائج دقيقة واحترافية مع تحسين أداء تطبيقك

### الأسئلة الشائعة

#### س: ما هو Aspose.PDF لـ .NET؟

ج: Aspose.PDF for .NET هي مكتبة قوية تمكن المطورين من العمل مع مستندات PDF في تطبيقات C#. وهو يوفر وظائف متنوعة، بما في ذلك تحويل ملفات TIFF إلى PDF.

#### س: لماذا أرغب في تحسين أداء تحويل TIFF إلى PDF؟

ج: يمكن أن يؤدي تحسين أداء تحويل TIFF إلى PDF إلى تحسين كفاءة تطبيقك بشكل كبير، خاصة عند التعامل مع عدد كبير من ملفات TIFF. تؤدي التحويلات الأسرع إلى تحسين تجربة المستخدم وتقليل وقت المعالجة.

#### س: كيف يمكنني تعيين الدليل لملفات TIFF؟

 ج: يمكنك تعيين الدليل لملفات TIFF عن طريق استبدال ملف`"YOUR DOCUMENTS DIRECTORY"` عنصر نائب في الكود مع المسار الفعلي حيث توجد ملفات TIFF الخاصة بك.

#### س: ما هي التحسينات التي تم تطبيقها في مقتطف الشفرة لتحسين الأداء؟

 ج: يستخدم مقتطف الشفرة تقنيات مختلفة لتحسين أداء التحويل، مثل تعيين الهوامش، وتكوين دقة الصورة وحجمها، وتعيين`IsBlackWhite`الملكية إلى صحيح. تساعد هذه التحسينات على تبسيط عملية التحويل.

#### س: هل يمكنني تخصيص خصائص الصورة في ملف PDF الناتج؟

ج: نعم، يمكنك تخصيص خصائص الصورة في ملف PDF الناتج، مثل الحجم والدقة والهوامش، لتحقيق التخطيط والمظهر المطلوب.