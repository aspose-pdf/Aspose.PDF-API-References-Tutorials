---
title: أضف طابع التاريخ والوقت في ملف PDF
linktitle: أضف طابع التاريخ والوقت في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة طابع التاريخ والوقت في ملف PDF بسهولة باستخدام Aspose.PDF for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
في هذه المقالة ، سوف نأخذك خطوة بخطوة حول كيفية إضافة طابع التاريخ والوقت في ملف PDF باستخدام Aspose.PDF for .NET. سنوضح لك كيفية استخدام كود المصدر C # المقدم لإضافة طابع التاريخ والوقت إلى ملف PDF موجود.

## متطلبات

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- بيئة تطوير .NET مثبتة.
- تم تنزيل مكتبة Aspose.PDF لـ .NET والمشار إليها في مشروعك.

## الخطوة الأولى: تهيئة البيئة

قبل أن تتمكن من إضافة طابع التاريخ والوقت إلى مستند PDF ، تحتاج إلى إعداد بيئة التطوير الخاصة بك. فيما يلي الخطوات التي يجب اتباعها:

1. افتح IDE المفضل لديك (بيئة التطوير المتكاملة).
2. إنشاء مشروع C # جديد.
3. تأكد من إضافة مرجع إلى مكتبة Aspose.PDF لـ .NET.

## الخطوة 2: إضافة مكتبة Aspose.PDF

مطلوب مكتبة Aspose.PDF لـ .NET للعمل مع مستندات PDF في مشروعك.

## الخطوة 3: تحميل مستند PDF

تتمثل الخطوة الأولى لإضافة طابع التاريخ والوقت في تحميل مستند PDF الحالي في مشروعك. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// افتح المستند
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

تأكد من استبدال "دليل المستندات" بالمسار الفعلي للدليل حيث يوجد مستند PDF الخاص بك.

## الخطوة 4: إنشاء طابع التاريخ والوقت

الآن بعد أن قمت بتحميل المستند

  PDF ، يمكنك إنشاء طابع التاريخ والوقت لإضافته. هيريس كيفية القيام بذلك:

```csharp
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt");

// قم بإنشاء مخزن نصي
TextStamp textStamp = new TextStamp(annotationText);
```

يقوم الكود أعلاه بإنشاء مخزن نص جديد يحتوي على التاريخ والوقت الحاليين.

## الخطوة 5: تكوين خصائص الطوابع

قبل إضافة الختم إلى مستند PDF ، يمكنك تكوين خصائص متنوعة للختم ، مثل الهامش ، والمحاذاة الأفقية والرأسية ، وما إلى ذلك ، وإليك الطريقة:

```csharp
// تعيين خصائص المخزن المؤقت
textStamp.BottomMargin = 10;
textStamp. RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

يمكنك تعديل هذه الخصائص وفقًا لاحتياجاتك.

## الخطوة السادسة: إضافة طابع إلى ملف PDF

الآن وبعد أن أصبح طابع التاريخ والوقت جاهزًا ، يمكنك إضافته إلى صفحة معينة من مستند PDF. إليك الطريقة:

```csharp
// أضف الختم إلى مجموعة طوابع الصفحة
pdfDocument.Pages[1].AddStamp(textStamp);
```

يضيف الرمز أعلاه الطابع إلى الصفحة الأولى من مستند PDF. يمكنك تحديد صفحة أخرى إذا لزم الأمر.

## الخطوة 7: احفظ المستند الناتج

بمجرد إضافة طابع التاريخ والوقت ، يمكنك حفظ مستند PDF المعدل. إليك الطريقة:

```csharp
// احفظ المستند الناتج
pdfDocument.Save(dataDir);
```

يحفظ الكود أعلاه مستند PDF المحرر في الدليل المحدد.

### نموذج التعليمات البرمجية المصدر لـ Add Date Time Stamp باستخدام Aspose.PDF for .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح المستند
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");

// إنشاء طابع نصي
TextStamp textStamp = new TextStamp(annotationText);

// تعيين خصائص الطابع
textStamp.BottomMargin = 10;
textStamp.RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// إضافة الطوابع على جمع الطوابع
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

// حفظ وثيقة الإخراج
pdfDocument.Save(dataDir);
Console.WriteLine("\nDate time stamp added successfully.\nFile saved at " + dataDir);  
          
```

## خاتمة

