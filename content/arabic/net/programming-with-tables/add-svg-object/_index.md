---
title: إضافة كائن SVG في ملف PDF
linktitle: إضافة كائن SVG في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: يمكنك بسهولة إضافة كائنات SVG إلى ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 30
url: /ar/net/programming-with-tables/add-svg-object/
---
في هذا البرنامج التعليمي، سوف نتعلم كيفية إضافة كائن SVG إلى ملف PDF باستخدام مكتبة Aspose.PDF for .NET. يعد SVG (Scalable Vector Graphics) تنسيقًا شائعًا للرسومات المتجهة التي يمكن تغيير حجمها بسهولة دون فقدان الجودة. باستخدام Aspose.PDF، يمكنك إضافة كائنات SVG إلى مستندات PDF الخاصة بك برمجيًا.

## متطلبات

قبل أن نبدأ، تأكد من أن لديك ما يلي:

- تم تثبيت Visual Studio
- تم تثبيت Aspose.PDF لمكتبة .NET

## الخطوة 1: إعداد البيئة

أولاً، لنقم بإعداد البيئة عن طريق إنشاء مشروع C# جديد في Visual Studio. افتح Visual Studio واتبع الخطوات التالية:

1. انقر على "ملف" > "جديد" > "مشروع" لإنشاء مشروع جديد.
2. حدد قالب "تطبيق وحدة التحكم (.NET Framework)" أو "تطبيق وحدة التحكم (.NET Core)"، وفقًا لإعدادك.
3. اختر اسمًا وموقعًا مناسبًا لمشروعك، ثم انقر على "إنشاء".

## الخطوة 2: إنشاء كائنات المستندات والصور

