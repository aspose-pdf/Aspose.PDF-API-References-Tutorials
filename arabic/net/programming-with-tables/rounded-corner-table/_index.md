---
title: طاولة زاوية مستديرة
linktitle: طاولة زاوية مستديرة
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إنشاء جدول زاوية مستدير في مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 190
url: /ar/net/programming-with-tables/rounded-corner-table/
---

في هذا البرنامج التعليمي ، سنوجهك خطوة بخطوة لإنشاء جدول زاوية مستدير في مستند PDF باستخدام Aspose.PDF لـ .NET. سنشرح كود المصدر C # المقدم ونوضح لك كيفية تنفيذه.

## الخطوة الأولى: إنشاء الجدول
أولاً ، سننشئ الجدول باستخدام الكود التالي:

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## الخطوة 2: إعداد نمط الزاوية المستديرة
بعد ذلك ، سنقوم بتكوين نمط الزاوية المستديرة للجدول:

```csharp
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
```

## الخطوة 3: إعداد حدود الجدول
لإعطاء الجدول حد زاوية مستدير ، نحتاج إلى إنشاء كائن BorderInfo وتكوينه بالمعلمات المناسبة:

```csharp
//قم بإنشاء كائن GraphInfo لتعيين لون الحد
GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;

// إنشاء كائن BorderInfo فارغ
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);

// اضبط نصف قطر الحد المستدير على 15
bInfo.RoundedBorderRadius = 15;

// تطبيق معلومات الحدود على الجدول
tab1.Border = bInfo;
```

### مثال على كود مصدر Rounded Corner Table باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;
// قم بإنشاء كائن BorderInfo فارغ
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);
// عيّن الحد حدًا مستديرًا حيث يكون نصف قطر الجولة 15
bInfo.RoundedBorderRadius = 15;
// اضبط نمط ركن الجدول على شكل دائري.
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
// اضبط معلومات حدود الجدول
tab1.Border = bInfo;
```

## خاتمة
تهنئة ! لقد تعلمت الآن كيفية إنشاء جدول زاوية مستدير في مستند PDF باستخدام Aspose.PDF for .NET. يوضح لك هذا الدليل التفصيلي كيفية إعداد نمط الزاوية المستديرة وحدود الجدول. الآن يمكنك تطبيق هذه المعرفة على مشاريعك الخاصة.