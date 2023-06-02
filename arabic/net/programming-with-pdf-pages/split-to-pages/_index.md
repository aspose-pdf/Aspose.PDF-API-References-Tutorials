---
title: تقسيم إلى صفحات
linktitle: تقسيم إلى صفحات
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لتقسيم مستند PDF إلى صفحات فردية باستخدام Aspose.PDF for .NET.
type: docs
weight: 140
url: /ar/net/programming-with-pdf-pages/split-to-pages/
---
في هذا البرنامج التعليمي ، سنرشدك خلال العملية خطوة بخطوة لتقسيم مستند PDF إلى صفحات فردية باستخدام Aspose.PDF لـ .NET. سنشرح الكود المصدري C # المجمّع ونزودك بدليل شامل لمساعدتك على فهم هذه الميزة وتنفيذها في مشاريعك الخاصة. في نهاية هذا البرنامج التعليمي ، ستعرف كيفية تقسيم مستند PDF إلى ملفات PDF متعددة ، كل منها يحتوي على صفحة واحدة.

## المتطلبات الأساسية
قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- معرفة أساسية بلغة البرمجة C #
- تم تثبيت Aspose.PDF for .NET في بيئة التطوير الخاصة بك

## الخطوة 1: تحديد دليل المستند
أولاً ، تحتاج إلى تعيين المسار إلى دليل المستندات الخاص بك. هذا هو المكان الذي يوجد به مستند PDF الذي تريد تقسيمه. استبدل "دليل المستندات" بالمسار المناسب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: افتح مستند PDF
 ثم يمكنك فتح مستند PDF لتقسيمه باستخدام ملف`Document` فئة Aspose.PDF. تأكد من تحديد مسار المستند الصحيح.

```csharp
Document pdfDocument = new Document(dataDir + "SplitToPages.pdf");
```

## الخطوة 3: تصفح الصفحات وقسمها
يمكنك الآن تكرار كل صفحات مستند PDF باستخدام حلقة. لكل صفحة ، قم بإنشاء مستند جديد وإضافة تلك الصفحة إلى هذا المستند الجديد. ثم احفظ المستند الجديد باستخدام اسم ملف فريد لكل صفحة.

```csharp
int pageCount = 1;
foreach(Page pdfPage in pdfDocument.Pages)
{
Document newDocument = newDocument();
newDocument.Pages.Add(pdfPage);
newDocument.Save(dataDir + "page_" + pageCount + "_out" + ".pdf");
pageCount++;
}
```

### نموذج التعليمات البرمجية المصدر لـ Split To Pages باستخدام Aspose.PDF لـ .NET 

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "SplitToPages.pdf");
int pageCount = 1;
// حلقة من خلال جميع الصفحات
foreach (Page pdfPage in pdfDocument.Pages)
{
	Document newDocument = new Document();
	newDocument.Pages.Add(pdfPage);
	newDocument.Save(dataDir + "page_" + pageCount + "_out" + ".pdf");
	pageCount++;
}

```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية تقسيم مستند PDF إلى صفحات فردية باستخدام Aspose.PDF for .NET. باتباع هذا الدليل التفصيلي خطوة بخطوة ، يمكنك بسهولة تقسيم مستند PDF إلى ملفات PDF متعددة ، كل منها يحتوي على صفحة واحدة. يقدم Aspose.PDF واجهة برمجة تطبيقات قوية ومرنة للعمل مع مستندات PDF في مشاريعك. يمكنك الآن استخدام هذه الميزة لأداء عمليات تقسيم مستندات PDF وفقًا لاحتياجاتك الخاصة.
