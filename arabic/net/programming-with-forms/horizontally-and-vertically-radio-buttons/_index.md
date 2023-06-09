---
title: أزرار الراديو أفقيًا وعموديًا
linktitle: أزرار الراديو أفقيًا وعموديًا
second_title: Aspose.PDF لمرجع .NET API
description: يمكنك بسهولة إنشاء أزرار اختيار أفقية ورأسية في مستندات PDF الخاصة بك باستخدام Aspose.PDF for .NET.
type: docs
weight: 180
url: /ar/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---

في هذا البرنامج التعليمي ، سنوضح لك كيفية إنشاء أزرار اختيار مرتبة أفقيًا ورأسيًا في مستند PDF باستخدام Aspose.PDF for .NET. سنشرح كود المصدر C # خطوة بخطوة لإرشادك خلال هذه العملية.

## الخطوة الأولى: التحضير

تأكد من أنك قمت باستيراد المكتبات الضرورية وقم بتعيين المسار إلى دليل المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند

قم بتحميل مستند PDF الحالي:

```csharp
FormEditor formEditor = new FormEditor();
formEditor.BindPdf(dataDir + "input.pdf");
```

## الخطوة 3: تخصيص خيارات زر الاختيار

تخصيص خيارات زر الاختيار عن طريق تعيين الخصائص التالية:

```csharp
formEditor. RadioGap = 4; // المسافة بين خيارين لزر الاختيار
formEditor. RadioHoriz = true; // التخطيط الأفقي لأزرار الاختيار
formEditor.RadioButtonItemSize = 20; // حجم أزرار الاختيار
formEditor.Facade.BorderWidth = 1; // عرض حد زر الاختيار
formEditor.Facade.BorderColor = System.Drawing.Color.Black; // لون حد زر الاختيار
```

## الخطوة 4: إضافة أزرار راديو أفقية

أضف أزرار اختيار مرتبة أفقيًا عن طريق تحديد خيارات وموضع الحقل:

```csharp
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
```

## الخطوة 5: إضافة أزرار اختيار عمودية

أضف أزرار اختيار مرتبة عموديًا عن طريق تحديد خيارات وموضع الحقل:

```csharp
formEditor. RadioHoriz = false; // التخطيط العمودي لأزرار الاختيار
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
```

## الخطوة 6: احفظ المستند

احفظ مستند PDF المعدل:

```csharp
dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
formEditor.Save(dataDir);
```

### عينة من التعليمات البرمجية المصدر لأزرار الراديو الأفقية والرأسية باستخدام Aspose.PDF لـ .NET 
```csharp
try
{
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// قم بتحميل المستند المحفوظ مسبقًا
	FormEditor formEditor = new FormEditor();
	formEditor.BindPdf(dataDir + "input.pdf");
	// RadioGap هو المسافة بين خيارين من أزرار الاختيار.
	formEditor.RadioGap = 4;
	// إضافة زر اختيار أفقي
	formEditor.RadioHoriz = true;
	// RadioButtonItemSize إذا كان حجم عنصر زر الاختيار.
	formEditor.RadioButtonItemSize = 20;
	formEditor.Facade.BorderWidth = 1;
	formEditor.Facade.BorderColor = System.Drawing.Color.Black;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
	// إضافة زر اختيار آخر يقع عموديًا
	formEditor.RadioHoriz = false;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
	dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
	// احفظ مستند PDF
	formEditor.Save(dataDir);
	Console.WriteLine("\nHorizontally and vertically laid out radio buttons successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية إنشاء أزرار اختيار مرتبة أفقيًا ورأسيًا في مستند PDF باستخدام Aspose.PDF لـ .NET. باتباع هذه الخطوات ، يمكنك بسهولة تخصيص تخطيط أزرار الاختيار وإضافتها إلى مستندات PDF الخاصة بك باستخدام Aspose.PDF.