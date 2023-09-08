---
title: مربع الكتابة
linktitle: مربع الكتابة
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إنشاء حقل نصي في مستند PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 290
url: /ar/net/programming-with-forms/text-box/
---
سنشرح في هذا الدليل خطوة بخطوة كيفية استخدام مكتبة Aspose.PDF لـ .NET لإنشاء حقل نصي في مستند PDF. سنوضح لك كيفية فتح المستند وإنشاء حقل النص وتخصيص خصائصه وحفظ ملف PDF المحرر.

## الخطوة 1: تكوين دليل المستندات

 الخطوة الأولى هي تكوين دليل المستند حيث يوجد ملف PDF الذي تريد العمل عليه. يمكنك استخدام ال`dataDir` متغير لتحديد مسار الدليل.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 تأكد من استبدال`"YOUR DOCUMENTS DIRECTORY"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

## الخطوة 2: فتح مستند PDF

في هذه الخطوة، سنقوم بفتح مستند PDF باستخدام الملف`Document` فئة Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "TextField.pdf");
```

تأكد من وجود ملف PDF في دليل المستندات المحدد.

## الخطوة 3: إنشاء حقل النص

 سنقوم بإنشاء حقل نصي باستخدام`TextBoxField` فصل. يمكنك تحديد إحداثيات الموقع وحجم الحقل باستخدام`Rectangle` فصل.

```csharp
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField. PartialName = "textbox1";
textBoxField.Value = "Text Field";
```

قم بتخصيص الإحداثيات والحجم والاسم الجزئي وقيمة حقل النص حسب الحاجة.

## الخطوة 4: تخصيص خصائص حقل النص

في هذه الخطوة، سنقوم بتخصيص خصائص حقل النص مثل الحدود واللون وما إلى ذلك.

```csharp
Border border = new Border(textBoxField);
border. width = 5;
border. Dash = new Dash(1, 1);
textBoxField. Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```

قم بتخصيص خصائص حقل النص وفقًا لتفضيلاتك.

## الخطوة 5: إضافة الحقل إلى المستند

الآن بعد أن قمنا بإنشاء حقل النص وتكوينه، يمكننا إضافته إلى مستند PDF.

```csharp
pdfDocument.Form.Add(textBoxField, 1);
```

## الخطوة 6: حفظ ملف PDF المعدل

 أخيرًا، يمكننا حفظ ملف PDF المعدل باستخدام ملف`Save` طريقة`Document` فصل.

```csharp
dataDir = dataDir + "TextBox_out.pdf";
pdfDocument.Save(dataDir);
```

تأكد من تحديد المسار الكامل واسم الملف لملف PDF المحرر.

### نموذج التعليمات البرمجية المصدر لمربع النص باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "TextField.pdf");
// إنشاء حقل
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField.PartialName = "textbox1";
textBoxField.Value = "Text Box";
//TextBoxField.Border = حدود جديدة (
Border border = new Border(textBoxField);
border.Width = 5;
border.Dash = new Dash(1, 1);
textBoxField.Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
// إضافة حقل إلى الوثيقة
pdfDocument.Form.Add(textBoxField, 1);
dataDir = dataDir + "TextBox_out.pdf";
// حفظ ملف PDF المعدل
pdfDocument.Save(dataDir);
Console.WriteLine("\nTextbox field added successfully.\nFile saved at " + dataDir);
```

## خاتمة

في هذا الدليل، تعلمنا كيفية استخدام مكتبة Aspose.PDF لـ .NET لإنشاء حقل نصي في مستند PDF. باتباع الخطوات الموضحة، يمكنك تخصيص خصائص حقل النص وإضافته إلى المستند حسب الحاجة. لا تتردد في استكشاف المزيد من ميزات Aspose.PDF لـ .NET لتوسيع إمكانيات معالجة ملفات PDF.

### الأسئلة الشائعة

#### س: هل يمكنني استخدام Aspose.PDF لـ .NET لإنشاء حقول نصية متعددة في مستند PDF واحد؟

ج: نعم، يمكنك إنشاء حقول نصية متعددة في مستند PDF واحد باستخدام Aspose.PDF لـ .NET. ما عليك سوى تكرار عملية إنشاء الحقول النصية وتخصيصها لكل موقع مرغوب في المستند.

#### س: كيف يمكنني تخصيص مظهر حقل النص، مثل حجم الخط ولونه؟

ج: يمكنك تخصيص مظهر حقل النص عن طريق ضبط خصائصه، مثل حجم الخط ونمط الخط واللون ونمط الحدود ولون الخلفية والمزيد. في نموذج التعليمات البرمجية المصدر المقدم، يتم تخصيص عرض الحدود ونمط شرطة الحدود ولون النص.

#### س: هل من الممكن استخراج النص الذي أدخله المستخدم من حقل النص الذي تم إنشاؤه؟

ج: نعم، يمكنك استخراج النص الذي أدخله المستخدم من حقل النص الذي تم إنشاؤه. بعد قيام المستخدمين بملء حقل النص في مستند PDF، يمكنك استرداد قيمة الحقل برمجيًا باستخدام Aspose.PDF لـ .NET.

#### س: هل يمكنني إضافة حقول نصية إلى مستند PDF موجود دون إنشاء حقل جديد؟

ج: نعم، يمكنك إضافة حقول نصية إلى مستند PDF موجود دون إنشاء حقل جديد. يوفر Aspose.PDF for .NET القدرة على تعديل مستندات PDF الموجودة، بما في ذلك إضافة حقول نصية ومربعات اختيار وعناصر نموذج أخرى.

#### س: هل يدعم Aspose.PDF for .NET أنواعًا أخرى من حقول النماذج، مثل مربعات الاختيار وأزرار الاختيار؟

ج: نعم، يدعم Aspose.PDF for .NET أنواعًا مختلفة من حقول النماذج، بما في ذلك مربعات الاختيار وأزرار الاختيار والقوائم المنسدلة والمزيد. يمكنك استخدام المكتبة للعمل مع أنواع مختلفة من عناصر النموذج في مستندات PDF.