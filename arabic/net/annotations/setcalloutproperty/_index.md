---
title: قم بتعيين خاصية وسيلة الشرح في ملف PDF
linktitle: قم بتعيين خاصية وسيلة الشرح في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تعيين خاصية وسيلة الشرح في ملف PDF باستخدام Aspose.PDF لـ .NET. تخصيص التعليقات التوضيحية بخطوط وسيلة الشرح ولون النص وأنماط النهاية.
type: docs
weight: 130
url: /ar/net/annotations/setcalloutproperty/
---
 Aspose.PDF for .NET مكتبة قوية لإنشاء مستندات PDF ومعالجتها وتحويلها في C #. تتمثل إحدى الميزات التي توفرها هذه المكتبة في القدرة على تعيين خصائص وسيلة الشرح للتعليقات التوضيحية النصية المجانية في مستندات PDF. يمكن القيام بذلك باستخدام ملف`FreeTextAnnotation` class ، والتي تتيح لك إنشاء تعليقات توضيحية باستخدام وسائل الشرح.

في هذا البرنامج التعليمي ، سنوجهك خلال عملية تعيين خصائص وسيلة الشرح للحصول على تعليق توضيحي نصي مجاني باستخدام Aspose.PDF لـ .NET في C #. اتبع الخطوات أدناه للبدء.

