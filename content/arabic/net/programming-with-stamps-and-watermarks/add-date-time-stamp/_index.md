---
title: إضافة طابع التاريخ والوقت في ملف PDF
linktitle: إضافة طابع التاريخ والوقت في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة طابع التاريخ والوقت بسهولة إلى ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
في هذه المقالة، سنأخذك خطوة بخطوة حول كيفية إضافة طابع التاريخ والوقت في ملف PDF باستخدام Aspose.PDF لـ .NET. سنوضح لك كيفية استخدام كود مصدر C# المقدم لإضافة طابع التاريخ والوقت إلى ملف PDF موجود.

## متطلبات

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- بيئة تطوير .NET مثبتة.
- تم تنزيل مكتبة Aspose.PDF الخاصة بـ .NET والإشارة إليها في مشروعك.

## الخطوة 1: تهيئة البيئة

قبل أن تتمكن من إضافة طابع التاريخ والوقت إلى مستند PDF، تحتاج إلى إعداد بيئة التطوير الخاصة بك. فيما يلي الخطوات التي يجب اتباعها:

1. افتح IDE المفضل لديك (بيئة التطوير المتكاملة).
2. إنشاء مشروع C# جديد.
3. تأكد من إضافة مرجع إلى مكتبة Aspose.PDF لـ .NET.

## الخطوة 2: إضافة مكتبة Aspose.PDF

مكتبة Aspose.PDF لـ .NET مطلوبة للعمل مع مستندات PDF في مشروعك.

## الخطوة 3: تحميل وثيقة PDF

الخطوة الأولى لإضافة طابع التاريخ والوقت هي تحميل مستند PDF الموجود في مشروعك. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// افتح المستند
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

تأكد من استبدال "دليل المستندات الخاص بك" بالمسار الفعلي للدليل الذي يوجد به مستند PDF الخاص بك.

## الخطوة 4: إنشاء طابع التاريخ والوقت

الآن بعد أن قمت بتحميل المستند

  PDF، يمكنك إنشاء طابع التاريخ والوقت لإضافته. هيريس كيفية القيام بذلك:

```csharp
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt");

// إنشاء مخزن مؤقت للنص
TextStamp textStamp = new TextStamp(annotationText);
```

يقوم الكود أعلاه بإنشاء مخزن مؤقت نصي جديد يحتوي على التاريخ والوقت الحاليين.

## الخطوة 5: تكوين خصائص الطوابع

قبل إضافة الختم إلى مستند PDF، يمكنك تكوين خصائص مختلفة للختم، مثل الهامش والمحاذاة الأفقية والرأسية وما إلى ذلك. وإليك الطريقة:

```csharp
// تعيين خصائص المخزن المؤقت
textStamp.BottomMargin = 10;
textStamp. RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

يمكنك ضبط هذه الخصائص وفقًا لاحتياجاتك.

## الخطوة 6: إضافة ختم إلى PDF

الآن بعد أن أصبح طابع التاريخ والوقت جاهزًا، يمكنك إضافته إلى صفحة معينة من مستند PDF. إليك الطريقة:

```csharp
// أضف الختم إلى مجموعة الطوابع الخاصة بالصفحة
pdfDocument.Pages[1].AddStamp(textStamp);
```

يضيف الكود أعلاه الختم إلى الصفحة الأولى من مستند PDF. يمكنك تحديد صفحة أخرى إذا لزم الأمر.

## الخطوة 7: احفظ مستند الإخراج

بمجرد إضافة طابع التاريخ والوقت، يمكنك حفظ مستند PDF المعدل. إليك الطريقة:

```csharp
// احفظ مستند الإخراج
pdfDocument.Save(dataDir);
```

يحفظ الكود أعلاه مستند PDF المحرر في الدليل المحدد.

### نموذج التعليمات البرمجية المصدر لإضافة طابع زمني باستخدام Aspose.PDF لـ .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح المستند
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");

// إنشاء ختم النص
TextStamp textStamp = new TextStamp(annotationText);

// تعيين خصائص الطوابع
textStamp.BottomMargin = 10;
textStamp.RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// إضافة ختم على جمع الطوابع
pdfDocument.Pages[1].AddStamp(textStamp);
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 6, System.Drawing.Color.Black);
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(0, 0, 0, 0), default_appearance);
textAnnotation.Name = "Stamp";
textAnnotation.Accept(new AnnotationSelector(textAnnotation));
textAnnotation.Contents = textStamp.Value;

Border border = new Border(textAnnotation);
border.Width = 0;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(0, 0, 0, 0);
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddDateTimeStamp_out.pdf";

// حفظ مستند الإخراج
pdfDocument.Save(dataDir);
Console.WriteLine("\nDate time stamp added successfully.\nFile saved at " + dataDir);  
          
```

