---
title: قم بإنشاء مستند
linktitle: قم بإنشاء مستند
second_title: Aspose.PDF لمرجع .NET API
description: أنشئ مستندًا بسهولة باستخدام أزرار الاختيار باستخدام Aspose.PDF for .NET.
type: docs
weight: 40
url: /ar/net/programming-with-forms/create-doc/
---

في هذا البرنامج التعليمي ، سنوضح لك كيفية إنشاء مستند باستخدام أزرار الاختيار باستخدام Aspose.PDF for .NET. سنشرح كود المصدر C # خطوة بخطوة لإرشادك خلال هذه العملية.

## الخطوة 1: التحضير

أولاً ، تأكد من استيراد المكتبات الضرورية وتعيين المسار إلى دليل المستندات:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بإنشاء مستند جديد

قم بإنشاء كائن مستند جديد للاحتفاظ بمستند PDF:

```csharp
Document doc = new Document();
```

## الخطوة 3: أضف صفحة

أضف صفحة جديدة إلى المستند:

```csharp
Page page = doc.Pages.Add();
```

## الخطوة 4: أضف حقل زر اختيار

قم بإنشاء حقل زر اختيار وتعيين موضعه وحجمه:

```csharp
RadioButtonField field = new RadioButtonField(page);
field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
field. PartialName = "NewField";
```

## الخطوة 5: إضافة خيارات زر الاختيار

أضف الخيارات المطلوبة إلى حقل زر الاختيار. يمكنك ضبط إحداثيات وحجم كل خيار حسب الحاجة:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField();
opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
opt1.OptionName = "Item1";
opt1.Border = new Border(opt1);
opt1.Border.Width = 1;
opt1.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt2 = new RadioButtonOptionField();
opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
opt2.OptionName = "Item2";
opt2.Border = new Border(opt2);
opt2.Border.Width = 1;
opt2.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt3 = new RadioButtonOptionField();
opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
opt3.OptionName = "Item3";
opt3.Border = new Border(opt3);
opt3.Border.Width = 1;
opt3.Characteristics.Border = System.Drawing.Color.Black;

field. Add(opt1);
field. Add(opt2);
field. Add(opt3);
```

## الخطوة 6: أضف حقل زر الاختيار إلى النموذج

أضف حقل زر الاختيار إلى مجموعة حقول نموذج المستند:

```csharp
doc.Form.Add(field);
```

## الخطوة 7: احفظ المستند

احفظ مستند PDF:

```csharp
dataDir = dataDir + "CreateDoc_out.pdf";
doc.Save(dataDir);
```

### نموذج التعليمات البرمجية المصدر لـ Create Doc باستخدام Aspose.PDF for .NET 
```csharp
try
{
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// قم بإنشاء مستند جديد
	Document doc = new Document();
	Page page = doc.Pages.Add();
	// أضف حقل زر الاختيار
	RadioButtonField field = new RadioButtonField(page);
	field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
	field.PartialName = "NewField";
	// إضافة خيارات زر الاختيار. يرجى ملاحظة أن هذه الخيارات موجودة
	// لا أفقيا ولا رأسيا.
	// يمكنك محاولة تعيين أي إحداثيات (وحتى حجم) لها.
	RadioButtonOptionField opt1 = new RadioButtonOptionField();
	opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
	opt1.OptionName = "Item1";
	opt1.Border = new Border(opt1);
	opt1.Border.Width = 1;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt2 = new RadioButtonOptionField();
	opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
	opt2.OptionName = "Item2";
	opt2.Border = new Border(opt2);
	opt2.Border.Width = 1;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt3 = new RadioButtonOptionField();
	opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
	opt3.OptionName = "Item3";
	opt3.Border = new Border(opt3);
	opt3.Border.Width = 1;
	opt3.Characteristics.Border = System.Drawing.Color.Black;
	field.Add(opt1);
	field.Add(opt2);
	field.Add(opt3);
	doc.Form.Add(field);
	dataDir = dataDir + "CreateDoc_out.pdf";
	// احفظ مستند PDF
	doc.Save(dataDir);
	Console.WriteLine("\nNew doc with 3 items radio button created successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية إنشاء مستند باستخدام أزرار الاختيار باستخدام Aspose.PDF لـ .NET. باتباع هذه الخطوات ، يمكنك بسهولة إضافة أزرار اختيار إلى مستندات PDF الخاصة بك باستخدام Aspose.PDF.