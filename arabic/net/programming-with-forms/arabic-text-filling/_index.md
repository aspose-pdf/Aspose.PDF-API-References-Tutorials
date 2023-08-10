---
title: تعبئة النص العربي
linktitle: تعبئة النص العربي
second_title: Aspose.PDF لمرجع .NET API
description: قم بتعبئة حقول نموذج PDF بسهولة بالنص العربي باستخدام Aspose.PDF for .NET.
type: docs
weight: 20
url: /ar/net/programming-with-forms/arabic-text-filling/
---
في هذا البرنامج التعليمي ، سوف نتعلم كيفية تعبئة حقل نموذج PDF بالنص العربي باستخدام Aspose.PDF for .NET. Aspose.PDF هي مكتبة قوية تسمح للمطورين بمعالجة مستندات PDF برمجيًا. سنرشدك خلال العملية خطوة بخطوة ، وشرح شفرة المصدر C # المطلوبة لإنجاز هذه المهمة.

## الخطوة 1: تحميل محتوى نموذج PDF

أولاً ، نحتاج إلى تحميل نموذج PDF الذي يحتوي على الحقل الذي نريد ملؤه. نبدأ بتحديد المسار إلى الدليل حيث يوجد النموذج:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 بعد ذلك ، نقوم بإنشاء ملف`FileStream` كائن لقراءة وكتابة ملف النموذج:

```csharp
FileStream fs = new FileStream(dataDir + "FillFormField.pdf", FileMode.Open, FileAccess.ReadWrite);
```

 بعد ذلك ، نقوم بإنشاء مثيل`Document` كائن باستخدام الدفق الذي يحتوي على ملف النموذج:

```csharp
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
```

## الخطوة 2: قم بالوصول إلى حقل TextBoxField

 لملء حقل النموذج بالنص العربي ، نحتاج إلى الوصول إلى البيانات المحددة`TextBoxField` المجال الذي نريد ملؤه. في هذا المثال ، نفترض أن اسم الحقل هو "textbox1". يمكننا استرداد مرجع الحقل باستخدام`Form` ممتلكات`pdfDocument` هدف:

```csharp
TextBoxField txtFld = pdfDocument.Form["textbox1"] as TextBoxField;
```

## الخطوة 3: املأ حقل النموذج بالنص العربي

 الآن بعد أن أصبح لدينا`TextBoxField` مرجع ، يمكننا تخصيص النص العربي له`Value` ملكية:

```csharp
txtFld.Value = "يولد جميع الناس أحراراً متساوين في";
```

## الخطوة 4: احفظ المستند المحدث

أخيرًا ، نحفظ المستند المحدث في ملف جديد:

```csharp
dataDir = dataDir + "ArabicTextFilling_out.pdf";
pdfDocument.Save(dataDir);
```

نعرض أيضًا رسالة للإشارة إلى نجاح ملء النص العربي:

```csharp
Console.WriteLine("\nArabic text successfully filled in the form field.\nFile saved in the following location: " + dataDir);
```

### عينة من التعليمات البرمجية المصدر لتعبئة النص العربي باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// تحميل محتويات نموذج PDF
FileStream fs = new FileStream(dataDir + "FillFormField.pdf", FileMode.Open, FileAccess.ReadWrite);
//إنشاء مثيل المستند مع دفق ملف نموذج الاحتفاظ
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
// احصل على إحالة خاصة إلى TextBoxField
TextBoxField txtFld = pdfDocument.Form["textbox1"] as TextBoxField;
// تعبئة حقل النموذج بالنص العربي
txtFld.Value = "يولد جميع الناس أحراراً متساوين في";
dataDir = dataDir + "ArabicTextFilling_out.pdf";
// احفظ المستند المحدث
pdfDocument.Save(dataDir);
Console.WriteLine("\nArabic text filled successfully in form field.\nFile saved at " + dataDir);
```

## خاتمة

في هذا البرنامج التعليمي ، اكتشفنا كيفية تعبئة حقل نموذج PDF بالنص العربي باستخدام Aspose.PDF for .NET. مررنا خلال العملية خطوة بخطوة وشرحنا شفرة مصدر C # ذات الصلة. باتباع هذه التعليمات ، يمكنك بسهولة دمج وظيفة تعبئة النص العربي في تطبيقات .NET الخاصة بك. إذا كانت لديك أي أسئلة أخرى أو كنت بحاجة إلى مزيد من المعلومات ، فلا تتردد في الاتصال بفريق دعم Aspose.PDF أو تحقق من الموارد الإضافية أدناه.

### التعليمات

#### س: هل يمكنني ملء أنواع أخرى من حقول النموذج بنص عربي باستخدام Aspose.PDF for .NET؟

 ج: نعم ، يمكنك استخدام Aspose.PDF for .NET لملء أنواع أخرى من حقول النموذج بالنص العربي ، مثل مربعات الاختيار وأزرار الاختيار ومربعات التحرير والسرد والمزيد. تشبه العملية ملء أ`TextBoxField` . ما عليك سوى الوصول إلى الحقل المحدد باستخدام اسمه أو معرفه وتعيينه`Value` خاصية النص العربي المطلوب.

#### س: هل Aspose.PDF for .NET متوافق مع النص العربي والكتابة من اليمين إلى اليسار (RTL)؟

ج: نعم ، يدعم Aspose.PDF for .NET بشكل كامل النص العربي وكتابة RTL. يتعامل مع الأحرف العربية ومحاذاة النص بشكل صحيح ، مما يضمن أن مستندات PDF التي تم إنشاؤها تحافظ على التخطيط المرئي الصحيح للغات التي تكتب من اليمين إلى اليسار.

#### س: هل يمكنني استخدام Aspose.PDF for .NET لاستخراج النص العربي من ملفات PDF الموجودة؟

ج: نعم ، يوفر Aspose.PDF for .NET إمكانيات استخراج النص ، مما يسمح لك باستخراج النص العربي من ملفات PDF الموجودة. يمكنك استخراج نص برمجيًا من صفحات معينة أو من المستند بأكمله ، بما في ذلك النص العربي ، باستخدام المكتبة.

#### س: هل يمكنني تخصيص مظهر النص العربي المعبأ في حقل النموذج؟

ج: نعم ، يمكنك تخصيص مظهر النص العربي المعبأ في حقل النموذج باستخدام Aspose.PDF for .NET. يمكنك التحكم في أنماط الخطوط وأحجامها وألوانها وخيارات تنسيق النص الأخرى. يمكنك التأكد من أن النص العربي المعبأ يطابق المظهر الذي تريده في نموذج PDF.

#### س: كيف يمكنني الحصول على دعم أو العثور على موارد إضافية لـ Aspose.PDF لـ .NET؟

ج: يمكنك الحصول على دعم Aspose.PDF لـ .NET من خلال زيارة منتدى دعم Aspose الرسمي أو الاتصال بفريق الدعم الخاص بهم مباشرةً. بالإضافة إلى ذلك ، يمكنك العثور على وثائق وأمثلة ومراجع API مفيدة على موقع Aspose لمساعدتك في تنفيذ المهام المختلفة المتعلقة بـ PDF.