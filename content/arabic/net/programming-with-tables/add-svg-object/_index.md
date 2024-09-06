---
title: إضافة كائن SVG إلى ملف PDF
linktitle: إضافة كائن SVG إلى ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: يمكنك بسهولة إضافة كائنات SVG في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 30
url: /ar/net/programming-with-tables/add-svg-object/
---
في هذا البرنامج التعليمي، سنتعلم كيفية إضافة كائن SVG إلى ملف PDF باستخدام مكتبة Aspose.PDF for .NET. SVG (رسومات متجهية قابلة للتطوير) هو تنسيق شائع للرسومات المتجهة التي يمكن توسيع نطاقها بسهولة دون فقدان الجودة. باستخدام Aspose.PDF، يمكنك إضافة كائنات SVG إلى مستندات PDF الخاصة بك برمجيًا.

## متطلبات

قبل أن نبدأ، تأكد من أن لديك ما يلي:

- تم تثبيت Visual Studio
- تم تثبيت مكتبة Aspose.PDF لـ .NET

## الخطوة 1: إعداد البيئة

أولاً، دعنا ننشئ البيئة عن طريق إنشاء مشروع C# جديد في Visual Studio. افتح Visual Studio واتبع الخطوات التالية:

1. انقر فوق "ملف" > "جديد" > "مشروع" لإنشاء مشروع جديد.
2. حدد قالب "تطبيق وحدة التحكم (.NET Framework)" أو "تطبيق وحدة التحكم (.NET Core)"، وفقًا لإعدادك.
3. قم باختيار الاسم والموقع المناسبين لمشروعك، ثم اضغط على "إنشاء".

## الخطوة 2: إنشاء كائنات المستندات والصور

