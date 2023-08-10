---
title: استخراج النص من منطقة الصفحة
linktitle: استخراج النص من منطقة الصفحة
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استخراج نص من منطقة معينة على صفحة من مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 190
url: /ar/net/programming-with-text/extract-text-from-page-region/
---

سيرشدك هذا البرنامج التعليمي خلال عملية استخراج نص من منطقة معينة على صفحة من مستند PDF باستخدام Aspose.PDF for .NET. يوضح كود المصدر C # المقدم الخطوات الضرورية.

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
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

## الخطوة 5: استخراج نص من منطقة الصفحة
 إنشاء`TextAbsorber`كائن لاستخراج النص من المستند. قم بتكوين ملف`TextSearchOptions` لقصر البحث على منطقة صفحة معينة محددة بواسطة مستطيل.

```csharp
TextAbsorber absorb = new TextAbsorber();
absorb.TextSearchOptions.LimitToPageBounds = true;
absorb.TextSearchOptions.Rectangle = new Aspose.Pdf.Rectangle(100, 200, 250, 350);
pdfDocument.Pages[1].Accept(absorb);
```

## الخطوة 6: احصل على النص المستخرج
 قم بالوصول إلى النص المستخرج من ملف`TextAbsorber` هدف.

```csharp
string extractedText = absorb.Text;
```

## الخطوة 7: احفظ النص المستخرج
 إنشاء`TextWriter` وافتح الملف حيث تريد حفظ النص المستخرج. اكتب النص المستخرج في الملف وأغلق الدفق.

```csharp
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
tw.WriteLine(extractedText);
tw. Close();
```

### نموذج التعليمات البرمجية المصدر لاستخراج النص من منطقة الصفحة باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
// إنشاء كائن TextAbsorber لاستخراج النص
TextAbsorber absorber = new TextAbsorber();
absorber.TextSearchOptions.LimitToPageBounds = true;
absorber.TextSearchOptions.Rectangle = new Aspose.Pdf.Rectangle(100, 200, 250, 350);
// تقبل الممتص للصفحة الأولى
pdfDocument.Pages[1].Accept(absorber);
// احصل على النص المستخرج
string extractedText = absorber.Text;
// قم بإنشاء كاتب وافتح الملف
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
// اكتب سطرًا من النص في الملف
tw.WriteLine(extractedText);
// أغلق الدفق
tw.Close();
```

## خاتمة
لقد نجحت في استخراج نص من منطقة معينة في صفحة وثيقة PDF باستخدام Aspose.PDF for .NET. تم حفظ النص المستخرج في ملف الإخراج المحدد.