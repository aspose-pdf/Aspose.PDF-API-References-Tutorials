---
title: تعيين خاصية وسيلة الشرح في ملف PDF
linktitle: تعيين خاصية وسيلة الشرح في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تعيين خاصية وسيلة الشرح في ملف PDF باستخدام Aspose.PDF لـ .NET. قم بتخصيص التعليقات التوضيحية باستخدام خطوط وسائل الشرح ولون النص وأنماط النهاية.
type: docs
weight: 130
url: /ar/net/annotations/setcalloutproperty/
---
 Aspose.PDF for .NET هي مكتبة قوية لإنشاء مستندات PDF ومعالجتها وتحويلها بلغة C#. إحدى الميزات التي توفرها هذه المكتبة هي القدرة على تعيين خصائص وسائل الشرح للتعليقات التوضيحية النصية المجانية في مستندات PDF. ويمكن القيام بذلك باستخدام`FreeTextAnnotation` class، والذي يسمح لك بإنشاء التعليقات التوضيحية مع وسائل الشرح.

في هذا البرنامج التعليمي، سنرشدك خلال عملية تعيين خصائص وسائل الشرح لتعليق توضيحي للنص الحر باستخدام Aspose.PDF لـ .NET في C#. اتبع الخطوات أدناه للبدء.