في هذه الخطوة، سنقوم بإنشاء الكائنات اللازمة لمستند PDF وصورة SVG. افتح ملف C# الخاص بمشروعك وأضف الكود التالي:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// كائن المستند الفوري
Document doc = new Document();
// إنشاء مثيل للصورة
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
```

## الخطوة 3: تعيين خصائص الصورة

بعد ذلك، سنقوم بتعيين خصائص صورة SVG الخاصة بنا. سنحدد نوع الملف على أنه SVG، والمسار إلى ملف SVG، وأبعاد الصورة. أضف الكود التالي بعد الخطوة السابقة:

```csharp
// تعيين نوع الصورة كـ SVG
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// المسار لملف المصدر
img.File = dataDir + "SVGToPDF.svg";
// تعيين عرض لنموذج الصورة
img. FixWidth = 50;
// تعيين الارتفاع لنموذج الصورة
img.FixHeight = 50;
```

## الخطوة 4: إنشاء الجدول وتكوينه

الآن، لنقم بإنشاء كائن جدول وتعيين عرض الأعمدة. سننشئ جدولًا به عمودين، كل منهما بعرض 100 وحدة. أضف الكود التالي:

```csharp
// إنشاء جدول مثيل
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// تعيين عرض خلايا الجدول
table. ColumnWidths = "100 100";
```

## الخطوة 5: إضافة خلايا إلى الجدول

في هذه الخطوة سنقوم بإضافة صف وخلايا إلى الجدول، حيث يمثل كل صف صفًا أفقيًا في الجدول، ويتم إضافة خلايا إلى الصفوف، أضف الكود التالي:

```csharp
//إنشاء كائن صف وإضافته إلى مثيل الجدول
Aspose.Pdf.Row row = table.Rows.Add();
// إنشاء كائن خلية وإضافته إلى مثيل الصف
Aspose.Pdf.Cell cell = row.Cells.Add();
```

## الخطوة 6: إضافة نص وصورة إلى الخلايا

بعد ذلك، دعنا نضيف النص وصورة SVG إلى خلايا الجدول. سنضيف النص "الخلية الأولى" إلى الخلية الأولى وصورة SVG إلى الخلية الثانية. أضف الكود التالي:

```csharp
// إضافة جزء نصي إلى مجموعة فقرات كائن الخلية
cell.Paragraphs.Add(new TextFragment("First cell"));
// إضافة خلية أخرى إلى كائن الصف
cell = row. Cells. Add();
// إضافة صورة SVG إلى مجموعة فقرات من مثيلات الخلايا المضافة حديثًا
cell.Paragraphs.Add(img);
```

## الخطوة 7: إنشاء صفحة وإضافتها إلى المستند

الآن، لنقم بإنشاء كائن صفحة وإضافته إلى المستند. سيتم إضافة الجدول إلى مجموعة الفقرات الخاصة بالصفحة. أضف الكود التالي:

```csharp
// إنشاء كائن الصفحة وإضافته إلى مجموعة الصفحات الخاصة بمثيل المستند
Page page = doc.Pages.Add();
// إضافة جدول إلى مجموعة فقرات كائن الصفحة
page.Paragraphs.Add(table);
```

## الخطوة 8: احفظ ملف PDF

أخيرًا، سنحفظ ملف PDF في المكان المحدد. أضف الكود التالي:

```csharp
dataDir = dataDir + "AddSVGObject_out.pdf";
// حفظ ملف PDF
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);
```

### مثال على كود المصدر لإضافة كائن SVG باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء كائن مستند
Document doc = new Document();
// إنشاء مثيل للصورة
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// تعيين نوع الصورة كـ SVG
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// المسار لملف المصدر
img.File = dataDir + "SVGToPDF.svg";
// تعيين عرض لنموذج الصورة
img.FixWidth = 50;
// تعيين الارتفاع لنموذج الصورة
img.FixHeight = 50;
// إنشاء مثيل للجدول
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// تعيين عرض خلايا الجدول
table.ColumnWidths = "100 100";
//إنشاء كائن صف وإضافته إلى مثيل الجدول
Aspose.Pdf.Row row = table.Rows.Add();
// إنشاء كائن خلية وإضافته إلى مثيل الصف
Aspose.Pdf.Cell cell = row.Cells.Add();
// إضافة جزء نصي إلى مجموعة فقرات كائن الخلية
cell.Paragraphs.Add(new TextFragment("First cell"));
// إضافة خلية أخرى إلى كائن الصف
cell = row.Cells.Add();
// إضافة صورة SVG إلى مجموعة فقرات من مثيلات الخلايا المضافة حديثًا
cell.Paragraphs.Add(img);
// إنشاء كائن الصفحة وإضافته إلى مجموعة الصفحات الخاصة بمثيل المستند
Page page = doc.Pages.Add();
// إضافة جدول إلى مجموعة فقرات كائن الصفحة
page.Paragraphs.Add(table);

dataDir = dataDir + "AddSVGObject_out.pdf";
// حفظ ملف PDF
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);            
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية إضافة كائن SVG إلى ملف PDF باستخدام مكتبة Aspose.PDF for .NET. لقد قمنا بتغطية العملية خطوة بخطوة لإنشاء مستند، وإعداد البيئة، وإضافة صورة SVG إلى خلية جدول، وحفظ ملف PDF. يمكنك الآن دمج كائنات SVG في مستندات PDF الخاصة بك برمجيًا.

### الأسئلة الشائعة حول إضافة كائن SVG إلى ملف PDF

#### س: هل يمكنني إضافة كائنات SVG متعددة إلى مستند PDF؟

 ج: نعم، يمكنك إضافة كائنات SVG متعددة إلى مستند PDF. ما عليك سوى إنشاء وتكوين كائنات SVG إضافية`Aspose.Pdf.Image` قم بإنشاء مثيلات لكل صورة SVG تريد إضافتها ثم قم بإضافتها إلى خلايا الجدول أو الفقرات المطلوبة في مستند PDF.

#### س: كيف يمكنني تعديل حجم وموضع صورة SVG في خلية الجدول؟

 أ: لتعديل حجم وموضع صورة SVG في خلية الجدول، يمكنك تعديل`FixWidth` و`FixHeight` خصائص`Aspose.Pdf.Image`على سبيل المثال. يمكنك أيضًا استخدام خصائص أخرى مثل`HorizontalAlignment` و`VerticalAlignment` من خلية الجدول للتحكم في الموضع.

#### س: هل من الممكن إضافة نص إلى جانب صورة SVG في نفس خلية الجدول؟

 ج: نعم، من الممكن إضافة نص إلى جانب صورة SVG في نفس خلية الجدول. يمكنك استخدام`cell.Paragraphs.Add(new TextFragment("Your Text Here"));` طريقة لإضافة نص إلى الخلية مع صورة SVG.

#### س: هل يمكنني إضافة ارتباطات تشعبية إلى صورة SVG؟

 ج: نعم، يمكنك إضافة ارتباطات تشعبية إلى صورة SVG باستخدام`Hyperlink` ممتلكات`Aspose.Pdf.Image` على سبيل المثال. قم بتعيين عنوان URL للرابط التشعبي أو الإجراء لجعل الصورة قابلة للنقر.

#### س: هل Aspose.PDF for .NET متوافق مع .NET Core 3.1 أو الإصدارات الأحدث؟

ج: نعم، برنامج Aspose.PDF for .NET متوافق مع .NET Core 3.1 والإصدارات الأحدث. ويمكنك استخدامه في تطبيقات .NET Framework و.NET Core.