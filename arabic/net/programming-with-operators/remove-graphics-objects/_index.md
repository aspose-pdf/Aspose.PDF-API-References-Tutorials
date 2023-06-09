---
title: قم بإزالة كائنات الرسومات
linktitle: قم بإزالة كائنات الرسومات
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لإزالة الكائنات الرسومية من مستند PDF باستخدام Aspose.PDF for .NET. تخصيص وتنظيف ملفات PDF الخاصة بك.
type: docs
weight: 30
url: /ar/net/programming-with-operators/remove-graphics-objects/
---
في هذا البرنامج التعليمي ، سنزودك بدليل تفصيلي حول كيفية إزالة الكائنات الرسومية من مستند PDF باستخدام Aspose.PDF for .NET. Aspose.PDF هي مكتبة قوية تسمح لك بإنشاء مستندات PDF ومعالجتها وتحويلها برمجيًا. باستخدام عوامل التشغيل التي يوفرها Aspose.PDF ، يمكنك استهداف وإزالة كائنات رسومية معينة من صفحة PDF.

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
using Aspose.Pdf.Operators;
```

## الخطوة 3: تحميل مستند PDF

استخدم الكود التالي لتحميل مستند PDF:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document doc = new Document(dataDir + "RemoveGraphicsObjects.pdf");
Page page = doc.Pages[2];
OperatorCollection oc = page.Contents;
```

تأكد من تحديد المسار الفعلي لملف PDF على جهازك وضبط رقم الصفحة حسب الحاجة.

## الخطوة 4: حذف الكائنات الرسومية

استخدم الكود التالي لإزالة الكائنات الرسومية من صفحة PDF:

```csharp
Operator[] operators = new Operator[] {
newStroke(),
new ClosePathStroke(),
newFill()
};
oc.Delete(operators);
```

يزيل الكود أعلاه الكائنات الرسومية المحددة بواسطة عوامل Stroke و Path Close و Fill.

### نموذج التعليمات البرمجية المصدر لإزالة كائنات الرسومات باستخدام Aspose.PDF لـ .NET
 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir+ "RemoveGraphicsObjects.pdf");
Page page = doc.Pages[2];
OperatorCollection oc = page.Contents;
// استخدام عوامل رسم المسار
Operator[] operators = new Operator[] {
		new Aspose.Pdf.Operators.Stroke(),
		new Aspose.Pdf.Operators.ClosePathStroke(),
		new Aspose.Pdf.Operators.Fill()
};
oc.Delete(operators);
doc.Save(dataDir+ "No_Graphics_out.pdf");

```

## خاتمة

في هذا البرنامج التعليمي ، تعلمت كيفية إزالة الكائنات الرسومية من مستند PDF باستخدام Aspose.PDF لـ .NET. باستخدام عوامل التشغيل التي يوفرها Aspose.PDF ، يمكنك استهداف وإزالة كائنات رسومية معينة من صفحة PDF. يتيح لك ذلك تخصيص محتوى مستندات PDF وتنظيفه وفقًا لاحتياجاتك.
