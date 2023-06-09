---
title: PDF إلى PDFA3b
linktitle: PDF إلى PDFA3b
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لتحويل PDF إلى PDF / A-3b باستخدام Aspose.PDF for .NET.
type: docs
weight: 150
url: /ar/net/document-conversion/pdf-to-pdfa3b/
---

في هذا البرنامج التعليمي ، سنرشدك خلال عملية تحويل ملف PDF إلى تنسيق PDF / A-3b باستخدام Aspose.PDF for .NET. PDF / A-3b هو معيار ISO لدمج الملفات والبيانات في مستند PDF. باتباع الخطوات أدناه ، ستتمكن من تحويل ملفات PDF إلى تنسيق PDF / A-3b.

## المتطلبات الأساسية
قبل أن تبدأ ، تأكد من تلبية المتطلبات الأساسية التالية:

- المعرفة الأساسية بلغة البرمجة C #.
- تثبيت مكتبة Aspose.PDF لـ .NET على نظامك.
- بيئة تطوير مثل Visual Studio.

## الخطوة 1: فتح ملف PDF المصدر
في هذه الخطوة ، سنفتح ملف PDF المصدر باستخدام Aspose.PDF لـ .NET. اتبع الكود أدناه:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// افتح مستند PDF المصدر
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 تأكد من استبدال`"YOUR DOCUMENTS DIRECTORY"` مع الدليل الفعلي حيث يوجد ملف PDF الخاص بك.

## الخطوة 2: التحويل إلى PDF / A-3b
بعد فتح ملف PDF ، يمكننا متابعة التحويل إلى تنسيق PDF / A-3b. استخدم الكود التالي:

```csharp
// قم بالتحويل إلى تنسيق PDF / A-3b
pdfDocument.Convert(new MemoryStream(), PdfFormat.PDF_A_3B, ConvertErrorAction.Delete);
```

يحول الكود أعلاه ملف PDF إلى تنسيق PDF / A-3b ويزيل أي أخطاء في التحويل.

## الخطوة 3: حفظ ملف PDF / A-3b الناتج
بعد اكتمال التحويل ، نحتاج إلى حفظ ملف PDF / A-3b الناتج. هذه هي الخطوة الأخيرة:

```csharp
dataDir = dataDir + "PDFToPDFA3b_out.pdf";
// احفظ المستند الناتج
pdfDocument.Save(dataDir);
```

 يستبدل`"YOUR DOCUMENTS DIRECTORY"` مع الدليل المطلوب حيث تريد حفظ ملف PDF / A-3b الناتج.

### مثال على كود المصدر لـ PDF إلى PDFA3b باستخدام Aspose.PDF for .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح المستند
Document pdfDocument = new Document(dataDir + "input.pdf");            

pdfDocument.Convert(new MemoryStream(), PdfFormat.PDF_A_3B, ConvertErrorAction.Delete);

dataDir = dataDir + "PDFToPDFA3b_out.pdf";
// حفظ وثيقة الإخراج
pdfDocument.Save(dataDir);

Console.WriteLine("\nPDF file converted to PDF/A-3B format.\nFile saved at " + dataDir);
```

## خاتمة
في هذا البرنامج التعليمي ، قمنا بتغطية العملية خطوة بخطوة لتحويل ملف PDF إلى تنسيق PDF / A-3b باستخدام Aspose.PDF لـ .NET. باتباع الإرشادات الموضحة أعلاه ، يجب أن تكون الآن قادرًا على تحويل ملفات PDF إلى تنسيق PDF / A-3b. هذه الميزة مفيدة عندما تريد دمج ملفات وبيانات إضافية في مستند PDF يتوافق مع معيار PDF / A-3b.