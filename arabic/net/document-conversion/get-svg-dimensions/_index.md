---
title: احصل على أبعاد SVG
linktitle: احصل على أبعاد SVG
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة للحصول على أبعاد SVG باستخدام Aspose.PDF for .NET.
type: docs
weight: 40
url: /ar/net/document-conversion/get-svg-dimensions/
---
## مقدمة
في هذا البرنامج التعليمي ، سنرشدك خلال عملية الحصول على أبعاد ملف SVG باستخدام Aspose.PDF لـ .NET. SVG (Scalable Vector Graphics) هو تنسيق صورة مستند إلى XML يستخدم لتمثيل الرسومات المتجهة. باستخدام الخطوات أدناه ، ستتمكن من الحصول على أبعاد ملف SVG وحفظها كملف PDF.

## المتطلبات الأساسية
قبل أن تبدأ ، تأكد من تلبية المتطلبات الأساسية التالية:

- المعرفة الأساسية بلغة البرمجة C #.
- تثبيت مكتبة Aspose.PDF لـ .NET على نظامك.
- بيئة تطوير مثل Visual Studio.

## الخطوة 1: تحميل ملف SVG
في هذه الخطوة ، سنقوم بتحميل ملف SVG باستخدام Aspose.PDF لـ .NET. اتبع الكود أدناه:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

var loadopt = new SvgLoadOptions();
loadopt.AdjustPageSize = true;
var svgDoc = new Document(dataDir + "GetSVGDimensions.svg", loadopt);
```

 تأكد من استبدال`"YOUR DOCUMENTS DIRECTORY"` مع الدليل الفعلي حيث يوجد ملف SVG الخاص بك.

## الخطوة 2: تعديل حجم الصفحة
الآن بعد أن قمنا بتحميل ملف SVG ، يمكننا ضبط حجم الصفحة لتلائم محتوى SVG. استخدم الكود التالي:

```csharp
svgDoc.Pages[1].PageInfo.Margin.Top = 0;
svgDoc.Pages[1].PageInfo.Margin.Left = 0;
svgDoc.Pages[1].PageInfo.Margin.Bottom = 0;
svgDoc.Pages[1].PageInfo.Margin.Right = 0;
```

يحدد الكود أعلاه هوامش الصفحة إلى الصفر ، مما يسمح بتعديل حجم الصفحة بناءً على محتوى SVG.

## الخطوة 3: حفظ ملف PDF الناتج
بعد ضبط حجم الصفحة ، يمكننا الآن حفظ مستند PDF الناتج. هذه هي الخطوة الأخيرة:

```csharp
svgDoc.Save(dataDir + "GetSVGDimensions_out.pdf");
```

 يستبدل`"YOUR DOCUMENTS DIRECTORY"` مع الدليل المطلوب حيث تريد حفظ ملف PDF الناتج.
  
### مثال على شفرة المصدر للحصول على أبعاد SVG باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

var loadopt = new SvgLoadOptions();
loadopt.AdjustPageSize = true;
var svgDoc = new Document(dataDir + "GetSVGDimensions.svg", loadopt);
svgDoc.Pages[1].PageInfo.Margin.Top = 0;
svgDoc.Pages[1].PageInfo.Margin.Left = 0;
svgDoc.Pages[1].PageInfo.Margin.Bottom = 0;
svgDoc.Pages[1].PageInfo.Margin.Right = 0;
svgDoc.Save(dataDir + "GetSVGDimensions_out.pdf");
```

## خاتمة
في هذا البرنامج التعليمي ، قمنا بتغطية العملية خطوة بخطوة للحصول على أبعاد ملف SVG باستخدام Aspose.PDF لـ .NET. باتباع الإرشادات الموضحة أعلاه ، يجب أن تكون قادرًا الآن على الحصول على أبعاد ملف SVG وحفظها في تنسيق PDF. يمكن أن تكون هذه الميزة مفيدة عندما تحتاج إلى قياس أبعاد الرسم المتجه.

### التعليمات

#### س: ما هو SVG؟

ج: SVG (Scalable Vector Graphics) هو تنسيق صورة مستند إلى XML يستخدم لتمثيل الرسومات المتجهة. على عكس الصور النقطية ، فإن ملفات SVG مستقلة عن الدقة ويمكن قياسها دون فقدان الجودة. يستخدم SVG على نطاق واسع لعرض الرسومات على الويب ويمكن تحريره ومعالجته بسهولة.

#### س: لماذا تستخدم Aspose.PDF لـ .NET لتحويل SVG إلى PDF؟

ج: يوفر Aspose.PDF for .NET طريقة موثوقة وفعالة للتعامل مع ملفات SVG وتحويلها إلى تنسيق PDF. يوفر خيارات وإعدادات متنوعة لتخصيص عملية التحويل ، مثل ضبط حجم الصفحة والهوامش والخصائص الأخرى لضمان التمثيل الدقيق في ملف PDF.

#### س: هل يمكنني تحويل ملفات SVG برسومات ونصوص معقدة؟

ج: نعم ، يمكن لـ Aspose.PDF for .NET التعامل مع ملفات SVG ذات الرسومات المعقدة والنصوص وعناصر المتجهات. إنه يحافظ بدقة على تفاصيل وجودة محتوى SVG أثناء عملية التحويل ، مما ينتج عنه مستندات PDF عالية الجودة.

#### س: هل من الممكن استخراج نص من ملفات SVG باستخدام Aspose.PDF for .NET؟

ج: نعم ، يسمح لك Aspose.PDF for .NET باستخراج النص من ملفات SVG. يمكنك استخدام ميزات استخراج نصوص المكتبة لاستخراج عناصر النص من SVG وحفظها بشكل منفصل لمزيد من المعالجة.