---
title: تعيين معلومات الملف
linktitle: تعيين معلومات الملف
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استخدام Aspose.PDF for .NET لتعيين معلومات الملف في مستندات PDF الخاصة بك باستخدام هذا الدليل التفصيلي.
type: docs
weight: 310
url: /ar/net/programming-with-document/setfileinfo/
---
إذا كنت تعمل في مشروع يتطلب إدارة ملفات PDF باستخدام Aspose.PDF for .NET ، فإن إحدى الميزات التي قد ترغب في استخدامها هي القدرة على تعيين معلومات الملف لمستند PDF. تتضمن معلومات الملف تفاصيل مختلفة مثل المؤلف وتاريخ الإنشاء والكلمات الرئيسية وتاريخ التعديل والموضوع والعنوان. سيرشدك هذا الدليل خلال عملية تعيين معلومات الملف لمستند PDF باستخدام الكود المصدري C # مع Aspose.PDF for .NET.

## دليل خطوة بخطوة لإعداد معلومات الملف باستخدام Aspose.PDF for .NET

1. قم بإنشاء مشروع C # جديد في Visual Studio IDE الخاص بك.
2. أضف مرجعًا إلى مكتبة Aspose.PDF لـ .NET في مشروعك.
3. قم بإنشاء كائن مستند PDF جديد من خلال توفير المسار إلى ملف PDF الذي تريد تعديل معلومات الملف له.

## الخطوة 1: حدد المسار إلى دليل المستندات.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: افتح مستند PDF

```csharp
// افتح المستند
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");
```

## الخطوة 3: استخدم كائن DocumentInfo للوصول إلى معلومات ملف مستند PDF.

```csharp
DocumentInfo docInfo = new DocumentInfo(pdfDocument);
```

## الخطوة 4: قم بتعيين قيم معلومات الملف المطلوبة باستخدام خصائص كائن DocumentInfo.

```csharp
docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";
```

## الخطوة 5: احفظ مستند PDF المحدث في الموقع المحدد.

```csharp
dataDir = dataDir + "SetFileInfo_out.pdf";
pdfDocument.Save(dataDir);
```

## الخطوة 6: تحقق من تحديث معلومات الملف بنجاح.

```csharp
Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

لقد نجحت في تعيين معلومات الملف لمستند PDF باستخدام Aspose.PDF for .NET.

### مثال على التعليمات البرمجية المصدر لـ Set File Info باستخدام Aspose.PDF for .NET


```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح المستند
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");

// حدد معلومات المستند
DocumentInfo docInfo = new DocumentInfo(pdfDocument);

docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";

dataDir = dataDir + "SetFileInfo_out.pdf";
// حفظ وثيقة الإخراج
pdfDocument.Save(dataDir);

Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

## خاتمة

في الختام ، يوفر Aspose.PDF for .NET طريقة بسيطة وفعالة لتعيين معلومات الملف لمستندات PDF. باتباع الخطوات المذكورة أعلاه ، يمكنك بسهولة تعيين قيم معلومات الملف المطلوبة لمستندات PDF الخاصة بك باستخدام كود المصدر C #.