## خاتمة

تهنئة ! لقد تعلمت كيفية إضافة طابع التاريخ والوقت باستخدام Aspose.PDF لـ .NET. يمكنك الآن تطبيق هذه المعرفة على مشاريعك الخاصة لإضافة طوابع التاريخ والوقت إلى مستندات PDF.

### الأسئلة الشائعة لإضافة طابع التاريخ والوقت في ملف PDF

#### س: ما هو الغرض من إضافة طابع التاريخ والوقت إلى مستند PDF باستخدام Aspose.PDF لـ .NET؟

ج: تؤدي إضافة طابع التاريخ والوقت إلى مستند PDF إلى تحسين قيمته المعلوماتية من خلال الإشارة إلى وقت تعديل المستند أو إنشائه. تعد هذه الميزة مفيدة لتتبع تغييرات المستند وتوفير نقطة مرجعية لتاريخ المستند.

#### س: هل يمكنني تخصيص تنسيق طابع التاريخ والوقت ليتوافق مع متطلبات محددة؟

 ج: نعم، يمكنك تخصيص تنسيق طابع التاريخ والوقت وفقًا لتفضيلاتك. يستخدم كود مصدر C# المقدم`DateTime.Now.ToString()` طريقة لإنشاء الطابع الزمني بتنسيق معين. يمكنك تعديل هذا الرمز لتنسيق الطابع الزمني حسب الحاجة.

#### س: هل من الممكن إضافة طابع التاريخ والوقت إلى موقع محدد على صفحة PDF؟

 ج: بالتأكيد، يمكنك ضبط موضع طابع التاريخ والوقت على صفحة PDF عن طريق تعديل خصائص الملف`TextStamp` هدف. يوضح الكود الموجود في البرنامج التعليمي كيفية تعيين خصائص مثل الهامش والمحاذاة والموضع الرأسي.

#### س: هل يمكنني إضافة طوابع التاريخ والوقت المتعددة إلى صفحات مختلفة من نفس مستند PDF؟

 ج: نعم، يمكنك إضافة طوابع التاريخ والوقت المتعددة إلى صفحات مختلفة من نفس مستند PDF. ما عليك سوى تكرار عملية إنشاء ملف`TextStamp` الكائن وتكوين خصائصه لكل صفحة مرغوبة.

#### س: كيف يمكنني تغيير الخط أو الحجم أو اللون لنص طابع التاريخ والوقت؟

 ج: لتعديل الخط أو الحجم أو اللون لنص طابع التاريخ والوقت، يمكنك تخصيص خصائص الملف`DefaultAppearance` الكائن المستخدم لإنشاء`TextStamp`. اضبط اسم الخط وحجمه وقيم اللون لتحقيق المظهر المطلوب.

#### س: هل من الممكن إضافة أنواع أخرى من التعليقات التوضيحية أو الطوابع إلى مستند PDF باستخدام Aspose.PDF لـ .NET؟

ج: نعم، يوفر Aspose.PDF for .NET نطاقًا واسعًا من أنواع التعليقات التوضيحية التي يمكنك إضافتها إلى مستندات PDF، بما في ذلك التعليقات التوضيحية النصية والطوابع والخطوط والأشكال والمزيد. يمكنك استكشاف وثائق Aspose.PDF لمزيد من التفاصيل حول التعامل مع التعليقات التوضيحية.

#### س: هل هناك أي قيود أو اعتبارات عند إضافة طابع التاريخ والوقت إلى مستند PDF؟

ج: على الرغم من أن إضافة طابع التاريخ والوقت هو أمر بسيط، إلا أنه يجب مراعاة عوامل مثل تخطيط المستند والمحتوى الموجود. تأكد من أن وضع الختم لا يحجب المعلومات المهمة أو يؤثر على سهولة قراءة المستند.

#### س: كيف يمكنني دمج هذه الطريقة في مشاريعي الخاصة لإضافة طوابع التاريخ والوقت إلى مستندات PDF؟

ج: لدمج هذه الطريقة، اتبع الخطوات المقدمة واضبط الكود ليناسب بنية مشروعك. يمكنك إضافة طوابع التاريخ والوقت إلى مستندات PDF الموجودة لتعزيز فائدتها وتوفير جدول زمني واضح للتغييرات.

#### س: هل يمكنني أتمتة عملية إضافة طوابع التاريخ والوقت إلى مستندات PDF متعددة؟

ج: نعم، يمكنك أتمتة عملية إضافة طوابع التاريخ والوقت إلى مستندات PDF متعددة عن طريق إنشاء برنامج نصي أو برنامج يتكرر خلال قائمة المستندات ويطبق نفس عملية الختم على كل منها.