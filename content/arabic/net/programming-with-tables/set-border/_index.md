---
title: تعيين الحدود في PDF إلى الجدول
linktitle: تعيين الحدود في PDF إلى الجدول
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تعيين حدود في ملف PDF لجدول باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 200
url: /ar/net/programming-with-tables/set-border/
---
في هذا البرنامج التعليمي، سنرشدك خطوة بخطوة لتعيين حد في جدول مستند PDF باستخدام Aspose.PDF لـ .NET. سنشرح لك كود مصدر C# المقدم ونوضح لك كيفية تنفيذه.

## الخطوة 1: إنشاء مثيل لكائن المستند
أولاً، سنقوم بإنشاء كائن Document:

```csharp
Document doc = new Document();
```

## الخطوة 2: إضافة صفحة إلى مستند PDF
بعد ذلك، سنقوم بإضافة صفحة إلى مستند PDF:

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

## الخطوة 5: إنشاء مثيل لكائن الجدول
لنقم الآن بإنشاء كائن جدول:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## الخطوة 6: تحديد عرض الأعمدة
سنحدد عرض أعمدة الجدول:

```csharp
table. ColumnWidths = "100";
```

## الخطوة 7: إنشاء كائن الصف
سنقوم بإنشاء كائن صف:

```csharp
Aspose.Pdf.Row row = table.Rows.Add();
```

## الخطوة 8: إضافة خلية إلى الصف
بعد ذلك، سنقوم بإضافة خلية إلى الصف:

```csharp
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
```

## الخطوة 9: تعيين حدود الخلية
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
أخيرًا، سنقوم بحفظ مستند PDF:

```csharp
dataDir = dataDir + "TableBorderTest_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

### مثال على التعليمات البرمجية المصدر لـ Set Border باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء مثيل لكائن المستند
Document doc = new Document();
// إضافة صفحة إلى وثيقة PDF
Page page = doc.Pages.Add();
// إنشاء كائن BorderInfo
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
//حدد أن الحد العلوي سيكون مزدوجًا
border.Top.IsDoubled = true;
// حدد أن الحد السفلي سيكون مزدوجًا
border.Bottom.IsDoubled = true;
// إنشاء كائن الجدول
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// تحديد معلومات عرض الأعمدة
table.ColumnWidths = "100";
// إنشاء كائن صف
Aspose.Pdf.Row row = table.Rows.Add();
// إضافة خلية جدول إلى مجموعة خلايا الصف
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
// تعيين الحدود لكائن الخلية (حد مزدوج)
cell.Border = border;
// إضافة جدول إلى مجموعة الفقرات من الصفحة
page.Paragraphs.Add(table);
dataDir = dataDir + "TableBorderTest_out.pdf";
// احفظ مستند PDF
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

## خاتمة
تهنئة ! لقد تعلمت الآن كيفية تعيين حدود في جدول مستند PDF باستخدام Aspose.PDF لـ .NET. يوضح لك هذا الدليل خطوة بخطوة كيفية إنشاء مستند وإضافة صفحة وتكوين حدود الجدول وحفظ مستند PDF. الآن يمكنك تطبيق هذه المعرفة على مشاريعك الخاصة.

### الأسئلة الشائعة

#### س: هل يمكنني تعيين أنماط حدود مختلفة (على سبيل المثال، متقطعة أو منقط) للحدود العلوية والسفلية للجدول؟

 ج: نعم، يمكنك تعيين أنماط حدود مختلفة للحدود العلوية والسفلية للجدول عن طريق تعديل`border.Top.Style` و`border.Bottom.Style`الخصائص في كود مصدر C# المقدم. يتيح لك Aspose.PDF for .NET الاختيار من بين أنماط الحدود المتنوعة، بما في ذلك Solid وDashed وDotted وDouble والمزيد.

#### س: كيف يمكنني ضبط لون حدود الجدول؟

 ج: يمكنك ضبط لون حدود الجدول عن طريق تعديل`border.Color` الخاصية في كود مصدر C#. ببساطة قم بتوفير اللون المطلوب، مثل`Aspose.Pdf.Color.Red` أو أي تمثيل ألوان صالح آخر، لتخصيص لون الحدود.

#### س: هل من الممكن تطبيق الحدود على الخلايا الفردية داخل الجدول باستخدام إعدادات مختلفة (على سبيل المثال، ألوان مختلفة أو أنماط حدود)؟

 ج: نعم، يمكنك تطبيق الحدود على الخلايا الفردية داخل الجدول باستخدام إعدادات مختلفة عن طريق تكوين`cell.Border` خاصية لكل خلية على حدة. يتيح لك ذلك الحصول على أنماط وألوان حدود خاصة بالخلية بناءً على متطلباتك.

#### س: هل يمكنني إزالة الحدود من جوانب معينة من الجدول (على سبيل المثال، الحدود اليسرى واليمنى)؟

 ج: نعم، يمكنك إزالة الحدود من جوانب معينة من الجدول عن طريق تعديل`border.Left`, `border.Right`, `border.Top` ، و`border.Bottom`الخصائص في كود مصدر C#. ضبط هذه الخصائص على`null` سيؤدي إلى إزالة الحدود من الجوانب المقابلة للجدول.

#### س: كيف يمكنني ضبط سمك حدود الطاولة؟

 ج: يمكنك ضبط سمك حدود الجدول عن طريق تعديل`border.Width` الخاصية في كود مصدر C#. ما عليك سوى ضبط عرض الحدود المطلوب (بالنقاط) لتحقيق السُمك المطلوب.