---
title: احصل على إحداثيات حقل نموذج PDF
linktitle: احصل على إحداثيات حقل نموذج PDF
second_title: Aspose.PDF لمرجع .NET API
description: احصل بسهولة على إحداثيات حقل نموذج PDF في مستندات PDF الخاصة بك باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 120
url: /ar/net/programming-with-forms/get-coordinates/
---
سنوضح لك في هذا البرنامج التعليمي كيفية الحصول على إحداثيات حقل نموذج PDF باستخدام Aspose.PDF لـ .NET. سنشرح لك كود مصدر C# خطوة بخطوة لإرشادك خلال هذه العملية.

## الخطوة 1: التحضير

تأكد من استيراد المكتبات الضرورية وتعيين المسار إلى دليل المستندات:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل مستند الإخراج

قم بتحميل مستند PDF الناتج:

```csharp
Document doc1 = new Document(dataDir + "input.pdf");
```

## الخطوة 3: ابحث عن الحقول المضافة

ابحث عن حقول النموذج المضافة (في هذا المثال، نستخدم الحقول "Item1" و"Item2" و"Item3"):

```csharp
RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
```

## الخطوة 4: عرض مواضع العناصر الفرعية لكل حقل

قم بالتنقل بين الخيارات الخاصة بكل حقل واعرض الإحداثيات الخاصة بكل عنصر فرعي:

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

### نموذج التعليمات البرمجية المصدر للحصول على الإحداثيات باستخدام Aspose.PDF لـ .NET 
```csharp
try
{
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// قم بتحميل مستند الإخراج
	Document doc1 = new Document( dataDir + "input.pdf");
	// البحث عن الحقول المضافة
	RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
	RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
	RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
	// وإظهار مواضع العناصر الفرعية لكل منها.
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

في هذا البرنامج التعليمي، تعلمنا كيفية الحصول على إحداثيات حقل النموذج باستخدام Aspose.PDF لـ .NET. باتباع هذه الخطوات، يمكنك بسهولة استرداد إحداثيات العناصر الفرعية لحقول النموذج الخاصة بك في مستندات PDF الخاصة بك باستخدام Aspose.PDF.

### الأسئلة الشائعة

#### س: هل يمكنني استخدام هذه الطريقة للحصول على إحداثيات لأي نوع من حقول النموذج في Aspose.PDF لـ .NET؟

ج: نعم، يمكنك استخدام هذه الطريقة للحصول على إحداثيات لأنواع مختلفة من حقول النماذج في Aspose.PDF لـ .NET. يوضح كود مصدر C# المقدم كيفية الحصول على إحداثيات لحقول RadioButton، ولكن يمكنك تكييف نفس الأسلوب مع أنواع حقول النموذج الأخرى، مثل TextBox وCheckBox وListBox والمزيد.

#### س: كيف يمكنني تعديل أو تعديل إحداثيات حقل النموذج؟

ج: تعتمد إحداثيات حقل النموذج على النظام الإحداثي لمستند PDF، حيث يقع الأصل (0،0) في الركن السفلي الأيسر من الصفحة. لتعديل أو ضبط إحداثيات حقل النموذج، يمكنك تحديث`Rect` خاصية حقل النموذج المعني أو عناصره الفرعية، مثل RadioButtonOptionField.

#### س: هل يمكنني إضافة إحداثيات حقول النموذج برمجياً إلى مستند PDF؟

ج: نعم، يمكنك الحصول على إحداثيات حقول النموذج التي تمت إضافتها برمجيًا إلى مستند PDF. يتيح لك Aspose.PDF for .NET إضافة حقول النماذج ديناميكيًا، وبمجرد إضافتها، يمكنك استرداد إحداثياتها باستخدام الطريقة الموضحة في هذا البرنامج التعليمي.

#### س: ما هو الغرض من استرجاع إحداثيات حقل النموذج؟

ج: يمكن أن يكون استرداد إحداثيات حقل النموذج مفيدًا عندما تحتاج إلى إجراء عمليات محددة متعلقة بالتخطيط أو عمليات التحقق من الصحة في حقول النموذج داخل مستند PDF. فهو يسمح لك بتحديد موضع حقول النموذج ومحاذاتها بدقة بناءً على إحداثياتها، مما يضمن ظهورها بشكل صحيح في المستند وتوفير تجربة مستخدم سلسة.

#### س: هل يتم التعبير عن إحداثيات حقل النموذج بالنقاط أم بوحدة أخرى؟

ج: يتم التعبير عن إحداثيات حقل النموذج في Aspose.PDF لـ .NET بالنقاط. النقطة الواحدة تعادل 1/72 بوصة، مما يجعلها وحدة قياس قياسية بتنسيق PDF.