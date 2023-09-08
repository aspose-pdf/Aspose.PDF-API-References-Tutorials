---
title: إنشاء مستند
linktitle: إنشاء مستند
second_title: Aspose.PDF لمرجع .NET API
description: قم بإنشاء مستند بسهولة باستخدام أزرار الاختيار باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 40
url: /ar/net/programming-with-forms/create-doc/
---
سنوضح لك في هذا البرنامج التعليمي كيفية إنشاء مستند باستخدام أزرار الاختيار باستخدام Aspose.PDF لـ .NET. سنشرح لك كود مصدر C# خطوة بخطوة لإرشادك خلال هذه العملية.

##الخطوة الأولى: التحضير

أولاً، تأكد من استيراد المكتبات اللازمة وتعيين المسار إلى دليل المستندات:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: إنشاء مستند جديد

قم بإنشاء كائن مستند جديد للاحتفاظ بمستند PDF:

```csharp
Document doc = new Document();
```

## الخطوة 3: إضافة صفحة

إضافة صفحة جديدة إلى المستند:

```csharp
Page page = doc.Pages.Add();
```

## الخطوة 4: إضافة حقل زر الاختيار

قم بإنشاء حقل زر اختيار وضبط موضعه وحجمه:

```csharp
RadioButtonField field = new RadioButtonField(page);
field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
field. PartialName = "NewField";
```

## الخطوة 5: إضافة خيارات زر الاختيار

أضف الخيارات المطلوبة إلى حقل زر الاختيار. يمكنك ضبط الإحداثيات وحجم كل خيار حسب الحاجة:

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

### نموذج التعليمات البرمجية المصدر لإنشاء مستند باستخدام Aspose.PDF لـ .NET 
```csharp
try
{
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// إنشاء مستند جديد
	Document doc = new Document();
	Page page = doc.Pages.Add();
	// إضافة حقل زر الاختيار
	RadioButtonField field = new RadioButtonField(page);
	field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
	field.PartialName = "NewField";
	// إضافة خيارات زر الاختيار. يرجى ملاحظة أن هذه الخيارات موجودة
	// لا أفقيا ولا عموديا.
	// يمكنك محاولة تعيين أي إحداثيات (وحتى حجم) لهم.
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

في هذا البرنامج التعليمي، تعلمنا كيفية إنشاء مستند باستخدام أزرار الاختيار باستخدام Aspose.PDF لـ .NET. باتباع هذه الخطوات، يمكنك بسهولة إضافة أزرار الاختيار إلى مستندات PDF الخاصة بك باستخدام Aspose.PDF.

### الأسئلة الشائعة

#### س: هل يمكنني تخصيص مظهر أزرار الاختيار في المستند باستخدام Aspose.PDF لـ .NET؟

ج: نعم، يمكنك تخصيص مظهر أزرار الاختيار في المستند باستخدام Aspose.PDF لـ .NET. يمكنك تعيين خصائص مثل الحجم واللون ونمط الحدود والمزيد لتخصيص مظهر أزرار الاختيار.

#### س: كيف يمكنني إضافة مجموعات أزرار الاختيار مع خيارات حصرية متبادلة؟

ج: لإنشاء خيارات حصرية متبادلة، يمكنك إضافة حقول أزرار اختيار متعددة بنفس الاسم. سيضمن هذا أنه عند تحديد خيار واحد، سيتم إلغاء تحديد الخيارات الأخرى التي تحمل الاسم نفسه تلقائيًا.

#### س: هل من الممكن تعيين خيار محدد افتراضيًا لأزرار الاختيار؟

ج: نعم، يمكنك تعيين خيار محدد افتراضيًا لأزرار الاختيار باستخدام Aspose.PDF لـ .NET. يمكنك استخدام ال`Selected` ملكية`RadioButtonOptionField` كائن لوضع علامة على الخيار على أنه محدد افتراضيًا.

#### س: هل يمكنني إضافة معالجات الأحداث إلى أزرار الاختيار؟

 ج: نعم، يمكنك إضافة معالجات الأحداث إلى أزرار الاختيار باستخدام Aspose.PDF لـ .NET. يمكنك ربط إجراءات JavaScript، مثل`OnValueChanged`، إلى أزرار الاختيار لتنفيذ إجراءات محددة عندما يحدد المستخدم خيارًا.

#### س: كيف يمكنني استرداد الخيار المحدد من مجموعة أزرار الاختيار بعد أن يقوم المستخدم بالتحديد؟

 ج: يمكنك استرداد الخيار المحدد من مجموعة أزرار الاختيار باستخدام Aspose.PDF لـ .NET. بعد أن يقوم المستخدم بالاختيار، يمكنك الوصول إلى`Selected` ملكية`RadioButtonOptionField` كائن للتحقق من الخيار المحدد.