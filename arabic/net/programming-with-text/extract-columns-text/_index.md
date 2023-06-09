---
title: استخراج نص الأعمدة
linktitle: استخراج نص الأعمدة
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استخراج نصوص الأعمدة من مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 150
url: /ar/net/programming-with-text/extract-columns-text/
---

سيرشدك هذا البرنامج التعليمي خلال عملية استخراج نصوص الأعمدة من مستند PDF باستخدام Aspose.PDF for .NET. يوضح كود المصدر C # المقدم الخطوات الضرورية.

## متطلبات
قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي مترجم C # آخر مثبت على جهازك.
- Aspose.PDF لمكتبة .NET. يمكنك تنزيله من موقع Aspose الرسمي أو استخدام مدير الحزم مثل NuGet لتثبيته.

## الخطوة 1: قم بإعداد المشروع
1. قم بإنشاء مشروع C # جديد في بيئة التطوير المفضلة لديك.
2. قم بإضافة مرجع إلى Aspose.PDF لمكتبة .NET.

## الخطوة 2: استيراد مساحات الأسماء المطلوبة
في ملف التعليمات البرمجية حيث تريد استخراج نص الأعمدة ، أضف ما يلي باستخدام التوجيهات في أعلى الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

## الخطوة 3: قم بتعيين دليل المستند
 في الكود ، حدد موقع السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدالها`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل حيث يتم تخزين المستندات الخاصة بك.

## الخطوة 4: افتح مستند PDF
 افتح مستند PDF موجود باستخدام امتداد`Document` المُنشئ وتمرير المسار إلى ملف PDF المُدخل.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## الخطوة 5: ضبط حجم الخط
قم بتقليل حجم خط أجزاء النص بمعامل 0.7 لتحسين إمكانية القراءة وتمثيل النص العمودي بشكل أفضل.

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
 احفظ مستند PDF المعدل في تدفق الذاكرة وأعد تحميله كمستند جديد. ثم استخدم ملف`TextAbsorber` فئة لاستخراج النص من الأعمدة.

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
	// تحتاج إلى تصغير حجم الخط بنسبة 70٪ على الأقل
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
لقد نجحت في استخراج نص أعمدة من مستند PDF باستخدام Aspose.PDF for .NET. تم حفظ النص المستخرج في ملف الإخراج المحدد.