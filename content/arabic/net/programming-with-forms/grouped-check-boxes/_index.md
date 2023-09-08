---
title: مربعات الاختيار المجمعة في وثيقة PDF
linktitle: مربعات الاختيار المجمعة في وثيقة PDF
second_title: Aspose.PDF لمرجع .NET API
description: قم بإنشاء مربعات اختيار مجمعة بسهولة في مستند PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 170
url: /ar/net/programming-with-forms/grouped-check-boxes/
---
سنوضح لك في هذا البرنامج التعليمي كيفية إنشاء مربعات اختيار مجمعة في مستند PDF باستخدام Aspose.PDF لـ .NET. سنشرح لك كود مصدر C# خطوة بخطوة لإرشادك خلال هذه العملية.

## الخطوة 1: التحضير

تأكد من استيراد المكتبات الضرورية وتعيين المسار إلى دليل المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: إنشاء مثيل لكائن المستند

إنشاء مثيل لكائن المستند:

```csharp
Document pdfDocument = new Document();
```

## الخطوة 3: إضافة صفحة إلى مستند PDF

إضافة صفحة إلى مستند PDF:

```csharp
Page page = pdfDocument.Pages.Add();
```

## الخطوة 4: إنشاء مثيل لكائن RadioButtonField

إنشاء مثيل لكائن RadioButtonField باستخدام رقم الصفحة كوسيطة:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## الخطوة 5: إضافة خيارات زر الاختيار

أضف خيارات زر الاختيار باستخدام كائن RadioButtonOptionField وحدد موضعها باستخدام كائن Rectangle:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
opt1.OptionName = "Test1";
opt2.OptionName = "Test2";
radio.Add(opt1);
radio.Add(opt2);
```

## الخطوة 6: تخصيص خيارات زر الاختيار

قم بتخصيص خيارات زر الاختيار من خلال تحديد نمطها وحدودها ومظهرها:

```csharp
opt1.Style = BoxStyle.Square;
opt2.Style = BoxStyle.Square;
opt1.Border = new Border(opt1);
opt1.Border.Style = BorderStyle.Solid;
opt1.Border.Width = 1;
opt2.Border = new Border(opt2);
opt2.Border.Width = 1;
opt2.Border.Style = BorderStyle.Solid;
```

## الخطوة 7: أضف أزرار الاختيار إلى النموذج

أضف أزرار الاختيار إلى كائن نموذج المستند:

```csharp
pdfDocument.Form.Add(radio);
```

## الخطوة 8: احفظ المستند

احفظ مستند PDF:

```csharp
dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
pdfDocument.Save(dataDir);
```

### نموذج التعليمات البرمجية المصدر لمربعات الاختيار المجمعة باستخدام Aspose.PDF لـ .NET 
```csharp
try
{
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// إنشاء مثيل لكائن المستند
	Document pdfDocument = new Document();
	// إضافة صفحة إلى ملف PDF
	Page page = pdfDocument.Pages.Add();
	// إنشاء كائن RadioButtonField باستخدام رقم الصفحة كوسيطة
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// أضف خيار زر الاختيار الأول وحدد أيضًا أصله باستخدام كائن المستطيل
	RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
	RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
	opt1.OptionName = "Test1";
	opt2.OptionName = "Test2";
	radio.Add(opt1);
	radio.Add(opt2);
	opt1.Style = BoxStyle.Square;
	opt2.Style = BoxStyle.Square;
	opt1.Style = BoxStyle.Cross;
	opt2.Style = BoxStyle.Cross;
	opt1.Border = new Border(opt1);
	opt1.Border.Style = BorderStyle.Solid;
	opt1.Border.Width = 1;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	opt2.Border = new Border(opt2);
	opt2.Border.Width = 1;
	opt2.Border.Style = BorderStyle.Solid;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	// أضف زر الاختيار لتكوين كائن كائن المستند
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
	// احفظ مستند PDF
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nGrouped checkboxes added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية إنشاء مربعات اختيار مجمعة في مستند PDF باستخدام Aspose.PDF لـ .NET. باتباع هذه الخطوات، يمكنك بسهولة إضافة خيارات أزرار الاختيار المخصصة وتجميعها في مستندات PDF الخاصة بك باستخدام Aspose.PDF.

### الأسئلة الشائعة

#### س: ما هي مربعات الاختيار المجمعة في مستند PDF؟

ج: تشير مربعات الاختيار المجمعة في مستند PDF إلى مجموعة من خيارات أزرار الاختيار المجمعة معًا. تسمح أزرار الاختيار للمستخدمين بتحديد خيار واحد فقط من مجموعة من الاختيارات المتبادلة. عند تحديد زر اختيار واحد، يتم إلغاء تحديد الأزرار الأخرى الموجودة في نفس المجموعة تلقائيًا. يكون سلوك التجميع هذا مفيدًا عندما تريد تقديم خيارات متعددة للمستخدمين ولكن تحديدهم يقتصر على خيار واحد فقط.

#### س: هل يمكنني تخصيص مظهر مربعات الاختيار المجمعة في Aspose.PDF لـ .NET؟

ج: نعم، يمكنك تخصيص مظهر مربعات الاختيار المجمعة في Aspose.PDF لـ .NET. توفر واجهة برمجة التطبيقات (API) خيارات متنوعة لتعيين نمط خيارات زر الاختيار وحدودها ومظهرها. يمكنك تحديد موضع كل خيار، والاختيار من بين أنماط المربعات المختلفة (على سبيل المثال، مربع، أو دائرة، أو متقاطع)، وضبط خصائص الحدود لتحقيق التمثيل المرئي المطلوب.

#### س: كيف يمكنني إضافة مربعات اختيار مجمعة إلى صفحة معينة في مستند PDF؟

ج: لإضافة مربعات اختيار مجمعة إلى صفحة محددة في مستند PDF، تحتاج إلى إنشاء مثيل`RadioButtonField` كائن برقم الصفحة المطلوبة كوسيطة. ثم قم بإنشاء`RadioButtonOptionField` كائنات تمثل كل خيار من خيارات أزرار الاختيار وحدد موضعها باستخدام الزر`Rectangle` هدف. وأخيرا، قم بإضافة هذه الخيارات إلى`RadioButtonField` وتخصيص مظهرها حسب الحاجة قبل إضافة الملف`RadioButtonField` إلى نموذج الوثيقة.

#### س: هل يمكنني إضافة مجموعات متعددة من مربعات الاختيار إلى مستند PDF واحد؟

 ج: نعم، يمكنك إضافة مجموعات متعددة من مربعات الاختيار إلى مستند PDF واحد. يجب أن يكون لكل مجموعة فريدة من نوعها`RadioButtonField` الكائن، و`RadioButtonOptionField` يجب أن تشترك الكائنات الموجودة داخل كل مجموعة في نفس الصفحة والأسماء الفريدة لخياراتها. وهذا يضمن أن أزرار الاختيار الموجودة داخل كل مجموعة تعمل بشكل صحيح، وأن التحديدات حصرية بشكل متبادل.

#### س: هل مربعات الاختيار المجمعة مدعومة في جميع برامج عرض وتطبيقات PDF؟

ج: نعم، يتم دعم مربعات الاختيار المجمعة في جميع تطبيقات وعارضات PDF المتوافقة مع المعايير. تحدد مواصفات PDF أزرار الاختيار وسلوك التجميع الخاص بها، مما يجعلها معترف بها عالميًا بتنسيق PDF. ومع ذلك، من الضروري اختبار الوظيفة في برامج عرض PDF مختلفة لضمان السلوك المتسق عبر الأنظمة الأساسية المختلفة.