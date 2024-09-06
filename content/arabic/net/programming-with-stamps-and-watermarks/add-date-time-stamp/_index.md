---
title: إضافة طابع التاريخ والوقت في ملف PDF
linktitle: إضافة طابع التاريخ والوقت في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية إضافة طابع التاريخ والوقت بسهولة في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
في هذه المقالة، سنوضح لك خطوة بخطوة كيفية إضافة طابع التاريخ والوقت في ملف PDF باستخدام Aspose.PDF for .NET. وسنوضح لك كيفية استخدام كود المصدر C# المقدم لإضافة طابع التاريخ والوقت إلى ملف PDF موجود.

## متطلبات

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- بيئة تطوير .NET مثبتة.
- تم تنزيل مكتبة Aspose.PDF لـ .NET والإشارة إليها في مشروعك.

## الخطوة 1: إعداد البيئة

قبل أن تتمكن من إضافة طابع التاريخ والوقت إلى مستند PDF، يتعين عليك إعداد بيئة التطوير الخاصة بك. فيما يلي الخطوات التي يجب اتباعها:

1. افتح بيئة التطوير المتكاملة المفضلة لديك.
2. إنشاء مشروع C# جديد.
3. تأكد من أنك قمت بإضافة مرجع إلى مكتبة Aspose.PDF لـ .NET.

## الخطوة 2: إضافة مكتبة Aspose.PDF

تعتبر مكتبة Aspose.PDF لـ .NET ضرورية للعمل مع مستندات PDF في مشروعك.

## الخطوة 3: تحميل مستند PDF

الخطوة الأولى لإضافة طابع التاريخ والوقت هي تحميل مستند PDF الموجود في مشروعك. وإليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// افتح المستند
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

تأكد من استبدال "دليل المستندات الخاص بك" بالمسار الفعلي إلى الدليل الذي يوجد به مستند PDF الخاص بك.

## الخطوة 4: إنشاء طابع التاريخ والوقت

الآن بعد أن قمت بتحميل المستند

  PDF، يمكنك إنشاء طابع التاريخ والوقت لإضافته. وإليك كيفية القيام بذلك:

```csharp
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt");

// إنشاء مخزن نصي
TextStamp textStamp = new TextStamp(annotationText);
```

يقوم الكود أعلاه بإنشاء مخزن نص جديد يحتوي على التاريخ والوقت الحاليين.

## الخطوة 5: تكوين خصائص الطوابع

قبل إضافة الطابع إلى مستند PDF، يمكنك تكوين خصائص مختلفة للطابع، مثل الهامش والمحاذاة الأفقية والرأسية، وما إلى ذلك. وإليك الطريقة:

```csharp
// تعيين خصائص المخزن المؤقت
textStamp.BottomMargin = 10;
textStamp. RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

يمكنك تعديل هذه الخصائص وفقًا لاحتياجاتك.

## الخطوة 6: إضافة الطابع إلى ملف PDF

الآن بعد أن أصبح ختم التاريخ والوقت جاهزًا، يمكنك إضافته إلى صفحة معينة من مستند PDF. إليك الطريقة:

```csharp
// أضف الطابع إلى مجموعة الطوابع الخاصة بالصفحة
pdfDocument.Pages[1].AddStamp(textStamp);
```

يضيف الكود أعلاه الطابع إلى الصفحة الأولى من مستند PDF. يمكنك تحديد صفحة أخرى إذا لزم الأمر.

## الخطوة 7: احفظ المستند الناتج

بمجرد إضافة طابع التاريخ والوقت، يمكنك حفظ مستند PDF المعدّل. إليك الطريقة:

```csharp
// حفظ المستند الناتج
pdfDocument.Save(dataDir);
```

يقوم الكود أعلاه بحفظ مستند PDF المحرر في الدليل المحدد.

### عينة من كود المصدر لإضافة طابع التاريخ والوقت باستخدام Aspose.PDF لـ .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// فتح المستند
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");

// إنشاء ختم نصي
TextStamp textStamp = new TextStamp(annotationText);

// تعيين خصائص الطوابع
textStamp.BottomMargin = 10;
textStamp.RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// إضافة طابع إلى مجموعة الطوابع
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

// حفظ المستند الناتج
pdfDocument.Save(dataDir);
Console.WriteLine("\nDate time stamp added successfully.\nFile saved at " + dataDir);  
          
```

## خاتمة

