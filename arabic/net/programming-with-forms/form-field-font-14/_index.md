---
title: خط حقل النموذج 14
linktitle: خط حقل النموذج 14
second_title: Aspose.PDF لمرجع .NET API
description: يمكنك بسهولة تكوين خط حقول النموذج في مستندات PDF الخاصة بك باستخدام Aspose.PDF for .NET.
type: docs
weight: 110
url: /ar/net/programming-with-forms/form-field-font-14/
---

في هذا البرنامج التعليمي ، سنوضح لك كيفية تكوين خط حقل النموذج باستخدام Aspose.PDF for .NET. سنشرح كود المصدر C # خطوة بخطوة لإرشادك خلال هذه العملية.

## الخطوة الأولى: التحضير

أولاً ، تأكد من استيراد المكتبات الضرورية وتعيين المسار إلى دليل المستندات:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: افتح المستند

افتح مستند PDF الموجود:

```csharp
Document pdfDocument = new Document(dataDir + "FormFieldFont14.pdf");
```

## الخطوة 3: احصل على حقل نموذج معين

احصل على حقل النموذج المطلوب (في هذا المثال ، نستخدم حقل "textbox1"):

```csharp
Aspose.Pdf.Forms.Field field = pdfDocument.Form["textbox1"] as Aspose.Pdf.Forms.Field;
```

## الخطوة 4: إنشاء كائن الخط

أنشئ كائن خط للخط الجديد الذي تريد استخدامه (على سبيل المثال ، "ComicSansMS"):

```csharp
Aspose.Pdf.Text.Font font = FontRepository.FindFont("ComicSansMS");
```

## الخطوة 5: تكوين معلومات الخط لحقل النموذج

قم بتكوين معلومات الخط لحقل النموذج باستخدام الخط الذي تم إنشاؤه مسبقًا:

```csharp
field.DefaultAppearance = new Aspose.Pdf.Forms.DefaultAppearance(font, 14, System.Drawing.Color.Black);
```

## الخطوة 6: احفظ المستند المحدث

احفظ مستند PDF المحدث:

```csharp
dataDir = dataDir + "FormFieldFont14_out.pdf";
pdfDocument.Save(dataDir);
```


### نموذج التعليمات البرمجية المصدر لـ Form Field Font 14 باستخدام Aspose.Words for .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "FormFieldFont14.pdf");
//احصل على حقل نموذج معين من المستند
Aspose.Pdf.Forms.Field field = pdfDocument.Form["textbox1"] as Aspose.Pdf.Forms.Field;
// إنشاء كائن الخط
Aspose.Pdf.Text.Font font = FontRepository.FindFont("ComicSansMS");
// قم بتعيين معلومات الخط لحقل النموذج
// Field.DefaultAppearance = جديد Aspose.Pdf.Forms.in.DefaultAppearance (الخط ، 10 ، System.Drawing.Color.Black) ؛
dataDir = dataDir + "FormFieldFont14_out.pdf";
// احفظ المستند المحدث
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field font setup successfully.\nFile saved at " + dataDir);
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية تكوين خط حقل النموذج باستخدام Aspose.PDF for .NET. باتباع هذه الخطوات ، يمكنك بسهولة تحديد الخط وحجم الخط لحقول النموذج في مستندات PDF الخاصة بك باستخدام Aspose.PDF.