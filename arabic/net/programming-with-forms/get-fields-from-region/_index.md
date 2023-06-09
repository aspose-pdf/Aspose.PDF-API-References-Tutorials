---
title: احصل على الحقول من المنطقة
linktitle: احصل على الحقول من المنطقة
second_title: Aspose.PDF لمرجع .NET API
description: احصل بسهولة على الحقول من منطقة معينة في مستندات PDF الخاصة بك باستخدام Aspose.PDF for .NET.
type: docs
weight: 130
url: /ar/net/programming-with-forms/get-fields-from-region/
---

في هذا البرنامج التعليمي ، سنوضح لك كيفية الحصول على حقول منطقة معينة في مستند PDF باستخدام Aspose.PDF لـ .NET. سنشرح كود المصدر C # خطوة بخطوة لإرشادك خلال هذه العملية.

## الخطوة الأولى: التحضير

تأكد من أنك قمت باستيراد المكتبات الضرورية وقم بتعيين المسار إلى دليل المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: افتح ملف PDF

افتح ملف PDF:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
```

## الخطوة 3: قم بإنشاء كائن مستطيل لربط المنطقة

قم بإنشاء كائن مستطيل لربط المنطقة حيث تريد الحصول على الحقول:

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
```

## الخطوة 4: الحصول على نموذج PDF

احصل على نموذج PDF للمستند:

```csharp
Aspose.Pdf.Forms.Form form = doc.Form;
```

## الخطوة 5: احصل على الحقول في المنطقة المستطيلة

احصل على الحقول الموجودة في المنطقة المستطيلة المحددة:

```csharp
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
```

## الخطوة 6: عرض أسماء الحقول والقيم

كرر الحقول الناتجة واعرض أسمائها وقيمها:

```csharp
foreach (Field field in fields)
{
Console.Out.WriteLine("Field name: " + field.FullName + "-" + "Field value: " + field.Value);
}
```

### نموذج التعليمات البرمجية المصدر للحصول على الحقول من المنطقة باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح ملف pdf
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
// قم بإنشاء كائن مستطيل للحصول على الحقول في تلك المنطقة
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
// احصل على نموذج PDF
Aspose.Pdf.Forms.Form form = doc.Form;
//احصل على الحقول في المنطقة المستطيلة
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
// عرض أسماء الحقول والقيم
foreach (Field field in fields)
{
	// عرض خصائص وضع الصور لجميع المواضع
	Console.Out.WriteLine("Field Name: " + field.FullName + "-" + "Field Value: " + field.Value);
}
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية الحصول على حقول منطقة معينة في مستند PDF باستخدام Aspose.PDF لـ .NET. باتباع هذه الخطوات ، يمكنك بسهولة استخراج الحقول الموجودة في منطقة مستطيلة معينة من مستند PDF الخاص بك باستخدام Aspose.PDF.