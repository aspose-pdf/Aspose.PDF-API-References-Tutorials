---
title: احتواء محتويات الصفحة
linktitle: احتواء محتويات الصفحة
second_title: Aspose.PDF لمرجع .NET API
description: دليل مفصل خطوة بخطوة لضبط محتوى صفحة PDF باستخدام Aspose.PDF for .NET. سهل التنفيذ وخاتمة مجزية.
type: docs
weight: 50
url: /ar/net/programming-with-pdf-pages/fit-page-contents/
---
في هذا البرنامج التعليمي ، سنرشدك خلال العملية خطوة بخطوة لضبط محتوى صفحة PDF باستخدام Aspose.PDF for .NET. سنشرح الكود المصدري C # المجمّع ونزودك بدليل شامل لمساعدتك على فهم هذه الميزة وتنفيذها في مشاريعك الخاصة. في نهاية هذا البرنامج التعليمي ، ستعرف كيفية ضبط محتوى صفحات PDF باستخدام Aspose.PDF for .NET.

## المتطلبات الأساسية
قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- معرفة أساسية بلغة البرمجة C #
- تم تثبيت Aspose.PDF for .NET في بيئة التطوير الخاصة بك

## الخطوة 1: تحديد دليل المستند
أولاً ، تحتاج إلى تعيين المسار إلى دليل المستندات الخاص بك. هذا هو المكان الذي يوجد به ملف PDF للإدخال. استبدل "دليل المستندات" بالمسار المناسب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: قم بتحميل مستند PDF
 ثم يمكنك تحميل مستند PDF باستخدام ملف`Document` فئة Aspose.PDF. تأكد من تحديد المسار الصحيح لملف PDF المدخل.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## الخطوة 3: ضبط محتوى الصفحة
يمكنك الآن التنقل بين جميع صفحات المستند وضبط محتوى كل صفحة وفقًا لحجم صندوق الوسائط. في المثال المقدم ، نقوم بتعديل عرض الصفحة لعرضها في الوضع الأفقي (أفقي) مع الحفاظ على نفس الارتفاع. يتم حساب العرض الجديد بناءً على نسبة العرض إلى الارتفاع لمربع الوسائط.

```csharp
foreach(Page page in doc.Pages)
{
     Rectangle r = page.MediaBox;
     double newHeight = r.Height;
     double newWidth = r.Height * r.Height / r.Width;
}
```

### نموذج التعليمات البرمجية المصدر لمحتويات الصفحة باستخدام Aspose.PDF لـ .NET 

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
foreach (Page page in doc.Pages)
{
	Rectangle r = page.MediaBox;
	// ارتفاع جديد هو نفسه
	double newHeight = r.Height;
	// يتم توسيع العرض الجديد بشكل متناسب لجعل الاتجاه أفقيًا
	// (نفترض أن الاتجاه السابق هو عمودي)
	double newWidth = r.Height * r.Height / r.Width;
}          

```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية ضبط محتوى صفحة PDF باستخدام Aspose.PDF لـ .NET. باتباع الخطوات الموضحة أعلاه ، يمكنك بسهولة تنفيذ هذه الوظيفة في مشاريعك الخاصة. لا تتردد في استكشاف وثائق Aspose.PDF لاكتشاف الميزات المفيدة الأخرى للعمل مع ملفات PDF.
