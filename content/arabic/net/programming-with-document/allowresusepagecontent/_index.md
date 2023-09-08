---
title: السماح بإعادة استخدام محتوى الصفحة
linktitle: السماح بإعادة استخدام محتوى الصفحة
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تحسين ملفات PDF من خلال تمكين ميزة "السماح بإعادة استخدام محتوى الصفحة" باستخدام Aspose.PDF لـ .NET. تقليل حجم الملف وتحسين الأداء.
type: docs
weight: 50
url: /ar/net/programming-with-document/allowresusepagecontent/
---
سنشرح في هذا البرنامج التعليمي كيفية تمكين ميزة "السماح بإعادة استخدام محتوى الصفحة" باستخدام Aspose.PDF لـ .NET. تعمل هذه الميزة على تحسين مستند PDF عن طريق إعادة استخدام محتوى الصفحة وتقليل حجم الملف وتحسين الأداء. اتبع الدليل خطوة بخطوة أدناه:

## الخطوة 1: قم بتحميل مستند PDF

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## الخطوة 2: قم بتعيين خيارAllowReusePageContent

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    AllowReusePageContent = true
};
```

## الخطوة 3: تحسين مستند PDF

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## الخطوة 4: احفظ المستند المحدث

```csharp
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## الخطوة 5: التحقق من تقليل حجم الملف

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

تهانينا! لقد سمحت بنجاح بإعادة استخدام محتوى الصفحة في مستند PDF الخاص بك.

### مثال على التعليمات البرمجية المصدر للسماح بإعادة استخدام محتوى الصفحة باستخدام Aspose.PDF لـ .NET:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح المستند
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");

// قم بتعيين خيارAllowReusePageContent
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    AllowReusePageContent = true
};

Console.WriteLine("Start");

// تحسين مستند PDF باستخدام OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);

// حفظ المستند المحدث
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");

Console.WriteLine("Finished");

var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);

Console.WriteLine("\nAllowed reuse of page content successfully.\nFile saved at " + dataDir);
```

يمكنك الآن تحسين مستندات PDF الخاصة بك بشكل فعال من خلال السماح بإعادة استخدام محتوى الصفحة.

## خاتمة

في هذا البرنامج التعليمي، شرحنا كيفية تمكين ميزة "السماح بإعادة استخدام محتوى الصفحة" باستخدام Aspose.PDF لـ .NET. باتباع الدليل الموضح خطوة بخطوة واستخدام كود مصدر C#، يمكنك تحسين مستندات PDF الخاصة بك بشكل فعال من خلال السماح بإعادة استخدام محتوى الصفحة. يؤدي هذا التحسين إلى ملفات PDF أصغر، مما قد يؤدي إلى أوقات تحميل أسرع وتحسين الأداء عند التعامل مع مستندات PDF كبيرة الحجم. يوفر Aspose.PDF for .NET حلاً قويًا وسهل الاستخدام لتحسين ملفات PDF، مما يتيح لك إنشاء ملفات PDF فعالة وعالية الجودة بسهولة.

### الأسئلة الشائعة

#### س: ما هو الغرض من تمكين ميزة "السماح بإعادة استخدام محتوى الصفحة" في مستند PDF؟

ج: يؤدي تمكين ميزة "السماح بإعادة استخدام محتوى الصفحة" في مستند PDF إلى تحسين الملف عن طريق إعادة استخدام محتوى الصفحة، مما يقلل من حجم الملف ويحسن الأداء العام. ينتج عن هذا التحسين ملفات PDF أصغر دون المساس بجودة المحتوى.

#### س: كيف تعمل ميزة "السماح بإعادة استخدام محتوى الصفحة"؟

ج: عند تمكين ميزة "السماح بإعادة استخدام محتوى الصفحة"، تتم مشاركة كائنات الصفحة المتطابقة داخل مستند PDF وإعادة استخدامها، بدلاً من تكرارها في كل مرة. تؤدي مشاركة محتوى الصفحة إلى تقليل الحجم الإجمالي للملف بشكل كبير.

#### س: هل يمكنني التراجع عن التحسين واستعادة المستند الأصلي؟

ج: لا، بمجرد إجراء التحسين باستخدام "السماح بإعادة استخدام محتوى الصفحة" وحفظ مستند PDF، تصبح التغييرات دائمة. يُنصح بالاحتفاظ بنسخة احتياطية من المستند الأصلي قبل إجراء أي تحسين.

#### س: هل يؤثر تمكين هذه الميزة على المظهر المرئي أو محتوى مستند PDF؟

ج: لا يؤثر تمكين ميزة "السماح بإعادة استخدام محتوى الصفحة" على المظهر المرئي لمستند PDF أو محتواه. فهو يعمل فقط على تحسين البنية الداخلية للملف لتقليل التكرار وتعزيز الكفاءة.

#### س: هل يعد Aspose.PDF for .NET حلاً موثوقًا لتحسين ملفات PDF ومعالجتها؟

ج: نعم، Aspose.PDF for .NET هي مكتبة موثوقة وغنية بالميزات لتحسين ملفات PDF ومعالجتها. فهو يوفر خيارات واسعة لتحسين ملفات PDF، بما في ذلك تقليل حجم الملف، وإزالة الموارد غير المستخدمة، وتحسين الأداء العام.