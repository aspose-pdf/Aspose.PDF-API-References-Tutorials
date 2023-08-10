---
title: تعيين اسم الخط الافتراضي
linktitle: تعيين اسم الخط الافتراضي
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لتعيين اسم الخط الافتراضي في ملف PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 270
url: /ar/net/document-conversion/set-default-font-name/
---
في هذا البرنامج التعليمي ، سنوضح لك كيفية تعيين اسم الخط الافتراضي في ملف PDF باستخدام Aspose.PDF لـ .NET. في بعض الأحيان عندما تستخرج صورًا من ملف PDF ، قد تواجه مشكلات في الخط المفقودة. من خلال تحديد اسم الخط الافتراضي ، يمكنك التأكد من عرض النص المستخرج بشكل صحيح. اتبع الخطوات أدناه لتعيين اسم الخط الافتراضي في ملف PDF.

## المتطلبات الأساسية
قبل أن تبدأ ، تأكد من تلبية المتطلبات الأساسية التالية:

- المعرفة الأساسية بلغة البرمجة C #.
- تثبيت مكتبة Aspose.PDF لـ .NET على نظامك.
- بيئة تطوير مثل Visual Studio.

## الخطوة 1: تحميل مستند PDF
 تتمثل الخطوة الأولى في تحميل مستند PDF إلى ملف`Document` هدف. استخدم الكود التالي:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
     // رمز للإضافة
}
```

 تأكد من استبدال`"YOUR DOCUMENTS DIRECTORY"` مع الدليل الفعلي حيث يوجد ملف PDF الخاص بك.

## الخطوة 2: تعيين اسم الخط الافتراضي
 بعد ذلك ، سنقوم بتعيين اسم الخط الافتراضي باستخدام امتداد`DefaultFontName` خيار`RenderingOptions` هدف. استخدم الكود التالي:

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
        
         // رمز للإضافة
     }
}
```

 تأكد من استبدال`"Arial"` مع اسم الخط المطلوب.

## الخطوة 3: استخراج الصور
بعد ذلك ، سنقوم باستخراج الصورة من الصفحة المحددة لمستند PDF. استخدم الكود التالي:

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
في هذا البرنامج التعليمي ، تعلمنا كيفية تعيين اسم الخط الافتراضي في ملف PDF باستخدام Aspose.PDF لـ .NET. من خلال تحديد اسم الخط الافتراضي ، يمكنك التأكد من عرض النص المستخرج بشكل صحيح. استخدم هذه الطريقة لحل مشكلات الخط المفقودة عند استخراج الصور من ملفات PDF.

### التعليمات

#### س: ما هو Aspose.PDF لـ .NET؟

ج: Aspose.PDF for .NET مكتبة قوية تمكن المطورين من العمل مع مستندات PDF في تطبيقات C #. يوفر وظائف متنوعة ، بما في ذلك تعيين اسم الخط الافتراضي في ملف PDF.

#### س: لماذا أحتاج إلى تعيين اسم الخط الافتراضي في ملف PDF؟

ج: يعد تعيين اسم الخط الافتراضي مفيدًا عند استخراج نص من مستند PDF. إذا كان ملف PDF يحتوي على نص يحتوي على خطوط غير متوفرة في آلة الاستخراج ، فإن تحديد اسم الخط الافتراضي يضمن عرض النص بشكل صحيح.

#### س: كيف يمكنني تحميل مستند PDF وتعيين اسم الخط الافتراضي باستخدام Aspose.PDF for .NET؟

 ج: لتحميل مستند PDF وتعيين اسم الخط الافتراضي ، يمكنك استخدام ملف`Document`فئة لتحميل ملف PDF و`RenderingOptions.DefaultFontName` الخاصية لتحديد اسم الخط الافتراضي المطلوب.

#### س: هل يمكنني اختيار أي خط كاسم الخط الافتراضي؟

ج: نعم ، يمكنك اختيار أي خط متوفر على آلة الاستخراج كاسم الخط الافتراضي. استخدم خطًا يتطابق بشكل وثيق مع الخطوط المفقودة في ملف PDF الأصلي لضمان دقة عرض النص.

#### س: هل يعد تعيين اسم الخط الافتراضي تغييرًا دائمًا لملف PDF؟

ج: لا ، تعيين اسم الخط الافتراضي باستخدام Aspose.PDF for .NET هو تغيير مؤقت تم إجراؤه أثناء استخراج النص. لا يقوم بتعديل ملف PDF الأصلي.