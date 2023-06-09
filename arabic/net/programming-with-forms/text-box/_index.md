---
title: مربع الكتابة
linktitle: مربع الكتابة
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إنشاء حقل نصي في مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 290
url: /ar/net/programming-with-forms/text-box/
---

في هذا الدليل ، سنشرح خطوة بخطوة كيفية استخدام مكتبة Aspose.PDF لـ .NET لإنشاء حقل نصي في مستند PDF. سنوضح لك كيفية فتح المستند وإنشاء حقل النص وتخصيص خصائصه وحفظ ملف PDF المحرر.

## الخطوة 1: تكوين دليل الوثيقة

 تتمثل الخطوة الأولى في تكوين دليل المستند حيث يوجد ملف PDF الذي تريد العمل عليه. يمكنك استخدام ال`dataDir`متغير لتحديد مسار الدليل.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 تأكد من استبدال`"YOUR DOCUMENTS DIRECTORY"` مع المسار الفعلي إلى دليل المستندات الخاص بك.

## الخطوة 2: فتح مستند PDF

 في هذه الخطوة ، سنفتح مستند PDF باستخدام امتداد`Document`فئة Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "TextField.pdf");
```

تأكد من وجود ملف PDF في دليل المستندات المحدد.

## الخطوة 3: إنشاء حقل النص

 سنقوم بإنشاء حقل نصي باستخدام`TextBoxField` فصل. يمكنك تحديد إحداثيات الموقع وحجم الحقل باستخدام ملف`Rectangle` فصل.

```csharp
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField. PartialName = "textbox1";
textBoxField.Value = "Text Field";
```

قم بتخصيص الإحداثيات والحجم والاسم الجزئي وقيمة الحقل النصي حسب الحاجة.

## الخطوة 4: تخصيص خصائص حقل النص

في هذه الخطوة ، سنخصص خصائص حقل النص مثل الحدود واللون وما إلى ذلك.

```csharp
Border border = new Border(textBoxField);
border. width = 5;
border. Dash = new Dash(1, 1);
textBoxField. Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```

قم بتخصيص خصائص حقل النص وفقًا لتفضيلاتك.

## الخطوة 5: إضافة الحقل إلى المستند

الآن بعد أن قمنا بإنشاء وتكوين حقل النص ، يمكننا إضافته إلى مستند PDF.

```csharp
pdfDocument.Form.Add(textBoxField, 1);
```

## الخطوة 6: حفظ ملف PDF المعدل

 أخيرًا ، يمكننا حفظ ملف PDF المعدل باستخدام امتداد`Save` طريقة`Document` فصل.

```csharp
dataDir = dataDir + "TextBox_out.pdf";
pdfDocument.Save(dataDir);
```

تأكد من تحديد المسار الكامل واسم الملف لملف PDF المحرر.

### نموذج التعليمات البرمجية المصدر لـ Text Box باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "TextField.pdf");
// قم بإنشاء حقل
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField.PartialName = "textbox1";
textBoxField.Value = "Text Box";
// TextBoxField.Border = حد جديد (
Border border = new Border(textBoxField);
border.Width = 5;
border.Dash = new Dash(1, 1);
textBoxField.Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
// أضف حقلاً إلى المستند
pdfDocument.Form.Add(textBoxField, 1);
dataDir = dataDir + "TextBox_out.pdf";
// احفظ ملف PDF المعدل
pdfDocument.Save(dataDir);
Console.WriteLine("\nTextbox field added successfully.\nFile saved at " + dataDir);
```

## خاتمة

في هذا الدليل ، تعلمنا كيفية استخدام مكتبة Aspose.PDF لـ .NET لإنشاء حقل نصي في مستند PDF. باتباع الخطوات الموضحة ، يمكنك تخصيص خصائص حقل النص وإضافته إلى المستند حسب الحاجة. لا تتردد في استكشاف ميزات Aspose.PDF لـ .NET لتوسيع إمكانيات معالجة ملفات PDF.