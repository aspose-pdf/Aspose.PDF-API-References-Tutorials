---
title: إدراج فاصل الصفحة في ملف PDF
linktitle: إدراج فاصل الصفحة في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية إدراج فاصل الصفحة في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 110
url: /ar/net/programming-with-tables/insert-page-break/
---
في هذا البرنامج التعليمي، سنتعلم كيفية إدراج فاصل صفحة في ملف PDF باستخدام Aspose.PDF for .NET. وسنشرح الكود المصدري بلغة C# خطوة بخطوة. وفي نهاية هذا البرنامج التعليمي، ستعرف كيفية إضافة فاصل صفحة بعد عدد معين من الأسطر في جدول في مستند PDF. لنبدأ!

## الخطوة 1: إعداد البيئة
تأكد من تكوين بيئة تطوير C# الخاصة بك باستخدام Aspose.PDF لـ .NET. أضف المرجع إلى المكتبة واستورد المساحات الأساسية اللازمة.

## الخطوة 2: إنشاء المستند والجدول
نقوم بإنشاء مثيل مستند جديد ونضيف صفحة إلى هذا المستند. بعد ذلك، نقوم بإنشاء مثيل جدول لتمثيل الجدول في مستند PDF. نقوم أيضًا بتحديد أنماط الحدود للجدول.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab. ColumnWidths = "100 100";
```

## الخطوة 3: إضافة صفوف إلى الجدول
نستخدم حلقة لإضافة 200 صف إلى المصفوفة. لكل صف، نقوم بإنشاء مثيل من الصف ونضيف خليتين بمحتوى نصي.

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
    
     // عند إضافة 10 أسطر، نقوم بإدراج فاصل صفحة جديد
     if (counter % 10 == 0 && counter != 0)
         row. IsInNewPage = true;
}
```

## الخطوة 4: إضافة الجدول إلى المستند
نضيف الجدول إلى مجموعة الفقرات الخاصة بصفحة المستند.

```csharp
doc.Pages[1].Paragraphs.Add(tab);
```

## الخطوة 5: احفظ المستند
نقوم بحفظ مستند PDF مع إدراج فاصل الصفحة.

```csharp
doc.Save(dataDir + "InsertPageBreak_out.pdf");
```

### مثال على كود المصدر لإدراج فاصل الصفحة باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء مثيل مستند
Document doc = new Document();
// إضافة صفحة إلى مجموعة صفحات ملف PDF
doc.Pages.Add();
// إنشاء مثيل للجدول
Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
// تعيين نمط الحدود للجدول
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// تعيين نمط الحدود الافتراضي للجدول مع لون الحدود باللون الأحمر
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// تحديد عرض عمود الجدول
tab.ColumnWidths = "100 100";
// إنشاء حلقة لإضافة 200 صف للجدول
for (int counter = 0; counter <= 200; counter++)
{
	Aspose.Pdf.Row row = new Aspose.Pdf.Row();
	tab.Rows.Add(row);
	Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
	cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
	row.Cells.Add(cell1); Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
	cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
	row.Cells.Add(cell2);
	// عند إضافة 10 صفوف، قم بعرض صف جديد في صفحة جديدة
	if (counter % 10 == 0 && counter != 0) row.IsInNewPage = true;
}
// إضافة جدول إلى مجموعة فقرات ملف PDF
doc.Pages[1].Paragraphs.Add(tab);

dataDir = dataDir + "InsertPageBreak_out.pdf";
// حفظ مستند PDF
doc.Save(dataDir);

Console.WriteLine("\nPage break inserted successfully.\nFile saved at " + dataDir);
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية إدراج فاصل صفحة في مستند PDF باستخدام Aspose.PDF for .NET. يمكنك استخدام هذا الدليل التفصيلي لإضافة فاصل صفحة بعد عدد معين من الأسطر في جدول في مستند PDF باستخدام C#.

### الأسئلة الشائعة حول إدراج فاصل الصفحة في ملف PDF

#### س: كيف يمكنني تغيير حجم الصفحة للصفحات الجديدة التي تم إنشاؤها بعد تقسيم الصفحة؟

 أ: لتغيير حجم الصفحة للصفحات الجديدة التي تم إنشاؤها بعد فاصل الصفحة، يمكنك ضبط`PageSize` ممتلكات`Page` على سبيل المثال، يمكنك استخدام الكود التالي لتعيين حجم الصفحة إلى A4:

```csharp
// ضبط حجم الصفحة إلى A4
doc.Pages[1].SetPageSize(PageSize.A4);
```

#### س: هل يمكنني التحكم في هوامش الصفحة للصفحات الجديدة بعد تقسيم الصفحة؟

 ج: نعم، يمكنك التحكم في هوامش الصفحات الجديدة بعد فاصل الصفحات. استخدم`Margin` ممتلكات`Page` كائن لتعيين هوامش الصفحة. على سبيل المثال، لتعيين جميع الهوامش إلى 10 نقاط، يمكنك استخدام الكود التالي:

```csharp
// تعيين جميع الهوامش إلى 10 نقاط
doc.Pages[1].Margin = new MarginInfo(10, 10, 10, 10);
```

#### س: هل من الممكن إضافة رؤوس وتذييلات للصفحات الجديدة بعد تقسيم الصفحة؟

 ج: نعم، يمكنك إضافة رؤوس وتذييلات للصفحات الجديدة بعد فاصل الصفحات. استخدم`Page.Header` و`Page.Footer` خصائص لإضافة المحتوى إلى أقسام الرأس والتذييل في الصفحة. على سبيل المثال:

```csharp
// إضافة رأس الصفحة إلى الصفحات الجديدة
doc.Pages[1].Header = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Header content") }
};

// إضافة تذييل إلى الصفحات الجديدة
doc.Pages[1].Footer = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Footer content") }
};
```

#### س: هل يمكنني إدراج فواصل الصفحات في مواقع محددة بخلاف تلك الموجودة بعد عدد معين من الصفوف؟

 ج: نعم، يمكنك إدراج فواصل الصفحات في مواقع محددة بخلاف تلك الموجودة بعد عدد معين من الصفوف. يمكنك ضبط`IsInNewPage` خاصية صف إلى`true` لإجبار الجدول على بدء صفحة جديدة بعد هذا الصف.

#### س: كيف يمكنني تعديل سلوك كسر الصفحة استنادًا إلى ارتفاع المحتوى؟

 أ: يمكنك استخدام`IsBroken` خاصية الجدول لتمكين أو تعطيل تقسيم الصفوف تلقائيًا عبر الصفحات. عند ضبطها على`true`يسمح بتقسيم الصفوف عبر الصفحات استنادًا إلى ارتفاع المحتوى.