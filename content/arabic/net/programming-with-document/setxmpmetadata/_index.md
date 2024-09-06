---
title: تعيين XMPMetadata في ملف PDF
linktitle: تعيين XMPMetadata في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية تعيين XMPMetadata في ملف PDF باستخدام Aspose.PDF لـ .NET. اتبع هذا الدليل خطوة بخطوة.
type: docs
weight: 330
url: /ar/net/programming-with-document/setxmpmetadata/
---
في هذه المقالة، سنقدم دليلًا خطوة بخطوة حول كيفية استخدام Aspose.PDF لـ .NET لتعيين بيانات تعريف XMP في ملف PDF. وسنقدم مثالاً كاملاً لرمز المصدر في نهاية المقالة.

## الخطوة 1: تعيين المسار إلى دليل المستند

قبل أن نبدأ، نحتاج إلى تحديد المسار إلى الدليل الذي يوجد به مستند PDF الخاص بنا. سنخزن هذا المسار في متغير يسمى "dataDir".

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 تأكد من الاستبدال`YOUR DOCUMENT DIRECTORY` مع المسار الفعلي لملف PDF الخاص بك.

## الخطوة 2: افتح ملف PDF

 الخطوة الأولى هي فتح ملف PDF الذي تريد تعيين بيانات تعريف XMP له. للقيام بذلك، ستحتاج إلى إنشاء ملف تعريف جديد`Document` الكائن وتمريره في المسار إلى ملف PDF الخاص بك.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// فتح المستند
Document pdfDocument = new Document(dataDir + "SetXMPMetadata.pdf");
```

## الخطوة 3: تعيين خصائص بيانات XMP

الآن بعد أن قمت بفتح ملف PDF، يمكنك البدء في تعيين خصائص بيانات XMP التعريفية. ستعتمد الخصائص التي تحددها على احتياجاتك المحددة، ولكن إليك بعض الخصائص الشائعة التي قد ترغب في تعيينها:

- `xmp:CreateDate`:تاريخ إنشاء ملف PDF.
- `xmp:Nickname`:اسم مستعار أو اسم مستعار لملف PDF.
- `xmp:CustomProperty`:خاصية مخصصة بقيمة تحددها.

 لتعيين هذه الخصائص، يمكنك استخدام`Metadata` ممتلكات`Document` الكائن. فيما يلي مثال:

```csharp
// تعيين الخصائص
pdfDocument.Metadata["xmp:CreateDate"] = DateTime.Now;
pdfDocument.Metadata["xmp:Nickname"] = "Nickname";
pdfDocument.Metadata["xmp:CustomProperty"] = "Custom Value";
```

في هذا البرنامج التعليمي، نقوم بتعيين تاريخ الإنشاء إلى التاريخ والوقت الحاليين، والاسم المستعار إلى "Nickname"، والخاصية المخصصة إلى "Custom Value". يمكنك استبدال هذه القيم بقيمك الخاصة.

## الخطوة 4: احفظ ملف PDF

 بعد تعيين خصائص بيانات تعريف XMP، تحتاج إلى حفظ ملف PDF. للقيام بذلك، يمكنك استخدام`Save` طريقة`Document` قم بإنشاء الكائن وتمريره في المسار الذي تريد حفظ ملف PDF المحدث فيه.

```csharp
dataDir = dataDir + "SetXMPMetadata_out.pdf";
// حفظ المستند
pdfDocument.Save(dataDir);
```

### مثال على كود المصدر لتعيين XMPMetadata باستخدام Aspose.PDF لـ .NET

فيما يلي مثال كامل لمصدر الكود لإعداد XMPMetadata باستخدام Aspose.PDF لـ .NET:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// فتح المستند
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

يوفر Aspose.PDF for .NET طريقة مباشرة لتعيين بيانات تعريف XMP في ملفات PDF، مما يتيح لك إضافة معلومات وصفية وخصائص إلى مستنداتك. يوضح لك الدليل التفصيلي المقدم أعلاه كيفية تعيين خصائص مختلفة لبيانات تعريف XMP باستخدام كود مصدر C#. بالإضافة إلى ذلك، يمكنك تخصيص بيانات تعريف XMP لتتناسب مع احتياجاتك ومتطلبات عملك المحددة. مع Aspose.PDF for .NET، تصبح إدارة بيانات تعريف PDF فعالة وتسمح بتنظيم مستندات PDF الخاصة بك وإمكانية البحث فيها بشكل أفضل.

### الأسئلة الشائعة حول تعيين بيانات XMPMetadata في ملف PDF

#### س: ما هي بيانات XMP في ملف PDF، ولماذا هي مهمة؟

ج: XMP (منصة البيانات الوصفية القابلة للتوسيع) هو معيار لتضمين البيانات الوصفية في تنسيقات ملفات مختلفة، بما في ذلك PDF. تتيح لك البيانات الوصفية القابلة للتوسيع في ملف PDF إضافة معلومات وصفية وخصائص إلى المستند، مثل تاريخ الإنشاء والمؤلف والعنوان والكلمات الرئيسية والخصائص المخصصة. وهو أمر ضروري لتحسين تنظيم مستندات PDF وإمكانية البحث عنها وأرشفتها.

#### س: هل يمكنني تعيين خصائص بيانات تعريف XMP أخرى بالإضافة إلى تلك المذكورة في المثال؟

 ج: نعم، يمكنك تعيين مجموعة واسعة من خصائص بيانات XMP وفقًا لمتطلباتك المحددة. تتضمن بعض الخصائص الشائعة`dc:title` (عنوان الوثيقة)`dc:creator` (منشئ الوثيقة)،`dc:description` (وصف الوثيقة)`pdf:Keywords` (كلمات رئيسية للمستند)، والمزيد. توفر مواصفات XMP مساحات أسماء قياسية ومساحات أسماء مخصصة مختلفة لتعيين أنواع مختلفة من البيانات الوصفية.

#### س: هل من الممكن استرجاع وقراءة بيانات XMP من ملف PDF موجود؟

 ج: نعم، يوفر Aspose.PDF لـ .NET القدرة على قراءة واسترجاع بيانات تعريف XMP من ملف PDF موجود. يمكنك استخدام`Metadata` ممتلكات`Document` فئة للوصول إلى بيانات XMP واسترجاع قيم خصائص محددة.