## قم بتثبيت Aspose.PDF لـ .NET

 إذا لم تكن قد قمت بذلك بالفعل، فسوف تحتاج إلى ذلك[تحميل](https://releases.aspose.com/pdf/net/) وقم بتثبيت Aspose.PDF لـ .NET من إصدارات Aspose أو عبر مدير الحزم NuGet.

## الخطوة 1: إنشاء مستند PDF جديد

 قم بإنشاء مستند PDF جديد باستخدام`Document`فئة مقدمة من Aspose.PDF لـ .NET.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## الخطوة 2: إضافة صفحة جديدة إلى المستند

 أضف صفحة جديدة إلى المستند باستخدام`Pages` جمع من`Document` فصل.

```csharp
Page page = doc.Pages.Add();
```

## الخطوة 3: تعيين المظهر الافتراضي

 قم بتعيين المظهر الافتراضي للتعليق التوضيحي للنص الحر عن طريق إنشاء ملف جديد`DefaultAppearance` الكائن وتعيين خصائصه مثل`TextColor` و`FontSize`.

```csharp
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
```

## الخطوة 4: إنشاء تعليق توضيحي نصي مجاني باستخدام وسيلة الشرح

 قم بإنشاء تعليق توضيحي نصي مجاني جديد باستخدام وسيلة الشرح باستخدام`FreeTextAnnotation` فصل. تعيين`Intent` الملكية ل`FreeTextIntent.FreeTextCallout` لتحديد أن هذا تعليق توضيحي لوسيلة شرح. تعيين`EndingStyle` الملكية ل`LineEnding.OpenArrow` لتحديد نمط السهم في نهاية وسيلة الشرح. تعيين`Callout` الملكية لمجموعة من`Point` الكائنات التي تمثل النقاط الموجودة على الصفحة حيث يجب رسم خط وسيلة الشرح.

```csharp
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
fta.Callout = new Point[]
{
    new Point(428.25,651.75), new Point(462.75,681.375), new Point(474,681.375)
};
```

## الخطوة 5: أضف التعليق التوضيحي النصي المجاني إلى الصفحة

 أضف التعليق التوضيحي النصي المجاني إلى الصفحة باستخدام`Annotations` جمع من`Page` فصل.

```csharp
page.Annotations.Add(fta);
```

## الخطوة 6: إضافة نص إلى التعليق التوضيحي

 أضف نصًا إلى التعليق التوضيحي عن طريق ضبط`RichText`الخاصية إلى سلسلة من تنسيق XML. في هذا البرنامج التعليمي، نقوم بتعيين لون النص إلى اللون الأحمر وحجم الخط إلى 9.

```csharp
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"اللون:#FF
```

## الخطوة 7: احفظ المستند

الآن احفظ المستند باستخدام الكود التالي:

```csharp
doc.Save(dataDir + "SetCalloutProperty.pdf")
```

### مثال على التعليمات البرمجية المصدر لتعيين خاصية وسيلة الشرح باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
Page page = doc.Pages.Add();
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
fta.Callout = new Point[]
{
	new Point(428.25,651.75), new Point(462.75,681.375), new Point(474,681.375)
};
page.Annotations.Add(fta);
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"color:#FF0000;font-weight:normal;font-style:normal;font-stretch:normal\"><p dir=\"ltr\"> <span style=\"font-size:9.0pt;font-family:Helvetica\">هذه عينة</span></p></body>";
doc.Save(dataDir + "SetCalloutProperty.pdf");
```

## خاتمة

في هذا البرنامج التعليمي، اكتشفنا كيفية تعيين خصائص وسائل الشرح لتعليق توضيحي للنص الحر في مستند PDF باستخدام Aspose.PDF لـ .NET. تعد التعليقات التوضيحية لوسائل الشرح مفيدة في توفير معلومات أو توضيحات إضافية تتعلق بمناطق محددة في المستند. يوفر Aspose.PDF for .NET نطاقًا واسعًا من الميزات والإمكانيات للعمل مع ملفات PDF، بما في ذلك إنشاء التعليقات التوضيحية وتخصيصها، مثل وسائل الشرح. من خلال اتباع الدليل خطوة بخطوة واستخدام كود مصدر C# المقدم، يمكن للمطورين تنفيذ التعليقات التوضيحية لوسائل الشرح بسهولة في مستندات PDF الخاصة بهم، مما يعزز سهولة استخدام مستنداتهم ووضوحها. Aspose.PDF for .NET هي مكتبة متعددة الاستخدامات وموثوقة لعمليات PDF في تطبيقات .NET، وتوفر أدوات قوية للتعامل مع المهام المختلفة المتعلقة بـ PDF بكفاءة.

### الأسئلة الشائعة لتعيين خاصية وسيلة الشرح في ملف PDF

#### س: ما هو التعليق التوضيحي لوسيلة الشرح في مستند PDF؟

ج: التعليق التوضيحي لوسائط الشرح في مستند PDF هو نوع من التعليقات التوضيحية التي تسمح لك بإنشاء مربع نص به سطر سابق يشير إلى منطقة معينة في المستند. يتم استخدامه بشكل شائع لتوفير معلومات أو تعليقات إضافية تتعلق بقسم أو عنصر معين في المستند.

#### س: هل يمكنني تخصيص مظهر التعليق التوضيحي لوسيلة الشرح باستخدام Aspose.PDF لـ .NET؟

ج: نعم، يمكنك تخصيص خصائص مختلفة للتعليق التوضيحي لوسيلة الشرح، مثل اللون وحجم الخط ومحاذاة النص ونمط الخط ونمط السهم والمزيد.

#### س: كيف يمكنني إضافة نص إلى التعليق التوضيحي لوسيلة الشرح؟

 ج: لإضافة نص إلى التعليق التوضيحي لوسيلة الشرح، يمكنك تعيين`RichText` ملكية`FreeTextAnnotation` هدف. ال`RichText` تأخذ الخاصية سلسلة من XML المنسق الذي يمثل النص الذي سيتم عرضه في التعليق التوضيحي لوسيلة الشرح.

#### س: هل يمكنني إضافة تعليقات توضيحية متعددة لوسائط الشرح إلى مستند PDF باستخدام Aspose.PDF لـ .NET؟

 ج: نعم، يمكنك إنشاء تعليقات توضيحية متعددة لوسائط الشرح في مستند PDF عن طريق إنشاء مثيلات متعددة لـ`FreeTextAnnotation`الكائن وإضافته إلى صفحات أو مواقع مختلفة في المستند.