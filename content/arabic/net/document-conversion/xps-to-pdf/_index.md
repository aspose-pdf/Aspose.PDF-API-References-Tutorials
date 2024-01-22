---
title: XPS إلى PDF
linktitle: XPS إلى PDF
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لتحويل ملف XPS إلى PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 350
url: /ar/net/document-conversion/xps-to-pdf/
---
في هذا البرنامج التعليمي، سنرشدك إلى كيفية تحويل ملف XPS إلى PDF باستخدام مكتبة Aspose.PDF لـ .NET خطوة بخطوة. سنقوم بتفصيل كود مصدر C# المقدم ونوضح لك كيفية تنفيذه في مشاريعك الخاصة. بحلول نهاية هذا البرنامج التعليمي، ستتمكن بسهولة من تحويل ملفات XPS إلى مستندات PDF.

## الخطوة 1: قم بتعيين دليل المستندات
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```
 يستبدل`"YOUR DOCUMENTS DIRECTORY"` بالمسار الذي قمت بحفظ ملفاتك فيه.

## الخطوة 2: إنشاء كائن LoadOptions باستخدام خيارات تحميل XPS
```csharp
Aspose.Pdf.LoadOptions options = new XpsLoadOptions();
```
قم بإنشاء مثيل لكائن LoadOptions باستخدام خيارات تحميل XPS.

## الخطوة 3: إنشاء كائن المستند
```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "XPSToPDF.xps", options);
```
قم بإنشاء كائن مستند يحدد ملف XPS المدخل وخيارات التحميل.

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

	// إنشاء كائن المستند
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
في هذا البرنامج التعليمي، تعلمنا كيفية تحويل ملف XPS إلى PDF باستخدام مكتبة Aspose.PDF لـ .NET. باتباع الخطوات المتوفرة، يمكنك إجراء هذا التحويل بسهولة في تطبيقاتك الخاصة. احصل على نتائج دقيقة واحترافية عند تحويل ملفات XPS إلى PDF.

### الأسئلة الشائعة

#### س: ما هو XPS، ولماذا أرغب في تحويله إلى PDF؟

ج: XPS (مواصفات ورق XML) هو تنسيق مستند ذو تخطيط ثابت تم تطويره بواسطة Microsoft. يتيح لك تحويل XPS إلى PDF تسهيل الوصول إلى المستند وجعله متوافقًا على نطاق واسع، حيث أن PDF هو تنسيق مدعوم عالميًا عبر الأنظمة الأساسية والأجهزة المختلفة.

#### س: هل تدعم مكتبة Aspose.PDF تنسيقات ملفات أخرى إلى جانب XPS؟

ج: نعم، يدعم Aspose.PDF for .NET العديد من تنسيقات الملفات الأخرى للتحويل، مثل HTML وEPUB وSVG وXML والمزيد. كما يسمح لك بإنشاء مستندات PDF ومعالجتها برمجيًا.

#### س: هل يمكنني تخصيص عملية تحويل PDF، مثل تحديد حجم الصفحة أو الهوامش أو خيارات أخرى؟

ج: نعم، يمكنك تخصيص عملية تحويل PDF باستخدام Aspose.PDF لـ .NET. توفر المكتبة نطاقًا واسعًا من الخيارات للتحكم في حجم الصفحة والهوامش وضغط الصور وتضمين الخطوط والإعدادات الأخرى المتعلقة بملف PDF لتلبية متطلباتك المحددة.

#### س: هل هناك إصدار تجريبي من Aspose.PDF لـ .NET متاح للاختبار؟

ج: نعم، يمكنك تنزيل وتجربة الإصدار التجريبي من Aspose.PDF لـ .NET من موقع Aspose الرسمي. تتيح لك النسخة التجريبية استكشاف ميزات المكتبة قبل إجراء عملية الشراء.

#### س: هل يمكنني تحويل ملفات XPS متعددة إلى PDF في عملية مجمعة؟

ج: نعم، يمكنك تحويل ملفات XPS متعددة إلى PDF في عملية دفعية عن طريق تنفيذ حلقة أو التكرار خلال قائمة ملفات XPS وتحويل كل ملف إلى PDF باستخدام الكود المقدم.