تهنئة ! لقد تعلمت كيفية إضافة طابع التاريخ والوقت باستخدام Aspose.PDF for .NET. يمكنك الآن تطبيق هذه المعرفة على مشاريعك الخاصة لإضافة طوابع التاريخ والوقت إلى مستندات PDF.

### الأسئلة الشائعة حول إضافة طابع زمني للتاريخ في ملف PDF

#### س: ما هو الغرض من إضافة طابع التاريخ والوقت إلى مستند PDF باستخدام Aspose.PDF for .NET؟

ج: تؤدي إضافة طابع التاريخ والوقت إلى مستند PDF إلى تحسين قيمته المعلوماتية من خلال الإشارة إلى وقت تعديل المستند أو إنشائه. هذه الميزة مفيدة لتعقب تغييرات المستند وتوفير نقطة مرجعية لمحفوظات المستند.

#### س: هل يمكنني تخصيص تنسيق طابع التاريخ والوقت لمطابقة متطلبات محددة؟

 ج: نعم ، يمكنك تخصيص تنسيق طابع التاريخ والوقت وفقًا لتفضيلاتك. يستخدم كود المصدر C # المقدم الامتداد`DateTime.Now.ToString()` طريقة لإنشاء الطابع الزمني بتنسيق معين. يمكنك تعديل هذا الرمز لتنسيق الطابع الزمني حسب الحاجة.

#### س: هل من الممكن إضافة طابع التاريخ والوقت إلى موقع معين على صفحة PDF؟

 ج: بالتأكيد ، يمكنك ضبط موضع طابع التاريخ والوقت على صفحة PDF عن طريق تعديل خصائص`TextStamp` هدف. يوضح الكود المقدم في البرنامج التعليمي كيفية تعيين الخصائص مثل الهامش والمحاذاة والموضع الرأسي.

#### س: هل يمكنني إضافة أختام تاريخ ووقت متعددة إلى صفحات مختلفة من نفس مستند PDF؟

 ج: نعم ، يمكنك إضافة أختام تاريخ ووقت متعددة إلى صفحات مختلفة من نفس مستند PDF. ببساطة كرر عملية إنشاء ملف`TextStamp` الكائن وتكوين خصائصه لكل صفحة مطلوبة.

#### س: كيف يمكنني تغيير الخط أو الحجم أو لون نص طابع التاريخ والوقت؟

 ج: لتعديل الخط أو الحجم أو لون نص طابع التاريخ والوقت ، يمكنك تخصيص خصائص ملف`DefaultAppearance` الكائن المستخدم في إنشاء`TextStamp`. اضبط اسم الخط وحجمه وقيم اللون لتحقيق المظهر المطلوب.

#### س: هل من الممكن إضافة أنواع أخرى من التعليقات التوضيحية أو الأختام إلى مستند PDF باستخدام Aspose.PDF لـ .NET؟

ج: نعم ، يوفر Aspose.PDF for .NET نطاقًا واسعًا من أنواع التعليقات التوضيحية التي يمكنك إضافتها إلى مستندات PDF ، بما في ذلك التعليقات التوضيحية النصية والطوابع والخطوط والأشكال والمزيد. يمكنك استكشاف وثائق Aspose.PDF لمزيد من التفاصيل حول التعامل مع التعليقات التوضيحية.

#### س: هل هناك أي قيود أو اعتبارات عند إضافة طابع التاريخ والوقت إلى مستند PDF؟

ج: أثناء إضافة طابع التاريخ والوقت بشكل مباشر ، ضع في اعتبارك عوامل مثل تخطيط المستند والمحتوى الموجود. تأكد من أن وضع الختم لا يحجب المعلومات المهمة أو يؤثر على سهولة قراءة المستند.

#### س: كيف يمكنني دمج هذه الطريقة في مشاريعي الخاصة لإضافة طوابع التاريخ والوقت إلى مستندات PDF؟

ج: لدمج هذه الطريقة ، اتبع الخطوات المتوفرة واضبط الكود ليناسب هيكل مشروعك. يمكنك إضافة أختام التاريخ والوقت إلى مستندات PDF الموجودة لتحسين فائدتها وتوفير مخطط زمني واضح للتغييرات.

#### س: هل يمكنني أتمتة عملية إضافة طوابع التاريخ والوقت إلى مستندات PDF متعددة؟

ج: نعم ، يمكنك أتمتة عملية إضافة طوابع التاريخ والوقت إلى مستندات PDF متعددة عن طريق إنشاء نص أو برنامج يتكرر من خلال قائمة المستندات ويطبق نفس عملية الختم على كل منها.