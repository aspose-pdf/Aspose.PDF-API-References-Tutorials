---
title: احصل على إحداثيات
linktitle: احصل على إحداثيات
second_title: Aspose.PDF لمرجع .NET API
description: احصل بسهولة على إحداثيات حقل النموذج في مستندات PDF الخاصة بك باستخدام Aspose.PDF for .NET.
type: docs
weight: 120
url: /ar/net/programming-with-forms/get-coordinates/
---

في هذا البرنامج التعليمي ، سنوضح لك كيفية الحصول على إحداثيات حقل النموذج باستخدام Aspose.PDF for .NET. سنشرح كود المصدر C # خطوة بخطوة لإرشادك خلال هذه العملية.

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