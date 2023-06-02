---
title: تسطيح الأشكال
linktitle: تسطيح الأشكال
second_title: Aspose.PDF لمرجع .NET API
description: قم بتسوية النماذج بسهولة في مستندات PDF الخاصة بك باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 100
url: /ar/net/programming-with-forms/flatten-forms/
---

في هذا البرنامج التعليمي ، سنوضح لك كيفية تسوية النماذج باستخدام Aspose.PDF for .NET. سنشرح كود المصدر C # خطوة بخطوة لإرشادك خلال هذه العملية.

## الخطوة الأولى: التحضير

أولاً ، تأكد من استيراد المكتبات الضرورية وتعيين المسار إلى دليل المستندات:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: تحميل نموذج PDF المصدر

قم بتحميل نموذج PDF المصدر:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## الخطوة 3: تسطيح النماذج

تحقق أولاً من وجود أي حقول نموذج في المستند. إذا كان الأمر كذلك ، فكرر كل حقل وقم بتطبيق التسطيح:

```csharp
if (doc.Form.Fields.Count() > 0)
{
foreach (var item in doc.Form.Fields)
{
item. Flatten();
}
}
```

## الخطوة 4: احفظ المستند المحدث

احفظ مستند PDF المحدث:

```csharp
dataDir = dataDir + "FlattenForms_out.pdf";
doc.Save(dataDir);
```

### نموذج التعليمات البرمجية المصدر لـ Flatten Forms باستخدام Aspose.Words for .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// تحميل نموذج PDF المصدر
Document doc = new Document(dataDir + "input.pdf");
// تسطيح الأشكال
if (doc.Form.Fields.Count() > 0)
{
	foreach (var item in doc.Form.Fields)
	{
		item.Flatten();
	}
}
dataDir = dataDir + "FlattenForms_out.pdf";
// احفظ المستند المحدث
doc.Save(dataDir);
Console.WriteLine("\nForms flattened successfully.\nFile saved at " + dataDir);
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية تسوية النماذج باستخدام Aspose.PDF لـ .NET. باتباع هذه الخطوات ، يمكنك بسهولة تسوية النماذج في مستندات PDF الخاصة بك ، مما يجعل الحقول غير قابلة للتعديل ودمج التعليقات التوضيحية مع محتوى المستند.