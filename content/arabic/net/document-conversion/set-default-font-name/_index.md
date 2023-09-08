---
title: تعيين اسم الخط الافتراضي
linktitle: تعيين اسم الخط الافتراضي
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لتعيين اسم الخط الافتراضي في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 270
url: /ar/net/document-conversion/set-default-font-name/
---
سنوضح لك في هذا البرنامج التعليمي كيفية تعيين اسم الخط الافتراضي في ملف PDF باستخدام Aspose.PDF لـ .NET. في بعض الأحيان، عند قيامك باستخراج صور من ملف PDF، قد تواجه مشكلات الخط المفقود. من خلال تحديد اسم الخط الافتراضي، يمكنك التأكد من عرض النص المستخرج بشكل صحيح. اتبع الخطوات أدناه لتعيين اسم الخط الافتراضي في ملف PDF.

## المتطلبات الأساسية
قبل البدء، تأكد من استيفاء المتطلبات الأساسية التالية:

- المعرفة الأساسية بلغة البرمجة C#.
- مكتبة Aspose.PDF لـ .NET مثبتة على نظامك.
- بيئة تطوير مثل Visual Studio.

## الخطوة 1: تحميل وثيقة PDF
 الخطوة الأولى هي تحميل مستند PDF إلى ملف`Document` هدف. استخدم الكود التالي:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
     // كود للإضافة
}
```

 تأكد من استبدال`"YOUR DOCUMENTS DIRECTORY"` مع الدليل الفعلي الذي يوجد به ملف PDF الخاص بك.

## الخطوة 2: تعيين اسم الخط الافتراضي
 بعد ذلك، سنقوم بتعيين اسم الخط الافتراضي باستخدام`DefaultFontName` خيار`RenderingOptions` هدف. استخدم الكود التالي:

```csharp
using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
     using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
     {
         Resolution resolution = new Resolution(300);
         PngDevice pngDevice = new PngDevice(resolution);
         RenderingOptions ro = new RenderingOptions();
         ro.DefaultFontName = "Arial";
         pngDevice.RenderingOptions = ro;
        
         // كود للإضافة
     }
}
```

 تأكد من استبدال`"Arial"` مع اسم الخط المطلوب

## الخطوة 3: استخراج الصور
بعد ذلك، سنقوم باستخراج الصورة من الصفحة المحددة لمستند PDF. استخدم الكود التالي:

```csharp
pngDevice.Process(pdfDocument.Pages[1], imageStream);
```

 تأكد من تحديد رقم الصفحة الصحيح في`pdfDocument.Pages[1]`.

### مثال على التعليمات البرمجية المصدر لتعيين اسم الخط الافتراضي باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
	using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
	{
		Resolution resolution = new Resolution(300);
		PngDevice pngDevice = new PngDevice(resolution);
		RenderingOptions ro = new RenderingOptions();
		ro.DefaultFontName = "Arial";
		pngDevice.RenderingOptions = ro;
		pngDevice.Process(pdfDocument.Pages[1], imageStream);
	}
}
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية تعيين اسم الخط الافتراضي في ملف PDF باستخدام Aspose.PDF لـ .NET. من خلال تحديد اسم الخط الافتراضي، يمكنك التأكد من عرض النص المستخرج بشكل صحيح. استخدم هذه الطريقة لحل مشكلات الخطوط المفقودة عند استخراج الصور من ملفات PDF.

### الأسئلة الشائعة

#### س: ما هو Aspose.PDF لـ .NET؟

ج: Aspose.PDF for .NET هي مكتبة قوية تمكن المطورين من العمل مع مستندات PDF في تطبيقات C#. وهو يوفر وظائف متنوعة، بما في ذلك تحديد اسم الخط الافتراضي في ملف PDF.

#### س: لماذا أحتاج إلى تعيين اسم الخط الافتراضي في ملف PDF؟

ج: يعد تعيين اسم الخط الافتراضي مفيدًا عند استخراج النص من مستند PDF. إذا كان ملف PDF يحتوي على نص بخطوط غير متوفرة على آلة الاستخراج، فإن تحديد اسم الخط الافتراضي يضمن عرض النص الصحيح.

#### س: كيف يمكنني تحميل مستند PDF وتعيين اسم الخط الافتراضي باستخدام Aspose.PDF لـ .NET؟

 ج: لتحميل مستند PDF وتعيين اسم الخط الافتراضي، يمكنك استخدام`Document`فئة لتحميل ملف PDF و`RenderingOptions.DefaultFontName` الخاصية لتحديد اسم الخط الافتراضي المطلوب.

#### س: هل يمكنني اختيار أي خط كاسم الخط الافتراضي؟

ج: نعم، يمكنك اختيار أي خط متوفر على جهاز الاستخراج كاسم الخط الافتراضي. استخدم خطًا يتطابق بشكل وثيق مع الخطوط المفقودة في ملف PDF الأصلي لضمان عرض النص بدقة.

#### س: هل يعد تعيين اسم الخط الافتراضي تغييرًا دائمًا لملف PDF؟

ج: لا، يعد تعيين اسم الخط الافتراضي باستخدام Aspose.PDF لـ .NET بمثابة تغيير مؤقت يتم إجراؤه أثناء استخراج النص. لا يقوم بتعديل ملف PDF الأصلي.