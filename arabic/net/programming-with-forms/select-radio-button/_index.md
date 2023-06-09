---
title: حدد زر الاختيار
linktitle: حدد زر الاختيار
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تحديد زر اختيار في مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 250
url: /ar/net/programming-with-forms/select-radio-button/
---

فيما يلي برنامج تعليمي مفصل حول كيفية تحديد زر اختيار باستخدام Aspose.PDF for .NET. اتبع هذه الخطوات:

##  الخطوة 1: ابدأ بتحديد دليل المستندات الخاصة بك عن طريق تحديد المسار في ملف`dataDir` variable.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

##  الخطوة 2: افتح مستند PDF باستخدام ملف`Document` class and the document path.

```csharp
Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
```

## الخطوة 3: احصل على حقل زر الاختيار من نموذج المستند.

```csharp
RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
```

## الخطوة 4: حدد فهرس زر الاختيار للاختيار من المجموعة.

```csharp
radioField. Selected = 2;
```

## الخطوة 5: قم بتعيين مسار الإخراج لملف PDF المحرر.

```csharp
dataDir = dataDir + "SelectRadioButton_out.pdf";
```

## الخطوة السادسة: احفظ ملف PDF المعدل.

```csharp
pdfDocument.Save(dataDir);
```

## الخطوة 7: عرض رسالة تأكيد وموقع الملف المحفوظ.

```csharp
Console.WriteLine("\nRadio button successfully selected in group.\nFile saved to location: " + dataDir);
```

### نموذج التعليمات البرمجية المصدر لتحديد زر الراديو باستخدام Aspose.PDF لـ .NET 
```csharp
try
{
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// افتح المستند
	Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
	// احصل على حقل
	RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
	// حدد فهرس زر الاختيار من المجموعة
	radioField.Selected = 2;
	dataDir = dataDir + "SelectRadioButton_out.pdf";
	// احفظ ملف PDF
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadioButton from group selected successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية تحديد زر اختيار باستخدام Aspose.PDF لـ .NET. باتباع الخطوات الموضحة أعلاه ، يمكنك معالجة وتعديل أزرار الاختيار في مستندات PDF الخاصة بك باستخدام Aspose.PDF for .NET.