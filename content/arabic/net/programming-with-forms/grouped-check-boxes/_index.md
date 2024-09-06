---
title: مربعات الاختيار المجمعة في مستند PDF
linktitle: مربعات الاختيار المجمعة في مستند PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: يمكنك بسهولة إنشاء مربعات اختيار مجمعة في مستند PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 170
url: /ar/net/programming-with-forms/grouped-check-boxes/
---
في هذا البرنامج التعليمي، سنوضح لك كيفية إنشاء مربعات اختيار مجمعة في مستند PDF باستخدام Aspose.PDF لـ .NET. وسنشرح لك التعليمات البرمجية المصدرية بلغة C# خطوة بخطوة لإرشادك خلال هذه العملية.

## الخطوة 1: التحضير

تأكد من أنك قمت باستيراد المكتبات الضرورية وقمت بتعيين المسار إلى دليل المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: إنشاء كائن مستند

إنشاء كائن مستند:

```csharp
Document pdfDocument = new Document();
```

## الخطوة 3: إضافة صفحة إلى مستند PDF

إضافة صفحة إلى مستند PDF:

```csharp
Page page = pdfDocument.Pages.Add();
```

## الخطوة 4: إنشاء كائن RadioButtonField

إنشاء كائن RadioButtonField مع رقم الصفحة كحجة:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## الخطوة 5: إضافة خيارات أزرار الاختيار

أضف خيارات أزرار الراديو باستخدام كائن RadioButtonOptionField وحدد موضعها باستخدام كائن Rectangle:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
opt1.OptionName = "Test1";
opt2.OptionName = "Test2";
radio.Add(opt1);
radio.Add(opt2);
```

## الخطوة 6: تخصيص خيارات أزرار الاختيار

تخصيص خيارات أزرار الاختيار عن طريق ضبط نمطها وحدودها ومظهرها:

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

## الخطوة 7: إضافة أزرار الاختيار إلى النموذج

أضف أزرار الاختيار إلى كائن نموذج المستند:

```csharp
pdfDocument.Form.Add(radio);
```

## الخطوة 8: احفظ المستند

حفظ مستند PDF:

```csharp
dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
pdfDocument.Save(dataDir);
```

### عينة من كود المصدر لمربعات الاختيار المجمعة باستخدام Aspose.PDF لـ .NET 
```csharp
try
{
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// إنشاء كائن مستند
	Document pdfDocument = new Document();
	// إضافة صفحة إلى ملف PDF
	Page page = pdfDocument.Pages.Add();
	// إنشاء كائن RadioButtonField مع رقم الصفحة كحجة
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
	// إضافة زر اختياري إلى كائن النموذج الخاص بكائن المستند
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
	// حفظ مستند PDF
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

أ: تشير مربعات الاختيار المجمعة في مستند PDF إلى مجموعة من خيارات أزرار الاختيار المجمعة معًا. تتيح أزرار الاختيار للمستخدمين تحديد خيار واحد فقط من مجموعة من الخيارات المتبادلة الحصرية. عند تحديد زر اختيار واحد، يتم إلغاء تحديد الأزرار الأخرى في نفس المجموعة تلقائيًا. يكون سلوك التجميع هذا مفيدًا عندما تريد تقديم خيارات متعددة للمستخدمين ولكن تقييد اختيارهم بخيار واحد فقط.

#### س: هل يمكنني تخصيص مظهر مربعات الاختيار المجمعة في Aspose.PDF لـ .NET؟

ج: نعم، يمكنك تخصيص مظهر مربعات الاختيار المجمعة في Aspose.PDF لـ .NET. توفر واجهة برمجة التطبيقات خيارات متنوعة لتعيين نمط وحدود ومظهر خيارات أزرار الاختيار. يمكنك تحديد موضع كل خيار، والاختيار بين أنماط مربعات مختلفة (على سبيل المثال، مربع، دائرة، صليب)، وضبط خصائص الحدود لتحقيق التمثيل المرئي المطلوب.

#### س: كيف يمكنني إضافة مربعات اختيار مجمعة إلى صفحة معينة في مستند PDF؟

أ: لإضافة مربعات اختيار مجمعة إلى صفحة معينة في مستند PDF، تحتاج إلى إنشاء مثيل`RadioButtonField` الكائن الذي يحتوي على رقم الصفحة المطلوب كحجة. ثم قم بإنشاء`RadioButtonOptionField` الكائنات التي تمثل كل خيار من خيارات زر الاختيار وتحديد موضعها باستخدام`Rectangle` الكائن. وأخيرًا، أضف هذه الخيارات إلى`RadioButtonField` وتخصيص مظهرها حسب الحاجة قبل الإضافة`RadioButtonField` إلى نموذج الوثيقة.

#### س: هل يمكنني إضافة مجموعات متعددة من مربعات الاختيار إلى مستند PDF واحد؟

 ج: نعم، يمكنك إضافة مجموعات متعددة من مربعات الاختيار إلى مستند PDF واحد. يجب أن يكون لكل مجموعة مربع اختيار فريد.`RadioButtonField` الكائن، و`RadioButtonOptionField` يجب أن تتشارك الكائنات الموجودة داخل كل مجموعة في نفس الصفحة والأسماء الفريدة لخياراتها. وهذا يضمن أن أزرار الاختيار داخل كل مجموعة تعمل بشكل صحيح، وأن الاختيارات متبادلة الاستبعاد.

#### س: هل يتم دعم مربعات الاختيار المجمعة في جميع برامج عرض PDF والتطبيقات؟

ج: نعم، يتم دعم مربعات الاختيار المجمعة في جميع برامج عرض ملفات PDF والتطبيقات المتوافقة مع المعايير. تحدد مواصفات PDF أزرار الاختيار وسلوكيات تجميعها، مما يجعلها معروفة عالميًا بتنسيق PDF. ومع ذلك، من الضروري اختبار الوظيفة في برامج عرض ملفات PDF المختلفة لضمان السلوك المتسق عبر منصات مختلفة.