---
title: صندوق التحرير
linktitle: صندوق التحرير
second_title: Aspose.PDF لمرجع .NET API
description: قم بإنشاء قائمة مربعات التحرير والسرد بسهولة في مستندات PDF الخاصة بك باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 30
url: /ar/net/programming-with-forms/combo-box/
---
سنوضح لك في هذا البرنامج التعليمي كيفية إنشاء قائمة مربعات التحرير والسرد باستخدام Aspose.PDF لـ .NET. سنشرح لك كود مصدر C# خطوة بخطوة لإرشادك خلال هذه العملية.

## الخطوة 1: التحضير

أولاً، تأكد من استيراد المكتبات اللازمة وتعيين المسار إلى دليل المستندات:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: إنشاء كائن مستند

قم بإنشاء كائن مستند للاحتفاظ بنموذج PDF:

```csharp
Document doc = new Document();
```

## الخطوة 3: إضافة صفحة

إضافة صفحة إلى المستند:

```csharp
doc.Pages.Add();
```

## الخطوة 4: إنشاء كائن ComboBoxField

إنشاء مثيل لكائن ComboBoxField بالأبعاد المطلوبة:

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

أضف كائن ComboBoxField إلى مجموعة حقول نموذج المستند:

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
	// إضافة صفحة إلى كائن المستند
	doc.Pages.Add();
	// إنشاء كائن حقل ComboBox
	ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
	// إضافة خيار إلى ComboBox
	combo.AddOption("Red");
	combo.AddOption("Yellow");
	combo.AddOption("Green");
	combo.AddOption("Blue");
	// إضافة كائن مربع التحرير والسرد إلى مجموعة حقول النموذج لكائن المستند
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

في هذا البرنامج التعليمي، تعلمنا كيفية إنشاء قائمة مربعات التحرير والسرد باستخدام Aspose.PDF لـ .NET. باتباع هذه الخطوات، يمكنك بسهولة إضافة قائمة مربع التحرير والسرد إلى مستندات PDF الخاصة بك باستخدام Aspose.PDF.

### الأسئلة الشائعة

#### س: هل يمكنني تخصيص مظهر قائمة مربعات التحرير والسرد باستخدام Aspose.PDF لـ .NET؟

ج: نعم، يمكنك تخصيص مظهر قائمة مربعات التحرير والسرد باستخدام Aspose.PDF لـ .NET. يمكنك تعيين خصائص مثل حجم الخط واللون ولون الخلفية ونمط الحدود والمزيد لتتناسب مع الشكل والمظهر المطلوبين.

#### س: هل يمكنني تعيين الخيارات المحددة الافتراضية في قائمة مربع التحرير والسرد؟

 ج: نعم، يمكنك تعيين الخيارات المحددة الافتراضية في قائمة مربع التحرير والسرد باستخدام Aspose.PDF لـ .NET. يمكنك استخدام ال`Selected` ملكية`ComboBoxField` كائن لوضع علامة على خيار واحد أو أكثر على أنه محدد افتراضيًا.

#### س: كيف يمكنني استرداد القيمة المحددة من قائمة مربع التحرير والسرد بعد قيام المستخدم بإجراء التحديد؟

 ج: يمكنك استرداد القيمة المحددة من قائمة مربعات التحرير والسرد باستخدام Aspose.PDF لـ .NET. بعد أن يقوم المستخدم بالاختيار، يمكنك الوصول إلى`Value` ملكية`ComboBoxField`كائن للحصول على القيمة المحددة.

#### س: هل من الممكن إضافة معالجات الأحداث أو الإجراءات إلى قائمة مربع التحرير والسرد؟

 ج: نعم، يسمح لك Aspose.PDF for .NET بإضافة معالجات الأحداث أو الإجراءات إلى قائمة مربعات التحرير والسرد. يمكنك ربط إجراءات JavaScript، مثل`OnValueChanged`، إلى قائمة مربع التحرير والسرد لتنفيذ إجراءات محددة عندما يحدد المستخدم خيارًا.

#### س: هل يمكنني إضافة تلميحات أدوات أو أوصاف إلى الخيارات الموجودة في قائمة مربعات التحرير والسرد؟

 ج: نعم، يمكنك إضافة تلميحات أدوات أو أوصاف إلى الخيارات الموجودة في قائمة مربعات التحرير والسرد باستخدام Aspose.PDF لـ .NET. يمكنك ضبط`AlternateName` خاصية كل خيار لتوفير تلميح أداة أو وصف سيتم عرضه عندما يقوم المستخدم بالتمرير فوق الخيار.