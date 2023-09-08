---
title: قم بتعيين XMPMetadata في ملف PDF
linktitle: قم بتعيين XMPMetadata في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تعيين XMPMetadata في ملف PDF باستخدام Aspose.PDF لـ .NET. اتبع هذا الدليل خطوة بخطوة.
type: docs
weight: 330
url: /ar/net/programming-with-document/setxmpmetadata/
---
في هذه المقالة، سنقدم دليلاً خطوة بخطوة حول كيفية استخدام Aspose.PDF لـ .NET لتعيين بيانات تعريف XMP في ملف PDF. سنقدم مثالًا كاملاً للكود المصدري في نهاية المقالة.

## الخطوة 1: قم بتعيين المسار إلى دليل المستند

قبل أن نبدأ، نحتاج إلى تعيين المسار إلى الدليل الذي يوجد به مستند PDF الخاص بنا. سنقوم بتخزين هذا المسار في متغير يسمى "dataDir".

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 تأكد من استبدال`YOUR DOCUMENT DIRECTORY` مع المسار الفعلي لملف PDF الخاص بك.

## الخطوة 2: افتح ملف PDF

 الخطوة الأولى هي فتح ملف PDF الذي تريد تعيين بيانات تعريف XMP له. للقيام بذلك، سوف تحتاج إلى إنشاء جديد`Document` كائن وتمرير في المسار إلى ملف PDF الخاص بك.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح المستند
Document pdfDocument = new Document(dataDir + "SetXMPMetadata.pdf");
```

## الخطوة 3: قم بتعيين خصائص بيانات تعريف XMP

الآن بعد أن أصبح ملف PDF مفتوحًا، يمكنك البدء في تعيين خصائص بيانات تعريف XMP. ستعتمد الخصائص التي تقوم بتعيينها على احتياجاتك المحددة، ولكن فيما يلي بعض الخصائص الشائعة التي قد ترغب في تعيينها:

- `xmp:CreateDate`: تاريخ إنشاء ملف PDF.
- `xmp:Nickname`: اللقب أو الاسم المستعار لملف PDF.
- `xmp:CustomProperty`: خاصية مخصصة بقيمة تحددها.

 لتعيين هذه الخصائص، يمكنك استخدام`Metadata` ملكية`Document` هدف. هنا مثال:

```csharp
// تعيين الخصائص
pdfDocument.Metadata["xmp:CreateDate"] = DateTime.Now;
pdfDocument.Metadata["xmp:Nickname"] = "Nickname";
pdfDocument.Metadata["xmp:CustomProperty"] = "Custom Value";
```

في هذا البرنامج التعليمي، نقوم بتعيين تاريخ الإنشاء على التاريخ والوقت الحاليين، واللقب على "اللقب"، والخاصية المخصصة على "القيمة المخصصة". يمكنك استبدال هذه القيم بقيمك الخاصة.

## الخطوة 4: احفظ ملف PDF

 بعد تعيين خصائص بيانات تعريف XMP، ستحتاج إلى حفظ ملف PDF. للقيام بذلك، يمكنك استخدام`Save` طريقة`Document` كائن وتمرير المسار إلى المكان الذي تريد حفظ ملف PDF المحدث فيه.

```csharp
dataDir = dataDir + "SetXMPMetadata_out.pdf";
// حفظ المستند
pdfDocument.Save(dataDir);
```

### مثال على كود المصدر لتعيين XMPMetadata باستخدام Aspose.PDF لـ .NET

فيما يلي المثال الكامل للتعليمة البرمجية المصدر لإعداد XMPMetadata باستخدام Aspose.PDF لـ .NET:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح المستند
Document pdfDocument = new Document(dataDir + "SetXMPMetadata.pdf");

// تعيين الخصائص
pdfDocument.Metadata["xmp:CreateDate"] = DateTime.Now;
pdfDocument.Metadata["xmp:Nickname"] = "Nickname";
pdfDocument.Metadata["xmp:CustomProperty"] = "Custom Value";

dataDir = dataDir + "SetXMPMetadata_out.pdf";
// حفظ المستند
pdfDocument.Save(dataDir);

Console.WriteLine("\nXMP metadata in a pdf file setup successfully.\nFile saved at " + dataDir);
```

## خاتمة

يوفر Aspose.PDF for .NET طريقة مباشرة لتعيين بيانات تعريف XMP في ملفات PDF، مما يتيح لك إضافة معلومات وخصائص وصفية إلى مستنداتك. يوضح لك الدليل التفصيلي الموضح أعلاه كيفية تعيين خصائص بيانات تعريف XMP المتنوعة باستخدام كود مصدر C#. بالإضافة إلى ذلك، يمكنك تخصيص بيانات تعريف XMP لتتوافق مع احتياجاتك ومتطلبات العمل الخاصة بك. باستخدام Aspose.PDF for .NET، تصبح إدارة البيانات التعريفية لـ PDF فعالة وتسمح بتنظيم أفضل وإمكانية البحث في مستندات PDF الخاصة بك.

### الأسئلة الشائعة حول تعيين بيانات XMPMetadata في ملف PDF

#### س: ما هي بيانات تعريف XMP الموجودة في ملف PDF، وما سبب أهميتها؟

ج: XMP (منصة بيانات التعريف القابلة للتوسيع) هو معيار لتضمين بيانات التعريف في تنسيقات ملفات مختلفة، بما في ذلك PDF. تسمح لك بيانات تعريف XMP في ملف PDF بإضافة معلومات وخصائص وصفية إلى المستند، مثل تاريخ الإنشاء والمؤلف والعنوان والكلمات الأساسية والخصائص المخصصة. إنه ضروري لتحسين تنظيم مستندات PDF وإمكانية البحث فيها وأرشفتها.

#### س: هل يمكنني تعيين خصائص بيانات تعريف XMP أخرى إلى جانب تلك المذكورة في المثال؟

 ج: نعم، يمكنك تعيين نطاق واسع من خصائص بيانات تعريف XMP وفقًا لمتطلباتك المحددة. وتشمل بعض الخصائص المشتركة`dc:title` (عنوان الوثيقة)،`dc:creator` (منشئ المستند)،`dc:description` (وصف المستند)،`pdf:Keywords` (الكلمات الرئيسية للمستند)، والمزيد. توفر مواصفات XMP مساحات أسماء قياسية متنوعة ومساحات أسماء مخصصة لتعيين أنواع مختلفة من بيانات التعريف.

#### س: هل من الممكن استرداد بيانات تعريف XMP وقراءتها من ملف PDF موجود؟

 ج: نعم، يوفر Aspose.PDF for .NET القدرة على قراءة بيانات تعريف XMP واستردادها من ملف PDF موجود. يمكنك استخدام ال`Metadata` ملكية`Document` فئة للوصول إلى بيانات تعريف XMP واسترداد قيم خصائص محددة.