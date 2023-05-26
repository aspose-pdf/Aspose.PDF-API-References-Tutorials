---
title: تحديث تعليق النص الحر
linktitle: تحديث تعليق النص الحر
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تحديث ميزة التعليق التوضيحي للنص المجاني في Aspose.PDF for .NET باستخدام الكود المصدري C #.
type: docs
weight: 160
url: /ar/net/annotations/updatefreetextannotation/
---
في هذه المقالة ، سنقدم دليلاً خطوة بخطوة لشرح التعليمات البرمجية المصدر C # التالية لميزة Update Free Text Annotation الخاصة بـ Aspose.PDF for .NET. سنتناول كل سطر من التعليمات البرمجية ونوضح ما يفعله ، حتى يتمكن حتى المبتدئين من فهمه.

الآن دعنا نشرح كل سطر من الكود أعلاه خطوة بخطوة:

## الخطوة 1: إعداد دليل المستند

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

في هذا السطر ، نقوم بتعيين المسار إلى الدليل الذي يحتوي على مستند PDF الذي نريد تحديثه.

## الخطوة 2: فتح مستند PDF

```csharp
Document doc1 = new Document(dataDir + "input.pdf");
```

 نحن هنا نفتح مستند PDF باستخدام Aspose.PDF's`Document` class وتحديد المسار إلى ملف PDF المدخل.

## الخطوة 3: تحديث حجم الخط ولون التعليق التوضيحي للنص المجاني

```csharp
(doc1.Pages[1].Annotations[0] as FreeTextAnnotation).TextStyle.FontSize = 18;
(doc1.Pages[1].Annotations[0] as FreeTextAnnotation).TextStyle.Color = System.Drawing.Color.Green;
```

 في هذه الخطوة ، نقوم بتحديث حجم الخط ولونه في أول تعليق توضيحي للنص الحر في الصفحة الثانية من مستند PDF. نحن نقوم بذلك عن طريق الوصول إلى`TextStyle` ممتلكات`FreeTextAnnotation` الكائن وتحديده`FontSize` و`Color` خصائص إلى 18 والأخضر ، على التوالي.

## الخطوة 4: معالجة الاستثناءات

```csharp
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```

 هذا معيار`try-catch` الذي يمسك أي استثناءات قد تحدث أثناء تنفيذ التعليمات البرمجية ويطبع رسالة الخطأ إلى وحدة التحكم.

## خاتمة

في هذه المقالة ، قدمنا دليلاً خطوة بخطوة لشرح الكود المصدري C # لميزة Update Free Text Annotation في Aspose.PDF for .NET. باتباع هذه الخطوات ، يمكنك بسهولة تحديث حجم الخط ولون التعليقات التوضيحية النصية المجانية في مستندات PDF الخاصة بك باستخدام Aspose.PDF for .NET.

### مثال على الكود المصدري لتحديث التعليق التوضيحي للنص الحر باستخدام Aspose.PDF for .NET

قبل الغوص في شرح الكود ، دعنا أولاً نلقي نظرة على الكود نفسه. يوضح مثال الكود هذا كيفية تحديث خصائص التعليق التوضيحي للنص الحر في مستند PDF باستخدام Aspose.PDF لـ .NET.

```csharp
try
{
    // المسار إلى دليل المستندات.
    string dataDir = "YOUR DOCUMENT DIRECTORY";

    // افتح المستند
    Document doc1 = new Document(dataDir + "input.pdf");

    // اضبط حجم الخط ولونه في التعليق التوضيحي:
    (doc1.Pages[1].Annotations[0] as FreeTextAnnotation).TextStyle.FontSize = 18;
    (doc1.Pages[1].Annotations[0] as FreeTextAnnotation).TextStyle.Color = System.Drawing.Color.Green;
                
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```