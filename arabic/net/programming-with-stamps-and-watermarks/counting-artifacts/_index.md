---
title: عد القطع الأثرية
linktitle: عد القطع الأثرية
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية حساب العلامات المائية بسهولة في مستندات PDF الخاصة بك باستخدام Aspose.PDF for .NET.
type: docs
weight: 60
url: /ar/net/programming-with-stamps-and-watermarks/counting-artifacts/
---

في هذا البرنامج التعليمي ، سوف نأخذك خطوة بخطوة حول كيفية حساب العناصر الأثرية في مستند PDF باستخدام Aspose.PDF لـ .NET. سنوضح لك كيفية استخدام كود المصدر C # المقدم لحساب عدد القطع الأثرية "للعلامة المائية" على صفحة معينة من مستند PDF.

## الخطوة الأولى: تهيئة البيئة

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- بيئة تطوير .NET مثبتة.
- تم تنزيل مكتبة Aspose.PDF لـ .NET والمشار إليها في مشروعك.

## الخطوة الثانية: تحميل مستند PDF

تتمثل الخطوة الأولى في تحميل مستند PDF الحالي في مشروعك. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// افتح المستند
Document pdfDocument = new Document(dataDir + "watermark.pdf");
```

تأكد من استبدال "دليل المستندات" بالمسار الفعلي للدليل حيث يوجد مستند PDF الخاص بك.

## الخطوة 3: عد القطع الأثرية

الآن بعد أن قمت بتحميل مستند PDF ، يمكنك حساب عناصر نوع "العلامة المائية" على صفحة معينة من المستند. إليك الطريقة:

```csharp
// تهيئة العداد
int count = 0;

// حلقة من خلال جميع القطع الأثرية الصفحة الأولى
foreach(Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
     // إذا كان النوع الفرعي للقطعة الأثرية هو "علامة مائية" ، قم بزيادة العداد
     if (artifact.Subtype == Artifact.ArtifactSubtype.Watermark)
         count++;
}

// عرض عدد القطع الأثرية من نوع "العلامة المائية"
Console.WriteLine("The page contains " + count + " watermarks");
```

يتكرر الكود أعلاه عبر جميع القطع الأثرية الموجودة في الصفحة الأولى من مستند PDF ويزيد العداد لكل قطعة أثرية من نوع "العلامة المائية" تمت مواجهتها.

### عينة من التعليمات البرمجية المصدر لـ Counting Artifacts باستخدام Aspose.PDF لـ .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح المستند
Document pdfDocument = new Document( dataDir +  "watermark.pdf");

int count = 0;
foreach (Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
	// إذا كان نوع الأداة اليدوية علامة مائية ، فقم بإنشاء العداد
	if (artifact.Subtype == Artifact.ArtifactSubtype.Watermark) count++;
}
Console.WriteLine("Page contains " + count + " watermarks");

```

## خاتمة

تهنئة ! لقد تعلمت كيفية حساب آثار "العلامة المائية" في مستند PDF باستخدام Aspose.PDF لـ .NET. يمكنك الآن استخدام هذه المعرفة لإجراء تحليل ومعالجة محددة على القطع الأثرية في مستندات PDF الخاصة بك.
