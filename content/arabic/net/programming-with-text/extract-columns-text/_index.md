---
title: استخراج نص الأعمدة في ملف PDF
linktitle: استخراج نص الأعمدة في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استخراج نص الأعمدة في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 150
url: /ar/net/programming-with-text/extract-columns-text/
---
سيرشدك هذا البرنامج التعليمي خلال عملية استخراج نص الأعمدة في ملف PDF باستخدام Aspose.PDF لـ .NET. يوضح كود مصدر C# المقدم الخطوات اللازمة.

## متطلبات
قبل أن تبدأ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي مترجم C# آخر مثبت على جهازك.
- Aspose.PDF لمكتبة .NET. يمكنك تنزيله من موقع Aspose الرسمي أو استخدام مدير الحزم مثل NuGet لتثبيته.

## الخطوة 1: إعداد المشروع
1. قم بإنشاء مشروع C# جديد في بيئة التطوير المفضلة لديك.
2. قم بإضافة مرجع إلى Aspose.PDF لمكتبة .NET.

## الخطوة 2: استيراد مساحات الأسماء المطلوبة
في ملف التعليمات البرمجية الذي تريد استخراج نص الأعمدة منه، أضف ما يلي باستخدام التوجيهات الموجودة في الجزء العلوي من الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

## الخطوة 3: قم بتعيين دليل المستند
 في الكود، حدد السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدال`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل حيث يتم تخزين المستندات الخاصة بك.

## الخطوة 4: افتح مستند PDF
 افتح مستند PDF موجود باستخدام الملف`Document`منشئ وتمرير المسار إلى ملف PDF الإدخال.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## الخطوة 5: ضبط حجم الخط
قم بتقليل حجم الخط لأجزاء النص بمعامل 0.7 لتحسين إمكانية القراءة وتمثيل النص العمودي بشكل أفضل.

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach(TextFragment tf in tfc)
{
     tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
```

## الخطوة 6: استخراج النص من الأعمدة
 احفظ مستند PDF المعدل في دفق الذاكرة وأعد تحميله كمستند جديد. ثم استخدم`TextAbsorber` فئة لاستخراج النص من الأعمدة.

```csharp
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument);
```

## الخطوة 7: احفظ النص المستخرج
احفظ النص المستخرج في ملف نصي في مسار ملف الإخراج المحدد.

```csharp
dataDir = dataDir + "ExtractColumnsText_out.txt";
File.WriteAllText(dataDir, extractedText);
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

### نموذج التعليمات البرمجية المصدر لاستخراج نص الأعمدة باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");                
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach (TextFragment tf in tfc)
{
	// تحتاج إلى تقليل حجم الخط بنسبة 70% على الأقل
	tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument); 
dataDir = dataDir + "ExtractColumnsText_out.txt";
System.IO.File.WriteAllText(dataDir, extractedText);           
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

## خاتمة
لقد نجحت في استخراج نص الأعمدة من مستند PDF باستخدام Aspose.PDF لـ .NET. تم حفظ النص المستخرج في ملف الإخراج المحدد.

### الأسئلة الشائعة

#### س: ما هو الغرض من هذا البرنامج التعليمي؟

ج: يقدم هذا البرنامج التعليمي دليلاً خطوة بخطوة حول استخراج أعمدة النص من ملف PDF باستخدام Aspose.PDF لـ .NET. يوفر كود مصدر C# المصاحب عرضًا عمليًا للإجراءات المطلوبة.

#### س: ما هي مساحات الأسماء التي يجب علي استيرادها؟

ج: في ملف التعليمات البرمجية الذي تنوي استخراج أعمدة نصية فيه، قم بتضمين ما يلي باستخدام التوجيهات في بداية الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

#### س: كيف أحدد دليل المستندات؟

 ج: تحديد موقع الخط`string dataDir = "YOUR DOCUMENT DIRECTORY";` في التعليمات البرمجية واستبدال`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

#### س: كيف يمكنني فتح مستند PDF موجود؟

 ج: في الخطوة 4، ستفتح مستند PDF موجودًا باستخدام الملف`Document` منشئ وتوفير المسار إلى ملف PDF الإدخال.

#### س: لماذا تم تعديل حجم الخط؟

ج: تتضمن الخطوة 5 تقليل حجم خط أجزاء النص بمعامل 0.7. يعمل هذا التعديل على تحسين إمكانية القراءة ويمثل النص العمودي بدقة أكبر.

#### س: كيف يمكنني استخراج النص من الأعمدة؟

 ج: تتكون الخطوة 6 من حفظ مستند PDF المعدل في دفق الذاكرة، وإعادة تحميله كمستند جديد، ثم استخدام`TextAbsorber` فئة لاستخراج النص من الأعمدة.

#### س: ما الهدف من حفظ النص المستخرج؟

ج: في الخطوة 7، ستحفظ النص المستخرج في ملف نصي في مسار ملف الإخراج المحدد.

#### س: لماذا تقليل حجم الخط قبل الاستخراج؟

ج: يساعد تقليل حجم الخط على التأكد من محاذاة النص المستخرج بشكل صحيح داخل الأعمدة، مما يوفر تمثيلاً أكثر دقة للتخطيط الأصلي.

#### س: ما هي الوجبات الرئيسية من هذا البرنامج التعليمي؟

ج: باتباع هذا البرنامج التعليمي، تكون قد اكتسبت المعرفة والمهارات اللازمة لاستخراج أعمدة النص من مستند PDF باستخدام Aspose.PDF لـ .NET. تم حفظ النص الناتج في ملف الإخراج المحدد.