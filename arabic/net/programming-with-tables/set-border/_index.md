---
title: تعيين الحدود
linktitle: تعيين الحدود
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تعيين حد في جدول PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 200
url: /ar/net/programming-with-tables/set-border/
---

في هذا البرنامج التعليمي ، سنوجهك خطوة بخطوة لتعيين حد في جدول مستند PDF باستخدام Aspose.PDF لـ .NET. سنشرح كود المصدر C # المقدم ونوضح لك كيفية تنفيذه.

## الخطوة 1: إنشاء كائن المستند
أولاً ، سننشئ كائن المستند:

```csharp
Document doc = new Document();
```

## الخطوة 2: إضافة صفحة إلى وثيقة PDF
بعد ذلك ، سنضيف صفحة إلى مستند PDF:

```csharp
Page page = doc.Pages.Add();
```

## الخطوة 3: إنشاء كائن BorderInfo
سنقوم الآن بإنشاء كائن BorderInfo لتحديد حدود الجدول:

```csharp
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
```

## الخطوة 4: تحديد الحدود العلوية والسفلية
سنحدد أن الحدين العلوي والسفلي سيكونان مزدوجين:

```csharp
border.Top.IsDoubled = true;
border.Bottom.IsDoubled = true;
```

## الخطوة 5: إنشاء كائن الجدول
لنقم الآن بإنشاء كائن جدول:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## الخطوة 6: تحديد عرض العمود
سنحدد عرض أعمدة الجدول:

```csharp
table. ColumnWidths = "100";
```

## الخطوة 7: إنشاء كائن الصف
سننشئ كائن Row:

```csharp
Aspose.Pdf.Row row = table.Rows.Add();
```

## الخطوة 8: إضافة خلية إلى الصف
بعد ذلك ، سنضيف خلية إلى الصف:

```csharp
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
```

## الخطوة 9: ضبط حدود الخلية
سنقوم بتعريف حدود الخلية (حد مزدوج):

```csharp
cell. Border = border;
```

## الخطوة 10: إضافة الجدول إلى الصفحة
لنقم الآن بإضافة الجدول إلى صفحة المستند:

```csharp
page.Paragraphs.Add(table);
```

## الخطوة 11: احفظ مستند PDF
أخيرًا ، سنحفظ مستند PDF:

```csharp
dataDir = dataDir + "TableBorderTest_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

### مثال على التعليمات البرمجية المصدر لـ Set Border باستخدام Aspose.PDF for .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء كائن المستند
Document doc = new Document();
// أضف صفحة إلى مستند PDF
Page page = doc.Pages.Add();
// إنشاء كائن BorderInfo
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
// حدد أن الحد العلوي سيكون مزدوجًا
border.Top.IsDoubled = true;
// حدد أن الحد السفلي سيكون مزدوجًا
border.Bottom.IsDoubled = true;
// إنشاء كائن جدول
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// حدد معلومات عرض الأعمدة
table.ColumnWidths = "100";
// إنشاء كائن صف
Aspose.Pdf.Row row = table.Rows.Add();
// أضف خلية جدول إلى مجموعة خلايا من الصفوف
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
// تعيين حد كائن الخلية (حد مزدوج)
cell.Border = border;
// أضف جدولاً إلى مجموعة فقرات الصفحة
page.Paragraphs.Add(table);
dataDir = dataDir + "TableBorderTest_out.pdf";
// احفظ مستند PDF
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

## خاتمة
تهنئة ! لقد تعلمت الآن كيفية تعيين حد في جدول مستند PDF باستخدام Aspose.PDF لـ .NET. يوضح لك هذا الدليل التفصيلي كيفية إنشاء مستند وإضافة صفحة وتكوين حدود الجدول وحفظ مستند PDF. الآن يمكنك تطبيق هذه المعرفة على مشاريعك الخاصة.