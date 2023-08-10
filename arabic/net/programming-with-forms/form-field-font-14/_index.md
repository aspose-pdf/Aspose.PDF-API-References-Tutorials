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


### نموذج التعليمات البرمجية المصدر لـ Form Field Font 14 باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "FormFieldFont14.pdf");
// احصل على حقل نموذج معين من المستند
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

### التعليمات

#### س: هل يمكنني استخدام أي خط لحقول النموذج في Aspose.PDF for .NET؟

ج: نعم ، يمكنك استخدام أي خط TrueType أو OpenType لحقول النموذج في Aspose.PDF for .NET. طالما أن الخط متاحًا ومثبتًا على النظام أو يمكن الوصول إليه من خلال FontRepository ، يمكنك استخدامه لتخصيص مظهر نص حقل النموذج.

#### س: كيف يمكنني العثور على الخطوط المتاحة في Aspose.PDF for .NET؟

 ج: للعثور على الخطوط المتاحة في Aspose.PDF for .NET ، يمكنك استخدام ملحق`FontRepository.GetAvailableFonts()`طريقة. تقوم هذه الطريقة بإرجاع مجموعة من الخطوط المتاحة التي يمكنك استخدامها لحقول النموذج أو أي عمليات أخرى متعلقة بالنص في مستند PDF الخاص بك.

#### س: هل يمكنني تغيير حجم الخط لحقول النموذج إلى أي قيمة؟

ج: نعم ، يمكنك تغيير حجم الخط لحقول النموذج إلى أي قيمة رقمية موجبة باستخدام Aspose.PDF for .NET. ومع ذلك ، فمن الضروري التأكد من أن حجم الخط مناسب لحقل النموذج المحدد ولا يؤدي إلى اقتطاع النص أو تداخله مع العناصر الأخرى في المستند.

#### س: هل يمكنني تغيير لون الخط لحقول النموذج؟

ج: نعم ، يمكنك تغيير لون الخط لحقول النموذج باستخدام Aspose.PDF for .NET. في التعليمات البرمجية المصدر C # المقدمة ، يتم تعيين لون الخط إلى الأسود (`System.Drawing.Color.Black`) ، ولكن يمكنك تخصيصها لأي قيمة لونية أخرى صالحة.

#### س: كيف يمكنني محاذاة النص داخل حقل النموذج؟

 ج: لمحاذاة النص داخل حقل النموذج ، يمكنك استخدام`Multiline`خاصية حقل النموذج وضبطها على "صواب". تعمل هذه الخاصية على تمكين النص متعدد الأسطر داخل حقل النموذج ، مما يسمح لك بالتحكم في محاذاة النص باستخدام فواصل الأسطر وإرجاع أول السطر.