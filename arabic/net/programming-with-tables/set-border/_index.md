---
title: تعيين الحدود في PDF على الجدول
linktitle: تعيين الحدود في PDF على الجدول
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تعيين حد في PDF للجدول باستخدام Aspose.PDF for .NET.
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
//حدد أن الحد العلوي سيكون مزدوجًا
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

### التعليمات

#### س: هل يمكنني تعيين أنماط حدود مختلفة (على سبيل المثال ، متقطع أو منقط) للحدود العلوية والسفلية للجدول؟

 ج: نعم ، يمكنك تعيين أنماط حدود مختلفة للحدود العلوية والسفلية للجدول عن طريق تعديل`border.Top.Style` و`border.Bottom.Style`الخصائص في كود المصدر C # المقدم. يتيح لك Aspose.PDF for .NET الاختيار من بين أنماط حدود مختلفة ، بما في ذلك Solid و Dashed و Dotted و Double والمزيد.

#### س: كيف يمكنني ضبط لون حدود الجدول؟

 ج: يمكنك ضبط لون حدود الجدول عن طريق تعديل`border.Color` الخاصية في شفرة المصدر C #. ما عليك سوى توفير اللون المطلوب ، مثل`Aspose.Pdf.Color.Red` أو أي تمثيل لون آخر صالح ، لتخصيص لون الحدود.

#### س: هل من الممكن تطبيق حدود على خلايا فردية داخل الجدول بإعدادات مختلفة (على سبيل المثال ، ألوان مختلفة أو أنماط حدود)؟

 ج: نعم ، يمكنك تطبيق حدود على خلايا فردية داخل الجدول بإعدادات مختلفة عن طريق تكوين ملف`cell.Border` خاصية لكل خلية على حدة. يتيح لك ذلك الحصول على أنماط وألوان حدود خاصة بالخلية بناءً على متطلباتك.

#### س: هل يمكنني إزالة الحد من جوانب معينة من الجدول (على سبيل المثال ، الحدود اليمنى واليسرى)؟

 ج: نعم ، يمكنك إزالة الحد من جوانب معينة من الجدول عن طريق تعديل`border.Left`, `border.Right`, `border.Top` ، و`border.Bottom`الخصائص في شفرة المصدر C #. تعيين هذه الخصائص إلى`null` سيزيل الحد من الجوانب المقابلة للجدول.

#### س: كيف يمكنني ضبط سمك حدود الجدول؟

 ج: يمكنك ضبط سمك حدود الجدول عن طريق تعديل`border.Width` الخاصية في شفرة المصدر C #. ما عليك سوى تعيين عرض الحد المطلوب (بالنقاط) لتحقيق السماكة المطلوبة.