---
title: عناصر بنية النص
linktitle: عناصر بنية النص
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة عناصر بنية النص إلى مستند PDF باستخدام Aspose.PDF for .NET. قم بتحسين هيكل وإمكانية الوصول إلى ملفات PDF الخاصة بك.
type: docs
weight: 230
url: /ar/net/programming-with-tagged-pdf/text-structure-elements/
---
في هذا البرنامج التعليمي التفصيلي ، سنرشدك خلال التعليمات البرمجية المصدر C # المقدمة خطوة بخطوة لإنشاء عناصر بنية النص في مستند PDF بعلامات باستخدام Aspose.PDF for .NET. اتبع الإرشادات أدناه لفهم كيفية إضافة عناصر بنية النص إلى مستند PDF الخاص بك.

## الخطوة الأولى: تهيئة البيئة

قبل أن تبدأ ، تأكد من تكوين بيئة التطوير الخاصة بك لاستخدام Aspose.PDF لـ .NET. يتضمن ذلك تثبيت مكتبة Aspose.PDF وتهيئة مشروعك للرجوع إليه.

## الخطوة الثانية: إنشاء وثيقة PDF

في هذه الخطوة ، سننشئ كائن مستند PDF جديدًا باستخدام Aspose.PDF.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بإنشاء مستند PDF
Document document = new Document();
```

لقد أنشأنا مستند PDF جديدًا باستخدام Aspose.PDF.

## الخطوة 3: احصل على المحتوى الذي تم وضع علامة عليه وقم بتعيين العنوان واللغة

الآن دعنا نحصل على المحتوى المميز لمستند PDF ونضبط عنوان المستند ولغته.

```csharp
// احصل على المحتوى الذي تم وضع علامة عليه
ITaggedContent taggedContent = document.TaggedContent;

// حدد عنوان المستند ولغته
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

لقد قمنا بتعيين عنوان ولغة وثيقة PDF الموسومة.

## الخطوة 4: الحصول على عنصر بنية الجذر

الآن دعنا نحصل على عنصر بنية الجذر لمستند PDF.

```csharp
// الحصول على عنصر بنية الجذر
StructureElement rootElement = taggedContent.RootElement;
```

لقد حصلنا على عنصر البنية الجذرية لوثيقة PDF.

## الخطوة 5: إضافة عنصر بنية الفقرة

الآن دعنا نضيف عنصر بنية فقرة إلى مستند PDF الخاص بنا.

```csharp
// قم بإنشاء عنصر بنية الفقرة
ParagraphElement p = taggedContent.CreateParagraphElement();

// تعريف نص عنصر هيكل الفقرة
p.SetText("Paragraph.");

// أضف عنصر بنية الفقرة إلى عنصر بنية الجذر
rootElement.AppendChild(p);
```

أضفنا عنصر بنية فقرة مع نص إلى مستند PDF الخاص بنا.

## الخطوة 6: حفظ مستند PDF

الآن بعد أن انتهينا من تحرير مستند PDF ، دعنا نحفظه في ملف.

```csharp
// احفظ مستند PDF بعلامات
document.Save(dataDir + "ElementDeStructureDeTexte.pdf");
```

قمنا بحفظ مستند PDF الذي تم وضع علامة عليه بعنصر بنية النص في الدليل المحدد.


### عينة من التعليمات البرمجية المصدر لعناصر بنية النص باستخدام Aspose.PDF لـ .NET 

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

//احصل على عناصر بنية الجذر
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p = taggedContent.CreateParagraphElement();

// قم بتعيين النص إلى عنصر بنية النص
p.SetText("Paragraph.");
rootElement.AppendChild(p);

// حفظ وثيقة PDF الموسومة
document.Save(dataDir + "TextStructureElement.pdf");
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية استخدام Aspose.PDF لـ .NET لإضافة عناصر بنية النص إلى مستند PDF. يمكنك الآن استخدام هذه الميزات لتحسين هيكل وإمكانية الوصول إلى مستندات PDF الخاصة بك.