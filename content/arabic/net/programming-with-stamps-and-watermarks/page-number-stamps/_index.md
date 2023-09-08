---
title: طوابع رقم الصفحة في ملف PDF
linktitle: طوابع رقم الصفحة في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة طوابع أرقام الصفحات في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 160
url: /ar/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
في هذا البرنامج التعليمي، سنرشدك خطوة بخطوة حول كيفية إضافة طوابع أرقام الصفحات في ملف PDF باستخدام Aspose.PDF لـ .NET. سنستخدم كود مصدر C# المقدم لفتح مستند PDF موجود، وإنشاء ختم رقم الصفحة، وتعيين خصائصه، وإضافته إلى صفحة معينة في ملف PDF.

## الخطوة 1: تهيئة البيئة

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- بيئة تطوير .NET مثبتة.
- تم تنزيل مكتبة Aspose.PDF الخاصة بـ .NET والإشارة إليها في مشروعك.

## الخطوة 2: تحميل مستند PDF الموجود

الخطوة الأولى هي تحميل مستند PDF الموجود في مشروعك. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// افتح مستند PDF الموجود
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

تأكد من استبدال "دليل المستندات الخاص بك" بالمسار الفعلي للدليل الذي يوجد به مستند PDF الخاص بك.

## الخطوة 3: إنشاء وتكوين ختم ترقيم الصفحات

الآن بعد أن تم تحميل مستند PDF، يمكننا إنشاء مخزن مؤقت لترقيم الصفحات وتكوينه وفقًا لاحتياجاتنا. إليك الطريقة:

```csharp
// إنشاء مخزن مؤقت لرقم الصفحة
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// تحديد ما إذا كان المخزن المؤقت في الخلفية أم لا
pageNumberStamp.Background = false;

// تنسيق المخزن المؤقت لترقيم الصفحات
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;

// الهامش السفلي للمخزن المؤقت لترقيم الصفحات
pageNumberStamp.BottomMargin = 10;

// محاذاة أفقية للمخزن المؤقت لترقيم الصفحات
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;

// بداية ترقيم الصفحات
pageNumberStamp.StartingNumber = 1;

// تعيين خصائص النص المخزن المؤقت لرقم الصفحة
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

يقوم الكود أعلاه بإنشاء طابع رقم الصفحة بخصائص مثل تنسيق رقم الصفحة والهامش السفلي والمحاذاة الأفقية ورقم البداية وخصائص النص.

## الخطوة 4: إضافة ختم رقم الصفحة إلى صفحة معينة

بمجرد تكوين ختم رقم الصفحة، يمكننا إضافته إلى صفحة معينة من مستند PDF. إليك الطريقة:

```csharp
// إضافة المخزن المؤقت لرقم الصفحة إلى صفحة معينة
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

يضيف الكود أعلاه ختم رقم الصفحة إلى الصفحة الأولى من مستند PDF. يمكنك تغيير رقم الصفحة حسب الحاجة.

## الخطوة 5: حفظ مستند PDF المعدل

بمجرد إضافة ختم رقم الصفحة إلى مستند PDF، يمكننا حفظ مستند PDF المعدل. إليك الطريقة:

```csharp
// احفظ مستند PDF المعدل
pdfDocument.Save(dataDir + "PageNumberStamp_out.pdf");
```

تأكد من استبدال "دليل المستندات الخاص بك" بالمسار الفعلي للدليل الذي تريد حفظ مستند PDF المحرر فيه.

### نموذج التعليمات البرمجية المصدر لطوابع أرقام الصفحات باستخدام Aspose.PDF لـ .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح المستند
Document pdfDocument = new Document(dataDir+ "PageNumberStamp.pdf");

// إنشاء ختم رقم الصفحة
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// ما إذا كان الختم هو الخلفية
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

// إضافة طابع إلى صفحة معينة
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
dataDir = dataDir + "PageNumberStamp_out.pdf";

// حفظ مستند الإخراج
pdfDocument.Save(dataDir);
Console.WriteLine("\nPage number stamp added successfully.\nFile saved at " + dataDir);