في هذه الخطوة، سنقوم بإنشاء الكائنات الضرورية لمستند PDF وصورة SVG. افتح ملف C# الخاص بمشروعك وأضف الكود التالي:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// كائن المستند الفوري
Document doc = new Document();
// إنشاء مثيل الصورة
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
```

## الخطوة 3: تعيين خصائص الصورة

بعد ذلك، سنقوم بتعيين خصائص صورة SVG الخاصة بنا. سنحدد نوع الملف كـ SVG، والمسار إلى ملف SVG، وأبعاد الصورة. أضف الكود التالي بعد الخطوة السابقة:

```csharp
// قم بتعيين نوع الصورة كـ SVG
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// مسار الملف المصدر
img.File = dataDir + "SVGToPDF.svg";
// ضبط العرض لمثيل الصورة
img. FixWidth = 50;
// ضبط الارتفاع لمثال الصورة
img.FixHeight = 50;
```

## الخطوة 4: إنشاء الجدول وتكوينه

الآن، لنقم بإنشاء كائن جدول وضبط عرض الأعمدة. سنقوم بإنشاء جدول مكون من عمودين، عرض كل منهما 100 وحدة. أضف الكود التالي:

```csharp
// إنشاء جدول المثيلات
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// تعيين العرض لخلايا الجدول
table. ColumnWidths = "100 100";
```

## الخطوة 5: إضافة خلايا إلى الجدول

في هذه الخطوة، سنقوم بإضافة صف وخلايا إلى الجدول. يمثل كل صف صفًا أفقيًا في الجدول، وتتم إضافة الخلايا إلى الصفوف. أضف الكود التالي:

```csharp
//قم بإنشاء كائن صف وإضافته إلى مثيل الجدول
Aspose.Pdf.Row row = table.Rows.Add();
// قم بإنشاء كائن خلية وإضافته إلى مثيل الصف
Aspose.Pdf.Cell cell = row.Cells.Add();
```

## الخطوة 6: إضافة نص وصورة إلى الخلايا

بعد ذلك، دعونا نضيف نصًا وصورة SVG إلى خلايا الجدول. سنضيف النص "الخلية الأولى" إلى الخلية الأولى وصورة SVG إلى الخلية الثانية. أضف الكود التالي:

```csharp
// إضافة جزء نصي إلى مجموعة فقرات كائن الخلية
cell.Paragraphs.Add(new TextFragment("First cell"));
// إضافة خلية أخرى إلى كائن الصف
cell = row. Cells. Add();
// أضف صورة SVG إلى مجموعة الفقرات من مثيل الخلية المضافة مؤخرًا
cell.Paragraphs.Add(img);
```

## الخطوة 7: إنشاء وإضافة صفحة إلى المستند

الآن، لنقم بإنشاء كائن صفحة وإضافته إلى المستند. سيتم إضافة الجدول إلى مجموعة الفقرات بالصفحة. أضف الكود التالي:

```csharp
// قم بإنشاء كائن صفحة وإضافته إلى مجموعة الصفحات الخاصة بمثيل المستند
Page page = doc.Pages.Add();
// إضافة جدول إلى مجموعة الفقرات من كائن الصفحة
page.Paragraphs.Add(table);
```

## الخطوة 8: احفظ ملف PDF

وأخيرا، سوف نقوم بحفظ ملف PDF في الموقع المحدد. أضف الكود التالي:

```csharp
dataDir = dataDir + "AddSVGObject_out.pdf";
// حفظ ملف PDF
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);
```

### مثال على التعليمات البرمجية المصدر لإضافة كائن SVG باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء مثيل لكائن المستند
Document doc = new Document();
// إنشاء مثيل الصورة
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// قم بتعيين نوع الصورة كـ SVG
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// مسار الملف المصدر
img.File = dataDir + "SVGToPDF.svg";
// ضبط العرض لمثيل الصورة
img.FixWidth = 50;
// ضبط الارتفاع لمثال الصورة
img.FixHeight = 50;
// إنشاء مثيل الجدول
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// تعيين العرض لخلايا الجدول
table.ColumnWidths = "100 100";
//قم بإنشاء كائن صف وإضافته إلى مثيل الجدول
Aspose.Pdf.Row row = table.Rows.Add();
// قم بإنشاء كائن خلية وإضافته إلى مثيل الصف
Aspose.Pdf.Cell cell = row.Cells.Add();
// إضافة جزء نصي إلى مجموعة فقرات كائن الخلية
cell.Paragraphs.Add(new TextFragment("First cell"));
// إضافة خلية أخرى إلى كائن الصف
cell = row.Cells.Add();
// أضف صورة SVG إلى مجموعة الفقرات من مثيل الخلية المضافة مؤخرًا
cell.Paragraphs.Add(img);
// قم بإنشاء كائن صفحة وإضافته إلى مجموعة الصفحات الخاصة بمثيل المستند
Page page = doc.Pages.Add();
// إضافة جدول إلى مجموعة الفقرات من كائن الصفحة
page.Paragraphs.Add(table);

dataDir = dataDir + "AddSVGObject_out.pdf";
// حفظ ملف PDF
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);            
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية إضافة كائن SVG إلى ملف PDF باستخدام مكتبة Aspose.PDF for .NET. لقد قمنا بتغطية العملية خطوة بخطوة لإنشاء مستند، وإعداد البيئة، وإضافة صورة SVG إلى خلية جدول، وحفظ ملف PDF. يمكنك الآن دمج كائنات SVG في مستندات PDF الخاصة بك برمجيًا.

### الأسئلة الشائعة لإضافة كائن SVG في ملف PDF

#### س: هل يمكنني إضافة كائنات SVG متعددة إلى مستند PDF؟

 ج: نعم، يمكنك إضافة كائنات SVG متعددة إلى مستند PDF. ما عليك سوى إنشاء وتكوين المزيد`Aspose.Pdf.Image` مثيلات لكل صورة SVG تريد إضافتها ثم قم بإضافتها إلى خلايا أو فقرات الجدول المطلوبة في مستند PDF.

#### س: كيف يمكنني ضبط حجم وموضع صورة SVG في خلية الجدول؟

 ج: لضبط حجم وموضع صورة SVG في خلية الجدول، يمكنك تعديل`FixWidth` و`FixHeight` خصائص`Aspose.Pdf.Image`مثال. يمكنك أيضًا استخدام خصائص أخرى مثل`HorizontalAlignment` و`VerticalAlignment` من خلية الجدول للتحكم في تحديد المواقع.

#### س: هل من الممكن إضافة نص إلى جانب صورة SVG في نفس خلية الجدول؟

 ج: نعم، من الممكن إضافة نص بجانب صورة SVG في نفس خلية الجدول. يمكنك استخدام ال`cell.Paragraphs.Add(new TextFragment("Your Text Here"));` طريقة لإضافة نص إلى الخلية مع صورة SVG.

#### س: هل يمكنني إضافة ارتباطات تشعبية إلى صورة SVG؟

 ج: نعم، يمكنك إضافة ارتباطات تشعبية إلى صورة SVG باستخدام`Hyperlink` ملكية`Aspose.Pdf.Image` مثال. قم بتعيين عنوان URL للارتباط التشعبي أو الإجراء لجعل الصورة قابلة للنقر عليها.

#### س: هل يتوافق Aspose.PDF for .NET مع .NET Core 3.1 أو الإصدارات الأحدث؟

ج: نعم، Aspose.PDF for .NET متوافق مع .NET Core 3.1 والإصدارات الأحدث. يمكنك استخدامه في كل من تطبيقات .NET Framework و.NET Core.