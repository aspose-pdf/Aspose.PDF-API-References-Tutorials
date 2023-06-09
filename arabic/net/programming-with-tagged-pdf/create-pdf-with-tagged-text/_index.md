---
title: إنشاء ملف PDF بنص ذي علامات
linktitle: إنشاء ملف PDF بنص ذي علامات
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لإنشاء ملف PDF بنص مميز باستخدام Aspose.PDF for .NET.
type: docs
weight: 50
url: /ar/net/programming-with-tagged-pdf/create-pdf-with-tagged-text/
---
في هذا البرنامج التعليمي ، سنزودك بدليل تفصيلي حول كيفية إنشاء مستند PDF بنص ذي علامات باستخدام Aspose.PDF for .NET. Aspose.PDF هي مكتبة قوية تسمح لك بإنشاء مستندات PDF ومعالجتها وتحويلها برمجيًا. باستخدام ميزات بنية المحتوى الموسومة في Aspose.PDF ، يمكنك إضافة نص بعلامات إلى مستند PDF الخاص بك.

## المتطلبات الأساسية

قبل أن تبدأ ، تأكد من توفر المتطلبات الأساسية التالية:

1. Visual Studio مثبت مع .NET framework.
2. مكتبة Aspose.PDF لـ .NET.

## الخطوة 1: إعداد المشروع

للبدء ، أنشئ مشروعًا جديدًا في Visual Studio وأضف مرجعًا إلى Aspose.PDF لمكتبة .NET. يمكنك تنزيل المكتبة من موقع Aspose الرسمي وتثبيتها على جهازك.

## الخطوة 2: استيراد مساحات الأسماء الضرورية

في ملف كود C # الخاص بك ، قم باستيراد مساحات الأسماء المطلوبة للوصول إلى الفئات والطرق التي يوفرها Aspose.PDF:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## الخطوة 3: إنشاء مستند PDF بنص مميز

استخدم الكود التالي لإنشاء مستند PDF بنص مميز:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");

HeaderElement headerElement = taggedContent.CreateHeaderElement();
headerElement.ActualText = "Header 1";

ParagraphElement paragraphElement1 = taggedContent.CreateParagraphElement();
paragraphElement1.ActualText = "test1";

// أضف المزيد من الفقرات هنا

// احفظ مستند PDF
document.Save(dataDir + "PDFwithTagText.pdf");
```

ينشئ هذا الرمز مستند PDF فارغًا ويضيف نصًا مميزًا باستخدام الطرق التي يوفرها Aspose.PDF. يمكنك إضافة عناصر نصية ذات علامات تمييز مثل العناوين والفقرات باستخدام الطرق المناسبة.

### عينة من التعليمات البرمجية المصدر لإنشاء PDF مع نص ذي علامات تمييز باستخدام Aspose.PDF for .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// إنشاء مستند PDF
Document document = new Document();
// الحصول على محتوى للعمل مع TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;
// تعيين العنوان واللغة للوثيقة
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
// تكوين عناصر هيكل مستوى كتلة النص
HeaderElement headerElement = taggedContent.CreateHeaderElement();
headerElement.ActualText = "Heading 1";
ParagraphElement paragraphElement1 = taggedContent.CreateParagraphElement();
paragraphElement1.ActualText = "test1";
ParagraphElement paragraphElement2 = taggedContent.CreateParagraphElement();
paragraphElement2.ActualText = "test 2";
ParagraphElement paragraphElement3 = taggedContent.CreateParagraphElement();
paragraphElement3.ActualText = "test 3";
ParagraphElement paragraphElement4 = taggedContent.CreateParagraphElement();
paragraphElement4.ActualText = "test 4";
ParagraphElement paragraphElement5 = taggedContent.CreateParagraphElement();
paragraphElement5.ActualText = "test 5";
ParagraphElement paragraphElement6 = taggedContent.CreateParagraphElement();
paragraphElement6.ActualText = "test 6";
ParagraphElement paragraphElement7 = taggedContent.CreateParagraphElement();
paragraphElement7.ActualText = "test 7";
// حفظ وثيقة PDF
document.Save( dataDir + "PDFwithTaggedText.pdf");

```

## خاتمة

في هذا البرنامج التعليمي ، تعلمت كيفية إنشاء مستند PDF بنص ذي علامات باستخدام Aspose.PDF for .NET. تسمح لك ميزات بنية المحتوى المميزة لـ Aspose.PDF بهيكلة وتنظيم النص الخاص بك لتحسين إمكانية الوصول والدلالات.
