---
title: احصل على إحداثيات حقل نموذج PDF
linktitle: احصل على إحداثيات حقل نموذج PDF
second_title: Aspose.PDF لمرجع .NET API
description: احصل بسهولة على إحداثيات حقول نموذج PDF في مستندات PDF الخاصة بك باستخدام Aspose.PDF for .NET.
type: docs
weight: 120
url: /ar/net/programming-with-forms/get-coordinates/
---
في هذا البرنامج التعليمي ، سنوضح لك كيفية الحصول على إحداثيات حقل نموذج PDF باستخدام Aspose.PDF for .NET. سنشرح كود المصدر C # خطوة بخطوة لإرشادك خلال هذه العملية.

## الخطوة الأولى: التحضير

تأكد من أنك قمت باستيراد المكتبات الضرورية وقم بتعيين المسار إلى دليل المستندات:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل مستند الإخراج

قم بتحميل مستند PDF الناتج:

```csharp
Document doc1 = new Document(dataDir + "input.pdf");
```

## الخطوة 3: البحث عن الحقول المضافة

ابحث عن حقول النموذج المضافة (في هذا المثال ، نستخدم الحقول "Item1" و "Item2" و "Item3"):

```csharp
RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
```

## الخطوة 4: عرض مواضع البنود الفرعية لكل حقل

التنقل بين الخيارات الخاصة بكل حقل وعرض إحداثيات كل عنصر فرعي:

```csharp
foreach(RadioButtonOptionField option in field0)
{
Console.WriteLine(option.Rect);
}
foreach(RadioButtonOptionField option in field1)
{
Console.WriteLine(option.Rect);
}
foreach(RadioButtonOptionField option in field2)
{
Console.WriteLine(option.Rect);
}
```

### نموذج التعليمات البرمجية المصدر للحصول على إحداثيات باستخدام Aspose.PDF لـ .NET 
```csharp
try
{
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// قم بتحميل مستند الإخراج
	Document doc1 = new Document( dataDir + "input.pdf");
	// ابحث عن الحقول المضافة
	RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
	RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
	RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
	// وتظهر مواضع العناصر الفرعية لكل منها.
	foreach (RadioButtonOptionField option in field0)
	{
		Console.WriteLine(option.Rect);
	}
	foreach (RadioButtonOptionField option in field1)
	{
		Console.WriteLine(option.Rect);
	}
	foreach (RadioButtonOptionField option in field2)
	{
		Console.WriteLine(option.Rect);
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية الحصول على إحداثيات حقل النموذج باستخدام Aspose.PDF for .NET. باتباع هذه الخطوات ، يمكنك بسهولة استرداد إحداثيات العناصر الفرعية لحقول النموذج الخاصة بك في مستندات PDF الخاصة بك باستخدام Aspose.PDF.

### التعليمات

#### س: هل يمكنني استخدام هذه الطريقة للحصول على إحداثيات لأي نوع من حقول النموذج في Aspose.PDF for .NET؟

ج: نعم ، يمكنك استخدام هذه الطريقة للحصول على إحداثيات لأنواع مختلفة من حقول النموذج في Aspose.PDF for .NET. يوضح كود المصدر C # المقدم كيفية الحصول على إحداثيات لحقول RadioButton ، ولكن يمكنك تكييف نفس الأسلوب مع أنواع حقول النموذج الأخرى ، مثل TextBox و CheckBox و ListBox والمزيد.

#### س: كيف يمكنني تعديل أو تعديل إحداثيات حقل النموذج؟

ج: تستند إحداثيات حقل النموذج إلى نظام إحداثيات مستند PDF ، حيث يقع الأصل (0،0) في الركن الأيسر السفلي من الصفحة. لتعديل إحداثيات حقل النموذج أو ضبطها ، يمكنك تحديث ملف`Rect` خاصية حقل النموذج المعني أو عناصره الفرعية ، مثل RadioButtonOptionField.

#### س: هل يمكنني إضافة إحداثيات حقول النموذج برمجيًا إلى مستند PDF؟

ج: نعم ، يمكنك الحصول على إحداثيات حقول النموذج التي تمت إضافتها برمجيًا إلى مستند PDF. يتيح لك Aspose.PDF for .NET إضافة حقول النموذج ديناميكيًا ، وبمجرد إضافتها ، يمكنك استرداد إحداثياتها باستخدام الطريقة الموضحة في هذا البرنامج التعليمي.

#### س: ما هو الغرض من استرجاع إحداثيات مجال الاستمارة؟

ج: يمكن أن يكون استرداد إحداثيات حقل النموذج مفيدًا عندما تحتاج إلى إجراء عمليات محددة متعلقة بالتخطيط أو عمليات التحقق من صحة حقول النموذج داخل مستند PDF. يسمح لك بتحديد موضع حقول النموذج ومواءمتها بدقة بناءً على إحداثياتها ، مما يضمن ظهورها بشكل صحيح في المستند وتوفير تجربة مستخدم سلسة.

#### س: هل إحداثيات حقل النموذج معبر عنها بالنقاط أو بوحدة أخرى؟

ج: يتم التعبير عن إحداثيات حقل النموذج في Aspose.PDF for .NET بالنقاط. النقطة الواحدة تعادل 1/72 بوصة ، مما يجعلها وحدة قياس قياسية بتنسيق PDF.