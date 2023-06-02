---
title: CGM إلى PDF
linktitle: CGM إلى PDF
second_title: Aspose.PDF لمرجع .NET API
description: قم بتحويل ملفات CGM بسهولة إلى PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 20
url: /ar/net/document-conversion/cgm-to-pdf/
---

في هذا البرنامج التعليمي ، سنوجهك خطوة بخطوة لتحويل CGM إلى PDF باستخدام Aspose.PDF for .NET. سنشرح كود المصدر C # المقدم ونقدم إرشادات خطوة بخطوة لمساعدتك على المتابعة بسهولة.

## مقدمة

يتيح لك تحويل ملف CGM إلى PDF مشاركة رسوماتك الفنية وعرضها عالميًا. باستخدام Aspose.PDF for .NET ، يمكنك إجراء هذا التحويل بسهولة والحصول على ملفات PDF عالية الجودة.

## إعداد البيئة

قبل أن تبدأ ، تأكد من تكوين بيئة التطوير الخاصة بك للعمل مع Aspose.PDF for .NET. اتبع الخطوات التالية:

1. قم بتثبيت Visual Studio أو IDE آخر متوافق مع تطوير C #.
2. إنشاء مشروع C # جديد.
3. قم بتثبيت حزمة Aspose.PDF لـ .NET عبر NuGet لإضافة التبعيات الضرورية.

## تحويل ملف CGM إلى PDF

لتحويل ملف CGM إلى PDF ، اتبع الخطوات التالية:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// إنشاء كائن LoadOption باستخدام CGMLoadOption
Aspose.Pdf.CgmLoadOptions cgmload = new Aspose.Pdf.CgmLoadOptions();
// إنشاء كائن مستند
Document doc = new Document(dataDir + "CGMToPDF.CGM", cgmload);
// احفظ مستند PDF الناتج
doc.Save(dataDir + "TECHDRAW_out.pdf");
```

 في الكود أعلاه ، تأكد من استبداله`"YOUR DOCUMENTS DIRECTORY"` بالمسار الفعلي للدليل حيث يوجد ملف CGM المراد تحويله. يقوم هذا الرمز بتحميل ملف CGM باستخدام امتداد`CgmLoadOptions` class ، ثم يقوم بإنشاء مستند PDF باستخدام`Document` هدف. أخيرًا ، يتم حفظ مستند PDF الناتج.

### مثال على شفرة المصدر لـ CGM إلى PDF باستخدام Aspose.Words for .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء كائن LoadOption باستخدام CGMLoadOption
Aspose.Pdf.CgmLoadOptions cgmload = new Aspose.Pdf.CgmLoadOptions();
// إنشاء كائن المستند
Document doc = new Document(dataDir + "CGMToPDF.CGM", cgmload);
// احفظ مستند PDF الناتج
doc.Save(dataDir+ "TECHDRAW_out.pdf");
```

## خاتمة

تهنئة ! أنت الآن تعرف كيفية تحويل ملف CGM إلى PDF باستخدام Aspose.PDF لـ .NET. لقد مررنا بكل خطوة من خطوات العملية ، من تهيئة خيارات تحميل CGM إلى حفظ مستند PDF الناتج. استخدم نماذج التعليمات البرمجية المتوفرة لدمج هذه الوظيفة في مشاريعك الخاصة. جرب Aspose.PDF لـ .NET واكتشف الاحتمالات الموسعة التي يوفرها لمعالجة ملفات PDF.
