---
title: إنشاء ملف PDF مع صورة ذات علامات
linktitle: إنشاء ملف PDF مع صورة ذات علامات
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لإنشاء ملف PDF مع صورة مميزة باستخدام Aspose.PDF for .NET.
type: docs
weight: 40
url: /ar/net/programming-with-tagged-pdf/create-pdf-with-tagged-image/
---
في هذا البرنامج التعليمي ، سنزودك بدليل تفصيلي حول كيفية إنشاء مستند PDF مع صورة مميزة باستخدام Aspose.PDF for .NET. Aspose.PDF هي مكتبة قوية تسمح لك بإنشاء مستندات PDF ومعالجتها وتحويلها برمجيًا. باستخدام ميزات بنية المحتوى الموسومة في Aspose.PDF ، يمكنك إضافة صور ذات علامات إلى مستند PDF الخاص بك.

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

## الخطوة 3: إنشاء مستند PDF بصورة مميزة

استخدم الكود التالي لإنشاء مستند PDF مع صورة ذات علامات:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Creating a PDF with a tagged image");
taggedContent.SetLanguage("fr-FR");

IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Picture 1";
figure1.SetTag("Fig");
figure1.SetImage(dataDir + @"aspose-logo.jpg");
```

ينشئ هذا الرمز مستند PDF فارغًا ويضيف صورة ذات علامات باستخدام الطرق التي يوفرها Aspose.PDF. يتم تحديد الصورة بنص بديل وعنوان وعلامة.

## الخطوة 4: حفظ مستند PDF

استخدم الكود التالي لحفظ مستند PDF:

```csharp
document.Save(dataDir + "PDFwithTaggedImage.pdf");
```

يحفظ هذا الرمز مستند PDF مع الصورة ذات العلامات في ملف محدد.

### عينة من التعليمات البرمجية المصدر لإنشاء PDF مع صورة ذات علامات باستخدام Aspose.PDF for .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("CreatePDFwithTaggedImage");
taggedContent.SetLanguage("en-US");
IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Image 1";
figure1.SetTag("Fig");
// إضافة صورة بدقة 300 نقطة في البوصة (افتراضيًا)
figure1.SetImage(dataDir + @"aspose-logo.jpg");
// حفظ وثيقة PDF
document.Save(dataDir + "PDFwithTaggedImage.pdf");

```

## خاتمة

في هذا البرنامج التعليمي ، تعلمت كيفية إنشاء مستند PDF مع صورة مميزة باستخدام Aspose.PDF for .NET. تضيف الصور ذات العلامات معلومات منظمة إضافية إلى مستند PDF الخاص بك.
