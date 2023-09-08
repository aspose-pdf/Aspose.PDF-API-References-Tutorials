---
title: إضافة شرح PDF
linktitle: إضافة تعليق توضيحي
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة تعليقات توضيحية نصية بتنسيق PDF باستخدام Aspose.PDF لـ .NET باستخدام كود مصدر C# هذا. قم بتخصيص التعليقات التوضيحية الخاصة بك بتفاصيل وأيقونات محددة.
type: docs
weight: 10
url: /ar/net/annotations/addannotation/
---
تعد إضافة التعليقات التوضيحية إلى مستندات PDF ميزة قوية يمكنها تحسين عمليات التعاون والمراجعة. يسهل Aspose.PDF for .NET إضافة التعليقات التوضيحية برمجيًا إلى مستندات PDF باستخدام لغة C#. في هذا الدليل، سنشرح خطوة بخطوة كيفية استخدام Aspose.PDF لـ .NET لإضافة التعليقات التوضيحية إلى مستند PDF.

## الخطوة 1: إنشاء مشروع جديد وتثبيت Aspose.PDF لـ .NET

قبل أن نبدأ في كتابة التعليمات البرمجية لإضافة التعليقات التوضيحية، نحتاج إلى إنشاء مشروع جديد وتثبيت Aspose.PDF لـ .NET. لتثبيت Aspose.PDF لـ .NET، اتبع الخطوات التالية:

1. افتح Visual Studio وقم بإنشاء مشروع C# جديد.
2. انقر بزر الماوس الأيمن على المشروع في Solution Explorer وحدد "إدارة حزم NuGet".
3. ابحث عن "Aspose.PDF" وحدد "تثبيت".

بمجرد اكتمال التثبيت، يمكننا البدء في كتابة الكود.

## الخطوة 2: افتح مستند PDF

الخطوة الأولى في إضافة التعليقات التوضيحية هي فتح مستند PDF. يمكننا استخدام الكود التالي لفتح المستند:

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document pdfDocument = new Document(dataDir + "AddAnnotation.pdf");
```

في هذا الكود، نحدد المسار إلى مستند PDF الذي نريد فتحه. تأكد من استبدال "دليل بياناتك" بالمسار الفعلي لدليل بياناتك.

## الخطوة 3: إنشاء التعليق التوضيحي

 لإضافة تعليق توضيحي، نحتاج إلى إنشاء مثيل جديد لـ`TextAnnotation` فصل. يمكننا استخدام الكود التالي لإنشاء تعليق توضيحي نصي جديد:

```csharp
TextAnnotation textAnnotation = new TextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600));
textAnnotation.Title = "Sample Annotation Title";
textAnnotation.Subject = "Sample Subject";
textAnnotation.State = AnnotationState.Accepted;
textAnnotation.Contents = "Sample contents for the annotation";
textAnnotation.Open = true;
textAnnotation.Icon = TextIcon.Key;
```

في هذا الكود، نقوم بإنشاء تعليق توضيحي نصي جديد في الصفحة الثانية من مستند PDF. نقوم أيضًا بتعيين خصائص العنوان والموضوع والحالة والمحتويات والفتح والرمز للتعليق التوضيحي.

## الخطوة 4: تخصيص التعليق التوضيحي

 يمكننا تخصيص مظهر التعليق التوضيحي باستخدام`Border` فصل. يمكننا استخدام الكود التالي لتخصيص حدود التعليق التوضيحي:

```csharp
Border border = new Border(textAnnotation);
border.Width = 5;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(200, 400, 400, 600);
```

 في هذا الكود نقوم بإنشاء جديد`Border`الكائن وتعيين خصائص العرض والشرطة. نقوم بعد ذلك بتعيين`Border` خاصية الشرح للجديد`Border` هدف. وأخيراً قمنا بتعيين`Rect` خاصية التعليق التوضيحي لتحديد موضعه وحجمه.

## الخطوة 5: أضف التعليق التوضيحي إلى مستند PDF

بمجرد إنشاء التعليق التوضيحي وتخصيصه، نحتاج إلى إضافته إلى مستند PDF. يمكننا استخدام الكود التالي لإضافة التعليق التوضيحي إلى مستند PDF:

```csharp
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
```

في هذا الكود، نضيف التعليق التوضيحي إلى مجموعة التعليقات التوضيحية للصفحة الثانية من مستند PDF.

## الخطوة 6: احفظ ملف الإخراج

أخيرًا، نحتاج إلى حفظ مستند PDF مع التعليق التوضيحي المُضاف. يمكننا استخدام الكود التالي لحفظ ملف الإخراج:

```csharp
dataDir = dataDir + "AddAnnotation_out.pdf";
pdfDocument.Save(dataDir);
```
### مثال على التعليمات البرمجية المصدر لإضافة تعليق توضيحي باستخدام Aspose.PDF لـ .NET


```csharp   
 // المسار إلى دليل المستندات.
