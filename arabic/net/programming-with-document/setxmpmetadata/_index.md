---
title: قم بتعيين XMPMetadata في ملف PDF
linktitle: قم بتعيين XMPMetadata في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تعيين XMPMetadata في ملف PDF باستخدام Aspose.PDF لـ .NET. اتبع هذا الدليل المفصل خطوة بخطوة.
type: docs
weight: 330
url: /ar/net/programming-with-document/setxmpmetadata/
---
في هذه المقالة ، سنقدم دليلًا تفصيليًا حول كيفية استخدام Aspose.PDF لـ .NET لتعيين بيانات XMP الوصفية في ملف PDF. سنقوم بتوفير مثال كامل لشفرة المصدر في نهاية المقالة.

## الخطوة 1: قم بتعيين المسار إلى دليل المستند

قبل أن نبدأ ، نحتاج إلى تعيين المسار إلى الدليل حيث يوجد مستند PDF الخاص بنا. سنخزن هذا المسار في متغير يسمى "dataDir".

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 تأكد من استبداله`YOUR DOCUMENT DIRECTORY` بالمسار الفعلي لملف PDF الخاص بك.

## الخطوة 2: افتح ملف PDF

 الخطوة الأولى هي فتح ملف PDF الذي تريد تعيين بيانات XMP الوصفية له. للقيام بذلك ، ستحتاج إلى إنشاء ملف`Document` الكائن وتمرير المسار إلى ملف PDF الخاص بك.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح المستند
Document pdfDocument = new Document(dataDir + "SetXMPMetadata.pdf");
```

## الخطوة 3: تعيين خصائص بيانات تعريف XMP

الآن بعد أن أصبح لديك ملف PDF مفتوحًا ، يمكنك البدء في تعيين خصائص بيانات XMP الوصفية. ستعتمد الخصائص التي تحددها على احتياجاتك الخاصة ، ولكن إليك بعض الخصائص الشائعة التي قد ترغب في تعيينها:

- `xmp:CreateDate`: تاريخ إنشاء ملف PDF.
- `xmp:Nickname`: اسم مستعار أو اسم مستعار لملف PDF.
- `xmp:CustomProperty`: خاصية مخصصة بقيمة تحددها أنت.

 لتعيين هذه الخصائص ، يمكنك استخدام`Metadata` ممتلكات`Document`هدف. هذا مثال:

```csharp
// تعيين الخصائص
pdfDocument.Metadata["xmp:CreateDate"] = DateTime.Now;
pdfDocument.Metadata["xmp:Nickname"] = "Nickname";
pdfDocument.Metadata["xmp:CustomProperty"] = "Custom Value";
```

في هذا البرنامج التعليمي ، نقوم بتعيين تاريخ الإنشاء على التاريخ والوقت الحاليين ، واللقب على "اللقب" ، وخاصية مخصصة على "القيمة المخصصة". يمكنك استبدال هذه القيم بقيمك الخاصة.

## الخطوة 4: احفظ ملف PDF

 بعد تعيين خصائص بيانات XMP الأولية ، ستحتاج إلى حفظ ملف PDF. للقيام بذلك ، يمكنك استخدام ملف`Save` طريقة`Document` الكائن وتمرير المسار إلى المكان الذي تريد حفظ ملف PDF المحدث فيه.

```csharp
dataDir = dataDir + "SetXMPMetadata_out.pdf";
// احفظ المستند
pdfDocument.Save(dataDir);
```

### مثال التعليمات البرمجية المصدر لتعيين XMPMetadata باستخدام Aspose.PDF لـ .NET

إليك المثال الكامل لشفرة المصدر لإعداد XMPMetadata باستخدام Aspose.PDF لـ .NET:

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
// احفظ المستند
pdfDocument.Save(dataDir);

Console.WriteLine("\nXMP metadata in a pdf file setup successfully.\nFile saved at " + dataDir);
```

## خاتمة

يوفر Aspose.PDF for .NET طريقة مباشرة لتعيين بيانات XMP الوصفية في ملفات PDF ، مما يتيح لك إضافة معلومات وصفية وخصائص إلى مستنداتك. يوضح لك الدليل التفصيلي المقدم أعلاه كيفية تعيين خصائص بيانات تعريف XMP المتنوعة باستخدام كود مصدر C #. بالإضافة إلى ذلك ، يمكنك تخصيص بيانات XMP الوصفية لتلائم احتياجاتك الخاصة ومتطلبات عملك. باستخدام Aspose.PDF for .NET ، تصبح إدارة البيانات الوصفية لملفات PDF فعالة وتتيح تنظيمًا أفضل وإمكانية البحث في مستندات PDF الخاصة بك.

### الأسئلة الشائعة forSet XMPMetadata في ملف PDF

#### س: ما هي بيانات XMP الأولية في ملف PDF ، ولماذا هي مهمة؟

ج: XMP (النظام الأساسي للبيانات الوصفية الموسعة) هو معيار لدمج البيانات الأولية في تنسيقات ملفات متنوعة ، بما في ذلك PDF. تتيح لك بيانات XMP الأولية في ملف PDF إضافة معلومات وصفية وخصائص إلى المستند ، مثل تاريخ الإنشاء والمؤلف والعنوان والكلمات الأساسية والخصائص المخصصة. من الضروري تنظيم مستندات PDF وإمكانية البحث فيها وأرشفتها بشكل أفضل.

#### س: هل يمكنني تعيين خصائص بيانات تعريف XMP أخرى غير تلك المذكورة في المثال؟

 ج: نعم ، يمكنك تعيين مجموعة كبيرة من خصائص بيانات تعريف XMP وفقًا لمتطلباتك الخاصة. تشمل بعض الخصائص المشتركة`dc:title` (عنوان المستند) ،`dc:creator` (منشئ الوثيقة) ،`dc:description` (وصف المستند)،`pdf:Keywords` (وثيقة الكلمات الأساسية) ، وأكثر من ذلك. توفر مواصفات XMP العديد من مساحات الأسماء القياسية ومساحات الأسماء المخصصة لإعداد أنواع مختلفة من البيانات الوصفية.

#### س: هل من الممكن استرداد وقراءة بيانات XMP الأولية من ملف PDF موجود؟

 ج: نعم ، يوفر Aspose.PDF for .NET القدرة على قراءة واسترداد بيانات XMP الوصفية من ملف PDF موجود. يمكنك استخدام ال`Metadata` ممتلكات`Document` فئة للوصول إلى بيانات تعريف XMP واسترداد قيم خصائص معينة.