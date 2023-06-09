---
title: أضف صورة في خلية جدول
linktitle: أضف صورة في خلية جدول
second_title: Aspose.PDF لمرجع .NET API
description: أضف صورة في خلية جدول باستخدام Aspose.PDF for .NET دليل تفصيلي للمعالجة الدقيقة للصور في مستندات PDF.
type: docs
weight: 10
url: /ar/net/programming-with-tables/add-image-in-a-table-cell/
---

في هذا البرنامج التعليمي ، سنوجهك خلال عملية إضافة صورة إلى خلية جدول باستخدام Aspose.PDF لـ .NET. يوضح كود المصدر C # المقدم كيفية تحقيق هذه الوظيفة. باتباع الخطوات الموضحة أدناه ، ستتمكن من دمج الصور في خلايا الجدول بشكل فعال.

قبل الغوص في الكود ، تأكد من تثبيت Aspose.PDF لمكتبة .NET والمشار إليها في مشروعك.

## الخطوة 1: إعداد المستند

 للبدء ، نحتاج إلى إنشاء مثيل جديد من`Document`فئة من مساحة الاسم Aspose.Pdf. يمثل هذا الفصل وثيقة PDF.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء كائن مستند
Document pdfDocument = new Document();
```

## الخطوة 2: إنشاء صفحة

بعد ذلك ، نحتاج إلى إضافة صفحة إلى مستند PDF. تعمل الصفحة كحاوية للجدول والعناصر الأخرى.

```csharp
// قم بإنشاء صفحة في مستند pdf
Page sec1 = pdfDocument.Pages.Add();
```

## الخطوة 3: إضافة جدول

 في هذه الخطوة ، سننشئ جدولًا عن طريق إنشاء مثيل`Table` فئة من مساحة الاسم Aspose.Pdf.

```csharp
// إنشاء كائن جدول
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## الخطوة 4: تعيين حدود الخلية الافتراضية

 لضمان الاتساق ، يمكننا تعيين حد الخلية الافتراضي باستخدام`DefaultCellBorder` ممتلكات الجدول`BorderInfo` هدف.

```csharp
// تعيين حد الخلية الافتراضي باستخدام كائن BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## الخطوة 5: ضبط عرض العمود

 لتحديد عرض كل عمود في الجدول ، يمكننا ضبط`ColumnWidths` ملكية. حدد العروض كسلسلة ذات قيم مفصولة بمسافات.

```csharp
// اضبط مع عرض أعمدة الجدول
tab1.ColumnWidths = "100 100 120";
```

## الخطوة 6: إضافة صورة إلى خلية جدول

الآن يأتي الجزء المثير ، إضافة صورة إلى خلية الجدول. للقيام بذلك ، سوف نتبع الخطوات الفرعية التالية:

## الخطوة 6.1: إنشاء كائن صورة

 قم بإنشاء مثيل لـ`Image` فئة من مساحة الاسم Aspose.Pdf. تعيين`File` خاصية مسار ملف الصورة الذي تريد إضافته.

```csharp
// قم بإنشاء كائن صورة
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose.jpg";
```

## الخطوة 6.2: إنشاء صف وخلايا

لإضافة الصورة إلى الجدول ، نحتاج أولاً إلى إنشاء صف والخلايا اللازمة.

```csharp
// قم بإنشاء صف في الجدول
Aspose.Pdf.Row row1 = tab1.Rows.Add();

// أضف خلية نصية إلى الصف
row1.Cells.Add("Sample text in cell");

// أضف الخلية التي تحتوي على الصورة
Aspose.Pdf.Cell cell2 = row1.Cells.Add();
```

## الخطوة 6.3: إضافة الصورة إلى خلية الجدول

أخيرًا ، يمكننا إضافة الصورة إلى خلية الجدول عن طريق إضافتها كفقرة داخل الخلية.

```csharp
// أضف الصورة إلى خلية الجدول
cell2.Paragraphs.Add(img);
```

## الخطوة 6.4: إضافة خلايا إضافية

بعد إضافة خلية الصورة ، يمكننا إضافة المزيد من الخلايا إلى الصف إذا لزم الأمر.

```csharp
// أضف خلية أخرى إلى الصف
row1.Cells.Add("Previous cell with image");

// اضبط المحاذاة الرأسية للخلية الثالثة
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
```

## الخطوة 7: حفظ المستند

 أخيرًا ، يمكننا حفظ المستند المعدل في مكان محدد باستخدام امتداد`Save` طريقة.

```csharp
// احفظ المستند
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

تهانينا! لقد تعلمت بنجاح كيفية إضافة صورة إلى خلية جدول باستخدام Aspose.PDF for .NET. لا تتردد في استكشاف المزيد من خيارات التخصيص ودمج هذه الوظيفة في مشاريعك.

### مثال على كود المصدر لإضافة صورة في خلية جدول باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء كائن مستند
Document pdfDocument = new Document();
// قم بإنشاء صفحة في مستند pdf
Page sec1 = pdfDocument.Pages.Add();
// إنشاء كائن جدول
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
//أضف الجدول في مجموعة فقرات الصفحة المطلوبة
sec1.Paragraphs.Add(tab1);
// تعيين حد الخلية الافتراضي باستخدام كائن BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// اضبط مع عرض أعمدة الجدول
tab1.ColumnWidths = "100 100 120";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose.jpg";
// أنشئ صفوفًا في الجدول ثم أنشئ خلايا في الصفوف
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Sample text in cell");
// أضف الخلية التي تحتوي على الصورة
Aspose.Pdf.Cell cell2 = row1.Cells.Add();
// أضف الصورة إلى خلية الجدول
cell2.Paragraphs.Add(img);
row1.Cells.Add("Previous cell with image");
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
// احفظ المستند
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

## خاتمة

في هذا البرنامج التعليمي ، قمنا بتغطية دليل خطوة بخطوة حول كيفية إضافة صورة إلى خلية جدول باستخدام Aspose.PDF for .NET. بدأنا بإعداد المستند وإنشاء صفحة وإضافة جدول. بعد ذلك ، قمنا بتعيين حد الخلية الافتراضي وعرض العمود. أوضحنا كيفية إضافة صورة إلى خلية جدول وضبط المحاذاة الرأسية للخلية. أخيرًا ، قمنا بحفظ المستند المعدل. باتباع هذه الخطوات ، يمكنك تحسين مستندات PDF بالصور الموجودة في خلايا الجدول بكفاءة.