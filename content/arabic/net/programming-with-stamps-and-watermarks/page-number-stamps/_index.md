---
title: طوابع أرقام الصفحات في ملف PDF
linktitle: طوابع أرقام الصفحات في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية إضافة علامات أرقام الصفحات في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 160
url: /ar/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
في هذا البرنامج التعليمي، سنرشدك خطوة بخطوة حول كيفية إضافة علامات ترقيم الصفحات في ملف PDF باستخدام Aspose.PDF for .NET. سنستخدم كود المصدر C# المقدم لفتح مستند PDF موجود وإنشاء علامة ترقيم الصفحات وتعيين خصائصها وإضافتها إلى صفحة معينة في ملف PDF.

## الخطوة 1: إعداد البيئة

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- بيئة تطوير .NET مثبتة.
- تم تنزيل مكتبة Aspose.PDF لـ .NET والإشارة إليها في مشروعك.

## الخطوة 2: تحميل مستند PDF الموجود

الخطوة الأولى هي تحميل مستند PDF الموجود في مشروعك. وإليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// افتح مستند PDF الموجود
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

تأكد من استبدال "دليل المستندات الخاص بك" بالمسار الفعلي إلى الدليل الذي يوجد به مستند PDF الخاص بك.

## الخطوة 3: إنشاء وتكوين ختم ترقيم الصفحات

الآن بعد تحميل مستند PDF، يمكننا إنشاء مخزن مؤقت لترقيم الصفحات وتكوينه وفقًا لاحتياجاتنا. إليك الطريقة:

```csharp
// إنشاء مخزن مؤقت لأرقام الصفحات
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// تحديد ما إذا كان المخزن المؤقت موجودًا في الخلفية أم لا
pageNumberStamp.Background = false;

// تنسيق مخزن ترقيم الصفحات
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;

// الهامش السفلي لمخزن ترقيم الصفحات
pageNumberStamp.BottomMargin = 10;

// محاذاة أفقية لمخزن ترقيم الصفحات
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;

// رقم بداية ترقيم الصفحات
pageNumberStamp.StartingNumber = 1;

// تعيين خصائص نص المخزن المؤقت لرقم الصفحة
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

يقوم الكود أعلاه بإنشاء ختم رقم الصفحة مع خصائص مثل تنسيق رقم الصفحة، والهامش السفلي، والمحاذاة الأفقية، ورقم البداية وخصائص النص.

## الخطوة 4: إضافة ختم رقم الصفحة إلى صفحة معينة

بمجرد تكوين ختم رقم الصفحة، يمكننا إضافته إلى صفحة معينة من مستند PDF. إليك الطريقة:

```csharp
// إضافة مخزن أرقام الصفحات إلى صفحة معينة
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

يضيف الكود أعلاه ختم رقم الصفحة إلى الصفحة الأولى من مستند PDF. يمكنك تغيير رقم الصفحة حسب الحاجة.

## الخطوة 5: حفظ مستند PDF المعدل

بمجرد إضافة ختم رقم الصفحة إلى مستند PDF، يمكننا حفظ مستند PDF المعدّل. إليك الطريقة:

```csharp
// حفظ مستند PDF المعدل
pdfDocument.Save(dataDir + "PageNumberStamp_out.pdf");
```

تأكد من استبدال "دليل المستندات الخاص بك" بالمسار الفعلي للدليل الذي تريد حفظ مستند PDF المحرر فيه.

### عينة من كود المصدر لطوابع أرقام الصفحات باستخدام Aspose.PDF لـ .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// فتح المستند
Document pdfDocument = new Document(dataDir+ "PageNumberStamp.pdf");

// إنشاء ختم رقم الصفحة
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// هل الختم هو الخلفية
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

// حفظ المستند الناتج
pdfDocument.Save(dataDir);
Console.WriteLine("\nPage number stamp added successfully.\nFile saved at " + dataDir);

