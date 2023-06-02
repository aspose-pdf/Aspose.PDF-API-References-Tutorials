---
title: XML إلى PDF
linktitle: XML إلى PDF
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لتحويل ملف XML إلى PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 330
url: /ar/net/document-conversion/xml-to-pdf/
---

في هذا البرنامج التعليمي ، سنرشدك إلى كيفية تحويل ملف XML إلى PDF باستخدام مكتبة Aspose.PDF لـ .NET خطوة بخطوة. سنقوم بتفصيل كود المصدر C # المقدم ونوضح لك كيفية تنفيذه في مشاريعك الخاصة. بنهاية هذا البرنامج التعليمي ، ستتمكن من تحويل ملفات XML بسهولة إلى مستندات PDF.

## الخطوة 1: تعيين دليل المستندات
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```
 يستبدل`"YOUR DOCUMENTS DIRECTORY"` بالمسار الذي تريد حفظ ملف PDF الذي تم إنشاؤه فيه.

## الخطوة 2: إنشاء كائن مستند
```csharp
Document doc = new Document();
```
قم بإنشاء مثيل لكائن المستند.

## الخطوة 3: اربط ملف XML المصدر
```csharp
doc.BindXml(dataDir + "sample.xml");
```
يربط ملف XML المصدر بالمستند.

## الخطوة 4: احصل على مرجع كائن الصفحة من XML
```csharp
Page page = (Page)doc.GetObjectById("mainSection");
```
احصل على مرجع كائن الصفحة من XML باستخدام المعرف الخاص به.

## الخطوة 5: احصل على مرجع جزء النص من XML
```csharp
TextSegment segment = (TextSegment)doc.GetObjectById("boldHtml");
segment = (TextSegment)doc.GetObjectById("strongHtml");
```
احصل على مرجع لمقاطع النص من XML باستخدام معرفاتهم. يمكنك إضافة المزيد من الشرائح حسب الحاجة.

## الخطوة 6: احفظ ملف PDF الناتج
```csharp
doc.Save(dataDir + "XMLToPDF_out.pdf");
```
احفظ ملف PDF الناتج في الدليل المحدد.

### مثال على شفرة المصدر لـ XML إلى PDF باستخدام Aspose.Words for .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء كائن المستند
Document doc = new Document();
// ربط ملف XML المصدر
doc.BindXml( dataDir + "sample.xml");
// احصل على مرجع لكائن الصفحة من XML
Page page = (Page)doc.GetObjectById("mainSection");
// احصل على مرجع أول جزء نصي مع معرف boldHtml
TextSegment segment = (TextSegment)doc.GetObjectById("boldHtml");
// احصل على مرجع للجزء الثاني من TextSegment بمعرف strongHtml
segment = (TextSegment)doc.GetObjectById("strongHtml");
// حفظ ملف PDF الناتج
doc.Save(dataDir + "XMLToPDF_out.pdf");
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية تحويل ملف XML إلى PDF باستخدام مكتبة Aspose.PDF لـ .NET. لقد قمنا بتفصيل كود المصدر C # المقدم وشرحنا كل خطوة من خطوات عملية التحويل. باتباع هذه التعليمات ، يمكنك بسهولة دمج وظيفة تحويل XML إلى PDF في تطبيقات .NET الخاصة بك.