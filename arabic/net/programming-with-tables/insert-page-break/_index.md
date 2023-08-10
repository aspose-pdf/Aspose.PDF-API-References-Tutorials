---
title: إدراج فاصل صفحة في ملف PDF
linktitle: إدراج فاصل صفحة في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إدراج فاصل صفحات في ملف PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 110
url: /ar/net/programming-with-tables/insert-page-break/
---
في هذا البرنامج التعليمي ، سوف نتعلم كيفية إدراج فاصل صفحات في ملف PDF باستخدام Aspose.PDF for .NET. سنشرح الكود المصدري في C # خطوة بخطوة. في نهاية هذا البرنامج التعليمي ، ستعرف كيفية إضافة فاصل صفحة بعد عدد معين من الأسطر في جدول مستند PDF. لنبدأ!

## الخطوة الأولى: تهيئة البيئة
تأكد من تكوين بيئة التطوير C # الخاصة بك باستخدام Aspose.PDF for .NET. أضف المرجع إلى المكتبة واستورد مساحات الأسماء الضرورية.

## الخطوة 2: إنشاء المستند والجدول
نقوم بإنشاء مثيل مستند جديد وإضافة صفحة إلى هذا المستند. بعد ذلك ، نقوم بإنشاء مثيل Table لتمثيل جدولنا في مستند PDF. نحدد أيضًا أنماط الحدود للجدول.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab. ColumnWidths = "100 100";
```

## الخطوة 3: أضف صفوفًا إلى الجدول
نستخدم حلقة لإضافة 200 صف إلى المصفوفة. لكل صف ، نقوم بإنشاء مثيل للصف وإضافة خليتين بمحتوى نصي.

```csharp
for (int counter = 0; counter <= 200; counter++)
{
     Aspose.Pdf.Row row = new Aspose.Pdf.Row();
     tab. Rows. Add(row);
    
     Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
     cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
     row. Cells. Add(cell1);
    
     Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
     cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
     row. Cells. Add(cell2);
    
     // عند إضافة 10 أسطر ، نقوم بإدراج فاصل صفحة جديد
     if (counter % 10 == 0 && counter != 0)
         row. IsInNewPage = true;
}
```

## الخطوة 4: إضافة الجدول إلى المستند
نضيف الجدول إلى مجموعة الفقرات في صفحة الوثيقة.

```csharp
doc.Pages[1].Paragraphs.Add(tab);
```

## الخطوة 5: احفظ المستند
نقوم بحفظ مستند PDF مع إدراج فاصل الصفحة.

```csharp
doc.Save(dataDir + "InsertPageBreak_out.pdf");
```

### مثال على التعليمات البرمجية المصدر لإدراج فاصل صفحة باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// مثيل المستند
Document doc = new Document();
// أضف صفحة إلى مجموعة صفحات من ملف PDF
doc.Pages.Add();
// إنشاء مثيل الجدول
Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
// تعيين نمط الحدود للجدول
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// عيّن نمط الحدود الافتراضي للجدول بلون الحد باللون الأحمر
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// حدد جدول عمود Widht
tab.ColumnWidths = "100 100";
// قم بإنشاء حلقة لإضافة 200 صف للجدول
for (int counter = 0; counter <= 200; counter++)
{
	Aspose.Pdf.Row row = new Aspose.Pdf.Row();
	tab.Rows.Add(row);
	Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
	cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
	row.Cells.Add(cell1); Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
	cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
	row.Cells.Add(cell2);
	// عند إضافة 10 صفوف ، قم بعرض صف جديد في صفحة جديدة
	if (counter % 10 == 0 && counter != 0) row.IsInNewPage = true;
}
// أضف جدولاً إلى مجموعة فقرات ملف PDF
doc.Pages[1].Paragraphs.Add(tab);

dataDir = dataDir + "InsertPageBreak_out.pdf";
// احفظ مستند PDF
doc.Save(dataDir);

Console.WriteLine("\nPage break inserted successfully.\nFile saved at " + dataDir);
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية إدراج فاصل صفحات في مستند PDF باستخدام Aspose.PDF لـ .NET. يمكنك استخدام هذا الدليل المفصل خطوة بخطوة لإضافة فاصل صفحة بعد عدد معين من الأسطر في جدول في مستند PDF باستخدام C #.

### الأسئلة الشائعة حول إدراج فاصل صفحة في ملف PDF

#### س: كيف يمكنني تغيير حجم الصفحة للصفحات الجديدة التي تم إنشاؤها بعد فاصل الصفحة؟

 ج: لتغيير حجم الصفحة للصفحات الجديدة التي تم إنشاؤها بعد فاصل الصفحة ، يمكنك تعيين ملف`PageSize` ممتلكات`Page` هدف. على سبيل المثال ، يمكنك استخدام الكود التالي لتعيين حجم الصفحة على A4:

```csharp
// اضبط حجم الصفحة على A4
doc.Pages[1].SetPageSize(PageSize.A4);
```

#### س: هل يمكنني التحكم في هوامش الصفحات للصفحات الجديدة بعد فاصل الصفحة؟

 ج: نعم ، يمكنك التحكم في هوامش الصفحة للصفحات الجديدة بعد فاصل الصفحة. استخدم ال`Margin` ممتلكات`Page` لتعيين هوامش الصفحة. على سبيل المثال ، لتعيين جميع الهوامش على 10 نقاط ، يمكنك استخدام الكود التالي:

```csharp
// اضبط جميع الهوامش على 10 نقاط
doc.Pages[1].Margin = new MarginInfo(10, 10, 10, 10);
```

#### س: هل يمكن إضافة رؤوس وتذييلات للصفحات الجديدة بعد فاصل الصفحة؟

 ج: نعم ، يمكنك إضافة رؤوس وتذييلات إلى الصفحات الجديدة بعد فاصل الصفحة. استخدم ال`Page.Header` و`Page.Footer` خصائص لإضافة محتوى إلى مقاطع الرأس والتذييل للصفحة. على سبيل المثال:

```csharp
// إضافة رأس للصفحات الجديدة
doc.Pages[1].Header = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Header content") }
};

// إضافة تذييل للصفحات الجديدة
doc.Pages[1].Footer = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Footer content") }
};
```

#### س: هل يمكنني إدراج فواصل الصفحات في مواقع محددة بخلاف عدد معين من الصفوف؟

 ج: نعم ، يمكنك إدراج فواصل الصفحات في مواقع محددة بخلاف ما بعد عدد معين من الصفوف. يمكنك ضبط ملف`IsInNewPage` خاصية صف ل`true` لإجبار الجدول على بدء صفحة جديدة بعد هذا الصف.

#### س: كيف يمكنني ضبط سلوك فاصل الصفحة بناءً على ارتفاع المحتوى؟

ج: يمكنك استخدام ملف`IsBroken` الخاص بالجدول لتمكين فصل الصفوف تلقائيًا عبر الصفحات أو تعطيله. عند الضبط على`true`، فهو يسمح للصفوف بالتقسيم عبر الصفحات بناءً على ارتفاع المحتوى.