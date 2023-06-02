---
title: احصل على عدد الصفحات
linktitle: احصل على عدد الصفحات
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة للحصول على عدد الصفحات لملف PDF باستخدام Aspose.PDF for .NET. سهولة المتابعة والتنفيذ في مشاريعك.
type: docs
weight: 80
url: /ar/net/programming-with-pdf-pages/get-page-count/
---
في هذا البرنامج التعليمي ، سنرشدك خلال العملية خطوة بخطوة للحصول على عدد الصفحات لملف PDF باستخدام Aspose.PDF لـ .NET. سنشرح الكود المصدري C # المجمّع ونزودك بدليل شامل لمساعدتك على فهم هذه الميزة وتنفيذها في مشاريعك الخاصة. في نهاية هذا البرنامج التعليمي ، ستعرف كيفية الحصول على عدد الصفحات لملف PDF باستخدام Aspose.PDF for .NET.

## المتطلبات الأساسية
قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- معرفة أساسية بلغة البرمجة C #
- تم تثبيت Aspose.PDF for .NET في بيئة التطوير الخاصة بك

## الخطوة 1: إنشاء كائن مستند
أولاً ، تحتاج إلى إنشاء مثيل لكائن مستند باستخدام فئة Document لـ Aspose.PDF.

```csharp
Document doc = new Document();
```

## الخطوة 2: أضف صفحة إلى المستند
 ثم يمكنك إضافة صفحة إلى المستند باستخدام امتداد`Add()` طريقة مجموعة صفحات المستند.

```csharp
Page page = doc.Pages.Add();
```

## الخطوة 3: إنشاء محتوى الصفحة
يمكنك الآن إنشاء محتوى الصفحة عن طريق إضافة كائنات TextFragment إلى مجموعة فقرات كائن الصفحة. في هذا المثال ، أضفنا TextFragment مكررًا 300 مرة لمحاكاة مستند ذي محتوى أطول.

```csharp
for (int i = 0; i < 300; i++)
page.Paragraphs.Add(new TextFragment("Page count test"));
```

## الخطوة 4: معالجة الفقرات والحصول على عدد الصفحات
 بمجرد إضافة المحتوى إلى الصفحة ، تحتاج إلى معالجة فقرات المستند عن طريق استدعاء`ProcessParagraphs()` طريقة. هذا يسمح لـ Aspose.PDF بحساب عدد الصفحات بدقة.

```csharp
doc.ProcessParagraphs();
```

## الخطوة 5: عرض عدد الصفحات
 أخيرًا ، يمكنك عرض عدد الصفحات في المستند عن طريق الوصول إلى ملف`Count` ملكية مجموعة الصفحات.

```csharp
Console.WriteLine("Number of pages in document = " + doc.Pages.Count);
```

### نموذج التعليمات البرمجية المصدر للحصول على عدد الصفحات باستخدام Aspose.PDF for .NET 

```csharp

// مثيل المستند
Document doc = new Document();
// أضف صفحة إلى مجموعة صفحات من ملف PDF
Page page = doc.Pages.Add();
// إنشاء مثيل حلقة
for (int i = 0; i < 300; i++)
	// إضافة TextFragment إلى مجموعة فقرات كائن الصفحة
	page.Paragraphs.Add(new TextFragment("Pages count test"));
// قم بمعالجة الفقرات في ملف PDF للحصول على عدد صفحات دقيق
doc.ProcessParagraphs();
// طباعة عدد الصفحات في المستند
Console.WriteLine("Number of pages in document = " + doc.Pages.Count);

```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية الحصول على عدد الصفحات لملف PDF باستخدام Aspose.PDF لـ .NET. باتباع الخطوات الموضحة أعلاه ، يمكنك بسهولة تنفيذ هذه الوظيفة في مشاريعك الخاصة. لا تتردد في استكشاف وثائق Aspose.PDF لاكتشاف الميزات المفيدة الأخرى للعمل مع ملفات PDF.