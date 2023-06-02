---
title: أضف تعليقًا توضيحيًا
linktitle: أضف تعليقًا توضيحيًا
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة التعليقات التوضيحية النصية باستخدام Aspose.PDF for .NET باستخدام كود المصدر C #. تخصيص التعليقات التوضيحية الخاصة بك مع التفاصيل والرموز المحددة.
type: docs
weight: 10
url: /ar/net/annotations/addannotation/
---

تعد إضافة التعليقات التوضيحية إلى مستندات PDF ميزة قوية يمكنها تعزيز عمليات التعاون والمراجعة. يجعل Aspose.PDF for .NET من السهل إضافة التعليقات التوضيحية برمجيًا إلى مستندات PDF باستخدام C #. في هذا الدليل ، سنشرح كيفية استخدام Aspose.PDF for .NET خطوة بخطوة لإضافة التعليقات التوضيحية إلى مستند PDF.

## الخطوة 1: قم بإنشاء مشروع جديد وقم بتثبيت Aspose.PDF for .NET

قبل أن نبدأ في كتابة الكود لإضافة التعليقات التوضيحية ، نحتاج إلى إنشاء مشروع جديد وتثبيت Aspose.PDF for .NET. لتثبيت Aspose.PDF for .NET ، اتبع الخطوات التالية:

1. افتح Visual Studio وأنشئ مشروع C # جديد.
2. انقر بزر الماوس الأيمن فوق المشروع في "مستكشف الحلول" وحدد "إدارة حزم NuGet".
3. ابحث عن "Aspose.PDF" واختر "تثبيت".

بمجرد اكتمال التثبيت ، يمكننا البدء في كتابة الكود.

## الخطوة 2: افتح مستند PDF

الخطوة الأولى في إضافة التعليقات التوضيحية هي فتح مستند PDF. يمكننا استخدام الكود التالي لفتح المستند:

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document pdfDocument = new Document(dataDir + "AddAnnotation.pdf");
```

في هذا الكود ، نحدد المسار إلى مستند PDF الذي نريد فتحه. تأكد من استبدال "دليل البيانات الخاص بك" بالمسار الفعلي إلى دليل البيانات.

## الخطوة 3: قم بإنشاء التعليق التوضيحي

 لإضافة تعليق توضيحي ، نحتاج إلى إنشاء مثيل جديد لملف`TextAnnotation` فصل. يمكننا استخدام الكود التالي لإنشاء تعليق توضيحي نصي جديد:

```csharp
TextAnnotation textAnnotation = new TextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600));
textAnnotation.Title = "Sample Annotation Title";
textAnnotation.Subject = "Sample Subject";
textAnnotation.State = AnnotationState.Accepted;
textAnnotation.Contents = "Sample contents for the annotation";
textAnnotation.Open = true;
textAnnotation.Icon = TextIcon.Key;
```

في هذا الرمز ، نقوم بإنشاء تعليق توضيحي نصي جديد في الصفحة الثانية من مستند PDF. نقوم أيضًا بتعيين خصائص العنوان والموضوع والحالة والمحتويات وفتح وأيقونة التعليق التوضيحي.

## الخطوة 4: تخصيص التعليق التوضيحي

 يمكننا تخصيص مظهر التعليق التوضيحي باستخدام امتداد`Border` فصل. يمكننا استخدام الكود التالي لتخصيص حدود التعليق التوضيحي:

```csharp
Border border = new Border(textAnnotation);
border.Width = 5;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(200, 400, 400, 600);
```

 في هذا الرمز ، نقوم بإنشاء ملف`Border` الكائن وتعيين خصائص العرض والشرطة. ثم قمنا بتعيين ملف`Border` خاصية التعليق التوضيحي على الجديد`Border`هدف. أخيرًا ، قمنا بتعيين ملف`Rect` خاصية التعليق التوضيحي لتحديد موقعها وحجمها.

## الخطوة 5: أضف التعليق التوضيحي إلى مستند PDF

بمجرد إنشاء التعليق التوضيحي وتخصيصه ، نحتاج إلى إضافته إلى مستند PDF. يمكننا استخدام الكود التالي لإضافة تعليق توضيحي إلى مستند PDF:

```csharp
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
```

في هذا الرمز ، نضيف التعليق التوضيحي إلى مجموعة التعليقات التوضيحية للصفحة الثانية من مستند PDF.

## الخطوة 6: احفظ ملف الإخراج

أخيرًا ، نحتاج إلى حفظ مستند PDF مع التعليق التوضيحي الإضافي. يمكننا استخدام الكود التالي لحفظ ملف الإخراج:

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

// أنشئ تعليقًا توضيحيًا
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

// أضف تعليقًا توضيحيًا في مجموعة التعليقات التوضيحية بالصفحة
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddAnnotation_out.pdf";
// حفظ ملف الإخراج
pdfDocument.Save(dataDir);
```
يوضح هذا الرمز كيفية إضافة تعليق توضيحي نصي بعنوان محدد وموضوع وحالة ومحتويات وأيقونة إلى صفحة PDF باستخدام Aspose.PDF for .NET. يمكنك تعديل هذا الرمز وفقًا لمتطلباتك لإضافة التعليقات التوضيحية إلى مستندات PDF الخاصة بك. فقط تذكر استبدال دليل البيانات الخاص بك بمسار الدليل الفعلي حيث يوجد ملف PDF الخاص بك والمكان الذي تريد حفظ ملف الإخراج فيه.