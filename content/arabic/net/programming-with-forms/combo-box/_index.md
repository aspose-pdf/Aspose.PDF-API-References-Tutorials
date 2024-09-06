---
title: صندوق المجموعة
linktitle: صندوق المجموعة
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: يمكنك بسهولة إنشاء قائمة مربعات مجمعة في مستندات PDF الخاصة بك باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 30
url: /ar/net/programming-with-forms/combo-box/
---
في هذا البرنامج التعليمي، سنوضح لك كيفية إنشاء قائمة مربعات منسوخة باستخدام Aspose.PDF لـ .NET. وسنشرح لك التعليمات البرمجية المصدرية للغة C# خطوة بخطوة لإرشادك خلال هذه العملية.

## الخطوة 1: التحضير

أولاً، تأكد من استيراد المكتبات الضرورية وتعيين المسار إلى دليل المستندات:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: إنشاء كائن مستند

إنشاء كائن مستند لحمل نموذج PDF:

```csharp
Document doc = new Document();
```

## الخطوة 3: إضافة صفحة

إضافة صفحة إلى المستند:

```csharp
doc.Pages.Add();
```

## الخطوة 4: إنشاء كائن ComboBoxField

إنشاء كائن ComboBoxField بالأبعاد المطلوبة:

```csharp
ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
```

## الخطوة 5: إضافة خيارات إلى القائمة المنسدلة

أضف الخيارات المطلوبة إلى القائمة المنسدلة:

```csharp
combo.AddOption("Red");
combo.AddOption("Yellow");
combo.AddOption("Green");
combo.AddOption("Blue");
```

## الخطوة 6: أضف قائمة المربعات المنسدلة إلى النموذج

أضف كائن ComboBoxField إلى مجموعة حقول نموذج المستند:

```csharp
doc.Form.Add(combo);
```

## الخطوة 7: احفظ المستند

حفظ مستند PDF:

```csharp
dataDir = dataDir + "ComboBox_out.pdf";
doc.Save(dataDir);
```

### عينة من كود المصدر لـ Combo Box باستخدام Aspose.PDF لـ .NET 
```csharp
try
{
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// إنشاء كائن المستند
	Document doc = new Document();
	// إضافة صفحة إلى كائن المستند
	doc.Pages.Add();
	// إنشاء كائن حقل ComboBox
	ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
	// إضافة خيار إلى ComboBox
	combo.AddOption("Red");
	combo.AddOption("Yellow");
	combo.AddOption("Green");
	combo.AddOption("Blue");
	// إضافة كائن مربع التحرير والسرد إلى مجموعة حقول النموذج الخاصة بكائن المستند
	doc.Form.Add(combo);
	dataDir = dataDir + "ComboBox_out.pdf";
	// حفظ مستند PDF
	doc.Save(dataDir);
	Console.WriteLine("\nCombobox field added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية إنشاء قائمة مربعات منسوخة باستخدام Aspose.PDF لـ .NET. باتباع هذه الخطوات، يمكنك بسهولة إضافة قائمة مربعات منسوخة إلى مستندات PDF الخاصة بك باستخدام Aspose.PDF.

### الأسئلة الشائعة

#### س: هل يمكنني تخصيص مظهر قائمة المربعات المنسدلة باستخدام Aspose.PDF لـ .NET؟

ج: نعم، يمكنك تخصيص مظهر قائمة المربعات المنسدلة باستخدام Aspose.PDF لـ .NET. يمكنك تعيين خصائص مثل حجم الخط واللون ولون الخلفية ونمط الحدود والمزيد لتتناسب مع المظهر والشعور المطلوبين.

#### س: هل يمكنني تعيين الخيارات المحددة الافتراضية في قائمة المربع المنسدل؟

 ج: نعم، يمكنك تعيين الخيارات المحددة الافتراضية في قائمة المربعات المنسدلة باستخدام Aspose.PDF لـ .NET. يمكنك استخدام`Selected` ممتلكات`ComboBoxField` كائن لوضع علامة على خيار واحد أو أكثر كمحدد افتراضيًا.

#### س: كيف يمكنني استرجاع القيمة المحددة من قائمة المربعات المنسدلة بعد أن يقوم المستخدم بإجراء اختيار؟

 ج: يمكنك استرداد القيمة المحددة من قائمة المربعات المنسدلة باستخدام Aspose.PDF لـ .NET. بعد أن يقوم المستخدم باختيار، يمكنك الوصول إلى`Value` ممتلكات`ComboBoxField`كائن للحصول على القيمة المحددة.

#### س: هل من الممكن إضافة معالجات الأحداث أو الإجراءات إلى قائمة المربع المنسدل؟

 ج: نعم، يسمح لك Aspose.PDF for .NET بإضافة معالجات الأحداث أو الإجراءات إلى قائمة المربعات المنسدلة. يمكنك ربط إجراءات JavaScript، مثل`OnValueChanged`، إلى قائمة المربعات المنسدلة لأداء إجراءات محددة عندما يختار المستخدم خيارًا.

#### س: هل يمكنني إضافة تلميحات الأدوات أو الأوصاف إلى الخيارات الموجودة في قائمة المربع المنسدل؟

 ج: نعم، يمكنك إضافة تلميحات الأدوات أو الأوصاف إلى الخيارات في قائمة المربعات المنسدلة باستخدام Aspose.PDF لـ .NET. يمكنك ضبط`AlternateName` خاصية كل خيار لتوفير تلميح أو وصف سيتم عرضه عندما يحوم المستخدم فوق الخيار.