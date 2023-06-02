---
title: PDF إلى تلميح خط PNG
linktitle: PDF إلى تلميح خط PNG
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لتحويل PDF إلى PNG باستخدام تلميحات الخط باستخدام Aspose.PDF for .NET.
type: docs
weight: 160
url: /ar/net/document-conversion/pdf-to-png-font-hinting/
---

في هذا البرنامج التعليمي ، سنرشدك خلال عملية تحويل صور PDF إلى PNG باستخدام Aspose.PDF لـ .NET ، مع تمكين تلميح الخط. تلميح الخط هو أسلوب يعمل على تحسين قابلية قراءة الخطوط الصغيرة. باتباع الخطوات أدناه ، ستتمكن من تحويل كل صفحة من صفحات PDF إلى صورة PNG مع تلميح الخط.

## المتطلبات الأساسية
قبل أن تبدأ ، تأكد من تلبية المتطلبات الأساسية التالية:

- المعرفة الأساسية بلغة البرمجة C #.
- تثبيت مكتبة Aspose.PDF لـ .NET على نظامك.
- بيئة تطوير مثل Visual Studio.

## الخطوة 1: فتح ملف PDF المصدر
في هذه الخطوة ، سنفتح ملف PDF المصدر باستخدام Aspose.PDF لـ .NET. اتبع الكود أدناه:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 تأكد من استبدال`"YOUR DOCUMENTS DIRECTORY"` مع الدليل الفعلي حيث يوجد ملف PDF الخاص بك.

## الخطوة 2: تمكين تلميح الخط
بعد فتح ملف PDF ، سنقوم بتمكين تلميح الخط باستخدام خيارات التقديم. استخدم الكود التالي:

```csharp
// قم بإنشاء خيارات عرض لتمكين تلميح الخط
RenderingOptions opts = new RenderingOptions();
opts. UseFontHinting = true;
```

## الخطوة 3: التحويل إلى صور PNG
الآن سنقوم بتحويل كل صفحة من صفحات PDF إلى صورة PNG مع تلميح الخط. استخدم الكود التالي:

```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
     using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".png", FileMode.Create))
     {
         // قم بإنشاء كائن PNGDevice بالسمات المحددة
         // العرض ، الارتفاع ، الدقة ، الجودة
         // الجودة [0-100] ، 100 هي الحد الأقصى
         // قم بإنشاء كائن حل
         Resolution resolution = new Resolution(300);
         PngDevice pngDevice = new PngDevice(resolution);
         // قم بتعيين خيارات العرض المحددة مسبقًا
         pngDevice.RenderingOptions = opts;

         // قم بتحويل صفحة معينة وحفظ الصورة في الدفق
         pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);

         // أغلق الدفق
         imageStream.Close();
     }
}
```

يحول الكود أعلاه كل صفحة من PDF إلى صورة PNG مع تلميح الخط ويحفظ كل صورة كملف PNG منفصل.

### مثال على شفرة المصدر لـ PDF إلى PNGFont Hinting باستخدام Aspose.Words for .NET

```csharp
try
{
	
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// افتح المستند
	Document pdfDocument = new Document(dataDir + "input.pdf");
	// قم بإنشاء Aspose.Pdf.RenderingOptions لتمكين تلميح الخط
	RenderingOptions opts = new RenderingOptions();
	opts.UseFontHinting = true;
	
	for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
	{
		using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".png", FileMode.Create))
		{
			// قم بإنشاء جهاز PNG بسمات محددة
			// العرض ، الارتفاع ، الدقة ، الجودة
			// الجودة [0-100] ، 100 هي الحد الأقصى
			// إنشاء كائن القرار
			Resolution resolution = new Resolution(300);
			PngDevice pngDevice = new PngDevice(resolution);
			// قم بتعيين خيارات العرض المحددة مسبقًا
			pngDevice.RenderingOptions = opts;

			// قم بتحويل صفحة معينة وحفظ الصورة للدفق
			pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);

			// إغلاق الدفق
			imageStream.Close();
		}
	}
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## خاتمة
في هذا البرنامج التعليمي ، قمنا بتغطية العملية خطوة بخطوة لتحويل صور PDF إلى PNG مع تلميح الخط باستخدام Aspose.PDF لـ .NET. باتباع الإرشادات الموضحة أعلاه ، يجب أن تكون قادرًا الآن على تحويل كل صفحة من صفحات PDF إلى صورة PNG مع تلميح الخط. هذه الميزة مفيدة عندما تريد الحفاظ على قابلية قراءة الخطوط الصغيرة عند التحويل إلى صور PNG.