تهانينا! لقد تعلمت كيفية إضافة طابع التاريخ والوقت باستخدام Aspose.PDF لـ .NET. يمكنك الآن تطبيق هذه المعرفة على مشاريعك الخاصة لإضافة طابع التاريخ والوقت إلى مستندات PDF.

### الأسئلة الشائعة حول إضافة طابع التاريخ والوقت في ملف PDF

#### س: ما هو الغرض من إضافة طابع التاريخ والوقت إلى مستند PDF باستخدام Aspose.PDF لـ .NET؟

ج: إن إضافة ختم التاريخ والوقت إلى مستند PDF يعزز قيمته المعلوماتية من خلال الإشارة إلى وقت تعديل المستند أو إنشائه. تعد هذه الميزة مفيدة لتتبع تغييرات المستند وتوفير نقطة مرجعية لسجل المستند.

#### س: هل يمكنني تخصيص تنسيق طابع التاريخ والوقت لتتناسب مع متطلبات محددة؟

 ج: نعم، يمكنك تخصيص تنسيق طابع التاريخ والوقت وفقًا لتفضيلاتك. يستخدم كود المصدر C# المقدم`DateTime.Now.ToString()` طريقة لإنشاء الطابع الزمني بتنسيق معين. يمكنك تعديل هذا الكود لتنسيق الطابع الزمني حسب الحاجة.

#### س: هل من الممكن إضافة طابع التاريخ والوقت إلى موقع محدد على صفحة PDF؟

 ج: بالتأكيد، يمكنك تعديل موضع طابع التاريخ والوقت على صفحة PDF عن طريق تعديل خصائص`TextStamp` يوضح الكود المقدم في البرنامج التعليمي كيفية تعيين خصائص مثل الهامش والمحاذاة والموضع الرأسي.

#### س: هل يمكنني إضافة عدة طوابع تاريخ ووقت إلى صفحات مختلفة من نفس مستند PDF؟

 ج: نعم، يمكنك إضافة عدة طوابع تاريخ ووقت إلى صفحات مختلفة من نفس مستند PDF. ما عليك سوى تكرار عملية إنشاء`TextStamp` الكائن وتكوين خصائصه لكل صفحة مطلوبة.

#### س: كيف يمكنني تغيير الخط أو الحجم أو لون نص ختم التاريخ والوقت؟

 أ: لتعديل الخط أو الحجم أو لون نص ختم التاريخ والوقت، يمكنك تخصيص خصائص`DefaultAppearance` الكائن المستخدم لإنشاء`TextStamp`. قم بضبط اسم الخط وحجمه وقيم اللون لتحقيق المظهر المطلوب.

#### س: هل من الممكن إضافة أنواع أخرى من التعليقات أو الطوابع إلى مستند PDF باستخدام Aspose.PDF لـ .NET؟

ج: نعم، يوفر Aspose.PDF for .NET مجموعة واسعة من أنواع التعليقات التوضيحية التي يمكنك إضافتها إلى مستندات PDF، بما في ذلك التعليقات التوضيحية النصية والطوابع والخطوط والأشكال والمزيد. يمكنك استكشاف وثائق Aspose.PDF لمزيد من التفاصيل حول العمل مع التعليقات التوضيحية.

#### س: هل هناك أي قيود أو اعتبارات عند إضافة طابع التاريخ والوقت إلى مستند PDF؟

ج: على الرغم من أن إضافة ختم التاريخ والوقت أمر بسيط، إلا أنه يجب مراعاة عوامل مثل تصميم المستند والمحتوى الموجود. تأكد من أن وضع الختم لا يحجب المعلومات المهمة أو يؤثر على قابلية قراءة المستند.

#### س: كيف يمكنني دمج هذه الطريقة في مشاريعي الخاصة لإضافة طوابع التاريخ والوقت إلى مستندات PDF؟

ج: لدمج هذه الطريقة، اتبع الخطوات المقدمة واضبط الكود ليناسب بنية مشروعك. يمكنك إضافة طوابع التاريخ والوقت إلى مستندات PDF الموجودة لتعزيز فائدتها وتوفير جدول زمني واضح للتغييرات.

#### س: هل يمكنني أتمتة عملية إضافة طوابع التاريخ والوقت إلى مستندات PDF متعددة؟

ج: نعم، يمكنك أتمتة عملية إضافة طوابع التاريخ والوقت إلى مستندات PDF متعددة عن طريق إنشاء نص برمجي أو برنامج يتكرر عبر قائمة المستندات ويطبق نفس عملية الختم على كل منها.