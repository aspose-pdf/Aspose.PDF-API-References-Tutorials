---
title: قم بتعبئة حقل نموذج PDF
linktitle: قم بتعبئة حقل نموذج PDF
second_title: Aspose.PDF لمرجع .NET API
description: قم بملء حقول النموذج بسهولة في مستندات PDF الخاصة بك باستخدام Aspose.PDF for .NET.
type: docs
weight: 80
url: /ar/net/programming-with-forms/fill-form-field/
---
في هذا البرنامج التعليمي ، سنوضح لك كيفية ملء حقل نموذج باستخدام Aspose.PDF for .NET. سنشرح كود المصدر C # خطوة بخطوة لإرشادك خلال هذه العملية.

## الخطوة الأولى: التحضير

أولاً ، تأكد من استيراد المكتبات الضرورية وتعيين المسار إلى دليل المستندات:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: افتح المستند

افتح مستند PDF الموجود:

```csharp
Document pdfDocument = new Document(dataDir + "FillFormField.pdf");
```

## الخطوة 3: احصل على الميدان

احصل على حقل النموذج المطلوب (في هذا المثال ، نستخدم حقل "textbox1"):

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## الخطوة 4: قم بتغيير قيمة الحقل

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

### نموذج التعليمات البرمجية المصدر لملء حقل النموذج باستخدام Aspose.PDF لـ .NET 
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
// احفظ المستند المحدث
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field filled successfully.\nFile saved at " + dataDir);
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية ملء حقل نموذج باستخدام Aspose.PDF لـ .NET. باتباع هذه الخطوات ، يمكنك بسهولة تغيير قيم حقل النموذج في مستندات PDF الخاصة بك باستخدام Aspose.PDF.

### التعليمات

#### س: هل يمكنني ملء عدة حقول نموذجية في مستند PDF باستخدام Aspose.PDF for .NET؟

ج: نعم ، يمكنك ملء عدة حقول نموذجية في مستند PDF باستخدام Aspose.PDF for .NET. بعد فتح مستند PDF ، يمكنك الحصول على كل حقل نموذج على حدة وتعديل قيمته حسب الحاجة.

#### س: كيف يمكنني العثور على أسماء حقول النموذج في مستند PDF؟

 ج: للعثور على أسماء حقول النموذج في مستند PDF ، يمكنك التكرار من خلال ملف`pdfDocument.Form.Fields` مجموعة. يحتوي كل حقل نموذج على ملف`FullName` الخاصية التي تحتوي على اسمها الفريد. يمكنك استخدام هذه الأسماء لتعريف وتعديل حقول نموذج معينة.

#### س: ماذا لو كان حقل النموذج الذي أريد ملؤه غير موجود في مستند PDF؟

 ج: إذا كان حقل النموذج الذي تريد تعبئته غير موجود في مستند PDF ، تحاول الوصول إليه باستخدام`pdfDocument.Form["fieldName"]`سيعود فارغة. لذلك ، من الضروري التأكد من وجود حقل النموذج قبل محاولة ملئه. يمكنك إضافة حقول نموذج جديدة برمجيًا باستخدام Aspose.PDF for .NET إذا لزم الأمر.

#### س: هل يمكنني ملء حقول النموذج ببيانات ديناميكية من قاعدة بيانات أو مصدر بيانات آخر؟

ج: نعم ، يمكنك تعبئة حقول النموذج ببيانات ديناميكية من قاعدة بيانات أو أي مصدر بيانات آخر. قبل تعيين قيمة الحقل ، استرد البيانات من المصدر واستخدمها لتعيين قيمة حقل النموذج وفقًا لذلك.

#### س: هل هناك أي قيود عند ملء حقول النموذج في مستندات PDF المستندة إلى XFA؟

ج: يمكن أن يكون لملء حقول النموذج في مستندات PDF المستندة إلى XFA (XML Forms Architecture) بعض القيود بسبب البنية المعقدة لنماذج XFA. يدعم Aspose.PDF for .NET تعبئة حقول النموذج في نماذج XFA ، لكن بعض خصائص حقل النموذج المحددة الفريدة لنماذج XFA قد لا تكون مدعومة بالكامل في AcroForms.