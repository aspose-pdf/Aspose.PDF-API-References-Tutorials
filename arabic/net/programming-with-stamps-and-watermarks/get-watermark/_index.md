---
title: احصل على علامة مائية
linktitle: احصل على علامة مائية
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استخراج العلامات المائية من مستندات PDF الخاصة بك باستخدام Aspose.PDF for .NET.
type: docs
weight: 100
url: /ar/net/programming-with-stamps-and-watermarks/get-watermark/
---
في هذا البرنامج التعليمي ، سوف نأخذك خطوة بخطوة حول كيفية الحصول على علامة مائية من مستند PDF باستخدام Aspose.PDF for .NET. سنوضح لك كيفية استخدام كود المصدر C # المقدم للتكرار خلال القطع الأثرية لصفحة معينة والحصول على نوع العلامة المائية والنص والموقع.

## الخطوة الأولى: تهيئة البيئة

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- بيئة تطوير .NET مثبتة.
- تم تنزيل مكتبة Aspose.PDF لـ .NET والمشار إليها في مشروعك.

## الخطوة الثانية: تحميل مستند PDF

تتمثل الخطوة الأولى في تحميل مستند PDF الحالي في مشروعك. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// افتح مستند PDF
Document pdfDocument = new Document(dataDir + "watermark.pdf");
```

تأكد من استبدال "دليل المستندات" بالمسار الفعلي للدليل حيث يوجد مستند PDF الخاص بك.

## الخطوة 3: الحصول على العلامة المائية

الآن بعد أن قمت بتحميل مستند PDF ، يمكنك التكرار من خلال عناصر الصفحة المحددة للحصول على معلومات العلامة المائية. إليك الطريقة:

```csharp
// تصفح القطع الأثرية واحصل على العلامة المائية الفرعية والنص والموقع
foreach(Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
     Console.WriteLine(artifact.Subtype + " " + artifact.Text + " " + artifact.Rectangle);
}
```

تدور الكود أعلاه عبر جميع القطع الأثرية الموجودة في الصفحة الأولى من مستند PDF وتعرض النوع الفرعي والنص والمستطيل (الموقع) لكل علامة مائية تمت مواجهتها.

### نموذج التعليمات البرمجية المصدر للحصول على علامة مائية باستخدام Aspose.PDF لـ .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح المستند
Document pdfDocument = new Document( dataDir +  "watermark.pdf");

// كرر من خلال واحصل على نوع الحوض والنص وموقع القطع الأثرية
foreach (Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
	Console.WriteLine(artifact.Subtype + " " + artifact.Text + " " + artifact.Rectangle);
}

```

## خاتمة

تهنئة ! لقد تعلمت كيفية الحصول على معلومات العلامة المائية من مستند PDF باستخدام Aspose.PDF for .NET. يمكنك الآن استخدام هذه المعرفة لتحليل ومعالجة العلامات المائية في مستندات PDF الخاصة بك.
