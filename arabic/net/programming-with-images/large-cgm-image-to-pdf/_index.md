---
title: صورة كبيرة CGM إلى PDF
linktitle: CGMI كبير صورة إلى PDF
second_title: Aspose.PDF لمرجع .NET API
description: قم بتحويل صورة CGM كبيرة بسهولة إلى PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 190
url: /ar/net/programming-with-images/large-cgm-image-to-pdf/
---

في هذا البرنامج التعليمي ، سنستعرض دليلًا تفصيليًا حول كيفية تحويل صورة CGM كبيرة إلى ملف PDF باستخدام مكتبة Aspose.PDF في .NET. يوضح كود المصدر C # المقدم عملية تحويل ملف CGM إلى تنسيق PDF ، وتحديد حجم الصفحة ، وحفظ ملف الإخراج. سنشرح كل خطوة بالتفصيل لمساعدتك على فهم العملية بدقة.

## متطلبات
قبل أن نبدأ ، تأكد من توفر لديك ما يلي:
- المعرفة الأساسية بلغة البرمجة C #.
- Aspose.PDF لمكتبة .NET مثبتة في مشروعك.
- ملف صورة CGM تريد تحويله إلى PDF.

## الخطوة الأولى: إنشاء المشروع
1. قم بإنشاء مشروع C # جديد في بيئة التطوير المفضلة لديك.
2. أضف مرجعًا إلى مكتبة Aspose.PDF في مشروعك.

## الخطوة 2: استيراد مساحات الأسماء الضرورية
في بداية ملف C # الخاص بك ، قم باستيراد مساحات الأسماء المطلوبة للوصول إلى فئات وطرق Aspose.PDF. هذا مثال:
```csharp
using System;
using Aspose.Pdf;
using System.Drawing;
```

## الخطوة 3: تهيئة المتغيرات والمسارات
قبل إجراء التحويل ، نحتاج إلى إعداد المتغيرات والمسارات اللازمة.
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inputFile = dataDir + "corvette.cgm";
dataDir = dataDir + "LargeCGMImageToPDF_out.pdf";
```
 تأكد من استبداله`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستند الخاص بك.

## الخطوة 4: تحويل CGM إلى PDF
لتحويل صورة CGM إلى تنسيق PDF ، اتبع الخطوات التالية:
1.  قم بإنشاء مثيل لـ`CgmImportOptions` فصل.
```csharp
CgmImportOptions options = new CgmImportOptions();
```
2. حدد أبعاد استيراد حجم الصفحة.
```csharp
options. PageSize = new SizeF(1000, 1000);
```
هنا ، قمنا بتعيين حجم الصفحة على 1000 × 1000 بكسل. يمكنك ضبط الأبعاد وفقًا لمتطلباتك.
 3. استخدم`PdfProducer.Produce` طريقة لتحويل ملف CGM إلى تنسيق PDF.
```csharp
PdfProducer.Produce(inputFile, ImportFormat.Cgm, dataDir);
```
4. اعرض رسالة نجاح بالمسار حيث تم حفظ ملف PDF.
```csharp
Console.WriteLine("\nLarge CGM file converted to PDF successfully.\nFile saved at " + dataDir);
```

### عينة من التعليمات البرمجية المصدر لـ Large CGMImage to PDF باستخدام Aspose.PDF for .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inputFile = dataDir + "corvette.cgm";
dataDir = dataDir + "LargeCGMImageToPDF_out.pdf";
// قم بإنشاء مثيل لـ CgmImportOptions
CgmImportOptions options = new CgmImportOptions();
// حدد أبعاد استيراد حجم الصفحة
options.PageSize = new SizeF(1000, 1000);
// حفظ CGM في تنسيق PDF
PdfProducer.Produce(inputFile, ImportFormat.Cgm, dataDir);
Console.WriteLine("\nLarge CGM file converted to pdf successfully.\nFile saved at " + dataDir); 
```

## خاتمة
باتباع هذا الدليل المفصل خطوة بخطوة ، تعلمت كيفية تحويل صورة CGM كبيرة إلى ملف PDF باستخدام مكتبة Aspose.PDF في .NET. تتضمن هذه العملية إعداد المشروع ، واستيراد مساحات الأسماء الضرورية ، وتهيئة المتغيرات والمسارات ، وإجراء التحويل. يمكنك الآن دمج هذا الرمز في مشاريعك الخاصة وتعديله وفقًا لمتطلباتك الخاصة.