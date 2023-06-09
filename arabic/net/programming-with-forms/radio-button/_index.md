---
title: زر الراديو
linktitle: زر الراديو
second_title: Aspose.PDF لمرجع .NET API
description: أضف أزرار اختيار إلى مستندات PDF بسهولة باستخدام Aspose.PDF for .NET.
type: docs
weight: 220
url: /ar/net/programming-with-forms/radio-button/
---

في هذا البرنامج التعليمي ، سنوضح لك كيفية إضافة زر اختيار في مستند PDF باستخدام Aspose.PDF for .NET. سنشرح كود المصدر C # خطوة بخطوة لإرشادك خلال هذه العملية.

## الخطوة الأولى: التحضير

تأكد من أنك قمت باستيراد المكتبات الضرورية وقم بتعيين المسار إلى دليل المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: إنشاء كائن مستند

إنشاء كائن مستند لإنشاء مستند PDF جديد:

```csharp
Document pdfDocument = new Document();
```

## الخطوة 3: أضف صفحة

أضف صفحة إلى مستند PDF:

```csharp
pdfDocument.Pages.Add();
```

## الخطوة 4: إنشاء كائن RadioButtonField

إنشاء كائن RadioButtonField يحدد رقم الصفحة كوسيطة:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## الخطوة 5: إضافة خيارات زر الاختيار

أضف خيارات زر الاختيار إلى كائن RadioButtonField عن طريق تحديد إحداثيات كل خيار بكائن مستطيل:

```csharp
radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
```

## الخطوة 6: أضف زر الاختيار إلى النموذج

أضف زر الاختيار إلى كائن النموذج الخاص بالمستند:

```csharp
pdfDocument.Form.Add(radio);
```

## الخطوة 7: احفظ مستند PDF

احفظ مستند PDF الذي تم إنشاؤه:

```csharp
dataDir = dataDir + "RadioButton_out.pdf";
pdfDocument.Save(dataDir);
```

### نموذج التعليمات البرمجية المصدر لزر الراديو باستخدام Aspose.PDF لـ .NET 
```csharp
try
{
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// إنشاء كائن المستند
	Document pdfDocument = new Document();
	// أضف صفحة إلى ملف PDF
	pdfDocument.Pages.Add();
	// إنشاء كائن RadioButtonField مع رقم الصفحة كوسيطة
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// أضف خيار زر الاختيار الأول وحدد أيضًا أصله باستخدام كائن المستطيل
	radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
	// إضافة خيار زر الاختيار الثاني
	radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
	// إضافة زر اختيار لتكوين كائن من كائن المستند
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "RadioButton_out.pdf";
	// احفظ ملف PDF
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadio button field added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية إضافة زر اختيار في مستند PDF باستخدام Aspose.PDF لـ .NET. باتباع هذه الخطوات ، يمكنك بسهولة إنشاء زر اختيار ووضعه على صفحة معينة في مستند PDF الخاص بك.