---
title: SVG إلى PDF
linktitle: SVG إلى PDF
second_title: Aspose.PDF لمرجع .NET API
description: تحويل SVG إلى PDF سهل وسريع باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 280
url: /ar/net/document-conversion/svg-to-pdf/
---

سيرشدك هذا البرنامج التعليمي خلال خطوات تحويل ملف SVG إلى ملف PDF باستخدام Aspose.PDF for .NET. يقدم Aspose.PDF حلاً بسيطًا وفعالاً لتحويل ملفات SVG إلى PDF مع الحفاظ على جودة المحتوى وتخطيطه. اتبع الخطوات أدناه لإجراء هذا التحويل.

## المتطلبات الأساسية
قبل أن تبدأ ، تأكد من تلبية المتطلبات الأساسية التالية:

- المعرفة الأساسية بلغة البرمجة C #.
- تثبيت مكتبة Aspose.PDF لـ .NET على نظامك.
- بيئة تطوير مثل Visual Studio.

## الخطوة 1: تحميل ملف SVG
 تتمثل الخطوة الأولى في تحميل ملف SVG في ملف`Document`كائن باستخدام خيار تحميل SVG (`SvgLoadOptions`). استخدم الكود التالي:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// إنشاء كائن LoadOption باستخدام خيار تحميل SVG
Aspose.Pdf.LoadOptions loadopt = new Aspose.Pdf.SvgLoadOptions();

// إنشاء كائن المستند
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SVGToPDF.svg", loadopt);
```

 تأكد من استبدال`"YOUR DOCUMENTS DIRECTORY"` مع الدليل الفعلي حيث يوجد ملف SVG الخاص بك.

## الخطوة 2: التحويل إلى PDF
 الخطوة الثانية هي تحويل مستند SVG إلى مستند PDF باستخدام امتداد الملف`Save` طريقة`Document` هدف. استخدم الكود التالي:

```csharp
// احفظ مستند PDF الناتج
doc.Save(dataDir + "SVGToPDF_out.pdf");
```

تأكد من تحديد المسار المطلوب واسم الملف لملف PDF الناتج.

### مثال على شفرة المصدر لـ SVG إلى PDF باستخدام Aspose.Words for .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء كائن LoadOption باستخدام خيار تحميل SVG
Aspose.Pdf.LoadOptions loadopt = new Aspose.Pdf.SvgLoadOptions();

// إنشاء كائن المستند
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SVGToPDF.svg", loadopt);

// احفظ مستند PDF الناتج
doc.Save(dataDir + "SVGToPDF_out.pdf");
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية تحويل ملف SVG إلى ملف PDF باستخدام Aspose.PDF لـ .NET. باتباع الخطوات المذكورة أعلاه ، يمكنك بسهولة إجراء هذا التحويل. استخدم هذه الطريقة لتحويل ملفات SVG إلى PDF واستمتع بمرونة وجودة Aspose.PDF.