```

## خاتمة

تهنئة ! لقد تعلمت كيفية إضافة طوابع أرقام الصفحات إلى مستند PDF باستخدام Aspose.PDF لـ .NET. يمكنك الآن تخصيص مستندات PDF الخاصة بك عن طريق إضافة أرقام صفحات واضحة وغنية بالمعلومات.

### الأسئلة الشائعة حول طوابع أرقام الصفحات في ملف PDF

#### س: ما هو ختم رقم الصفحة، وكيف يتم استخدامه لإضافة أرقام الصفحات إلى ملف PDF؟

ج: يعد ختم رقم الصفحة إحدى الميزات الموجودة في Aspose.PDF والتي تسمح لك بإضافة أرقام صفحات ديناميكية إلى صفحات محددة من مستند PDF. في هذا البرنامج التعليمي، يتم تحقيق ذلك عن طريق إنشاء كائن PageNumberStamp، وتكوين خصائصه، وإضافته إلى صفحة معينة.

#### س: كيف ينجز كود مصدر C# المقدم إضافة طوابع أرقام الصفحات إلى ملف PDF؟

ج: يوضح الكود كيفية تحميل مستند PDF موجود، وإنشاء PageNumberStamp، وتعيين خصائص مختلفة (مثل التنسيق، والخط، والمحاذاة، وما إلى ذلك)، ثم إضافة الختم إلى صفحة معينة. يقوم الختم تلقائيًا بحساب إجمالي عدد الصفحات وإدراج أرقام الصفحات الصحيحة.

#### س: هل يمكنني تخصيص مظهر رقم الصفحة، مثل نمط الخط واللون والحجم؟

ج: بالتأكيد، يمكنك تخصيص مظهر ختم رقم الصفحة عن طريق ضبط خصائص مثل الخط وحجم الخط ونمط الخط (غامق ومائل وما إلى ذلك) ولون النص.

#### س: هل من الممكن إضافة طوابع أرقام الصفحات إلى صفحات متعددة داخل مستند PDF؟

ج: نعم، يمكنك إضافة طوابع أرقام الصفحات إلى صفحات متعددة عن طريق إنشاء كائنات PageNumberStamp متعددة وإضافة كل منها إلى الصفحات المطلوبة.

#### س: هل يمكنني اختيار ظهور ختم رقم الصفحة كجزء من محتوى الصفحة أو كعنصر خلفية؟

 ج: نعم، يمكنك التحكم في ظهور ختم رقم الصفحة كجزء من محتوى الصفحة أو كعنصر خلفية عن طريق ضبط الإعداد`Background` خاصية PageNumberStamp.

#### س: كيف يمكنني تحديد تنسيق رقم الصفحة، بما في ذلك إجمالي عدد الصفحات؟

 ج: يستخدم الكود`Format`خاصية PageNumberStamp لتحديد تنسيق رقم الصفحة. يتم استخدام الماكرو "# of" لتمثيل إجمالي عدد الصفحات.

#### س: ماذا يحدث إذا قمت بإضافة نفس ختم رقم الصفحة إلى صفحات متعددة؟

ج: ستؤدي إضافة نفس مثيل PageNumberStamp إلى صفحات متعددة إلى عرض أرقام الصفحات الصحيحة لكل صفحة. يقوم الختم تلقائيًا بضبط رقم الصفحة وإجمالي عدد الصفحات.

#### س: هل يمكنني إضافة طوابع أرقام الصفحات إلى أقسام الرأس أو التذييل في مستند PDF؟

ج: بينما تتم عادةً إضافة PageNumberStamps مباشرة إلى محتوى الصفحة، يمكنك استخدام FloatingBox أو تقنيات أخرى لوضعها في أقسام الرأس أو التذييل.

#### س: كيف أحدد موضع ختم رقم الصفحة على الصفحة؟

 ج: ال`BottomMargin` و`HorizontalAlignment` تسمح لك خصائص PageNumberStamp بالتحكم في موضع الختم داخل الصفحة.

#### س: ماذا لو كنت أرغب في بدء ترقيم الصفحات من رقم مختلف بدلاً من الرقم 1؟

 ج: يمكنك ضبط`StartingNumber`خاصية PageNumberStamp لتحديد رقم صفحة البداية.