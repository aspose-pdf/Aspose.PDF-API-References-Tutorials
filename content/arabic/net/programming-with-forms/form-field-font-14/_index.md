---
title: خط حقل النموذج 14
linktitle: خط حقل النموذج 14
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: يمكنك بسهولة تكوين خط حقول النماذج في مستندات PDF الخاصة بك باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 110
url: /ar/net/programming-with-forms/form-field-font-14/
---
في هذا البرنامج التعليمي، سنوضح لك كيفية تكوين الخط لحقل النموذج باستخدام Aspose.PDF لـ .NET. وسنشرح لك التعليمات البرمجية المصدرية بلغة C# خطوة بخطوة لإرشادك خلال هذه العملية.

## الخطوة 1: التحضير

أولاً، تأكد من استيراد المكتبات الضرورية وتعيين المسار إلى دليل المستندات:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: افتح المستند

افتح مستند PDF الموجود:

```csharp
Document pdfDocument = new Document(dataDir + "FormFieldFont14.pdf");
```

## الخطوة 3: الحصول على حقل نموذج معين

احصل على حقل النموذج المطلوب (في هذا المثال، نستخدم الحقل "textbox1"):

```csharp
Aspose.Pdf.Forms.Field field = pdfDocument.Form["textbox1"] as Aspose.Pdf.Forms.Field;
```

## الخطوة 4: إنشاء كائن الخط

قم بإنشاء كائن خط للخط الجديد الذي تريد استخدامه (على سبيل المثال، "ComicSansMS"):

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


### عينة من كود المصدر لخط حقل النموذج 14 باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// فتح المستند
Document pdfDocument = new Document(dataDir + "FormFieldFont14.pdf");
// الحصول على حقل نموذج معين من المستند
Aspose.Pdf.Forms.Field field = pdfDocument.Form["textbox1"] as Aspose.Pdf.Forms.Field;
// إنشاء كائن الخط
Aspose.Pdf.Text.Font font = FontRepository.FindFont("ComicSansMS");
// تعيين معلومات الخط لحقل النموذج
// Field.DefaultAppearance = new Aspose.Pdf.Forms.in.DefaultAppearance(الخط، 10، نظام الرسم. اللون. أسود)؛
dataDir = dataDir + "FormFieldFont14_out.pdf";
// حفظ المستند المحدث
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field font setup successfully.\nFile saved at " + dataDir);
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية تكوين الخط لحقل النموذج باستخدام Aspose.PDF لـ .NET. باتباع هذه الخطوات، يمكنك بسهولة تحديد الخط وحجم الخط لحقول النموذج في مستندات PDF الخاصة بك باستخدام Aspose.PDF.

### الأسئلة الشائعة

#### س: هل يمكنني استخدام أي خط لحقول النماذج في Aspose.PDF لـ .NET؟

ج: نعم، يمكنك استخدام أي خط TrueType أو OpenType لحقول النماذج في Aspose.PDF لـ .NET. طالما أن الخط متوفر ومثبت على النظام أو يمكن الوصول إليه من خلال FontRepository، فيمكنك استخدامه لتخصيص مظهر نص حقل النموذج.

#### س: كيف يمكنني العثور على الخطوط المتوفرة في Aspose.PDF لـ .NET؟

 أ: للعثور على الخطوط المتوفرة في Aspose.PDF لـ .NET، يمكنك استخدام`FontRepository.GetAvailableFonts()`الطريقة. تقوم هذه الطريقة بإرجاع مجموعة من الخطوط المتوفرة التي يمكنك استخدامها لحقول النماذج أو أي عمليات أخرى متعلقة بالنص في مستند PDF الخاص بك.

#### س: هل يمكنني تغيير حجم الخط لحقول النموذج إلى أي قيمة؟

ج: نعم، يمكنك تغيير حجم الخط لحقول النموذج إلى أي قيمة رقمية موجبة باستخدام Aspose.PDF لـ .NET. ومع ذلك، من الضروري التأكد من أن حجم الخط مناسب لحقل النموذج المحدد ولا يؤدي إلى اقتطاع النص أو التداخل مع عناصر أخرى في المستند.

#### س: هل يمكنني تغيير لون الخط لحقول النموذج؟

ج: نعم، يمكنك تغيير لون الخط لحقول النموذج باستخدام Aspose.PDF لـ .NET. في كود المصدر C# المقدم، تم تعيين لون الخط على اللون الأسود (`System.Drawing.Color.Black`)، ولكن يمكنك تخصيصه إلى أي قيمة لون صالحة أخرى.

#### س: كيف يمكنني محاذاة النص داخل حقل النموذج؟

 أ: لمحاذاة النص داخل حقل النموذج، يمكنك استخدام`Multiline`خاصية حقل النموذج وضبطها على true. تعمل هذه الخاصية على تمكين النص متعدد الأسطر داخل حقل النموذج، مما يسمح لك بالتحكم في محاذاة النص باستخدام فواصل الأسطر وإرجاع العربات.