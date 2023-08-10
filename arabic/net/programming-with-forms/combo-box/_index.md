---
title: صندوق التحرير
linktitle: صندوق التحرير
second_title: Aspose.PDF لمرجع .NET API
description: أنشئ بسهولة قائمة مربع تحرير وسرد في مستندات PDF الخاصة بك باستخدام Aspose.PDF for .NET.
type: docs
weight: 30
url: /ar/net/programming-with-forms/combo-box/
---
في هذا البرنامج التعليمي ، سنوضح لك كيفية إنشاء قائمة مربع تحرير وسرد باستخدام Aspose.PDF for .NET. سنشرح كود المصدر C # خطوة بخطوة لإرشادك خلال هذه العملية.

## الخطوة الأولى: التحضير

أولاً ، تأكد من استيراد المكتبات الضرورية وتعيين المسار إلى دليل المستندات:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: إنشاء كائن مستند

قم بإنشاء كائن مستند للاحتفاظ بنموذج PDF:

```csharp
Document doc = new Document();
```

## الخطوة 3: أضف صفحة

أضف صفحة إلى المستند:

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

## الخطوة 6: أضف قائمة مربع التحرير والسرد إلى النموذج

أضف كائن ComboBoxField إلى مجموعة Document Form Fields:

```csharp
doc.Form.Add(combo);
```

## الخطوة 7: احفظ المستند

احفظ مستند PDF:

```csharp
dataDir = dataDir + "ComboBox_out.pdf";
doc.Save(dataDir);
```

### نموذج التعليمات البرمجية المصدر لـ Combo Box باستخدام Aspose.PDF لـ .NET 
```csharp
try
{
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// إنشاء كائن المستند
	Document doc = new Document();
	// أضف صفحة إلى كائن المستند
	doc.Pages.Add();
	// إنشاء كائن حقل ComboBox
	ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
	// إضافة خيار إلى ComboBox
	combo.AddOption("Red");
	combo.AddOption("Yellow");
	combo.AddOption("Green");
	combo.AddOption("Blue");
	// إضافة كائن مربع تحرير وسرد لتكوين مجموعة حقول لكائن المستند
	doc.Form.Add(combo);
	dataDir = dataDir + "ComboBox_out.pdf";
	// احفظ مستند PDF
	doc.Save(dataDir);
	Console.WriteLine("\nCombobox field added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية إنشاء قائمة مربع تحرير وسرد باستخدام Aspose.PDF لـ .NET. باتباع هذه الخطوات ، يمكنك بسهولة إضافة قائمة مربع تحرير وسرد إلى مستندات PDF الخاصة بك باستخدام Aspose.PDF.

### التعليمات

#### س: هل يمكنني تخصيص مظهر قائمة مربع التحرير والسرد باستخدام Aspose.PDF for .NET؟

ج: نعم ، يمكنك تخصيص مظهر قائمة مربع التحرير والسرد باستخدام Aspose.PDF for .NET. يمكنك تعيين خصائص مثل حجم الخط واللون ولون الخلفية ونمط الحدود والمزيد لمطابقة الشكل والمظهر الذي تريده.

#### س: هل يمكنني تعيين الخيارات الافتراضية المحددة في قائمة مربع التحرير والسرد؟

 ج: نعم ، يمكنك تعيين الخيارات الافتراضية المحددة في قائمة مربع التحرير والسرد باستخدام Aspose.PDF for .NET. يمكنك استخدام ال`Selected` ممتلكات`ComboBoxField` لوضع علامة على خيار واحد أو أكثر على أنه محدد بشكل افتراضي.

#### س: كيف يمكنني استرداد القيمة المحددة من قائمة مربع التحرير والسرد بعد قيام المستخدم بالتحديد؟

 ج: يمكنك استرداد القيمة المحددة من قائمة مربع التحرير والسرد باستخدام Aspose.PDF for .NET. بعد قيام المستخدم بالاختيار ، يمكنك الوصول إلى ملف`Value` ممتلكات`ComboBoxField`كائن للحصول على القيمة المحددة.

#### س: هل من الممكن إضافة معالجات الأحداث أو الإجراءات إلى قائمة مربع التحرير والسرد؟

 ج: نعم ، يسمح لك Aspose.PDF for .NET بإضافة معالجات الأحداث أو الإجراءات إلى قائمة مربع التحرير والسرد. يمكنك ربط إجراءات JavaScript ، مثل`OnValueChanged`، إلى قائمة مربع التحرير والسرد لتنفيذ إجراءات محددة عندما يحدد المستخدم خيارًا.

#### س: هل يمكنني إضافة تلميحات الأدوات أو الأوصاف إلى الخيارات في قائمة مربع التحرير والسرد؟

 ج: نعم ، يمكنك إضافة تلميحات الأدوات أو الأوصاف إلى الخيارات في قائمة مربع التحرير والسرد باستخدام Aspose.PDF لـ .NET. يمكنك ضبط ملف`AlternateName` خاصية كل خيار لتوفير تلميح أداة أو وصف سيتم عرضه عندما يقوم المستخدم بتمرير الماوس فوق الخيار.