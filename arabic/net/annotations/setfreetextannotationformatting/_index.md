---
title: قم بتعيين تنسيق التعليقات التوضيحية للنص الحر
linktitle: قم بتعيين تنسيق التعليقات التوضيحية للنص الحر
second_title: Aspose.PDF لمرجع .NET API
description: تقدم هذه المقالة دليلاً تفصيليًا حول كيفية إنشاء تعليق توضيحي نصي مجاني وتحديد محتوياته باستخدام Aspose.PDF for .NET
type: docs
weight: 140
url: /ar/net/annotations/setfreetextannotationformatting/
---

Aspose.PDF for .NET هي واجهة برمجة تطبيقات معالجة مستندات PDF قوية وسهلة الاستخدام تتيح لك العمل مع ملفات PDF برمجيًا في تطبيقات .NET الخاصة بك. تتمثل إحدى الميزات التي يوفرها Aspose.PDF for .NET في القدرة على تعيين تنسيق نص مجاني للتعليقات التوضيحية في مستندات PDF. في هذه المقالة ، سنرشدك خلال العملية خطوة بخطوة لإعداد تنسيق مجاني للتعليقات التوضيحية النصية باستخدام Aspose.PDF for .NET.

## المتطلبات الأساسية

قبل أن نبدأ ، تأكد من توفر المتطلبات الأساسية التالية لديك:

- Microsoft Visual Studio 2010 أو أحدث
- Aspose.PDF لـ .NET
- المعرفة الأساسية لـ C #



## 1. إنشاء تطبيق وحدة تحكم C # جديد

أولاً ، قم بإنشاء تطبيق وحدة تحكم C # جديد في Microsoft Visual Studio. لإنشاء تطبيق وحدة تحكم جديد ، حدد "ملف"> "جديد"> "مشروع"> "Visual C #"> "تطبيق وحدة التحكم" من القائمة الرئيسية.

## 2. أضف إشارة إلى Aspose.PDF لـ .NET

بعد ذلك ، أضف مرجعًا إلى Aspose.PDF لـ .NET في مشروعك. للقيام بذلك ، انقر بزر الماوس الأيمن فوق مشروعك في جزء "مستكشف الحلول" ، وحدد "إضافة"> "مرجع" ، ثم استعرض الموقع حيث قمت بحفظ Aspose.PDF لملف .NET DLL. حدد ملف DLL وانقر على "موافق" لإضافة المرجع إلى مشروعك.

## 3. إعداد البيئة

بعد إضافة المرجع إلى Aspose.PDF لـ .NET ، تحتاج إلى إعداد البيئة. للقيام بذلك ، قم بإنشاء متغير سلسلة جديد يسمى "dataDir" وقم بتعيينه على مسار الدليل حيث يوجد مستند PDF الخاص بك. استبدل "YOUR DOCUMENT DIRECTORY" في الكود أدناه بالمسار الفعلي لدليل المستند:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 4. افتح مستند PDF

بمجرد قيامك بإعداد البيئة ، يمكنك فتح مستند PDF باستخدام الكود التالي:

```csharp
// افتح المستند
Document pdfDocument = new Document(dataDir + "SetFreeTextAnnotationFormatting.pdf");
```

استبدل "SetFreeTextAnnotationFormatting.pdf" بالاسم الفعلي لمستند PDF الخاص بك.

## 5. إعداد المظهر الافتراضي

لإعداد المظهر الافتراضي للتعليق التوضيحي للنص المجاني ، تحتاج إلى إنشاء مثيل لكائن DefaultAppearance بالخط المطلوب وحجم الخط واللون. في هذا البرنامج التعليمي ، نقوم بتعيين الخط على "Arial" وحجم الخط على 28 واللون إلى اللون الأحمر.

```csharp
// إنشاء كائن DefaultAppearance
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 28, System.Drawing.Color.Red);
```

## 6. إنشاء تعليق توضيحي نصي مجاني

الآن بعد أن قمت بإعداد المظهر الافتراضي ، يمكنك إنشاء تعليق توضيحي نصي مجاني باستخدام الكود التالي:

```csharp
// أنشئ تعليقًا توضيحيًا
FreeTextAnnotation freetext = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600), default_appearance);
```

ينشئ الكود أعلاه تعليقًا توضيحيًا نصيًا مجانيًا جديدًا في الصفحة الثانية من مستند PDF. سيتم وضع التعليق التوضيحي عند (200 ، 400) وسيكون عرضه 400 وارتفاعه 600.

## 7. حدد محتويات التعليق التوضيحي

بعد إنشاء التعليق التوضيحي للنص الحر ، يمكنك تحديد محتويات التعليق التوضيحي باستخدام الكود التالي:

```csharp
// حدد محتويات التعليق التوضيحي
freetext.Contents = "Free Text
```

### مثال على التعليمات البرمجية المصدر لـ Set Free Text Annotation Formatting باستخدام Aspose.PDF for .NET
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح المستند
Document pdfDocument = new Document(dataDir + "SetFreeTextAnnotationFormatting.pdf");

// إنشاء كائن DefaultAppearance
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 28, System.Drawing.Color.Red);
// أنشئ تعليقًا توضيحيًا
FreeTextAnnotation freetext = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600), default_appearance);
// حدد محتويات التعليق التوضيحي
freetext.Contents = "Free Text";
// إضافة شرح إلى مجموعة التعليقات التوضيحية للصفحة
pdfDocument.Pages[1].Annotations.Add(freetext);
dataDir = dataDir + "SetFreeTextAnnotationFormatting_out.pdf";
// احفظ المستند المحدث
pdfDocument.Save(dataDir);            
```
