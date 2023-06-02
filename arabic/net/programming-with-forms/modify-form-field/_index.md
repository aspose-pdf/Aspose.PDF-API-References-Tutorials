---
title: تعديل حقل النموذج
linktitle: تعديل حقل النموذج
second_title: Aspose.PDF لمرجع .NET API
description: قم بتحرير حقول النموذج بسهولة في مستندات PDF الخاصة بك باستخدام Aspose.PDF for .NET.
type: docs
weight: 190
url: /ar/net/programming-with-forms/modify-form-field/
---

في هذا البرنامج التعليمي ، سنوضح لك كيفية تحرير حقل نموذج في مستند PDF باستخدام Aspose.PDF for .NET. سنشرح كود المصدر C # خطوة بخطوة لإرشادك خلال هذه العملية.

## الخطوة الأولى: التحضير

تأكد من أنك قمت باستيراد المكتبات الضرورية وقم بتعيين المسار إلى دليل المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند

قم بتحميل مستند PDF الحالي:

```csharp
Document pdfDocument = new Document(dataDir + "ModifyFormField.pdf");
```

## الخطوة 3: احصل على حقل النموذج

احصل على حقل النموذج الذي تريد تحريره:

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## الخطوة 4: قم بتغيير قيمة الحقل

قم بتغيير قيمة حقل النموذج:

```csharp
textBoxField.Value = "New Value";
```

## الخطوة 5: تحرير خصائص الحقل

قم بتعديل خصائص حقل النموذج الإضافية حسب الحاجة. على سبيل المثال ، يمكنك جعله للقراءة فقط:

```csharp
textBoxField.ReadOnly = true;
```

## الخطوة 6: احفظ المستند المحرر

احفظ مستند PDF المعدل:

```csharp
dataDir = dataDir + "ModifyFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### نموذج التعليمات البرمجية المصدر لتعديل حقل النموذج باستخدام Aspose.Words for .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "ModifyFormField.pdf");
// احصل على حقل
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// تعديل قيمة الحقل
textBoxField.Value = "New Value";
textBoxField.ReadOnly = true;
dataDir = dataDir + "ModifyFormField_out.pdf";
// احفظ المستند المحدث
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field modified successfully.\nFile saved at " + dataDir);
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية تحرير حقل نموذج في مستند PDF باستخدام Aspose.PDF لـ .NET. باتباع هذه الخطوات ، يمكنك التنقل بسهولة إلى حقل معين وتغيير قيمته وضبط خصائصه حسب الحاجة.