## قم بتثبيت Aspose.PDF for .NET

 إذا لم تكن قد قمت بذلك بالفعل ، فستحتاج إلى ذلك[تحميل](https://releases.aspose.com/pdf/net/) وقم بتثبيت Aspose.PDF for .NET من إصدارات Aspose أو عبر مدير الحزم NuGet.

## الخطوة 1: قم بإنشاء مستند PDF جديد

 قم بإنشاء مستند PDF جديد باستخدام ملف`Document`فئة مقدمة من Aspose.PDF لـ .NET.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## الخطوة 2: أضف صفحة جديدة إلى المستند

 أضف صفحة جديدة إلى المستند باستخدام امتداد`Pages` جمع`Document` فصل.

```csharp
Page page = doc.Pages.Add();
```

## الخطوة 3: تعيين المظهر الافتراضي

 عيّن المظهر الافتراضي للتعليق النصي المجاني عن طريق إنشاء ملف`DefaultAppearance` الكائن وتعيين خصائصه مثل`TextColor` و`FontSize`.

```csharp
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
```

## الخطوة 4: قم بإنشاء تعليق توضيحي نصي مجاني باستخدام وسيلة الشرح

 أنشئ تعليقًا توضيحيًا نصيًا مجانيًا جديدًا باستخدام وسيلة الشرح باستخدام`FreeTextAnnotation` فصل. تعيين`Intent` الملكية ل`FreeTextIntent.FreeTextCallout` لتحديد أن هذا تعليق توضيحي. تعيين`EndingStyle` الملكية ل`LineEnding.OpenArrow` لتحديد نمط السهم في نهاية وسيلة الشرح. تعيين`Callout` خاصية لمجموعة من`Point` كائنات تمثل النقاط على الصفحة حيث يجب رسم خط وسيلة الشرح.

```csharp
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
fta.Callout = new Point[]
{
    new Point(428.25,651.75), new Point(462.75,681.375), new Point(474,681.375)
};
```

## الخطوة 5: أضف تعليقًا توضيحيًا نصيًا مجانيًا إلى الصفحة

 أضف التعليق التوضيحي للنص الحر إلى الصفحة باستخدام ملحق`Annotations` جمع`Page` فصل.

```csharp
page.Annotations.Add(fta);
```

## الخطوة 6: أضف نصًا إلى التعليق التوضيحي

 أضف نصًا إلى التعليق التوضيحي عن طريق تعيين`RichText`إلى سلسلة من XML المنسق. في هذا البرنامج التعليمي ، نقوم بتعيين لون النص إلى اللون الأحمر وحجم الخط على 9.

```csharp
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml \ "xmlns: xfa = \" http: //www.xfa.org/schema/xfa-data/1.0/ \ "xfa: APIVersion = \" Acrobat: 11.0.23 \ " xfa: المواصفات = \ "2.0.2 \" style = \ "color: #FF
```

## الخطوة 7: احفظ المستند

الآن احفظ المستند باستخدام الكود التالي:

```csharp
doc.Save(dataDir + "SetCalloutProperty.pdf")
```

### مثال على التعليمات البرمجية المصدر لـ Set Callout Property باستخدام Aspose.PDF for .NET

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
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml \ "xmlns: xfa = \" http: //www.xfa.org/schema/xfa-data/1.0/ \ "xfa: APIVersion = \" Acrobat: 11.0.23 \ " xfa: spec = \ "2.0.2 \" style = \ "color: # FF0000؛ font-weight: normal؛ font-style: normal؛ font-stretch: normal \"> <p dir = \ "ltr \"> <span style = \ "font-size: 9.0pt؛ font-family: Helvetica \"> هذا نموذج </ span> </p> </body> "؛
doc.Save(dataDir + "SetCalloutProperty.pdf");
```

## خاتمة

في هذا البرنامج التعليمي ، اكتشفنا كيفية تعيين خصائص وسيلة الشرح لتعليق نصي مجاني في مستند PDF باستخدام Aspose.PDF لـ .NET. تعد التعليقات التوضيحية لوسائل الشرح مفيدة في توفير معلومات أو تفسيرات إضافية تتعلق بمناطق معينة في المستند. يوفر Aspose.PDF for .NET نطاقًا واسعًا من الميزات والإمكانيات للعمل مع ملفات PDF ، بما في ذلك إنشاء التعليقات التوضيحية وتخصيصها ، مثل وسائل الشرح. باتباع الدليل خطوة بخطوة واستخدام الكود المصدري C # المقدم ، يمكن للمطورين بسهولة تنفيذ التعليقات التوضيحية لوسائل الشرح في مستندات PDF الخاصة بهم ، مما يعزز سهولة استخدام مستنداتهم ووضوحها. Aspose.PDF for .NET هي مكتبة متعددة الاستخدامات وموثوقة لعمليات PDF في تطبيقات .NET ، وتوفر أدوات قوية للتعامل مع المهام المختلفة المتعلقة بـ PDF بكفاءة.

### الأسئلة الشائعة الخاصة بخاصية وسيلة الشرح المحددة في ملف PDF

#### س: ما المقصود بالتعليق التوضيحي في مستند PDF؟

ج: التعليق التوضيحي في مستند PDF هو نوع من التعليقات التوضيحية التي تسمح لك بإنشاء مربع نص مع سطر رئيسي يشير إلى منطقة معينة في المستند. يتم استخدامه بشكل شائع لتقديم معلومات أو تعليقات إضافية تتعلق بقسم أو عنصر معين في المستند.

#### س: هل يمكنني تخصيص مظهر شرح وسيلة الشرح باستخدام Aspose.PDF لـ .NET؟

ج: نعم ، يمكنك تخصيص خصائص متنوعة لتعليق وسيلة الشرح ، مثل اللون وحجم الخط ومحاذاة النص ونمط الخط ونمط السهم والمزيد.

#### س: كيف أضيف نصًا إلى شرح وسيلة الشرح؟

 ج: لإضافة نص إلى شرح وسيلة الشرح ، يمكنك تعيين`RichText` ممتلكات`FreeTextAnnotation` هدف. ال`RichText` تأخذ الخاصية سلسلة من XML المنسق الذي يمثل النص الذي سيتم عرضه في شرح وسيلة الشرح.

#### س: هل يمكنني إضافة تعليقات توضيحية متعددة لوسائل الشرح إلى مستند PDF باستخدام Aspose.PDF لـ .NET؟

 ج: نعم ، يمكنك إنشاء تعليقات توضيحية متعددة لوسائل الشرح في مستند PDF عن طريق إنشاء مثيلات متعددة من`FreeTextAnnotation`الكائن وإضافتها إلى صفحات أو مواقع مختلفة في المستند.