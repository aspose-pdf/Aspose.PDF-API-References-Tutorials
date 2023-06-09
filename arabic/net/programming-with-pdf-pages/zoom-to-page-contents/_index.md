---
title: تكبير محتويات الصفحة
linktitle: تكبير محتويات الصفحة
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لتكبير محتوى الصفحة في ملف PDF باستخدام Aspose.PDF for .NET. قم بتحسين مستندات PDF الخاصة بك وفقًا لاحتياجاتك الخاصة.
type: docs
weight: 160
url: /ar/net/programming-with-pdf-pages/zoom-to-page-contents/
---
في هذا البرنامج التعليمي ، سنرشدك خلال العملية خطوة بخطوة لتكبير محتوى الصفحة لملف PDF باستخدام Aspose.PDF for .NET. سنشرح الكود المصدري C # المجمّع ونزودك بدليل شامل لمساعدتك على فهم هذه الميزة وتنفيذها في مشاريعك الخاصة. في نهاية هذا البرنامج التعليمي ، ستعرف كيفية تكبير محتوى الصفحة لملف PDF باستخدام Aspose.PDF for .NET.

## المتطلبات الأساسية
قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- معرفة أساسية بلغة البرمجة C #
- تم تثبيت Aspose.PDF for .NET في بيئة التطوير الخاصة بك

## الخطوة 1: تحديد دليل المستند
أولاً ، تحتاج إلى تعيين المسار إلى دليل المستندات الخاص بك. هذا هو المكان الذي توجد فيه ملفات PDF التي تريد معالجتها. استبدل "دليل المستندات" بالمسار المناسب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: قم بتحميل ملف PDF المصدر
 ثم يمكنك تحميل ملف PDF المصدر باستخدام امتداد`Document` فئة Aspose.PDF. تأكد من تحديد المسار الصحيح لملف PDF.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## الخطوة 3: تعيين تكبير محتوى الصفحة
لتكبير محتوى الصفحة ، نحتاج إلى القيام بما يلي:

- استرجع المساحة المستطيلة من الصفحة الأولى من ملف PDF.
-  تجسيد`PdfPageEditor` فصل.
-  اربط ملف PDF المصدر بملف`PdfPageEditor` مثال.
- حدد معامل الزوم وفقًا لعرض المستطيل وارتفاعه.
- تحديث حجم الصفحة باستخدام أبعاد المستطيل.

هذا هو الكود المقابل:

```csharp
Aspose.Pdf.Rectangle rect = doc.Pages[1].Rect;
PdfPageEditor ppe = new PdfPageEditor();
ppe.BindPdf(dataDir + "input.pdf");
ppe.Zoom = (float)(rect.Width / rect.Height);
ppe.PageSize = new Aspose.Pdf.PageSize((float)rect.Height, (float)rect.Width);
```

## الخطوة 4: احفظ ملف PDF الناتج
 أخيرًا ، يمكنك حفظ ملف PDF المعدل باستخدام امتداد`Save()` طريقة`Document`فصل. تأكد من تحديد المسار الصحيح واسم الملف.

```csharp
dataDir = dataDir + "ZoomToPageContents_out.pdf";
doc.Save(dataDir);
```

### نموذج التعليمات البرمجية المصدر لـ Zoom To Page Contents باستخدام Aspose.PDF for .NET 

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// قم بتحميل ملف PDF المصدر
Document doc = new Document(dataDir + "input.pdf");
// احصل على منطقة مستطيلة من الصفحة الأولى من PDF
Aspose.Pdf.Rectangle rect = doc.Pages[1].Rect;
// إنشاء مثيل PdfPageEditor
PdfPageEditor ppe = new PdfPageEditor();
// ربط مصدر PDF
ppe.BindPdf(dataDir + "input.pdf");
// اضبط معامل التكبير
ppe.Zoom = (float)(rect.Width / rect.Height);
// تحديث حجم الصفحة
ppe.PageSize = new Aspose.Pdf.PageSize((float)rect.Height, (float)rect.Width);
dataDir = dataDir + "ZoomToPageContents_out.pdf";
// حفظ ملف الإخراج
doc.Save(dataDir);
System.Console.WriteLine("\nZoom to page contents applied successfully.\nFile saved at " + dataDir);

```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية تكبير محتوى الصفحة لملف PDF باستخدام Aspose.PDF لـ .NET. باتباع هذا الدليل التفصيلي خطوة بخطوة ، يمكنك بسهولة تطبيق التكبير / التصغير على محتوى الصفحة في ملفات PDF الخاصة بك. يوفر Aspose.PDF واجهة برمجة تطبيقات قوية ومرنة للعمل مع ملفات PDF وأداء عمليات مختلفة ، بما في ذلك تكبير محتوى الصفحة. استخدم هذه المعرفة لتخصيص مستندات PDF وتحسينها وفقًا لاحتياجاتك الخاصة.
