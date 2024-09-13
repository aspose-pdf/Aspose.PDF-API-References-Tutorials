---
title: استخراج نص الأعمدة في ملف PDF
linktitle: استخراج نص الأعمدة في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية استخراج نص الأعمدة في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 150
url: /ar/net/programming-with-text/extract-columns-text/
---
سيرشدك هذا البرنامج التعليمي خلال عملية استخراج نص الأعمدة في ملف PDF باستخدام Aspose.PDF لـ .NET. يوضح كود المصدر C# المقدم الخطوات اللازمة.

## متطلبات
قبل أن تبدأ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي مُجمِّع C# آخر مُثبت على جهازك.
- مكتبة Aspose.PDF لـ .NET. يمكنك تنزيلها من موقع Aspose الرسمي أو استخدام مدير حزم مثل NuGet لتثبيتها.

## الخطوة 1: إعداد المشروع
1. قم بإنشاء مشروع C# جديد في بيئة التطوير المفضلة لديك.
2. أضف مرجعًا إلى مكتبة Aspose.PDF لـ .NET.

## الخطوة 2: استيراد المساحات المطلوبة
في ملف الكود الذي تريد استخراج نص الأعمدة منه، أضف ما يلي باستخدام التوجيهات في أعلى الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

## الخطوة 3: تعيين دليل المستند
 في الكود، حدد السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدالها`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل الذي يتم تخزين مستنداتك فيه.

## الخطوة 4: افتح مستند PDF
 افتح مستند PDF موجودًا باستخدام`Document`المنشئ وتمرير المسار إلى ملف PDF المدخل.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## الخطوة 5: ضبط حجم الخط
قم بتقليل حجم الخط في أجزاء النص بعامل 0.7 لتحسين قابلية القراءة وتمثيل النص العمودي بشكل أفضل.

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
 احفظ مستند PDF المعدّل في مجرى ذاكرة وأعد تحميله كمستند جديد. ثم استخدم`TextAbsorber` فئة لاستخراج النص من الأعمدة.

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

### عينة من كود المصدر لاستخراج نص الأعمدة باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// فتح المستند
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");                
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach (TextFragment tf in tfc)
{
	// يجب تقليل حجم الخط بنسبة 70% على الأقل
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

ج: يقدم هذا البرنامج التعليمي دليلاً خطوة بخطوة حول استخراج أعمدة نصية من ملف PDF باستخدام Aspose.PDF لـ .NET. يوفر كود المصدر C# المصاحب عرضًا عمليًا للإجراءات المطلوبة.

#### س: ما هي المساحات الأسماء التي يجب أن أستوردها؟

أ: في ملف الكود الذي تنوي استخراج أعمدة النص فيه، قم بتضمين ما يلي باستخدام التوجيهات في بداية الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

#### س: كيف أحدد دليل المستند؟

 أ: حدد موقع الخط`string dataDir = "YOUR DOCUMENT DIRECTORY";` في الكود واستبداله`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستند الخاص بك.

#### س: كيف يمكنني فتح مستند PDF موجود؟

 أ: في الخطوة 4، ستفتح مستند PDF موجودًا باستخدام`Document` المنشئ وتوفير المسار إلى ملف PDF المدخل.

#### س: لماذا يتم تعديل حجم الخط؟

أ: تتضمن الخطوة 5 تقليل حجم الخط في أجزاء النص بعامل 0.7. يعمل هذا التعديل على تحسين قابلية القراءة وتمثيل النص العمودي بدقة أكبر.

#### س: كيف يمكنني استخراج النص من الأعمدة؟

 أ: تتكون الخطوة 6 من حفظ مستند PDF المعدل في مجرى ذاكرة، وإعادة تحميله كمستند جديد، ثم استخدام`TextAbsorber` فئة لاستخراج النص من الأعمدة.

#### س: ما هو الهدف من حفظ النص المستخرج؟

أ: في الخطوة 7، ستحفظ النص المستخرج في ملف نصي في مسار ملف الإخراج المحدد.

#### س: لماذا يجب تقليل حجم الخط قبل الاستخراج؟

أ: يساعد تقليل حجم الخط على ضمان محاذاة النص المستخرج بشكل صحيح داخل الأعمدة، مما يوفر تمثيلًا أكثر دقة للتخطيط الأصلي.

#### س: ما هو أهم ما يمكن تعلمه من هذا البرنامج التعليمي؟

ج: باتباع هذا البرنامج التعليمي، اكتسبت المعرفة والمهارات اللازمة لاستخراج أعمدة نصية من مستند PDF باستخدام Aspose.PDF لـ .NET. تم حفظ النص الناتج في ملف الإخراج المحدد.