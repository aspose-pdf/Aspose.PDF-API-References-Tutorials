---
title: PDF إلى XML
linktitle: PDF إلى XML
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لتحويل PDF إلى XML باستخدام Aspose.PDF for .NET.
type: docs
weight: 210
url: /ar/net/document-conversion/pdf-to-xml/
---

في هذا البرنامج التعليمي ، سنرشدك خلال عملية تحويل ملف PDF إلى تنسيق XML باستخدام Aspose.PDF for .NET. XML (لغة التوصيف القابلة للتمدد) هي تنسيق بيانات يُستخدم لتخزين المعلومات المهيكلة وتبادلها. باتباع الخطوات أدناه ، ستتمكن من تحويل ملف PDF إلى تنسيق XML.

## المتطلبات الأساسية
قبل أن تبدأ ، تأكد من تلبية المتطلبات الأساسية التالية:

- المعرفة الأساسية بلغة البرمجة C #.
- تثبيت مكتبة Aspose.PDF لـ .NET على نظامك.
- بيئة تطوير مثل Visual Studio.

## الخطوة 1: تحميل مستند PDF
في هذه الخطوة سنقوم بتحميل ملف PDF المصدر باستخدام Aspose.PDF for .NET. اتبع الكود أدناه:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بتحميل مستند PDF
Document doc = new Document(dataDir + "input.pdf");
```

 تأكد من استبدال`"YOUR DOCUMENTS DIRECTORY"` مع الدليل الفعلي حيث يوجد ملف PDF الخاص بك.

## الخطوة 2: حفظ ملف XML الناتج
الآن سنقوم بحفظ ملف PDF المحول بتنسيق XML. استخدم الكود التالي:

```csharp
// احفظ الإخراج بتنسيق XML
doc.Save(dataDir + "PDFToXML_out.xml", SaveFormat.MobiXml);
```

 يحفظ الكود أعلاه ملف PDF المحول بتنسيق XML مع اسم الملف`"PDFToXML_out.xml"`.

### مثال على كود المصدر لـ PDF إلى XML باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";            
// قم بتحميل ملف PDF المصدر
Document doc = new Document(dataDir + "input.pdf");
// احفظ الإخراج بتنسيق XML
doc.Save(dataDir + "PDFToXML_out.xml", SaveFormat.MobiXml);
```

## خاتمة
في هذا البرنامج التعليمي ، قمنا بتغطية العملية خطوة بخطوة لتحويل ملف PDF إلى XML باستخدام Aspose.PDF لـ .NET. باتباع الإرشادات الموضحة أعلاه ، يجب أن تكون قادرًا الآن على تحويل ملف PDF إلى تنسيق XML. هذه الميزة مفيدة عندما تريد استخراج محتوى منظم من ملف PDF ومعالجته في تنسيق XML لاستخدامه لاحقًا.