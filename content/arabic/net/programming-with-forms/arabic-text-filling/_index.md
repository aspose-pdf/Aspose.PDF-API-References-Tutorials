---
title: تعبئة النص العربي
linktitle: تعبئة النص العربي
second_title: Aspose.PDF لمرجع .NET API
description: قم بملء حقول نموذج PDF بسهولة بالنص العربي باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 20
url: /ar/net/programming-with-forms/arabic-text-filling/
---
في هذا البرنامج التعليمي، سنتعلم كيفية ملء حقل نموذج PDF بنص عربي باستخدام Aspose.PDF for .NET. Aspose.PDF هي مكتبة قوية تسمح للمطورين بمعالجة مستندات PDF برمجياً. سنرشدك خلال العملية خطوة بخطوة، موضحين كود مصدر C# المطلوب لإنجاز هذه المهمة.

## الخطوة 1: تحميل محتوى نموذج PDF

أولاً، نحتاج إلى تحميل نموذج PDF الذي يحتوي على الحقل الذي نريد ملؤه. نبدأ بتحديد المسار إلى الدليل الذي يوجد به النموذج:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 بعد ذلك، نقوم بإنشاء`FileStream` كائن لقراءة وكتابة ملف النموذج:

```csharp
FileStream fs = new FileStream(dataDir + "FillFormField.pdf", FileMode.Open, FileAccess.ReadWrite);
```

 بعد ذلك، نقوم بإنشاء مثيل أ`Document` كائن يستخدم الدفق الذي يحتوي على ملف النموذج:

```csharp
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
```

## الخطوة 2: الوصول إلى حقل TextBoxField

 لملء حقل النموذج بالنص العربي، نحتاج إلى الوصول إلى البيانات المحددة`TextBoxField` الحقل الذي نريد ملؤه. في هذا المثال، نفترض أن اسم الحقل هو "textbox1". يمكننا استرداد مرجع الحقل باستخدام`Form` ملكية`pdfDocument` هدف:

```csharp
TextBoxField txtFld = pdfDocument.Form["textbox1"] as TextBoxField;
```

## الخطوة 3: املأ حقل النموذج بالنص العربي

 الآن بعد أن أصبح لدينا`TextBoxField` المرجع، يمكننا تخصيص النص العربي له`Value` ملكية:

```csharp
txtFld.Value = "يولد جميع الناس أحراراً متساوين في";
```

## الخطوة 4: احفظ المستند المحدث

وأخيرًا، نقوم بحفظ المستند المحدث في ملف جديد:

```csharp
dataDir = dataDir + "ArabicTextFilling_out.pdf";
pdfDocument.Save(dataDir);
```

كما نعرض رسالة للإشارة إلى نجاح تعبئة النص العربي:

```csharp
Console.WriteLine("\nArabic text successfully filled in the form field.\nFile saved in the following location: " + dataDir);
```

### نموذج التعليمات البرمجية المصدر لتعبئة النص العربي باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// تحميل محتويات نموذج PDF
FileStream fs = new FileStream(dataDir + "FillFormField.pdf", FileMode.Open, FileAccess.ReadWrite);
//إنشاء مثيل للمستند باستخدام ملف نموذج يحتوي على دفق
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
// احصل على مرجع خاص بـ TextBoxField
TextBoxField txtFld = pdfDocument.Form["textbox1"] as TextBoxField;
// املأ حقل النموذج بالنص العربي
txtFld.Value = "يولد جميع الناس أحراراً متساوين في";
dataDir = dataDir + "ArabicTextFilling_out.pdf";
// حفظ المستند المحدث
pdfDocument.Save(dataDir);
Console.WriteLine("\nArabic text filled successfully in form field.\nFile saved at " + dataDir);
```

## خاتمة

في هذا البرنامج التعليمي، اكتشفنا كيفية ملء حقل نموذج PDF بنص عربي باستخدام Aspose.PDF لـ .NET. لقد مررنا بهذه العملية خطوة بخطوة وشرحنا كود مصدر C# ذي الصلة. باتباع هذه الإرشادات، يمكنك بسهولة دمج وظيفة تعبئة النص العربي في تطبيقات .NET الخاصة بك. إذا كانت لديك أية أسئلة أخرى أو كنت بحاجة إلى مزيد من المعلومات، فلا تتردد في الاتصال بفريق دعم Aspose.PDF أو التحقق من الموارد الإضافية أدناه.

### الأسئلة الشائعة

#### س: هل يمكنني ملء أنواع أخرى من حقول النموذج بنص عربي باستخدام Aspose.PDF لـ .NET؟

 ج: نعم، يمكنك استخدام Aspose.PDF لـ .NET لملء أنواع أخرى من حقول النماذج بالنص العربي، مثل مربعات الاختيار وأزرار الاختيار ومربعات التحرير والسرد والمزيد. العملية مشابهة لملء أ`TextBoxField` . ما عليك سوى الوصول إلى الحقل المحدد باستخدام اسمه أو معرفه وتعيينه`Value` الملكية إلى النص العربي المطلوب.

#### س: هل يتوافق Aspose.PDF for .NET مع النص العربي والكتابة من اليمين إلى اليسار (RTL)؟

ج: نعم، Aspose.PDF for .NET يدعم بشكل كامل النص العربي والكتابة من اليمين إلى اليسار. فهو يتعامل مع الأحرف العربية ومحاذاة النص بشكل صحيح، مما يضمن أن مستندات PDF التي تم إنشاؤها تحافظ على التخطيط المرئي الصحيح للغات التي تكتب من اليمين إلى اليسار.

#### س: هل يمكنني استخدام Aspose.PDF لـ .NET لاستخراج النص العربي من ملفات PDF الموجودة؟

ج: نعم، يوفر Aspose.PDF for .NET إمكانيات استخراج النص، مما يسمح لك باستخراج النص العربي من ملفات PDF الموجودة. يمكنك استخراج النص برمجياً من صفحات محددة أو المستند بأكمله، بما في ذلك النص العربي، باستخدام المكتبة.

#### س: هل يمكنني تخصيص مظهر النص العربي المعبأ في حقل النموذج؟

ج: نعم، يمكنك تخصيص مظهر النص العربي المعبأ في حقل النموذج باستخدام Aspose.PDF لـ .NET. يمكنك التحكم في أنماط الخطوط وأحجامها وألوانها وخيارات تنسيق النص الأخرى. يمكنك التأكد من أن النص العربي المعبأ يطابق المظهر الذي تريده في نموذج PDF.

#### س: كيف يمكنني الحصول على الدعم أو العثور على موارد إضافية لـ Aspose.PDF لـ .NET؟

ج: يمكنك الحصول على دعم لـ Aspose.PDF لـ .NET من خلال زيارة منتدى دعم Aspose الرسمي أو الاتصال بفريق الدعم الخاص بهم مباشرة. بالإضافة إلى ذلك، يمكنك العثور على وثائق وأمثلة ومراجع API مفيدة على موقع Aspose الإلكتروني لمساعدتك في تنفيذ المهام المختلفة المتعلقة بملف PDF.