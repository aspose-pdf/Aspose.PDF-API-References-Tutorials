---
title: احصل على كافة الخطوط
linktitle: احصل على كافة الخطوط
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استخدام Aspose.PDF for .NET للحصول على جميع الخطوط المستخدمة في مستند PDF برمجيًا باستخدام هذا الدليل التفصيلي وكود المثال.
type: docs
weight: 160
url: /ar/net/programming-with-document/getallfonts/
---

Aspose.PDF for .NET مكتبة قوية تمكن المطورين من العمل مع مستندات PDF برمجيًا. إحدى الميزات التي يوفرها هي القدرة على الحصول على جميع الخطوط المستخدمة في مستند PDF. يمكن أن يكون هذا مفيدًا إذا كنت بحاجة إلى تحليل الخطوط أو معالجتها برمجيًا في مستند PDF.

في هذا البرنامج التعليمي ، سنناقش كيفية استخدام Aspose.PDF for .NET للحصول على جميع الخطوط المستخدمة في مستند PDF. سنقدم دليلًا تفصيليًا حول كيفية القيام بذلك ، جنبًا إلى جنب مع مثال على كود المصدر.

## الخطوة 1: إنشاء تطبيق C # Console جديد
للبدء ، قم بإنشاء تطبيق C # Console جديد في Visual Studio. يمكنك تسميته ما شئت. بمجرد إنشاء المشروع ، تحتاج إلى إضافة مرجع إلى Aspose.PDF لمكتبة .NET.

## الخطوة 2: استيراد Aspose.PDF Namespace
أضف السطر التالي من التعليمات البرمجية أعلى ملف C # لاستيراد مساحة الاسم Aspose.PDF:

```csharp
using Aspose.Pdf;
```

## الخطوة 3: قم بتحميل مستند PDF
قم بتحميل مستند PDF الذي تريد الحصول على الخطوط منه:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## الخطوة 4: احصل على كافة الخطوط
احصل على جميع الخطوط المستخدمة في مستند PDF:

```csharp
Aspose.Pdf.Text.Font[] fonts = doc.FontUtilities.GetAllFonts();
```

## الخطوة 5: طباعة كافة الخطوط
اطبع جميع الخطوط المستخدمة في مستند PDF:

```csharp
foreach (Aspose.Pdf.Text.Font font in fonts)
{
    Console.WriteLine(font.FontName);
}
```

### مثال على التعليمات البرمجية المصدر لـ Get All Fonts باستخدام Aspose.PDF لـ .NET
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
Aspose.Pdf.Text.Font[] fonts = doc.FontUtilities.GetAllFonts();
foreach (Aspose.Pdf.Text.Font font in fonts)
{
    Console.WriteLine(font.FontName);
}
```

## خاتمة
في هذا البرنامج التعليمي ، ناقشنا كيفية الحصول على جميع الخطوط المستخدمة في مستند PDF باستخدام Aspose.PDF لـ .NET. يمكن أن يكون الحصول على جميع الخطوط المستخدمة في مستند PDF مفيدًا إذا كنت بحاجة إلى تحليل الخطوط أو معالجتها برمجيًا في مستند PDF. يوفر Aspose.PDF for .NET واجهة برمجة تطبيقات بسيطة وسهلة الاستخدام للعمل مع مستندات PDF ، بما في ذلك الحصول على جميع الخطوط المستخدمة في مستند PDF.


