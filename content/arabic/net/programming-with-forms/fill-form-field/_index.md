---
title: ملء حقل نموذج PDF
linktitle: ملء حقل نموذج PDF
second_title: Aspose.PDF لمرجع .NET API
description: قم بملء حقول النموذج بسهولة في مستندات PDF الخاصة بك باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 80
url: /ar/net/programming-with-forms/fill-form-field/
---
سنوضح لك في هذا البرنامج التعليمي كيفية ملء حقل نموذج باستخدام Aspose.PDF لـ .NET. سنشرح لك كود مصدر C# خطوة بخطوة لإرشادك خلال هذه العملية.

## الخطوة 1: التحضير

أولاً، تأكد من استيراد المكتبات اللازمة وتعيين المسار إلى دليل المستندات:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: افتح المستند

افتح مستند PDF الموجود:

```csharp
Document pdfDocument = new Document(dataDir + "FillFormField.pdf");
```

## الخطوة 3: الحصول على الحقل

احصل على حقل النموذج المطلوب (في هذا المثال، نستخدم الحقل "textbox1"):

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## الخطوة 4: تغيير قيمة الحقل

قم بتعديل قيمة الحقل بالقيمة المطلوبة:

```csharp
textBoxField.Value = "Value to fill in the field";
```

## الخطوة 5: احفظ المستند المحدث

احفظ مستند PDF المحدث:

```csharp
dataDir = dataDir + "FillFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### نموذج التعليمات البرمجية المصدر لتعبئة حقل النموذج باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "FillFormField.pdf");
// احصل على حقل
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// تعديل قيمة الحقل
textBoxField.Value = "Value to be filled in the field";
dataDir = dataDir + "FillFormField_out.pdf";
// حفظ المستند المحدث
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field filled successfully.\nFile saved at " + dataDir);
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية ملء حقل نموذج باستخدام Aspose.PDF لـ .NET. باتباع هذه الخطوات، يمكنك بسهولة تغيير قيم حقول النموذج في مستندات PDF الخاصة بك باستخدام Aspose.PDF.

### الأسئلة الشائعة

#### س: هل يمكنني ملء حقول نماذج متعددة في مستند PDF باستخدام Aspose.PDF لـ .NET؟

ج: نعم، يمكنك ملء حقول نماذج متعددة في مستند PDF باستخدام Aspose.PDF لـ .NET. بعد فتح مستند PDF، يمكنك الحصول على كل حقل نموذج على حدة وتعديل قيمته حسب الحاجة.

#### س: كيف يمكنني العثور على أسماء حقول النموذج في مستند PDF؟

 ج: للعثور على أسماء حقول النموذج في مستند PDF، يمكنك التكرار من خلال ملف`pdfDocument.Form.Fields` مجموعة. يحتوي كل حقل نموذج على`FullName` الخاصية التي تحتوي على اسمها الفريد. يمكنك استخدام هذه الأسماء لتحديد وتعديل حقول نموذج معينة.

#### س: ماذا لو كان حقل النموذج الذي أريد تعبئته غير موجود في مستند PDF؟

 ج: إذا كان حقل النموذج الذي تريد تعبئته غير موجود في مستند PDF، فحاول الوصول إليه باستخدام`pdfDocument.Form["fieldName"]`سوف يعود فارغة. لذلك، من الضروري التأكد من وجود حقل النموذج قبل محاولة تعبئته. يمكنك إضافة حقول نماذج جديدة برمجيًا باستخدام Aspose.PDF لـ .NET إذا لزم الأمر.

#### س: هل يمكنني ملء حقول النموذج ببيانات ديناميكية من قاعدة بيانات أو مصدر بيانات آخر؟

ج: نعم، يمكنك ملء حقول النموذج ببيانات ديناميكية من قاعدة بيانات أو أي مصدر بيانات آخر. قبل تعيين قيمة الحقل، قم باسترداد البيانات من المصدر واستخدمها لتعيين قيمة حقل النموذج وفقًا لذلك.

#### س: هل هناك أي قيود عند ملء حقول النموذج في مستندات PDF المستندة إلى XFA؟

ج: يمكن أن يكون لملء حقول النموذج في مستندات PDF المستندة إلى XFA (بنية نماذج XML) بعض القيود بسبب البنية المعقدة لنماذج XFA. يدعم Aspose.PDF لـ .NET ملء حقول النموذج في نماذج XFA، ولكن قد لا تكون بعض خصائص حقل النموذج المحددة الفريدة لنماذج XFA مدعومة بشكل كامل في AcroForms.