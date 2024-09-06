---
title: تعيين الحدود في PDF إلى الجدول
linktitle: تعيين الحدود في PDF إلى الجدول
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية تعيين حدود في جدول PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 200
url: /ar/net/programming-with-tables/set-border/
---
في هذا البرنامج التعليمي، سنرشدك خطوة بخطوة إلى كيفية تعيين حدود في جدول في مستند PDF باستخدام Aspose.PDF لـ .NET. وسنشرح الكود المصدري C# المقدم ونوضح لك كيفية تنفيذه.

## الخطوة 1: إنشاء كائن المستند
أولاً، سنقوم بإنشاء كائن مستند:

```csharp
Document doc = new Document();
```

## الخطوة 2: إضافة صفحة إلى مستند PDF
بعد ذلك، سنضيف صفحة إلى مستند PDF:

```csharp
Page page = doc.Pages.Add();
```

## الخطوة 3: إنشاء كائن BorderInfo
سنقوم الآن بإنشاء كائن BorderInfo لتحديد حدود الجدول:

```csharp
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
```

## الخطوة 4: تحديد الحدود العلوية والسفلية
سنحدد أن الحدود العلوية والسفلية ستكون مزدوجة:

```csharp
border.Top.IsDoubled = true;
border.Bottom.IsDoubled = true;
```

## الخطوة 5: إنشاء كائن الجدول
الآن دعونا ننشئ كائن جدول:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## الخطوة 6: تحديد عرض الأعمدة
سنقوم بتحديد عرض أعمدة الجدول:

```csharp
table. ColumnWidths = "100";
```

## الخطوة 7: إنشاء كائن الصف
سوف نقوم بإنشاء كائن الصف:

```csharp
Aspose.Pdf.Row row = table.Rows.Add();
```

## الخطوة 8: إضافة خلية إلى الصف
بعد ذلك، سنضيف خلية إلى الصف:

```csharp
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
```

## الخطوة 9: ضبط حدود الخلية
سنقوم بتحديد حدود الخلية (الحدود المزدوجة):

```csharp
cell. Border = border;
```

## الخطوة 10: إضافة الجدول إلى الصفحة
الآن دعونا نضيف الجدول إلى صفحة المستند:

```csharp
page.Paragraphs.Add(table);
```

## الخطوة 11: حفظ مستند PDF
وأخيرًا، سنقوم بحفظ مستند PDF:

```csharp
dataDir = dataDir + "TableBorderTest_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

### مثال على كود المصدر لتعيين الحدود باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء كائن مستند
Document doc = new Document();
// إضافة صفحة إلى مستند PDF
Page page = doc.Pages.Add();
// إنشاء كائن BorderInfo
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
//حدد أن الحد العلوي سيكون مزدوجًا
border.Top.IsDoubled = true;
// حدد أن الحد السفلي سيكون مزدوجًا
border.Bottom.IsDoubled = true;
// إنشاء كائن جدول
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// تحديد معلومات عرض الأعمدة
table.ColumnWidths = "100";
// إنشاء كائن الصف
Aspose.Pdf.Row row = table.Rows.Add();
// إضافة خلية جدول إلى مجموعة خلايا الصف
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
// تعيين الحدود لكائن الخلية (حدود مزدوجة)
cell.Border = border;
// إضافة جدول إلى مجموعة فقرات الصفحة
page.Paragraphs.Add(table);
dataDir = dataDir + "TableBorderTest_out.pdf";
// حفظ مستند PDF
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

## خاتمة
تهانينا! لقد تعلمت الآن كيفية تعيين حدود في جدول في مستند PDF باستخدام Aspose.PDF لـ .NET. يوضح لك هذا الدليل خطوة بخطوة كيفية إنشاء مستند وإضافة صفحة وتكوين حدود الجدول وحفظ مستند PDF. يمكنك الآن تطبيق هذه المعرفة على مشاريعك الخاصة.

### الأسئلة الشائعة

#### س: هل يمكنني تعيين أنماط حدود مختلفة (على سبيل المثال، متقطعة أو منقطة) للحدود العلوية والسفلية للجدول؟

 ج: نعم، يمكنك تعيين أنماط حدود مختلفة للحدود العلوية والسفلية للجدول عن طريق تعديل`border.Top.Style` و`border.Bottom.Style`يتيح لك Aspose.PDF for .NET الاختيار من بين أنماط حدود مختلفة، بما في ذلك Solid وDashed وDotted وDouble والمزيد.

#### س: كيف يمكنني تعيين لون حدود الجدول؟

 أ: يمكنك ضبط لون حدود الجدول عن طريق تعديل`border.Color` الخاصية في كود المصدر C#. ما عليك سوى توفير اللون المطلوب، مثل`Aspose.Pdf.Color.Red` أو أي تمثيل لوني صالح آخر، لتخصيص لون الحدود.

#### س: هل من الممكن تطبيق حدود على خلايا فردية داخل الجدول بإعدادات مختلفة (على سبيل المثال، ألوان مختلفة أو أنماط حدود)؟

 ج: نعم، يمكنك تطبيق حدود على خلايا فردية داخل الجدول بإعدادات مختلفة عن طريق تكوين`cell.Border` خاصية لكل خلية على حدة. يتيح لك هذا الحصول على أنماط وألوان حدود خاصة بكل خلية بناءً على متطلباتك.

#### س: هل يمكنني إزالة الحدود من جوانب معينة من الجدول (على سبيل المثال، الحدود اليسرى واليمنى)؟

 ج: نعم، يمكنك إزالة الحدود من جوانب معينة من الجدول عن طريق تعديل`border.Left`, `border.Right`, `border.Top` ، و`border.Bottom`الخصائص في الكود المصدري للغة C#. ضبط هذه الخصائص على`null` سيتم إزالة الحدود من الجوانب المقابلة للجدول.

#### س: كيف يمكنني تعديل سمك حدود الجدول؟

 أ: يمكنك تعديل سمك حدود الجدول عن طريق تعديل`border.Width` الخاصية في الكود المصدر C#. ما عليك سوى تعيين عرض الحدود المطلوب (بالنقاط) لتحقيق السمك المطلوب.