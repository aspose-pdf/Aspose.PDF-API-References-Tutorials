---
title: EPUB إلى PDF
linktitle: EPUB إلى PDF
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لتحويل EPUB إلى PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 30
url: /ar/net/document-conversion/epub-to-pdf/
---

في هذا البرنامج التعليمي ، سنوجهك خلال عملية تحويل ملف EPUB إلى PDF باستخدام مكتبة Aspose.PDF لـ .NET. EPUB (المنشور الإلكتروني) هو تنسيق مستخدَم على نطاق واسع للكتب الإلكترونية ، بينما PDF (تنسيق المستند المحمول) هو معيار لتبادل المستندات. باتباع الخطوات الواردة أدناه ، ستتمكن من تحويل ملفات EPUB إلى تنسيق PDF دون عناء.

## المتطلبات الأساسية
قبل أن تبدأ ، تأكد من تلبية المتطلبات الأساسية التالية:

- المعرفة الأساسية بلغة البرمجة C #.
- تثبيت مكتبة Aspose.PDF لـ .NET على نظامك.
- بيئة تطوير مثل Visual Studio.

## الخطوة 1: تحميل ملف EPUB
في هذه الخطوة ، سنقوم بتحميل ملف EPUB باستخدام Aspose.PDF لـ .NET. اتبع الكود أدناه:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// إنشاء كائن LoadOption باستخدام خيار تحميل EPUB
EpubLoadOptions epubload = new EpubLoadOptions();

// قم بإنشاء كائن مستند
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document(dataDir + "EPUBToPDF.epub", epubload);
```

 تأكد من استبدال`"YOUR DOCUMENTS DIRECTORY"` مع الدليل الفعلي حيث يوجد ملف EPUB الخاص بك.

## الخطوة 2: تحويل EPUB إلى PDF
الآن بعد أن قمنا بتحميل ملف EPUB ، يمكننا متابعة التحويل إلى PDF. استخدم الكود التالي:

```csharp
// احفظ مستند PDF الناتج
pdf. Save(dataDir + "EPUBToPDF_out.pdf");
```

 يحول الكود أعلاه ملف EPUB الذي تم تحميله بتنسيق PDF ويحفظه كاسم ملف`"EPUBToPDF_out.pdf"`. تأكد من توفير المسار الصحيح واسم الملف لملف PDF الناتج.


 يستبدل`"YOUR DOCUMENTS DIRECTORY"` مع الدليل المطلوب حيث تريد حفظ ملف PDF الناتج.

### مثال على كود المصدر لـ EPUB إلى PDF باستخدام Aspose.PDF لـ .NET

```csharp
try
{
	
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// إنشاء كائن LoadOption باستخدام خيار تحميل EPUB
	EpubLoadOptions epubload = new EpubLoadOptions();

	// إنشاء كائن المستند
	Aspose.Pdf.Document pdf = new Aspose.Pdf.Document(dataDir + "EPUBToPDF.epub", epubload);

	// احفظ مستند PDF الناتج
	pdf.Save(dataDir + "EPUBToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}

```

## خاتمة
في هذا البرنامج التعليمي ، قمنا بتغطية العملية خطوة بخطوة لتحويل ملف EPUB إلى PDF باستخدام مكتبة Aspose.PDF لـ .NET. باتباع الإرشادات الموضحة أعلاه ، يجب أن تكون الآن قادرًا على تحويل ملفات EPUB إلى تنسيق PDF دون عناء. يفتح هذا التحويل إمكانيات مشاركة المستندات وطباعتها وأرشفتها.

