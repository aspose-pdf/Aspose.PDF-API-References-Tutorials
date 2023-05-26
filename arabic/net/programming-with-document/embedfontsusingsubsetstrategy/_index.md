---
title: دمج الخطوط باستخدام استراتيجية المجموعة الفرعية
linktitle: دمج الخطوط باستخدام استراتيجية المجموعة الفرعية
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تضمين الخطوط في ملف PDF باستخدام استراتيجية المجموعة الفرعية باستخدام Aspose.PDF for .NET. قم بتحسين حجم PDF الخاص بك عن طريق تضمين الأحرف الضرورية فقط.
type: docs
weight: 130
url: /ar/net/programming-with-document/embedfontsusingsubsetstrategy/
---

في هذا البرنامج التعليمي ، سنناقش كيفية تضمين الخطوط في ملف PDF باستخدام إستراتيجية مجموعة فرعية باستخدام Aspose.PDF لـ .NET. Aspose.PDF for .NET مكتبة قوية تتيح للمطورين إنشاء مستندات PDF وتحريرها ومعالجتها برمجيًا. يعد دمج الخطوط في ملف PDF خطوة مهمة لضمان عرض المستند بشكل صحيح على أجهزة مختلفة ، بغض النظر عما إذا كانت الخطوط المطلوبة مثبتة على تلك الأجهزة أم لا.

## الخطوة 1: إنشاء تطبيق C # Console جديد
للبدء ، قم بإنشاء تطبيق C # Console جديد في Visual Studio. يمكنك تسميته ما شئت. بمجرد إنشاء المشروع ، تحتاج إلى إضافة مرجع إلى Aspose.PDF لمكتبة .NET.

## الخطوة 2: استيراد Aspose.PDF Namespace
أضف السطر التالي من التعليمات البرمجية أعلى ملف C # لاستيراد مساحة الاسم Aspose.PDF:

```csharp
using Aspose.Pdf;
```

## الخطوة 3: تحميل ملف PDF موجود
لتضمين الخطوط في ملف PDF موجود ، تحتاج إلى تحميل هذا الملف باستخدام فئة المستند. يوضح الكود التالي كيفية تحميل ملف PDF موجود:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// قم بتحميل ملف PDF موجود
Document doc = new Document(dataDir + "input.pdf");
```

## الخطوة 4: تضمين الخطوط مع إستراتيجية المجموعة الفرعية
يوفر Aspose.PDF for .NET استراتيجيتين لدمج الخط: SubsetAllFonts و SubsetEmbeddedFontsOnly.

ستدمج استراتيجية SubsetAllFonts كل الخطوط في الوثيقة كمجموعة فرعية. المجموعة الفرعية هي جزء من الخط يحتوي فقط على الأحرف المستخدمة في المستند. هذه الإستراتيجية مفيدة لتقليل حجم ملف وثيقة PDF.

سوف تقوم استراتيجية SubsetEmbeddedFontsOnly بتضمين المجموعة الفرعية فقط من الخطوط المضمنة بالفعل في المستند. إذا لم يتم تضمين الخط ، فلن يتأثر بهذه الإستراتيجية.

يوضح الكود التالي كيفية تضمين الخطوط في ملف PDF بإستراتيجية مجموعة فرعية:

```csharp
// سيتم تضمين جميع الخطوط كمجموعة فرعية في المستند في حالة SubsetAllFonts.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetAllFonts);

// سيتم دمج مجموعة الخطوط الفرعية للخطوط المضمنة بالكامل ولكن الخطوط التي لم يتم تضمينها في المستند لن تتأثر.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetEmbeddedFontsOnly);
```

## الخطوة 5: احفظ مستند PDF
بمجرد قيامك بدمج جميع الخطوط في ملف PDF باستخدام إستراتيجية مجموعة فرعية ، فإنك تحتاج إلى حفظ المستند. يوضح الكود التالي كيفية حفظ ملف PDF:

```csharp
doc.Save(dataDir + "Output_out.pdf");
```

### مثال على كود المصدر لتضمين الخطوط مع إستراتيجية المجموعة الفرعية باستخدام Aspose.PDF for .NET. 

```csharp

            
            // المسار إلى دليل المستندات.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document(dataDir + "input.pdf");
            // سيتم تضمين جميع الخطوط كمجموعة فرعية في المستند في حالة SubsetAllFonts.
            doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetAllFonts);
            // سيتم دمج مجموعة الخطوط الفرعية للخطوط المضمنة بالكامل ولكن الخطوط التي لم يتم تضمينها في المستند لن تتأثر.
            doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetEmbeddedFontsOnly);
            doc.Save(dataDir + "Output_out.pdf");
            

        
```

## خاتمة
في هذه المقالة ، ناقشنا كيفية تضمين الخطوط في ملف PDF باستخدام إستراتيجية مجموعة فرعية باستخدام Aspose.PDF لـ .NET. يوفر Aspose.PDF for .NET واجهة برمجة تطبيقات بسيطة وسهلة الاستخدام للعمل مع مستندات PDF ، بما في ذلك إضافة الخطوط وتضمينها باستراتيجيات مختلفة. يعد دمج الخطوط في ملف PDF خطوة مهمة لضمان عرض المستند بشكل صحيح على أجهزة مختلفة ، وإستراتيجية المجموعة الفرعية هي ميزة مفيدة لتقليل حجم ملف مستند PDF.

