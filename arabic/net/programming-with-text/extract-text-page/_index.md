---
title: استخراج نص الصفحة
linktitle: استخراج نص الصفحة
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استخراج نص من صفحة معينة من مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 200
url: /ar/net/programming-with-text/extract-text-page/
---

سيرشدك هذا البرنامج التعليمي خلال عملية استخراج النص من صفحة معينة من مستند PDF باستخدام Aspose.PDF for .NET. يوضح كود المصدر C # المقدم الخطوات الضرورية.

## متطلبات
قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي مترجم C # آخر مثبت على جهازك.
- Aspose.PDF لمكتبة .NET. يمكنك تنزيله من موقع Aspose الرسمي أو استخدام مدير الحزم مثل NuGet لتثبيته.

## الخطوة 1: قم بإعداد المشروع
1. قم بإنشاء مشروع C # جديد في بيئة التطوير المفضلة لديك.
2. قم بإضافة مرجع إلى Aspose.PDF لمكتبة .NET.

## الخطوة 2: استيراد مساحات الأسماء المطلوبة
في ملف التعليمات البرمجية حيث تريد استخراج النص ، أضف ما يلي باستخدام التوجيهات في أعلى الملف:

```csharp
using Aspose.Pdf;
using System.IO;
```

## الخطوة 3: قم بتعيين دليل المستند
 في الكود ، حدد موقع السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدالها`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل حيث يتم تخزين المستندات الخاصة بك.

## الخطوة 4: افتح مستند PDF
 افتح مستند PDF موجود باستخدام امتداد`Document` المُنشئ وتمرير المسار إلى ملف PDF المُدخل.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## الخطوة 5: استخراج نص من صفحة معينة
 إنشاء`TextAbsorber` كائن لاستخراج النص من المستند. قبول الممتص للصفحة المطلوبة عن طريق الوصول إليها من خلال`Pages` جمع`pdfDocument`.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages[1].Accept(textAbsorber);
```

## الخطوة 6: احصل على النص المستخرج
 قم بالوصول إلى النص المستخرج من ملف`TextAbsorber` هدف.

```csharp
string extractedText = textAbsorber.Text;
```

## الخطوة 7: احفظ النص المستخرج
 إنشاء`TextWriter` وافتح الملف حيث تريد حفظ النص المستخرج. اكتب النص المستخرج في الملف وأغلق الدفق.

```csharp
dataDir = dataDir + "extracted-text_out.txt";
TextWriter tw = new StreamWriter(dataDir);
tw.WriteLine(extractedText);
tw. Close();
```

### نموذج التعليمات البرمجية المصدر لـ Extract Text Page باستخدام Aspose.PDF for .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
// إنشاء كائن TextAbsorber لاستخراج النص
TextAbsorber textAbsorber = new TextAbsorber();
// تقبل الممتص لصفحة معينة
pdfDocument.Pages[1].Accept(textAbsorber);
// احصل على النص المستخرج
string extractedText = textAbsorber.Text;
dataDir = dataDir + "extracted-text_out.txt";
// قم بإنشاء كاتب وافتح الملف
TextWriter tw = new StreamWriter(dataDir);
// اكتب سطرًا من النص في الملف
tw.WriteLine(extractedText);
// أغلق الدفق
tw.Close();
Console.WriteLine("\nText extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

## خاتمة
لقد نجحت في استخراج نص من صفحة معينة من مستند PDF باستخدام Aspose.PDF for .NET. تم حفظ النص المستخرج في ملف الإخراج المحدد.