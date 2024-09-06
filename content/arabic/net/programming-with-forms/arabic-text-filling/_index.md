---
title: تعبئة النصوص العربية
linktitle: تعبئة النصوص العربية
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: يمكنك بسهولة ملء حقول نموذج PDF بالنص العربي باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 20
url: /ar/net/programming-with-forms/arabic-text-filling/
---
في هذا البرنامج التعليمي، سنتعلم كيفية ملء حقل نموذج PDF بنص عربي باستخدام Aspose.PDF for .NET. Aspose.PDF هي مكتبة قوية تتيح للمطورين التعامل مع مستندات PDF برمجيًا. سنوضح لك العملية خطوة بخطوة، ونشرح الكود المصدري C# المطلوب لإنجاز هذه المهمة.

## الخطوة 1: تحميل محتوى نموذج PDF

أولاً، نحتاج إلى تحميل نموذج PDF الذي يحتوي على الحقل الذي نريد تعبئته. نبدأ بتحديد المسار إلى الدليل الذي يوجد به النموذج:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 بعد ذلك، نقوم بإنشاء`FileStream` كائن لقراءة وكتابة ملف النموذج:

```csharp
FileStream fs = new FileStream(dataDir + "FillFormField.pdf", FileMode.Open, FileAccess.ReadWrite);
```

 بعد ذلك، نقوم بإنشاء مثيل`Document` الكائن باستخدام التدفق الذي يحتوي على ملف النموذج:

```csharp
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
```

## الخطوة 2: الوصول إلى حقل TextBoxField

 لملء حقل النموذج بالنص العربي، نحتاج إلى الوصول إلى الحقل المحدد`TextBoxField` الحقل الذي نريد تعبئته. في هذا المثال، نفترض أن اسم الحقل هو "textbox1". يمكننا استرداد مرجع الحقل باستخدام`Form` ممتلكات`pdfDocument` هدف:

```csharp
TextBoxField txtFld = pdfDocument.Form["textbox1"] as TextBoxField;
```

## الخطوة 3: املأ حقل النموذج بالنص العربي

 الآن بعد أن أصبح لدينا`TextBoxField` المرجع، يمكننا أن ننسب النص العربي إلى`Value` ملكية:

```csharp
txtFld.Value = "يولد جميع الناس أحراراً متساوين في";
```

## الخطوة 4: احفظ المستند المحدث

وأخيرًا، نحفظ المستند المحدث في ملف جديد:

```csharp
dataDir = dataDir + "ArabicTextFilling_out.pdf";
pdfDocument.Save(dataDir);
```

ونعرض أيضًا رسالة للإشارة إلى نجاح ملء النص العربي:

```csharp
Console.WriteLine("\nArabic text successfully filled in the form field.\nFile saved in the following location: " + dataDir);
```

### عينة من الكود المصدري لملء النص العربي باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//تحميل محتويات نموذج PDF
FileStream fs = new FileStream(dataDir + "FillFormField.pdf", FileMode.Open, FileAccess.ReadWrite);
// إنشاء مثيل مستند باستخدام ملف نموذج يحمل التدفق
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
// الحصول على مرجع لـ TextBoxField معين
TextBoxField txtFld = pdfDocument.Form["textbox1"] as TextBoxField;
// املأ حقل النموذج بالنص العربي
txtFld.Value = "يولد جميع الناس أحراراً متساوين في";
dataDir = dataDir + "ArabicTextFilling_out.pdf";
// حفظ المستند المحدث
pdfDocument.Save(dataDir);
Console.WriteLine("\nArabic text filled successfully in form field.\nFile saved at " + dataDir);
```

## خاتمة

في هذا البرنامج التعليمي، استكشفنا كيفية ملء حقل نموذج PDF بنص عربي باستخدام Aspose.PDF لـ .NET. لقد شرحنا العملية خطوة بخطوة وشرحنا الكود المصدري ذي الصلة بلغة C#. باتباع هذه التعليمات، يمكنك بسهولة دمج وظيفة ملء النص العربي في تطبيقات .NET الخاصة بك. إذا كانت لديك أي أسئلة أخرى أو كنت بحاجة إلى مزيد من المعلومات، فلا تتردد في الاتصال بفريق دعم Aspose.PDF أو تحقق من الموارد الإضافية أدناه.

### الأسئلة الشائعة

#### س: هل يمكنني ملء أنواع أخرى من حقول النموذج بنص عربي باستخدام Aspose.PDF لـ .NET؟

 ج: نعم، يمكنك استخدام Aspose.PDF لـ .NET لملء أنواع أخرى من حقول النماذج بنص عربي، مثل مربعات الاختيار وأزرار الاختيار والمربعات المنسدلة والمزيد. العملية مماثلة لملء نموذج`TextBoxField` . ما عليك سوى الوصول إلى الحقل المحدد باستخدام اسمه أو معرفه وتعيينه`Value`الخاصية إلى النص العربي المطلوب.

#### س: هل Aspose.PDF لـ .NET متوافق مع النص العربي والكتابة من اليمين إلى اليسار (RTL)؟

ج: نعم، يدعم Aspose.PDF for .NET النص العربي والكتابة من اليمين إلى اليسار بشكل كامل. فهو يتعامل مع الأحرف العربية ومحاذاة النص بشكل صحيح، مما يضمن أن مستندات PDF الناتجة تحافظ على التخطيط المرئي الصحيح للغات التي تكتب من اليمين إلى اليسار.

#### س: هل يمكنني استخدام Aspose.PDF لـ .NET لاستخراج النص العربي من ملفات PDF الموجودة؟

ج: نعم، يوفر برنامج Aspose.PDF for .NET إمكانيات استخراج النصوص، مما يسمح لك باستخراج النص العربي من ملفات PDF الموجودة. يمكنك استخراج النص برمجيًا من صفحات معينة أو من المستند بالكامل، بما في ذلك النص العربي، باستخدام المكتبة.

#### س: هل يمكنني تخصيص مظهر النص العربي المملوء في حقل النموذج؟

ج: نعم، يمكنك تخصيص مظهر النص العربي المملوء في حقل النموذج باستخدام Aspose.PDF for .NET. يمكنك التحكم في أنماط الخطوط وأحجامها وألوانها وخيارات تنسيق النص الأخرى. يمكنك التأكد من أن النص العربي المملوء يطابق المظهر الذي تريده في نموذج PDF.

#### س: كيف يمكنني الحصول على الدعم أو العثور على موارد إضافية لـ Aspose.PDF لـ .NET؟

ج: يمكنك الحصول على الدعم لبرنامج Aspose.PDF لـ .NET من خلال زيارة منتدى دعم Aspose الرسمي أو الاتصال بفريق الدعم الخاص بهم مباشرةً. بالإضافة إلى ذلك، يمكنك العثور على وثائق مفيدة وأمثلة ومراجع API على موقع Aspose الإلكتروني لمساعدتك في تنفيذ المهام المختلفة المتعلقة بملفات PDF.