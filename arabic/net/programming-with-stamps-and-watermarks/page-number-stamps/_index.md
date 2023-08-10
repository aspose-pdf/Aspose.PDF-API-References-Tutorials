---
title: طوابع رقم الصفحة في ملف PDF
linktitle: طوابع رقم الصفحة في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة أختام رقم الصفحة في ملف PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 160
url: /ar/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
في هذا البرنامج التعليمي ، سنوجهك خطوة بخطوة حول كيفية إضافة أختام رقم الصفحة في ملف PDF باستخدام Aspose.PDF for .NET. سنستخدم الكود المصدري C # المقدم لفتح مستند PDF موجود ، وإنشاء طابع رقم الصفحة ، وتعيين خصائصه ، وإضافته إلى صفحة معينة في ملف PDF.

## الخطوة الأولى: تهيئة البيئة

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- بيئة تطوير .NET مثبتة.
- تم تنزيل مكتبة Aspose.PDF لـ .NET والمشار إليها في مشروعك.

## الخطوة 2: تحميل مستند PDF الحالي

تتمثل الخطوة الأولى في تحميل مستند PDF الحالي في مشروعك. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// افتح مستند PDF الموجود
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

تأكد من استبدال "دليل المستندات" بالمسار الفعلي للدليل حيث يوجد مستند PDF الخاص بك.

## الخطوة 3: إنشاء وتكوين طابع ترقيم الصفحة

الآن بعد أن تم تحميل مستند PDF ، يمكننا إنشاء مخزن مؤقت لترقيم الصفحات وتهيئته وفقًا لاحتياجاتنا. إليك الطريقة:

```csharp
// قم بإنشاء مخزن مؤقت لرقم الصفحة
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// حدد ما إذا كان المخزن المؤقت في الخلفية أم لا
pageNumberStamp.Background = false;

// تنسيق المخزن المؤقت لترقيم الصفحات
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;

// الهامش السفلي من المخزن المؤقت لترقيم الصفحات
pageNumberStamp.BottomMargin = 10;

// المحاذاة الأفقية لمخزن ترقيم الصفحات المؤقت
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;

// رقم بدء ترقيم الصفحات
pageNumberStamp.StartingNumber = 1;

// تعيين خصائص نص المخزن المؤقت لرقم الصفحة
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

يقوم الكود أعلاه بإنشاء طابع رقم الصفحة بخصائص مثل تنسيق رقم الصفحة والهامش السفلي والمحاذاة الأفقية ورقم البداية وخصائص النص.

## الخطوة 4: إضافة طابع رقم الصفحة إلى صفحة معينة

بمجرد تكوين طابع رقم الصفحة ، يمكننا إضافته إلى صفحة معينة من مستند PDF. إليك الطريقة:

```csharp
// أضف المخزن المؤقت لرقم الصفحة إلى صفحة معينة
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

يضيف الكود أعلاه طابع رقم الصفحة إلى الصفحة الأولى من مستند PDF. يمكنك تغيير رقم الصفحة حسب الحاجة.

## الخطوة 5: حفظ مستند PDF المعدل

بمجرد إضافة طابع رقم الصفحة إلى مستند PDF ، يمكننا حفظ مستند PDF المعدل. إليك الطريقة:

```csharp
// احفظ مستند PDF المعدل
pdfDocument.Save(dataDir + "PageNumberStamp_out.pdf");
```

تأكد من استبدال "دليل مستنداتك" بالمسار الفعلي للدليل حيث تريد حفظ مستند PDF المحرر.

### نموذج التعليمات البرمجية المصدر لطوابع رقم الصفحة باستخدام Aspose.PDF لـ .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح المستند
Document pdfDocument = new Document(dataDir+ "PageNumberStamp.pdf");

// إنشاء طابع رقم الصفحة
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// ما إذا كان الطابع هو الخلفية
pageNumberStamp.Background = false;
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;
pageNumberStamp.BottomMargin = 10;
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;
pageNumberStamp.StartingNumber = 1;

// تعيين خصائص النص
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;

// أضف طابعًا إلى صفحة معينة
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
dataDir = dataDir + "PageNumberStamp_out.pdf";

// حفظ وثيقة الإخراج
pdfDocument.Save(dataDir);
Console.WriteLine("\nPage number stamp added successfully.\nFile saved at " + dataDir);

