---
title: الحصول على قيمة من الحقل في مستند PDF
linktitle: الحصول على قيمة من الحقل في مستند PDF
second_title: Aspose.PDF لمرجع .NET API
description: احصل بسهولة على قيمة حقل النموذج في مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 140
url: /ar/net/programming-with-forms/get-value-from-field/
---
في هذا البرنامج التعليمي ، سنوضح لك كيفية الحصول على قيمة حقل النموذج باستخدام Aspose.PDF for .NET. سنشرح كود المصدر C # خطوة بخطوة لإرشادك خلال هذه العملية.

## الخطوة الأولى: التحضير

تأكد من أنك قمت باستيراد المكتبات الضرورية وقم بتعيين المسار إلى دليل المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: افتح المستند

افتح مستند PDF:

```csharp
Document pdfDocument = new Document(dataDir + "GetValueFromField.pdf");
```

## الخطوة 3: احصل على الميدان

احصل على حقل النموذج المطلوب (في هذا المثال ، نستخدم حقل "textbox1"):

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## الخطوة 4: الحصول على قيمة الحقل

 احصل على قيمة الحقل باستخدام`Value` ملكية:

```csharp
Console.WriteLine("PartialName: {0}", textBoxField.PartialName);
Console.WriteLine("Value: {0}", textBoxField.Value);
```

### نموذج التعليمات البرمجية المصدر لـ Get Value From Field باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "GetValueFromField.pdf");
// احصل على حقل
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// احصل على قيمة الحقل
Console.WriteLine("PartialName : {0} ", textBoxField.PartialName);
Console.WriteLine("Value : {0} ", textBoxField.Value);
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية الحصول على قيمة حقل النموذج باستخدام Aspose.PDF لـ .NET. باتباع هذه الخطوات ، يمكنك بسهولة استخراج قيمة حقل نموذج معين في مستندات PDF الخاصة بك باستخدام Aspose.PDF.

### التعليمات

#### س: هل يمكنني الحصول على قيمة حقل النموذج دون معرفة اسمه مسبقًا؟

 ج: لا ، أنت بحاجة إلى معرفة الاسم أو الاسم الجزئي لحقل النموذج للحصول على قيمته باستخدام Aspose.PDF for .NET. ال`pdfDocument.Form["fieldname"]` يتطلب بناء الجملة الاسم الدقيق أو الاسم الجزئي لحقل النموذج للوصول إلى خصائصه ، بما في ذلك القيمة.

#### س: ماذا لو لم يكن حقل النموذج موجودًا في مستند PDF؟

 ج: إذا لم يكن حقل النموذج موجودًا في مستند PDF ، فإن ملف`pdfDocument.Form["fieldname"]` سيعود بناء الجملة`null` . من الضروري التعامل مع مثل هذه الحالات عن طريق التحقق من وجودها`null` قبل الوصول إلى خصائص حقل النموذج لتجنب الاستثناءات.

#### س: كيف يمكنني التعامل مع أنواع مختلفة من حقول النموذج (مثل مربعات الاختيار وأزرار الاختيار) للحصول على قيمها؟

 ج: للتعامل مع أنواع مختلفة من حقول النموذج ، يمكنك استخدام فئات الحقول المناسبة المتوفرة في Aspose.PDF for .NET. على سبيل المثال ، استخدم`CheckBoxField` للعمل مع مربعات الاختيار و`RadioButtonField`للعمل مع أزرار الراديو. بمجرد حصولك على كائن الحقل الصحيح ، يمكنك الوصول إلى خصائصه ، بما في ذلك القيمة.

#### س: هل يمكنني الحصول على قيم حقول النماذج المتعددة مرة واحدة؟

ج: نعم ، يمكنك الحصول على قيم حقول نموذج متعددة مرة واحدة عن طريق التكرار خلال مجموعة حقول النموذج باستخدام استعلامات حلقة أو استعلامات LINQ. بهذه الطريقة ، يمكنك الوصول إلى قيمة كل حقل نموذج في مستند PDF برمجيًا.

#### س: هل من الممكن تعديل قيمة حقل النموذج وحفظ التغييرات مرة أخرى في مستند PDF؟

 ج: نعم ، يمكنك تعديل قيمة حقل النموذج باستخدام Aspose.PDF for .NET وحفظ التغييرات مرة أخرى في مستند PDF. بعد تحديث ملف`Value` خاصية حقل النموذج ، يمكنك استخدام`pdfDocument.Save()` طريقة لحفظ التغييرات على مستند PDF الأصلي.