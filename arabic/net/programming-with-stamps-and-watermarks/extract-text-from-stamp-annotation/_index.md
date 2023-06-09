---
title: استخراج النص من ختم التعليق التوضيحي
linktitle: استخراج النص من ختم التعليق التوضيحي
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استخراج النص بسهولة من تعليق توضيحي للطوابع في مستندات PDF الخاصة بك باستخدام Aspose.PDF for .NET.
type: docs
weight: 80
url: /ar/net/programming-with-stamps-and-watermarks/extract-text-from-stamp-annotation/
---
في هذا البرنامج التعليمي ، سوف نأخذك خطوة بخطوة حول كيفية استخراج نص من تعليق توضيحي للطوابع في مستند PDF باستخدام Aspose.PDF for .NET. سنوضح لك كيفية استخدام كود المصدر C # المقدم لاستخراج النص من تعليق توضيحي لختم معين في صفحة معينة من مستند PDF.

## الخطوة الأولى: تهيئة البيئة

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- بيئة تطوير .NET مثبتة.
- تم تنزيل مكتبة Aspose.PDF لـ .NET والمشار إليها في مشروعك.

## الخطوة الثانية: تحميل مستند PDF

تتمثل الخطوة الأولى في تحميل مستند PDF الحالي في مشروعك. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بتحميل المستند
Document doc = new Document(dataDir + "test.pdf");
```

تأكد من استبدال "دليل المستندات" بالمسار الفعلي للدليل حيث يوجد مستند PDF الخاص بك.

## الخطوة 3: استخرج النص من شرح الختم

الآن بعد أن قمت بتحميل مستند PDF ، يمكنك استخراج النص من التعليق التوضيحي للطابع المحدد. إليك الطريقة:

```csharp
// استرداد التعليق التوضيحي المخزن المؤقت
StampAnnotation annot = doc.Pages[1].Annotations[3] as StampAnnotation;

// قم بإنشاء ماص للنص
TextAbsorber ta = new TextAbsorber();

// قم بزيارة مظهر التعليق التوضيحي
XForm ap = annot. Appearance["N"];
ta.Visit(ap);

// اعرض النص المستخرج
Console.WriteLine(ta.Text);
```

يسترد الكود أعلاه التعليق التوضيحي للطوابع من الصفحة المحددة لمستند PDF ثم يستخدم ماصًا للنص لاستخراج النص من مظهر التعليق التوضيحي. ثم يتم عرض النص المستخرج في الإخراج.

### نموذج التعليمات البرمجية المصدر لـ Extract Text From Stamp Annotation باستخدام Aspose.PDF for .NET 
```csharp

string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "test.pdf");
StampAnnotation annot = doc.Pages[1].Annotations[3] as StampAnnotation;
TextAbsorber ta = new TextAbsorber();
XForm ap = annot.Appearance["N"];
ta.Visit(ap);
Console.WriteLine(ta.Text);

```

## خاتمة

تهنئة ! لقد تعلمت كيفية استخراج نص من تعليق توضيحي على طابع في مستند PDF باستخدام Aspose.PDF for .NET. يمكنك الآن استخدام هذه الطريقة لاستخراج نص من التعليقات التوضيحية الأخرى في مستندات PDF الخاصة بك.
