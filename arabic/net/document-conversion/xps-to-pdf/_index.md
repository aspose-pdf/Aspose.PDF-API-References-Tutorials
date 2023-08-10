---
title: XPS إلى PDF
linktitle: XPS إلى PDF
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لتحويل ملف XPS إلى PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 350
url: /ar/net/document-conversion/xps-to-pdf/
---
في هذا البرنامج التعليمي ، سنرشدك إلى كيفية تحويل ملف XPS إلى PDF باستخدام مكتبة Aspose.PDF لـ .NET خطوة بخطوة. سنقوم بتفصيل كود المصدر C # المقدم ونوضح لك كيفية تنفيذه في مشاريعك الخاصة. بنهاية هذا البرنامج التعليمي ، ستتمكن من تحويل ملفات XPS بسهولة إلى مستندات PDF.

## الخطوة 1: تعيين دليل المستندات
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```
 يستبدل`"YOUR DOCUMENTS DIRECTORY"` بالمسار حيث حفظت ملفاتك.

## الخطوة 2: إنشاء كائن LoadOptions باستخدام خيارات تحميل XPS
```csharp
Aspose.Pdf.LoadOptions options = new XpsLoadOptions();
```
قم بإنشاء مثيل لكائن LoadOptions باستخدام خيارات تحميل XPS.

## الخطوة 3: قم بإنشاء كائن المستند
```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "XPSToPDF.xps", options);
```
قم بإنشاء كائن مستند يحدد ملف XPS للإدخال وخيارات التحميل.

## الخطوة 4: احفظ مستند PDF الناتج
```csharp
document.Save(dataDir + "XPSToPDF_out.pdf");
```
احفظ مستند PDF الناتج في الدليل المحدد.

### مثال على التعليمات البرمجية المصدر لـ XPS إلى PDF باستخدام Aspose.PDF لـ .NET

```csharp
try
{
	
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	//إنشاء كائن LoadOption باستخدام خيار تحميل XPS
	Aspose.Pdf.LoadOptions options = new XpsLoadOptions();

	// إنشاء كائن الوثيقة
	Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "XPSToPDF.xps", options);

	// احفظ مستند PDF الناتج
	document.Save(dataDir + "XPSToPDF_out.pdf");
	
}
catch(Exception ex)
   
{
	Console.WriteLine(ex.Message);
}
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية تحويل ملف XPS إلى PDF باستخدام مكتبة Aspose.PDF لـ .NET. باتباع الخطوات المقدمة ، يمكنك بسهولة إجراء هذا التحويل في تطبيقاتك الخاصة. احصل على نتائج دقيقة واحترافية عند تحويل ملفات XPS إلى PDF.

### التعليمات

#### س: ما هو XPS ، ولماذا أرغب في تحويله إلى PDF؟

ج: XPS (مواصفات ورق XML) هو تنسيق مستند ذو تخطيط ثابت تم تطويره بواسطة Microsoft. يتيح لك تحويل XPS إلى PDF تسهيل الوصول إلى المستند وجعله متوافقًا على نطاق واسع ، حيث أن تنسيق PDF هو تنسيق مدعوم عالميًا عبر الأنظمة الأساسية والأجهزة المختلفة.

#### س: هل تدعم مكتبة Aspose.PDF تنسيقات ملفات أخرى إلى جانب XPS؟

ج: نعم ، يدعم Aspose.PDF for .NET العديد من تنسيقات الملفات الأخرى للتحويل ، مثل HTML و EPUB و SVG و XML والمزيد. كما يسمح لك بإنشاء مستندات PDF ومعالجتها برمجيًا.

#### س: هل يمكنني تخصيص عملية تحويل PDF ، مثل تعيين حجم الصفحة أو الهوامش أو خيارات أخرى؟

ج: نعم ، يمكنك تخصيص عملية تحويل PDF باستخدام Aspose.PDF for .NET. توفر المكتبة مجموعة كبيرة من الخيارات للتحكم في حجم الصفحة والهوامش وضغط الصور ودمج الخط والإعدادات الأخرى المتعلقة بـ PDF لتلبية متطلباتك المحددة.

#### س: هل يتوفر إصدار تجريبي من Aspose.PDF for .NET للاختبار؟

ج: نعم ، يمكنك تنزيل الإصدار التجريبي من Aspose.PDF for .NET وتجربته من موقع Aspose الرسمي. يسمح لك الإصدار التجريبي باستكشاف ميزات المكتبة قبل الشراء.

#### س: هل يمكنني تحويل ملفات XPS متعددة إلى PDF في عملية مجمعة؟

ج: نعم ، يمكنك تحويل ملفات XPS متعددة إلى PDF في عملية مجمعة عن طريق تنفيذ حلقة أو تكرار قائمة ملفات XPS وتحويل كل ملف إلى PDF باستخدام الكود المقدم.