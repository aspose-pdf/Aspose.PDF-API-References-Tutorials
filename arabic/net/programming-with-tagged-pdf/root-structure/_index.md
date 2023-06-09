---
title: هيكل الجذر
linktitle: هيكل الجذر
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لاستخدام عناصر بنية الجذر مع Aspose.PDF for .NET للوصول إلى الجذر وكائن StructTreeRoot لوثيقة PDF.
type: docs
weight: 130
url: /ar/net/programming-with-tagged-pdf/root-structure/
---
في هذا الدليل المفصل خطوة بخطوة ، سوف نوضح لك كيفية استخدام عناصر بنية الجذر مع Aspose.PDF for .NET. Aspose.PDF هي مكتبة قوية تتيح لك إنشاء مستندات PDF ومعالجتها برمجيًا. تسمح لك عناصر بنية الجذر بالوصول إلى كائن StructTreeRoot لوثيقة PDF وعنصر بنية الجذر.

دعنا نتعمق في الكود ونتعلم كيفية استخدام عناصر بنية الجذر مع Aspose.PDF for .NET.

## المتطلبات الأساسية

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

1. تثبيت مكتبة Aspose.PDF لـ .NET.
2. معرفة أساسية بلغة البرمجة C #.

## الخطوة الأولى: تهيئة البيئة

للبدء ، افتح بيئة التطوير C # وأنشئ مشروعًا جديدًا. تأكد من إضافة مرجع إلى مكتبة Aspose.PDF لـ .NET في مشروعك.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: إنشاء المستند

 تتمثل الخطوة الأولى في إنشاء مستند PDF جديد باستخدام امتداد`Document` فصل.

```csharp
// قم بإنشاء مستند PDF
Document document = new Document();
```

## الخطوة 3: العمل مع المحتوى الذي تم وضع علامة عليه

ثم نحصل على محتوى المستند الذي تم وضع علامة عليه للعمل معه.

```csharp
// احصل على محتوى المستند بعلامات
ITaggedContent taggedContent = document.TaggedContent;
```

## الخطوة 4: حدد عنوان المستند ولغته

يمكننا الآن تعيين عنوان المستند ولغته.

```csharp
// حدد عنوان المستند ولغته
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

## الخطوة 5: الوصول إلى عنصر بنية الجذر

الآن يمكننا الوصول إلى كائن StructTreeRoot الخاص بالمستند وعنصر بنية الجذر.

```csharp
// الوصول إلى عنصر بنية الجذر
StructTreeRootElement structTreeRootElement = taggedContent.StructTreeRootElement;
StructureElement rootElement = taggedContent.RootElement;
```

### نموذج التعليمات البرمجية المصدر لـ Root Structure باستخدام Aspose.PDF لـ .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء مستند PDF
Document document = new Document();

// الحصول على محتوى للعمل مع TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;

// تعيين العنوان واللغة للوثيقة
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");

// يتم استخدام خصائص StructTreeRootElement و RootElement للوصول إلى ملفات
// كائن StructTreeRoot لوثيقة pdf وعنصر بنية الجذر (عنصر بنية المستند).
StructTreeRootElement structTreeRootElement = taggedContent.StructTreeRootElement;
StructureElement rootElement = taggedContent.RootElement;

```

## خاتمة

تهنئة ! لقد تعلمت كيفية استخدام عناصر بنية الجذر مع Aspose.PDF for .NET. يمكنك الآن الوصول إلى كائن StructTreeRoot الخاص بمستند PDF وعنصر بنية الجذر لإجراء عمليات متقدمة على بنية المستند.
