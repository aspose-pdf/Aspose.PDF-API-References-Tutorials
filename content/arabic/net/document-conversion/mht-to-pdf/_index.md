---
title: MHT إلى PDF
linktitle: MHT إلى PDF
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لتحويل MHT إلى PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 70
url: /ar/net/document-conversion/mht-to-pdf/
---
في هذا البرنامج التعليمي، سنرشدك خلال عملية تحويل ملف MHT إلى PDF باستخدام Aspose.PDF لـ .NET. MHT (MIME HTML) هو تنسيق يستخدم لحفظ صفحة ويب كاملة، بما في ذلك الصور والمحتوى المرتبط بها. باتباع الخطوات أدناه، ستتمكن من تحويل ملفات MHT إلى تنسيق PDF.

## المتطلبات الأساسية
قبل البدء، تأكد من استيفاء المتطلبات الأساسية التالية:

- المعرفة الأساسية بلغة البرمجة C#.
- مكتبة Aspose.PDF لـ .NET مثبتة على نظامك.
- بيئة تطوير مثل Visual Studio.

## الخطوة 1: تحميل ملف MHT
في هذه الخطوة سنقوم بتحميل ملف MHT باستخدام Aspose.PDF لـ .NET. اتبع الكود أدناه:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

MhtLoadOptions options = new MhtLoadOptions();

// قم بتحميل المستند
Document document = new Document(dataDir + "test.mht", options);
```

 تأكد من استبدال`"YOUR DOCUMENTS DIRECTORY"` مع الدليل الفعلي الذي يوجد به ملف MHT الخاص بك.

## الخطوة 2: تحويل MHT إلى PDF
بعد تحميل ملف MHT، يمكننا متابعة التحويل إلى PDF. استخدم الكود التالي:

```csharp
// احفظ الإخراج كمستند PDF
document.Save(dataDir + "MHTToPDF_out.pdf");
```

 يقوم الكود أعلاه بتحويل ملف MHT إلى تنسيق PDF وحفظه كاسم الملف`"MHTToPDF_out.pdf"`.

### مثال على التعليمات البرمجية المصدر لـ MHT إلى PDF باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
MhtLoadOptions options = new MhtLoadOptions();
// قم بتحميل المستند
Document document = new Document(dataDir  + "test.mht", options);
// احفظ الإخراج كمستند PDF
document.Save(dataDir + "MHTToPDF_out.pdf");
```

## خاتمة
في هذا البرنامج التعليمي، قمنا بتغطية العملية خطوة بخطوة لتحويل ملف MHT إلى PDF باستخدام Aspose.PDF لـ .NET. باتباع الإرشادات الموضحة أعلاه، يجب أن تكون الآن قادرًا على تحويل ملفات MHT إلى تنسيق PDF. يمكن أن تكون هذه الميزة مفيدة عندما تحتاج إلى تحويل صفحات الويب بأكملها إلى مستندات PDF.

### الأسئلة الشائعة

#### س: هل يدعم Aspose.PDF for .NET تحويل ملفات MHT مع الصور المضمنة إلى PDF؟

ج: نعم، يدعم Aspose.PDF for .NET تحويل ملفات MHT مع الصور المضمنة إلى PDF. يمكن للمكتبة التعامل مع محتوى صفحة الويب بالكامل، بما في ذلك الصور والموارد المرتبطة بها، وتحويله إلى مستند PDF.

#### س: هل يمكنني تخصيص إخراج PDF أثناء عملية تحويل MHT إلى PDF؟

ج: نعم، يوفر Aspose.PDF for .NET خيارات متنوعة لتخصيص مخرجات PDF أثناء عملية تحويل MHT إلى PDF. يمكنك تعيين خصائص مثل حجم الصفحة والاتجاه والهوامش والمزيد للتحكم في مظهر مستند PDF الناتج.

#### س: هل يحتفظ Aspose.PDF for .NET بالارتباطات التشعبية والتنسيقات من ملف MHT الأصلي في مخرجات PDF؟

ج: نعم، يحتفظ Aspose.PDF for .NET بالارتباطات التشعبية والتنسيقات من ملف MHT الأصلي في مخرجات PDF. تضمن المكتبة أن يحتفظ ملف PDF المحول بنفس التخطيط والمحتوى مثل ملف MHT المصدر.

#### س: هل يمكنني تحويل ملفات MHT متعددة إلى مستندات PDF منفصلة باستخدام Aspose.PDF لـ .NET؟

ج: نعم، يمكنك تحويل ملفات MHT متعددة إلى مستندات PDF منفصلة باستخدام Aspose.PDF لـ .NET. ما عليك سوى تحميل كل ملف MHT وحفظه كمستند PDF منفصل باسم ملف فريد.