```

## خاتمة

تهانينا! لقد تعلمت كيفية إضافة علامات ترقيم الصفحات إلى مستند PDF باستخدام Aspose.PDF for .NET. يمكنك الآن تخصيص مستندات PDF الخاصة بك عن طريق إضافة أرقام صفحات واضحة ومفيدة.

### الأسئلة الشائعة حول طوابع أرقام الصفحات في ملف PDF

#### س: ما هو ختم رقم الصفحة، وكيف يتم استخدامه لإضافة أرقام الصفحات إلى ملف PDF؟

أ: إن ختم رقم الصفحة هو ميزة في Aspose.PDF تتيح لك إضافة أرقام صفحات ديناميكية إلى صفحات معينة من مستند PDF. في هذا البرنامج التعليمي، يتم تحقيق ذلك من خلال إنشاء كائن PageNumberStamp وتكوين خصائصه وإضافته إلى صفحة معينة.

#### س: كيف يقوم كود المصدر C# المقدم بإضافة أختام أرقام الصفحات إلى ملف PDF؟

ج: يوضح الكود كيفية تحميل مستند PDF موجود وإنشاء PageNumberStamp وتعيين خصائص مختلفة (مثل التنسيق والخط والمحاذاة وما إلى ذلك)، ثم إضافة الطابع إلى صفحة معينة. يحسب الطابع تلقائيًا إجمالي عدد الصفحات ويدرج أرقام الصفحات الصحيحة.

#### س: هل يمكنني تخصيص مظهر رقم الصفحة، مثل نمط الخط واللون والحجم؟

ج: بالتأكيد، يمكنك تخصيص مظهر ختم رقم الصفحة عن طريق ضبط خصائص مثل الخط وحجم الخط ونمط الخط (غامق، مائل، وما إلى ذلك) ولون النص.

#### س: هل من الممكن إضافة طوابع أرقام الصفحات إلى صفحات متعددة داخل مستند PDF؟

ج: نعم، يمكنك إضافة طوابع أرقام الصفحات إلى صفحات متعددة عن طريق إنشاء كائنات PageNumberStamp متعددة وإضافة كل منها إلى الصفحات المطلوبة.

#### س: هل يمكنني اختيار ما إذا كان ختم رقم الصفحة يظهر كجزء من محتوى الصفحة أو كعنصر خلفية؟

 ج: نعم، يمكنك التحكم فيما إذا كان طابع رقم الصفحة يظهر كجزء من محتوى الصفحة أو كعنصر خلفية من خلال ضبط`Background` خاصية PageNumberStamp.

#### س: كيف يمكنني تحديد تنسيق رقم الصفحة، بما في ذلك إجمالي عدد الصفحات؟

 أ: يستخدم الكود`Format`خاصية PageNumberStamp لتحديد تنسيق رقم الصفحة. يتم استخدام الماكرو "# of" لتمثيل إجمالي عدد الصفحات.

#### س: ماذا يحدث إذا قمت بإضافة نفس ختم رقم الصفحة إلى صفحات متعددة؟

ج: سيؤدي إضافة نفس نموذج PageNumberStamp إلى صفحات متعددة إلى عرض أرقام الصفحات الصحيحة لكل صفحة. يقوم الطابع تلقائيًا بتعديل رقم الصفحة وإجمالي عدد الصفحات.

#### س: هل يمكنني إضافة طوابع أرقام الصفحات إلى أقسام الرأس أو التذييل في مستند PDF؟

ج: في حين تتم إضافة PageNumberStamps عادةً مباشرةً إلى محتوى الصفحة، يمكنك استخدام FloatingBox أو تقنيات أخرى لوضعها في أقسام الرأس أو التذييل.

#### س: كيف يمكنني تحديد موضع ختم رقم الصفحة على الصفحة؟

 أ: ال`BottomMargin` و`HorizontalAlignment` تسمح لك خصائص PageNumberStamp بالتحكم في موضع الختم داخل الصفحة.

#### س: ماذا لو أردت البدء في ترقيم الصفحات من رقم مختلف بدلاً من 1؟

 أ: يمكنك ضبط`StartingNumber`خاصية PageNumberStamp لتحديد رقم الصفحة الأولية.