string dataDir = "YOUR DATA DIRECTORY";

// افتح المستند
Document pdfDocument = new Document(dataDir + "AddAnnotation.pdf");

// إنشاء تعليق توضيحي
TextAnnotation textAnnotation = new TextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600));
textAnnotation.Title = "Sample Annotation Title";
textAnnotation.Subject = "Sample Subject";
textAnnotation.State = AnnotationState.Accepted;
textAnnotation.Contents = "Sample contents for the annotation";
textAnnotation.Open = true;
textAnnotation.Icon = TextIcon.Key;

Border border = new Border(textAnnotation);
border.Width = 5;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(200, 400, 400, 600);

// أضف تعليقًا توضيحيًا في مجموعة التعليقات التوضيحية للصفحة
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddAnnotation_out.pdf";
// حفظ ملف الإخراج
pdfDocument.Save(dataDir);
```
يوضح هذا الرمز كيفية إضافة تعليق توضيحي نصي بعنوان وموضوع وحالة ومحتويات وأيقونة محددة إلى صفحة PDF باستخدام Aspose.PDF لـ .NET. يمكنك تعديل هذا الرمز وفقًا لمتطلباتك لإضافة التعليقات التوضيحية إلى مستندات PDF الخاصة بك. فقط تذكر استبدال دليل البيانات الخاص بك بمسار الدليل الفعلي حيث يوجد ملف PDF الخاص بك والمكان الذي تريد حفظ ملف الإخراج فيه.

## خاتمة

توفر إضافة التعليقات التوضيحية إلى مستندات PDF باستخدام Aspose.PDF لـ .NET أداة قيمة لتعزيز التعاون في المستندات وعمليات المراجعة. باتباع الدليل التفصيلي المقدم في هذه المقالة، يمكن للمطورين دمج إمكانات التعليقات التوضيحية بسلاسة في تطبيقات C# الخاصة بهم.

### الأسئلة الشائعة

#### س: ما أنواع التعليقات التوضيحية التي يمكن إضافتها باستخدام Aspose.PDF لـ .NET؟

ج: يدعم Aspose.PDF for .NET أنواعًا مختلفة من التعليقات التوضيحية، بما في ذلك التعليقات التوضيحية النصية والطوابع والروابط والأشكال والمزيد. يمكن للمطورين تخصيص مظهر وخصائص هذه التعليقات التوضيحية لتناسب احتياجاتهم الخاصة.

#### س: هل يمكنني إضافة تعليقات توضيحية إلى صفحات معينة في مستند PDF متعدد الصفحات؟

ج: نعم، Aspose.PDF for .NET يسمح لك بتحديد الصفحة التي تريد إضافة التعليق التوضيحي إليها. يمكنك اختيار صفحة معينة أو إضافة تعليقات توضيحية إلى صفحات متعددة حسب الحاجة.

#### س: كيف يمكنني تخصيص مظهر التعليقات التوضيحية؟

ج: يمكن تخصيص التعليقات التوضيحية باستخدام خصائص مثل عرض الحدود واللون ونمط الشرطة ونمط النص والمزيد. يوفر Aspose.PDF for .NET مجموعة غنية من الخيارات لتخصيص مظهر التعليقات التوضيحية.

#### س: هل من الممكن إضافة ارتباطات تشعبية كتعليقات توضيحية باستخدام Aspose.PDF لـ .NET؟

ج: نعم، يمكنك إضافة ارتباطات تشعبية كتعليقات توضيحية إلى مستندات PDF باستخدام Aspose.PDF لـ .NET. يمكن استخدام التعليقات التوضيحية للارتباط التشعبي للارتباط بعناوين URL الخارجية أو مواقع محددة داخل نفس المستند.

#### س: هل يمكن إضافة التعليقات التوضيحية إلى مستندات PDF الموجودة دون تغيير المحتوى الأصلي؟

ج: نعم، يضيف Aspose.PDF for .NET التعليقات التوضيحية كعناصر إضافية دون تغيير المحتوى الأصلي لمستند PDF. يبقى محتوى PDF الأصلي كما هو.