---
title: احصل على أبعاد
linktitle: احصل على أبعاد
second_title: Aspose.PDF لمرجع .NET API
description: في هذا البرنامج التعليمي ، نشرح كيفية الحصول على أبعاد صفحة PDF وإجراء عمليات معالجة باستخدام Aspose.PDF لـ .NET. يتم توفير خطوات مفصلة لإرشادك خلال العملية.
type: docs
weight: 60
url: /ar/net/programming-with-pdf-pages/get-dimensions/
---
في هذا البرنامج التعليمي ، سنرشدك خلال العملية خطوة بخطوة للحصول على أبعاد الصفحة في ملف PDF باستخدام Aspose.PDF for .NET. سنشرح الكود المصدري C # المجمّع ونزودك بدليل شامل لمساعدتك على فهم هذه الميزة وتنفيذها في مشاريعك الخاصة. في نهاية هذا البرنامج التعليمي ، ستعرف كيفية الحصول على أبعاد الصفحة في ملف PDF باستخدام Aspose.PDF for .NET.

## المتطلبات الأساسية
قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- معرفة أساسية بلغة البرمجة C #
- تم تثبيت Aspose.PDF for .NET في بيئة التطوير الخاصة بك

## الخطوة 1: تحديد دليل المستند
أولاً ، تحتاج إلى تعيين المسار إلى دليل المستندات الخاص بك. هذا هو المكان الذي يوجد به ملف PDF الخاص بك. استبدل "دليل المستندات" بالمسار المناسب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: افتح مستند PDF
 ثم يمكنك فتح ملف PDF باستخدام امتداد`Document` فئة Aspose.PDF. تأكد من تحديد المسار الصحيح لملف PDF.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## الخطوة 3: أضف صفحة فارغة (إذا لزم الأمر)
 إذا كان مستند PDF يحتوي بالفعل على صفحات ، فيمكنك الانتقال إلى صفحة موجودة باستخدام الفهرس`1` (تحتوي الصفحة الأولى على فهرس 1). خلاف ذلك ، يمكنك إضافة صفحة جديدة إلى المستند.

```csharp
Page page = pdfDocument.Pages.Count > 0? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
```

## الخطوة 4: احصل على أبعاد الصفحة
 يمكنك الآن الحصول على أبعاد الصفحة باستخدام ملف`GetPageRect()` طريقة`Page` هدف. تقوم هذه الطريقة بإرجاع ملف`Rectangle`كائن يحتوي على أبعاد الصفحة. يمكنك الوصول إلى العرض والارتفاع باستخدام ملف`Width` و`Height` ملكيات.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

## الخطوة 5: قم بتدوير الصفحة
 إذا كنت تريد تدوير الصفحة ، يمكنك استخدام امتداد`Rotate` ممتلكات`Page` هدف. في هذا المثال ، يتم تدوير الصفحة بمقدار 90 درجة.

```csharp
page. Rotate = Rotate. on90;
```

## الخطوة 6: احصل على أبعاد الصفحة مرة أخرى
 بعد تدوير الصفحة ، يمكنك الحصول على أبعاد الصفحة مرة أخرى باستخدام تنسيق`GetPageRect()` طريقة.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

### نموذج التعليمات البرمجية المصدر لـ Get Dimensions باستخدام Aspose.PDF for .NET 

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// يضيف صفحة فارغة إلى مستند pdf
Page page = pdfDocument.Pages.Count > 0 ? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
// احصل على معلومات ارتفاع الصفحة وعرضها
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
// تدوير الصفحة بزاوية 90 درجة
page.Rotate = Rotation.on90;
// احصل على معلومات ارتفاع الصفحة وعرضها
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);

```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية الحصول على أبعاد الصفحة في ملف PDF باستخدام Aspose.PDF لـ .NET. باتباع الخطوات المقدمة ، يمكنك بسهولة استخراج أبعاد الصفحة وتنفيذ عمليات معالجة PDF أخرى. يوفر Aspose.PDF for .NET مرونة كبيرة للعمل مع ملفات PDF ويسمح لك بتطوير حلول قوية ومخصصة.

لا تتردد في استكشاف توثيق Aspose.PDF لاكتشاف جميع الميزات التي توفرها هذه المكتبة.
