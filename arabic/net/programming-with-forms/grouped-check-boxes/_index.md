---
title: مربعات الاختيار المجمعة في مستند PDF
linktitle: مربعات الاختيار المجمعة في مستند PDF
second_title: Aspose.PDF لمرجع .NET API
description: أنشئ مربعات اختيار مجمعة بسهولة في مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 170
url: /ar/net/programming-with-forms/grouped-check-boxes/
---
في هذا البرنامج التعليمي ، سنوضح لك كيفية إنشاء مربعات اختيار مجمعة في مستند PDF باستخدام Aspose.PDF لـ .NET. سنشرح كود المصدر C # خطوة بخطوة لإرشادك خلال هذه العملية.

## الخطوة الأولى: التحضير

تأكد من أنك قمت باستيراد المكتبات الضرورية وقم بتعيين المسار إلى دليل المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: إنشاء كائن مستند

إنشاء كائن مستند:

```csharp
Document pdfDocument = new Document();
```

## الخطوة 3: أضف صفحة إلى مستند PDF

أضف صفحة إلى مستند PDF:

```csharp
Page page = pdfDocument.Pages.Add();
```

## الخطوة 4: إنشاء كائن RadioButtonField

إنشاء كائن RadioButtonField برقم الصفحة كوسيطة:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## الخطوة 5: إضافة خيارات زر الاختيار

أضف خيارات زر الاختيار باستخدام كائن RadioButtonOptionField وحدد موضعها باستخدام الكائن Rectangle:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
opt1.OptionName = "Test1";
opt2.OptionName = "Test2";
radio.Add(opt1);
radio.Add(opt2);
```

## الخطوة 6: تخصيص خيارات زر الاختيار

تخصيص خيارات زر الاختيار عن طريق تعيين النمط والحدود والمظهر:

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

### نموذج التعليمات البرمجية المصدر لخانات الاختيار المجمعة باستخدام Aspose.PDF لـ .NET 
```csharp
try
{
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// إنشاء كائن المستند
	Document pdfDocument = new Document();
	// أضف صفحة إلى ملف PDF
	Page page = pdfDocument.Pages.Add();
	// إنشاء كائن RadioButtonField مع رقم الصفحة كوسيطة
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
	// إضافة زر اختيار لتكوين كائن من كائن المستند
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

في هذا البرنامج التعليمي ، تعلمنا كيفية إنشاء مربعات اختيار مجمعة في مستند PDF باستخدام Aspose.PDF لـ .NET. باتباع هذه الخطوات ، يمكنك بسهولة إضافة خيارات زر اختيار مخصصة وتجميعها في مستندات PDF الخاصة بك باستخدام Aspose.PDF.

### التعليمات

#### س: ما هي مربعات الاختيار المجمعة في مستند PDF؟

ج: تشير مربعات الاختيار المجمعة في مستند PDF إلى مجموعة من خيارات أزرار الاختيار التي تم تجميعها معًا. تسمح أزرار الاختيار للمستخدمين بتحديد خيار واحد فقط من مجموعة الخيارات الحصرية المتبادلة. عند تحديد زر اختيار واحد ، يتم إلغاء تحديد الأزرار الأخرى في نفس المجموعة تلقائيًا. يكون سلوك التجميع هذا مفيدًا عندما تريد أن تقدم للمستخدمين خيارات متعددة ولكن تقصر اختيارهم على خيار واحد فقط.

#### س: هل يمكنني تخصيص مظهر مربعات الاختيار المجمعة في Aspose.PDF for .NET؟

ج: نعم ، يمكنك تخصيص مظهر مربعات الاختيار المجمعة في Aspose.PDF for .NET. توفر واجهة برمجة التطبيقات (API) خيارات متنوعة لتعيين نمط خيارات زر التحديد وحدودها ومظهرها. يمكنك تحديد موضع كل خيار ، والاختيار بين أنماط مربعات مختلفة (على سبيل المثال ، مربع ، دائرة ، تقاطع) ، وضبط خصائص الحدود لتحقيق التمثيل المرئي المطلوب.

#### س: كيف أقوم بإضافة مربعات اختيار مجمعة إلى صفحة معينة في مستند PDF؟

ج: لإضافة مربعات اختيار مجمعة إلى صفحة معينة في مستند PDF ، تحتاج إلى إنشاء مثيل`RadioButtonField` مع رقم الصفحة المطلوب كوسيطة. ثم قم بإنشاء`RadioButtonOptionField` كائنات تمثل كل خيار زر خيار وتحدد موقعها باستخدام`Rectangle` هدف. أخيرًا ، أضف هذه الخيارات إلى ملف`RadioButtonField` وتخصيص مظهرهم حسب الحاجة قبل إضافة`RadioButtonField` إلى نموذج المستند.

#### س: هل يمكنني إضافة مجموعات متعددة من مربعات الاختيار إلى مستند PDF واحد؟

 ج: نعم ، يمكنك إضافة مجموعات متعددة من مربعات الاختيار إلى مستند PDF واحد. يجب أن يكون لكل مجموعة ملف`RadioButtonField` الكائن و`RadioButtonOptionField` يجب أن تشترك الكائنات داخل كل مجموعة في نفس الصفحة والأسماء الفريدة لخياراتها. هذا يضمن أن أزرار الاختيار داخل كل مجموعة تعمل بشكل صحيح ، وأن التحديدات يستبعد بعضها بعضًا.

#### س: هل مربعات الاختيار المجمعة مدعومة في جميع برامج عرض PDF والتطبيقات؟

ج: نعم ، يتم دعم مربعات الاختيار المجمعة في جميع برامج عرض وتطبيقات PDF المتوافقة مع المعايير. تحدد مواصفات PDF أزرار الاختيار وسلوك التجميع ، مما يجعلها معروفة عالميًا بتنسيق PDF. ومع ذلك ، من الضروري اختبار الوظائف في برامج عرض PDF المختلفة لضمان سلوك متسق عبر الأنظمة الأساسية المختلفة.