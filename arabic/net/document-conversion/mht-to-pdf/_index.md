---
title: MHT إلى PDF
linktitle: MHT إلى PDF
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لتحويل MHT إلى PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 70
url: /ar/net/document-conversion/mht-to-pdf/
---

في هذا البرنامج التعليمي ، سنوجهك خلال عملية تحويل ملف MHT إلى PDF باستخدام Aspose.PDF لـ .NET. MHT (MIME HTML) هو تنسيق يستخدم لحفظ صفحة ويب كاملة ، بما في ذلك الصور والمحتوى المرتبط بها. باتباع الخطوات أدناه ، ستتمكن من تحويل ملفات MHT إلى تنسيق PDF.

## المتطلبات الأساسية
قبل أن تبدأ ، تأكد من تلبية المتطلبات الأساسية التالية:

- المعرفة الأساسية بلغة البرمجة C #.
- تثبيت مكتبة Aspose.PDF لـ .NET على نظامك.
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

 تأكد من استبدال`"YOUR DOCUMENTS DIRECTORY"` مع الدليل الفعلي حيث يوجد ملف MHT الخاص بك.

## الخطوة 2: تحويل MHT إلى PDF
بعد تحميل ملف MHT ، يمكننا المضي قدمًا في التحويل إلى PDF. استخدم الكود التالي:

```csharp
// احفظ الإخراج كمستند PDF
document.Save(dataDir + "MHTToPDF_out.pdf");
```

 يحول الكود أعلاه ملف MHT إلى تنسيق PDF ويحفظه كاسم ملف`"MHTToPDF_out.pdf"`.

### مثال على كود المصدر لـ MHT إلى PDF باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
MhtLoadOptions options = new MhtLoadOptions();
// تحميل المستند
Document document = new Document(dataDir  + "test.mht", options);
// احفظ الإخراج كمستند PDF
document.Save(dataDir + "MHTToPDF_out.pdf");
```

## خاتمة
في هذا البرنامج التعليمي ، قمنا بتغطية العملية خطوة بخطوة لتحويل ملف MHT إلى PDF باستخدام Aspose.PDF لـ .NET. باتباع الإرشادات الموضحة أعلاه ، يجب أن تكون الآن قادرًا على تحويل ملفات MHT إلى تنسيق PDF. يمكن أن تكون هذه الميزة مفيدة عندما تحتاج إلى تحويل صفحات الويب بأكملها إلى مستندات PDF.