---
title: أضف كائن SVG
linktitle: أضف كائن SVG
second_title: Aspose.PDF لمرجع .NET API
description: قم بإضافة كائنات SVG بسهولة إلى ملفات PDF الخاصة بك باستخدام Aspose.PDF for .NET.
type: docs
weight: 30
url: /ar/net/programming-with-tables/add-svg-object/
---

في هذا البرنامج التعليمي ، سوف نتعلم كيفية إضافة كائن SVG إلى ملف PDF باستخدام Aspose.PDF لمكتبة .NET. يعد تنسيق SVG (Scalable Vector Graphics) تنسيقًا شائعًا للرسومات المتجهة التي يمكن تحجيمها بسهولة دون فقدان الجودة. باستخدام Aspose.PDF ، يمكنك إضافة كائنات SVG إلى مستندات PDF الخاصة بك برمجيًا.

## متطلبات

قبل أن نبدأ ، تأكد من توفر لديك ما يلي:

- تم تثبيت Visual Studio
- تثبيت Aspose.PDF لمكتبة .NET

## الخطوة 1: إعداد البيئة

أولاً ، لنقم بإعداد البيئة عن طريق إنشاء مشروع C # جديد في Visual Studio. افتح Visual Studio واتبع الخطوات التالية:

1. انقر فوق "ملف"> "جديد"> "مشروع" لإنشاء مشروع جديد.
2. حدد قالب "تطبيق Console (.NET Framework)" أو "Console App (.NET Core)" ، بناءً على الإعداد الخاص بك.
3. اختر اسمًا وموقعًا مناسبين لمشروعك ، ثم انقر على "إنشاء".

## الخطوة 2: إنشاء كائنات المستند والصورة

في هذه الخطوة ، سننشئ الكائنات الضرورية لمستند PDF وصورة SVG. افتح ملف C # لمشروعك وأضف الكود التالي:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// كائن مستند فوري
Document doc = new Document();
// قم بإنشاء مثيل صورة
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
```

## الخطوة 3: تعيين خصائص الصورة

بعد ذلك ، سنقوم بتعيين خصائص صورة SVG الخاصة بنا. سنحدد نوع الملف كـ SVG والمسار إلى ملف SVG وأبعاد الصورة. أضف الكود التالي بعد الخطوة السابقة:

```csharp
// تعيين نوع الصورة كـ SVG
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// مسار الملف المصدر
img.File = dataDir + "SVGToPDF.svg";
// تعيين العرض لمثال الصورة
img. FixWidth = 50;
// تعيين الارتفاع لمثال الصورة
img.FixHeight = 50;
```

## الخطوة 4: إنشاء الجدول وتكوينه

الآن ، لنقم بإنشاء كائن جدول وضبط عرض العمود. سنقوم بإنشاء جدول به عمودين ، بعرض 100 وحدة لكل منهما. أضف الكود التالي:

```csharp
// إنشاء جدول المثيل
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// تعيين العرض لخلايا الجدول
table. ColumnWidths = "100 100";
```

## الخطوة 5: أضف خلايا إلى الجدول

في هذه الخطوة ، سنضيف صفًا وخلايا إلى الجدول. يمثل كل صف صفًا أفقيًا في الجدول ، ويتم إضافة خلايا إلى الصفوف. أضف الكود التالي:

```csharp
//إنشاء كائن صف وإضافته إلى مثيل الجدول
Aspose.Pdf.Row row = table.Rows.Add();
// قم بإنشاء كائن خلية وإضافته إلى مثيل الصف
Aspose.Pdf.Cell cell = row.Cells.Add();
```

## الخطوة 6: إضافة نص وصورة إلى الخلايا

بعد ذلك ، دعنا نضيف نصًا وصورة SVG إلى خلايا الجدول. سنضيف النص "الخلية الأولى" إلى الخلية الأولى وصورة SVG إلى الخلية الثانية. أضف الكود التالي:

```csharp
// إضافة جزء نص إلى مجموعة فقرات كائن الخلية
cell.Paragraphs.Add(new TextFragment("First cell"));
// أضف خلية أخرى إلى كائن الصف
cell = row. Cells. Add();
// أضف صورة SVG إلى مجموعة فقرات لمثيل الخلية المضافة حديثًا
cell.Paragraphs.Add(img);
```

## الخطوة 7: إنشاء وإضافة صفحة إلى المستند

الآن ، لنقم بإنشاء كائن صفحة وإضافته إلى المستند. سيتم إضافة الجدول إلى مجموعة فقرات الصفحة. أضف الكود التالي:

```csharp
// قم بتكوين كائن صفحة وإضافته إلى مجموعة صفحات مثيل المستند
Page page = doc.Pages.Add();
// إضافة جدول إلى مجموعة فقرات كائن الصفحة
page.Paragraphs.Add(table);
```

## الخطوة الثامنة: احفظ ملف PDF

أخيرًا ، سنقوم بحفظ ملف PDF في الموقع المحدد. أضف الكود التالي:

```csharp
dataDir = dataDir + "AddSVGObject_out.pdf";
// احفظ ملف PDF
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);
```

### مثال على التعليمات البرمجية المصدر لإضافة كائن SVG باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء كائن المستند
Document doc = new Document();
// قم بإنشاء مثيل صورة
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// تعيين نوع الصورة كـ SVG
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// مسار الملف المصدر
img.File = dataDir + "SVGToPDF.svg";
// تعيين العرض لمثال الصورة
img.FixWidth = 50;
// تعيين الارتفاع لمثال الصورة
img.FixHeight = 50;
// إنشاء مثيل الجدول
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// تعيين العرض لخلايا الجدول
table.ColumnWidths = "100 100";
//إنشاء كائن صف وإضافته إلى مثيل الجدول
Aspose.Pdf.Row row = table.Rows.Add();
// قم بإنشاء كائن خلية وإضافته إلى مثيل الصف
Aspose.Pdf.Cell cell = row.Cells.Add();
// إضافة جزء نص إلى مجموعة فقرات كائن الخلية
cell.Paragraphs.Add(new TextFragment("First cell"));
// أضف خلية أخرى إلى كائن الصف
cell = row.Cells.Add();
// أضف صورة SVG إلى مجموعة فقرات لمثيل الخلية المضافة حديثًا
cell.Paragraphs.Add(img);
// قم بتكوين كائن صفحة وإضافته إلى مجموعة صفحات مثيل المستند
Page page = doc.Pages.Add();
// إضافة جدول إلى مجموعة فقرات كائن الصفحة
page.Paragraphs.Add(table);

dataDir = dataDir + "AddSVGObject_out.pdf";
// احفظ ملف PDF
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);            
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية إضافة كائن SVG إلى ملف PDF باستخدام Aspose.PDF لمكتبة .NET. قمنا بتغطية العملية خطوة بخطوة لإنشاء مستند ، وإعداد البيئة ، وإضافة صورة SVG إلى خلية جدول ، وحفظ ملف PDF. يمكنك الآن دمج كائنات SVG في مستندات PDF الخاصة بك برمجيًا.