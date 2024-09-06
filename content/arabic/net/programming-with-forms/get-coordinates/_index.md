---
title: الحصول على إحداثيات حقل نموذج PDF
linktitle: الحصول على إحداثيات حقل نموذج PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: احصل بسهولة على إحداثيات حقل نموذج PDF في مستندات PDF الخاصة بك باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 120
url: /ar/net/programming-with-forms/get-coordinates/
---
في هذا البرنامج التعليمي، سنوضح لك كيفية الحصول على إحداثيات حقل نموذج PDF باستخدام Aspose.PDF لـ .NET. وسنشرح التعليمات البرمجية المصدرية بلغة C# خطوة بخطوة لإرشادك خلال هذه العملية.

## الخطوة 1: التحضير

تأكد من أنك قمت باستيراد المكتبات الضرورية وقمت بتعيين المسار إلى دليل المستندات:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: تحميل المستند الناتج

تحميل مستند PDF الناتج:

```csharp
Document doc1 = new Document(dataDir + "input.pdf");
```

## الخطوة 3: البحث عن الحقول المضافة

ابحث عن حقول النموذج المضافة (في هذا المثال، نستخدم الحقول "العنصر1"، و"العنصر2"، و"العنصر3"):

```csharp
RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
```

## الخطوة 4: عرض مواضع العناصر الفرعية لكل حقل

قم بالتنقل بين الخيارات لكل حقل وعرض إحداثيات كل عنصر فرعي:

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

### عينة من كود المصدر للحصول على الإحداثيات باستخدام Aspose.PDF لـ .NET 
```csharp
try
{
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// تحميل المستند الناتج
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

في هذا البرنامج التعليمي، تعلمنا كيفية الحصول على إحداثيات حقول النموذج باستخدام Aspose.PDF لـ .NET. باتباع هذه الخطوات، يمكنك بسهولة استرداد إحداثيات العناصر الفرعية لحقول النموذج في مستندات PDF الخاصة بك باستخدام Aspose.PDF.

### الأسئلة الشائعة

#### س: هل يمكنني استخدام هذه الطريقة للحصول على إحداثيات أي نوع من حقول النموذج في Aspose.PDF لـ .NET؟

ج: نعم، يمكنك استخدام هذه الطريقة للحصول على إحداثيات أنواع مختلفة من حقول النماذج في Aspose.PDF لـ .NET. يوضح كود المصدر C# المقدم كيفية الحصول على إحداثيات حقول RadioButton، ولكن يمكنك تكييف نفس النهج لأنواع حقول النماذج الأخرى، مثل TextBox وCheckBox وListBox والمزيد.

#### س: كيف يمكنني تعديل أو ضبط إحداثيات حقل النموذج؟

أ: تعتمد إحداثيات حقل النموذج على نظام إحداثيات مستند PDF، حيث يقع الأصل (0,0) في الزاوية اليسرى السفلية من الصفحة. لتعديل أو ضبط إحداثيات حقل النموذج، يمكنك تحديث`Rect` خاصية حقل النموذج المعني أو عناصره الفرعية، مثل RadioButtonOptionField.

#### س: هل يمكنني الحصول على إحداثيات حقول النموذج المضافة برمجيًا إلى مستند PDF؟

ج: نعم، يمكنك الحصول على إحداثيات حقول النماذج التي تمت إضافتها برمجيًا إلى مستند PDF. يتيح لك Aspose.PDF for .NET إضافة حقول النماذج ديناميكيًا، وبمجرد إضافتها، يمكنك استرداد إحداثياتها باستخدام النهج الموضح في هذا البرنامج التعليمي.

#### س: ما هو الغرض من استرجاع إحداثيات حقل النموذج؟

أ: قد يكون استرداد إحداثيات حقول النماذج مفيدًا عندما تحتاج إلى تنفيذ عمليات أو عمليات تحقق محددة متعلقة بالتخطيط على حقول النماذج داخل مستند PDF. فهو يتيح لك تحديد موضع حقول النماذج ومحاذاتها بدقة استنادًا إلى إحداثياتها، مما يضمن ظهورها بشكل صحيح في المستند وتوفير تجربة مستخدم سلسة.

#### س: هل يتم التعبير عن إحداثيات حقل النموذج بالنقاط أو بوحدة أخرى؟

ج: يتم التعبير عن إحداثيات حقل النموذج في Aspose.PDF لـ .NET بالنقاط. النقطة الواحدة تعادل 1/72 بوصة، مما يجعلها وحدة قياس قياسية في تنسيق PDF.