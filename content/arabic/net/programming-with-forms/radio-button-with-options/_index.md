---
title: زر الراديو مع الخيارات
linktitle: زر الراديو مع الخيارات
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: يمكنك بسهولة إضافة زر اختياري يحتوي على خيارات إلى مستند PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 230
url: /ar/net/programming-with-forms/radio-button-with-options/
---

في هذا البرنامج التعليمي، سنوضح لك كيفية إضافة زر اختياري يحتوي على خيارات إلى مستند PDF باستخدام Aspose.PDF for .NET. وسنشرح لك التعليمات البرمجية المصدرية بلغة C# خطوة بخطوة لإرشادك خلال هذه العملية.

## الخطوة 1: التحضير

تأكد من أنك قمت باستيراد المكتبات الضرورية وقمت بتعيين المسار إلى دليل المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: إنشاء كائن مستند

إنشاء كائن مستند لإنشاء مستند PDF جديد:

```csharp
Document doc = new Document();
```

## الخطوة 3: إضافة الصفحة والجدول

أضف صفحة إلى المستند وقم بإنشاء جدول لاحتواء خيارات أزرار الاختيار:

```csharp
Page page = doc.Pages.Add();
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "120 120 120";
page.Paragraphs.Add(table);
```

## الخطوة 4: إنشاء كائن RadioButtonField

إنشاء كائن RadioButtonField لتمثيل زر الاختيار:

```csharp
RadioButtonField rf = new RadioButtonField(page);
rf. PartialName = "radio";
doc.Form.Add(rf, 1);
```

## الخطوة 5: إضافة خيارات أزرار الاختيار

أضف خيارات زر الاختيار إلى كائن RadioButtonField:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField();
RadioButtonOptionField opt2 = new RadioButtonOptionField();
RadioButtonOptionField opt3 = new RadioButtonOptionField();
opt1.OptionName = "Item1";
opt2.OptionName = "Item2";
opt3.OptionName = "Item3";
opt1.Width = 15;
opt1. Height = 15;
opt2.Width = 15;
opt2. Height = 15;
opt3.Width = 15;
opt3. Height = 15;
rf.Add(opt1);
rf.Add(opt2);
rf.Add(opt3);
```

## الخطوة 6: تخصيص خيارات أزرار الاختيار

قم بتخصيص خيارات أزرار الاختيار عن طريق تعيين سمات مثل الحدود ولون النص ونص التسمية التوضيحية:

```csharp
opt1.Border = new Border(opt1);
opt1.Border.Width = 1;
opt1.Border.Style = BorderStyle.Solid;
opt1.Characteristics.Border = System.Drawing.Color.Black;
opt1.DefaultAppearance.TextColor = System.Drawing.Color.Red;
opt1.Caption = new TextFragment("Item1");

// كرر نفس الخطوات لخياري opt2 وopt3

```

## الخطوة 7: أضف خيارات أزرار الاختيار إلى الجدول

أضف خيارات أزرار الاختيار إلى الجدول لعرضها:

```csharp
Cell c1 = table.Rows.Add().Cells.Add();
Cell c2 = table.Rows[table.Rows.Count].Cells.Add();
Cell c3 = table.Rows[table.Rows.Count].Cells.Add();

c1.Paragraphs.Add(opt1);
c2.Paragraphs.Add(opt2);
c3.Paragraphs.Add(opt3);
```

## الخطوة 8: احفظ مستند PDF

احفظ مستند PDF الذي تم إنشاؤه:

```csharp
dataDir = dataDir + "RadioButtonWithOptions_out.pdf";
doc.Save(dataDir);
```

### عينة من كود المصدر لزر الراديو مع الخيارات باستخدام Aspose.PDF لـ .NET 
```csharp
try
{
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	Page page = doc.Pages.Add();
	Aspose.Pdf.Table table = new Aspose.Pdf.Table();
	table.ColumnWidths = "120 120 120";
	page.Paragraphs.Add(table);
	Row r1 = table.Rows.Add();
	Cell c1 = r1.Cells.Add();
	Cell c2 = r1.Cells.Add();
	Cell c3 = r1.Cells.Add();
	RadioButtonField rf = new RadioButtonField(page);
	rf.PartialName = "radio";
	doc.Form.Add(rf, 1);
	RadioButtonOptionField opt1 = new RadioButtonOptionField();
	RadioButtonOptionField opt2 = new RadioButtonOptionField();
	RadioButtonOptionField opt3 = new RadioButtonOptionField();
	opt1.OptionName = "Item1";
	opt2.OptionName = "Item2";
	opt3.OptionName = "Item3";
	opt1.Width = 15;
	opt1.Height = 15;
	opt2.Width = 15;
	opt2.Height = 15;
	opt3.Width = 15;
	opt3.Height = 15;
	rf.Add(opt1);
	rf.Add(opt2);
	rf.Add(opt3);
	opt1.Border = new Border(opt1);
	opt1.Border.Width = 1;
	opt1.Border.Style = BorderStyle.Solid;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	opt1.DefaultAppearance.TextColor = System.Drawing.Color.Red;
	opt1.Caption = new TextFragment("Item1");
	opt2.Border = new Border(opt1);
	opt2.Border.Width = 1;
	opt2.Border.Style = BorderStyle.Solid;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	opt2.DefaultAppearance.TextColor = System.Drawing.Color.Red;
	opt2.Caption = new TextFragment("Item2");
	opt3.Border = new Border(opt1);
	opt3.Border.Width = 1;
	opt3.Border.Style = BorderStyle.Solid;
	opt3.Characteristics.Border = System.Drawing.Color.Black;
	opt3.DefaultAppearance.TextColor = System.Drawing.Color.Red;
	opt3.Caption = new TextFragment("Item3");
	c1.Paragraphs.Add(opt1);
	c2.Paragraphs.Add(opt2);
	c3.Paragraphs.Add(opt3);
	dataDir = dataDir + "RadioButtonWithOptions_out.pdf";
	// حفظ ملف PDF
	doc.Save(dataDir);
	Console.WriteLine("\nRadio button field with three options added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## خاتمة

تهانينا! لقد نجحت في إضافة زر اختياري يحتوي على خيارات إلى مستند PDF باستخدام Aspose.PDF for .NET. يمكنك الآن استخدام هذه الطريقة لإنشاء نماذج تفاعلية في مستندات PDF الخاصة بك.