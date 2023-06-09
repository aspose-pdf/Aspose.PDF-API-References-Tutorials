---
title: تحسين أداء TIFF إلى PDF
linktitle: تحسين أداء TIFF إلى PDF
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لتحسين أداء تحويل TIFF إلى PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 310
url: /ar/net/document-conversion/tiff-to-pdf-performance-improvement/
---

في هذا البرنامج التعليمي ، سنرشدك خطوة بخطوة حول كيفية تحسين أداء تحويل ملفات TIFF إلى PDF باستخدام مكتبة Aspose.PDF لـ .NET. سنقوم بتفصيل كود المصدر C # المقدم ونوضح لك كيفية تنفيذه في مشاريعك الخاصة. بنهاية هذا البرنامج التعليمي ، ستكون قادرًا على إجراء تحويلات أسرع وأكثر كفاءة لملفات TIFF إلى PDF.

## الخطوة 1: تعيين دليل المستندات
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```
 يستبدل`"YOUR DOCUMENTS DIRECTORY"` بالمسار حيث حفظت ملفاتك.

## الخطوة 2: احصل على قائمة بملفات TIFF
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
 انتقل عبر كل ملف TIFF ، وقم بتحميله كملف`Bitmap` كائن ، ثم قم بإضافته إلى مستند PDF. يتم أيضًا تكوين المعلمات مثل الهوامش ودقة الصورة ومقياسها.

## الخطوة 5: احفظ ملف PDF الناتج
```csharp
doc.Save(dataDir + "PerformaceImprovement_out.pdf");
```
احفظ مستند PDF الناتج في الدليل المحدد.

### مثال على الكود المصدري لتحسين أداء TIFF إلى PDF باستخدام Aspose.PDF for .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// احصل على قائمة بملفات الصور المشاجرة
string[] files = System.IO.Directory.GetFiles(dataDir, "*.tif");

// إنشاء كائن مستند
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// تنقل عبر الملفات وفي ملف pdf
foreach (string myFile in files)
{

	// تحميل جميع ملفات tiff في صفيف بايت
	FileStream fs = new FileStream(myFile, FileMode.Open, FileAccess.Read);
	byte[] tmpBytes = new byte[fs.Length];
	fs.Read(tmpBytes, 0, Convert.ToInt32(fs.Length));

	MemoryStream mystream = new MemoryStream(tmpBytes);
	Bitmap b = new Bitmap(mystream);
	// قم بإنشاء صفحة جديدة في مستند Pdf
	Aspose.Pdf.Page currpage = doc.Pages.Add();

	// قم بتعيين الهوامش بحيث تناسب الصورة ، وما إلى ذلك.
	currpage.PageInfo.Margin.Top = 5;
	currpage.PageInfo.Margin.Bottom = 5;
	currpage.PageInfo.Margin.Left = 5;
	currpage.PageInfo.Margin.Right = 5;

	currpage.PageInfo.Width = (b.Width / b.HorizontalResolution) * 72;
	currpage.PageInfo.Height = (b.Height / b.VerticalResolution) * 72;

	// قم بإنشاء كائن صورة
	Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

	// أضف الصورة إلى مجموعة فقرات الصفحة
	currpage.Paragraphs.Add(image1);

	// اضبط خاصية IsBlackWhite على true لتحسين الأداء
	image1.IsBlackWhite = true;
	// اضبط ImageStream على كائن MemoryStream
	image1.ImageStream = mystream;
	// اضبط مقياس الصورة المطلوب
	image1.ImageScale = 0.95F;
}

// احفظ ملف PDF
doc.Save(dataDir + "PerformaceImprovement_out.pdf");
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية تحسين أداء تحويل ملفات TIFF إلى PDF باستخدام مكتبة Aspose.PDF لـ .NET. باتباع الخطوات المقدمة ، ستتمكن من تحقيق تحويلات أسرع وأكثر كفاءة لملفات TIFF إلى PDF. احصل على نتائج دقيقة واحترافية مع تحسين أداء تطبيقك