```

## خاتمة

تهنئة ! لقد تعلمت كيفية إضافة أختام رقم الصفحة إلى مستند PDF باستخدام Aspose.PDF for .NET. يمكنك الآن تخصيص مستندات PDF الخاصة بك عن طريق إضافة أرقام صفحات واضحة وغنية بالمعلومات.

### أسئلة وأجوبة لطوابع رقم الصفحة في ملف PDF

#### س: ما هو طابع رقم الصفحة ، وكيف يتم استخدامه لإضافة أرقام الصفحات إلى ملف PDF؟

ج: ختم رقم الصفحة هو ميزة في Aspose.PDF تسمح لك بإضافة أرقام صفحات ديناميكية إلى صفحات معينة من وثيقة PDF. في هذا البرنامج التعليمي ، يتم تحقيق ذلك عن طريق إنشاء كائن PageNumberStamp وتكوين خصائصه وإضافته إلى صفحة معينة.

#### س: كيف يُنجز كود المصدر C # المقدم إضافة طوابع رقم الصفحة إلى ملف PDF؟

ج: يوضح الكود كيفية تحميل مستند PDF موجود وإنشاء PageNumberStamp وتعيين خصائص متنوعة (مثل التنسيق والخط والمحاذاة وما إلى ذلك) ، ثم إضافة الطابع إلى صفحة معينة. يقوم الختم تلقائيًا بحساب إجمالي عدد الصفحات وإدراج أرقام الصفحات الصحيحة.

#### س: هل يمكنني تخصيص مظهر رقم الصفحة ، مثل نمط الخط واللون والحجم؟

ج: بالتأكيد ، يمكنك تخصيص مظهر طابع رقم الصفحة عن طريق ضبط خصائص مثل الخط وحجم الخط ونمط الخط (غامق ومائل وما إلى ذلك) ولون النص.

#### س: هل من الممكن إضافة أختام رقم الصفحة إلى صفحات متعددة داخل مستند PDF؟

ج: نعم ، يمكنك إضافة أختام رقم الصفحة إلى صفحات متعددة عن طريق إنشاء عدة كائنات PageNumberStamp وإضافة كل واحدة إلى الصفحات المطلوبة.

#### س: هل يمكنني اختيار ما إذا كان طابع رقم الصفحة يظهر كجزء من محتوى الصفحة أو كعنصر في الخلفية؟

 ج: نعم ، يمكنك التحكم في ظهور طابع رقم الصفحة كجزء من محتوى الصفحة أو كعنصر في الخلفية من خلال تعيين`Background` خاصية PageNumberStamp.

#### س: كيف يمكنني تحديد تنسيق رقم الصفحة ، بما في ذلك إجمالي عدد الصفحات؟

 ج: يستخدم الرمز الامتداد`Format`خاصية PageNumberStamp لتحديد تنسيق رقم الصفحة. يتم استخدام الماكرو "# من" لتمثيل إجمالي عدد الصفحات.

#### س: ماذا يحدث إذا أضفت نفس طابع رقم الصفحة إلى صفحات متعددة؟

ج: ستؤدي إضافة نفس مثيل PageNumberStamp إلى صفحات متعددة إلى عرض أرقام الصفحات الصحيحة لكل صفحة. يقوم الختم تلقائيًا بضبط رقم الصفحة وإجمالي عدد الصفحات.

#### س: هل يمكنني إضافة أختام رقم الصفحة إلى أقسام الرأس أو التذييل في مستند PDF؟

ج: أثناء إضافة PageNumberStamps عادةً مباشرةً إلى محتوى الصفحة ، يمكنك استخدام FloatingBox أو أساليب أخرى لوضعها في أقسام رأس أو تذييل الصفحة.

#### س: كيف يمكنني تحديد موضع طابع رقم الصفحة على الصفحة؟

 ج: إن`BottomMargin` و`HorizontalAlignment` تسمح لك خصائص PageNumberStamp بالتحكم في موضع الختم داخل الصفحة.

#### س: ماذا لو أردت أن أبدأ ترقيم الصفحات من رقم مختلف بدلاً من 1؟

 ج: يمكنك ضبط ملف`StartingNumber`خاصية PageNumberStamp لتحديد رقم صفحة البداية.