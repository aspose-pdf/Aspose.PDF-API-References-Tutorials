---
title: تحديث الإشارات
linktitle: تحديث الإشارات
second_title: Aspose.PDF لمرجع .NET API
description: قم بتحديث الإشارات المرجعية في ملفات PDF بسهولة باستخدام Aspose.PDF for .NET.
type: docs
weight: 100
url: /ar/net/programming-with-bookmarks/update-bookmarks/
---

غالبًا ما يكون تحديث الإشارات المرجعية في مستند PDF ضروريًا لعكس التغييرات أو التحديثات في بنية المستند أو محتواه. باستخدام Aspose.PDF for .NET ، يمكنك بسهولة تحديث الإشارات المرجعية باتباع التعليمات البرمجية المصدر التالية:

## الخطوة 1: استيراد المكتبات المطلوبة

قبل أن تبدأ ، تحتاج إلى استيراد المكتبات اللازمة لمشروع C # الخاص بك. فيما يلي توجيه الاستيراد الضروري:

```csharp
using Aspose.Pdf;
```

## الخطوة 2: حدد المسار إلى مجلد المستندات

 في هذه الخطوة ، تحتاج إلى تحديد المسار إلى المجلد الذي يحتوي على ملف PDF الذي تريد تحديثه. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود التالي بالمسار الفعلي لمجلد المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 3: افتح مستند PDF

سنفتح الآن مستند PDF الذي نريد تحديثه باستخدام الكود التالي:

```csharp
Document pdfDocument = new Document(dataDir + "UpdateBookmarks.pdf");
```

## الخطوة 4: احصل على كائن إشارة مرجعية

في هذه الخطوة ، سنحصل على كائن الإشارة المرجعية المحدد الذي نريد تحديثه. في المثال أدناه ، نسترجع الإشارة المرجعية في الفهرس 1 (الإشارة المرجعية الثانية في مجموعة الإشارات المرجعية). يمكنك ضبط الفهرس وفقًا لاحتياجاتك. هذا هو الكود المقابل:

```csharp
OutlineItemCollection pdfOutline = pdfDocument.Outlines[1];
```

## الخطوة 5: تحديث خصائص الإشارة المرجعية

لنقم الآن بتحديث خصائص الإشارة المرجعية مثل العنوان والنمط المائل والنمط الغامق. يمكنك تعديل هذه الخصائص وفقًا لاحتياجاتك. هذا هو الكود المقابل:

```csharp
pdfOutline.Title = "Updated Outline";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
```

## الخطوة 6: احفظ الملف المحدث

الآن دعنا نحفظ ملف PDF المحدث باستخدام امتداد`Save` طريقة`pdfDocument` هدف. هذا هو الكود المقابل:

```csharp
dataDir = dataDir + "UpdateBookmarks_out.pdf";
pdfDocument.Save(dataDir);
```

### نموذج التعليمات البرمجية المصدر لتحديث الإشارات المرجعية باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "UpdateBookmarks.pdf");
// احصل على كائن إشارة مرجعية
OutlineItemCollection pdfOutline = pdfDocument.Outlines[1];
pdfOutline.Title = "Updated Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
dataDir = dataDir + "UpdateBookmarks_out.pdf";
// حفظ الإخراج
pdfDocument.Save(dataDir);
Console.WriteLine("\nBookmarks updated successfully.\nFile saved at " + dataDir);
```

## خاتمة

تهنئة ! الآن لديك دليل تفصيلي خطوة بخطوة لتحديث الإشارات المرجعية باستخدام Aspose.PDF for .NET. يمكنك استخدام هذا الرمز لتغيير عناوين وأنماط الإشارات المرجعية في مستندات PDF الخاصة بك.

تأكد من إطلاعك على وثائق Aspose.PDF الرسمية لمزيد من المعلومات حول ميزات معالجة الإشارات المرجعية المتقدمة.