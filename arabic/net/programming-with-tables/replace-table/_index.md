---
title: استبدال الجدول
linktitle: استبدال الجدول
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استبدال جدول في مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 180
url: /ar/net/programming-with-tables/replace-table/
---

في هذا البرنامج التعليمي ، سنوجهك خطوة بخطوة لاستبدال جدول في مستند PDF باستخدام Aspose.PDF for .NET. سنشرح كود المصدر C # المقدم ونوضح لك كيفية تنفيذه.

## الخطوة 1: تحميل مستند PDF الحالي
أولاً ، تحتاج إلى تحميل مستند PDF الحالي باستخدام الكود التالي:

```csharp
// المسار إلى دليل المستندات
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بتحميل مستند PDF الموجود
Document pdfDocument = new Document(dataDir + @"Table_input.pdf");
```

## الخطوة 2: إنشاء كائن TableAbsorber للعثور على الجداول
بعد ذلك ، سننشئ كائن TableAbsorber للعثور على الجداول في مستند PDF:

```csharp
// قم بإنشاء كائن TableAbsorber للعثور على الجداول
TableAbsorber absorber = new TableAbsorber();
```

## الخطوة الثالثة: قم بزيارة الصفحة الأولى مع جهاز الامتصاص
سنقوم الآن بزيارة الصفحة الأولى من مستند PDF باستخدام أداة الامتصاص:

```csharp
// قم بزيارة الصفحة الأولى مع الممتص
absorb.Visit(pdfDocument.Pages[1]);
```

## الخطوة 4: الحصول على الجدول الأول على الصفحة
لكي نتمكن من استبدال الجدول ، سنحصل على الجدول الأول من الصفحة:

```csharp
// احصل على الجدول الأول على الصفحة
AbsorbedTable table = absorb.TableList[0];
```

## الخطوة الخامسة: إنشاء جدول جديد
سنقوم الآن بإنشاء جدول جديد بالأعمدة والخلايا المطلوبة:

```csharp
Table newTable = new Table();
newTable.ColumnWidths = "100 100 100";
newTable.DefaultCellBorder = new BorderInfo(BorderSide.All, 1F);

Row row = newTable.Rows.Add();
row. Cells. Add("Col 1");
row. Cells. Add("Col 2");
row. Cells. Add("Col 3");
```

## الخطوة 6: استبدال الجدول الحالي بالجدول الجديد
سنقوم الآن باستبدال الجدول الحالي بالجدول الجديد في الصفحة الأولى من المستند:

```csharp
// استبدل الجدول بالجدول الجديد
absorb.Replace(pdfDocument.Pages[1], table, newTable);
```

## الخطوة 7: حفظ المستند
أخيرًا ، نحفظ مستند PDF المعدل:

```csharp
pdfDocument.Save(dataDir + "TableReplaced_out.pdf");
```

### مثال على التعليمات البرمجية المصدر لاستبدال الجدول باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// قم بتحميل مستند PDF موجود
Document pdfDocument = new Document(dataDir + @"Table_input.pdf");

// قم بإنشاء كائن TableAbsorber للعثور على الجداول
TableAbsorber absorber = new TableAbsorber();

// زيارة الصفحة الأولى مع الماص
absorber.Visit(pdfDocument.Pages[1]);

// احصل على الجدول الأول على الصفحة
AbsorbedTable table = absorber.TableList[0];

// إنشاء جدول جديد
Table newTable = new Table();
newTable.ColumnWidths = "100 100 100";
newTable.DefaultCellBorder = new BorderInfo(BorderSide.All, 1F);

Row row = newTable.Rows.Add();
row.Cells.Add("Col 1");
row.Cells.Add("Col 2");
row.Cells.Add("Col 3");

// استبدل الجدول بآخر جديد
absorber.Replace(pdfDocument.Pages[1], table, newTable);

// احفظ المستند
pdfDocument.Save(dataDir + "TableReplaced_out.pdf");
```

## خاتمة
تهنئة ! لقد تعلمت الآن كيفية استبدال جدول في مستند PDF باستخدام Aspose.PDF لـ .NET. يوضح لك هذا الدليل التفصيلي كيفية تحميل المستند والعثور على الجدول الحالي وإنشاء جدول جديد واستبداله. الآن يمكنك تطبيق هذه المعرفة على مشاريعك الخاصة.