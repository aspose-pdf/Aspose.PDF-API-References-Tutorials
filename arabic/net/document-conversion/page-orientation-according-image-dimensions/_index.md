---
title: اتجاه الصفحة حسب أبعاد الصورة
linktitle: اتجاه الصفحة حسب أبعاد الصورة
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لتعيين اتجاه الصفحة بناءً على أبعاد الصورة باستخدام Aspose.PDF for .NET.
type: docs
weight: 80
url: /ar/net/document-conversion/page-orientation-according-image-dimensions/
---

في هذا البرنامج التعليمي ، سنرشدك خلال عملية تعيين اتجاه الصفحة بناءً على أبعاد الصورة باستخدام Aspose.PDF لـ .NET. سنقوم بالتكرار من خلال قائمة صور JPG في دليل معين وسنضبط اتجاه الصفحة تلقائيًا بناءً على عرض كل صورة. اتبع الخطوات أدناه لتحقيق ذلك.

## المتطلبات الأساسية
قبل أن تبدأ ، تأكد من تلبية المتطلبات الأساسية التالية:

- المعرفة الأساسية بلغة البرمجة C #.
- تثبيت مكتبة Aspose.PDF لـ .NET على نظامك.
- بيئة تطوير مثل Visual Studio.

## الخطوة 1: تصفح صور JPG
في هذه الخطوة ، سنتصفح جميع صور JPG في دليل معين. اتبع الكود أدناه:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بإنشاء مستند PDF جديد
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

//استرجع أسماء جميع ملفات JPG في دليل معين
string[] fileEntries = Directory.GetFiles(dataDir, "*.JPG");
```

 تأكد من استبدال`"YOUR DOCUMENTS DIRECTORY"` مع الدليل الفعلي حيث توجد صور JPG الخاصة بك.

## الخطوة الثانية: إنشاء الصفحة والصورة
بعد تصفح ملفات JPG ، سننشئ صفحة وصورة لكل ملف. استخدم الكود التالي:

```csharp
int counter;
for (counter = 0; counter < fileEntries.Length - 1; counter++)
{
// قم بإنشاء كائن الصفحة
Aspose.Pdf.Page page = doc.Pages.Add();

// قم بإنشاء كائن صورة
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = fileEntries[counter];
```

## الخطوة الثالثة: فحص أبعاد الصورة
الآن دعنا نتحقق من أبعاد كل صورة لتحديد اتجاه الصفحة. استخدم الكود التالي:

```csharp
// قم بإنشاء كائن BitMap للحصول على معلومات من ملف الصورة
Bitmap myimage = new Bitmap(fileEntries[counter]);

// تحقق مما إذا كان عرض الصورة أكبر من عرض الصفحة أم لا
if (myimage.Width > page.PageInfo.Width)
//

  If the width of the image is greater than the width of the page, set the page orientation to landscape
page.PageInfo.IsLandscape = true;
else
// إذا كان عرض الصورة أقل من عرض الصفحة ، فاضبط اتجاه الصفحة على الوضع الرأسي
page.PageInfo.IsLandscape = false;
```

## الخطوة 4: إضافة الصورة إلى مستند PDF
بعد التحقق من أبعاد الصورة ، سنضيف الصورة إلى مجموعة فقرات مستند PDF. استخدم الكود التالي:

```csharp
//أضف الصورة إلى مجموعة فقرات وثيقة PDF
page.Paragraphs.Add(image1);
```

## الخطوة 5: حفظ ملف PDF
بمجرد إضافة جميع الصور إلى مستند PDF ، يمكننا الآن حفظ ملف PDF الناتج. هذه هي الخطوة الأخيرة:

```csharp
// احفظ ملف PDF
doc.Save(dataDir + "SetPageOrientation_out.pdf");
```

 يستبدل`"YOUR DOCUMENTS DIRECTORY"` مع الدليل المطلوب حيث تريد حفظ ملف PDF الناتج.

### مثال على شفرة المصدر لاتجاه الصفحة وفقًا لأبعاد الصورة باستخدام Aspose.Words for .NET

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// استرجع أسماء جميع ملفات JPG في دليل معين
string[] fileEntries = Directory.GetFiles(dataDir, "*.JPG");

int counter;
for (counter = 0; counter < fileEntries.Length - 1; counter++)
{
	// قم بإنشاء كائن صفحة
	Aspose.Pdf.Page page = doc.Pages.Add();

	// قم بإنشاء كائن صورة
	Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
	image1.File = fileEntries[counter];

	// قم بإنشاء كائن BitMap للحصول على معلومات ملف الصورة
	Bitmap myimage = new Bitmap(fileEntries[counter]);
	// تحقق مما إذا كان عرض ملف الصورة أكبر من عرض الصفحة أم لا
	if (myimage.Width > page.PageInfo.Width)
		// إذا كان عرض الصورة أكبر من عرض الصفحة ، فاضبط اتجاه الصفحة على أفقي
		page.PageInfo.IsLandscape = true;
	else
		// إذا كان عرض الصورة أقل من عرض الصفحة ، فاضبط اتجاه الصفحة على عمودي
		page.PageInfo.IsLandscape = false;
	// أضف الصورة إلى مجموعة فقرات وثيقة PDF
	page.Paragraphs.Add(image1);
}
// احفظ ملف Pdf
doc.Save(dataDir + "SetPageOrientation_out.pdf");
```

## خاتمة
في هذا البرنامج التعليمي ، قمنا بتغطية العملية خطوة بخطوة لتعيين اتجاه الصفحة بناءً على أبعاد الصورة باستخدام Aspose.PDF لـ .NET. باتباع الإرشادات الموضحة أعلاه ، يجب أن تكون قادرًا الآن على إنشاء مستند PDF مع اتجاه الصفحة الصحيح لكل صورة. هذه الميزة مفيدة عندما يكون لديك صور بأحجام مختلفة وترغب في تضمينها في مستند PDF.