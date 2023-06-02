---
title: تضمين الخط أثناء إنشاء المستند
linktitle: تضمين الخط أثناء إنشاء المستند
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تضمين خط أثناء إنشاء مستند PDF باستخدام Aspose.PDF for .NET. تأكد من العرض الصحيح على أجهزة مختلفة.
type: docs
weight: 140
url: /ar/net/programming-with-document/embedfontwhiledoccreation/
---

في هذا البرنامج التعليمي ، سنناقش كيفية تضمين خط أثناء إنشاء مستند PDF باستخدام Aspose.PDF لـ .NET. Aspose.PDF for .NET مكتبة قوية تتيح للمطورين إنشاء مستندات PDF وتحريرها ومعالجتها برمجيًا. توفر هذه المكتبة مجموعة كبيرة من الميزات للعمل مع مستندات PDF ، بما في ذلك إضافة النصوص والصور والجداول وغير ذلك الكثير. يعد دمج الخطوط أثناء إنشاء مستند PDF مطلبًا شائعًا للمطورين الذين يرغبون في ضمان عرض مستند PDF بشكل صحيح على أجهزة مختلفة ، بغض النظر عما إذا كانت الخطوط المطلوبة مثبتة على تلك الأجهزة أم لا.

## الخطوة 1: إنشاء تطبيق C # Console جديد
للبدء ، قم بإنشاء تطبيق C # Console جديد في Visual Studio. يمكنك تسميته ما شئت. بمجرد إنشاء المشروع ، تحتاج إلى إضافة مرجع إلى Aspose.PDF لمكتبة .NET.

## الخطوة 2: استيراد Aspose.PDF Namespace
أضف السطر التالي من التعليمات البرمجية أعلى ملف C # لاستيراد مساحة الاسم Aspose.PDF:

```csharp
using Aspose.Pdf;
```

## الخطوة 3: إنشاء كائن Pdf
قم بإنشاء كائن Pdf عن طريق استدعاء المُنشئ الفارغ الخاص به:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## الخطوة 4: قم بإنشاء قسم في كائن Pdf
قم بإنشاء قسم في كائن Pdf:

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

## الخطوة 5: أضف نصًا إلى القسم
أضف نصًا إلى القسم:

```csharp
Aspose.Pdf.Text.TextFragment fragment = new Aspose.Pdf.Text.TextFragment("");
Aspose.Pdf.Text.TextSegment segment = new Aspose.Pdf.Text.TextSegment(" This is a sample text using Custom font.");
```

## الخطوة 6: اضبط الخط وقم بتضمينه
اضبط الخط وقم بتضمينه:

```csharp
Aspose.Pdf.Text.TextState ts = new Aspose.Pdf.Text.TextState();
ts.Font = FontRepository.FindFont("Arial");
ts.Font.IsEmbedded = true;
segment.TextState = ts;
fragment.Segments.Add(segment);
page.Paragraphs.Add(fragment);
```

## الخطوة 7: احفظ مستند PDF
بمجرد قيامك بتضمين الخط أثناء إنشاء مستند PDF ، ستحتاج إلى حفظ المستند:

```csharp
dataDir = dataDir + "EmbedFontWhileDocCreation_out.pdf";
// حفظ وثيقة PDF
doc.Save(dataDir);
```

### مثال على رمز المصدر لتضمين الخط أثناء إنشاء المستند باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء كائن Pdf عن طريق استدعاء المُنشئ الفارغ
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// قم بإنشاء قسم في كائن Pdf
Aspose.Pdf.Page page = doc.Pages.Add();

Aspose.Pdf.Text.TextFragment fragment = new Aspose.Pdf.Text.TextFragment("");

Aspose.Pdf.Text.TextSegment segment = new Aspose.Pdf.Text.TextSegment(" This is a sample text using Custom font.");
Aspose.Pdf.Text.TextState ts = new Aspose.Pdf.Text.TextState();
ts.Font = FontRepository.FindFont("Arial");
ts.Font.IsEmbedded = true;
segment.TextState = ts;
fragment.Segments.Add(segment);
page.Paragraphs.Add(fragment);

dataDir = dataDir + "EmbedFontWhileDocCreation_out.pdf";
// حفظ وثيقة PDF
doc.Save(dataDir);
```

## خاتمة
في هذا البرنامج التعليمي ، ناقشنا كيفية تضمين خط أثناء إنشاء مستند PDF باستخدام Aspose.PDF لـ .NET. يوفر Aspose.PDF for .NET واجهة برمجة تطبيقات بسيطة وسهلة الاستخدام للعمل مع مستندات PDF ، بما في ذلك إضافة الخطوط وتضمينها. يعد دمج الخطوط أثناء إنشاء مستند PDF خطوة مهمة لضمان عرض المستند بشكل صحيح على أجهزة مختلفة ، بغض النظر عما إذا كانت الخطوط المطلوبة مثبتة على تلك الأجهزة أم لا.

