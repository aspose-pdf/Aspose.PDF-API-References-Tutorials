---
title: تحديث الإشارات المرجعية التابعة
linktitle: تحديث الإشارات المرجعية التابعة
second_title: Aspose.PDF لمرجع .NET API
description: قم بتحديث الإشارات المرجعية الفرعية بسهولة في ملفات PDF الخاصة بك باستخدام Aspose.PDF for .NET.
type: docs
weight: 110
url: /ar/net/programming-with-bookmarks/update-child-bookmarks/
---

يتيح لك تحديث الإشارات المرجعية الفرعية في مستند PDF تعديل خصائص إشارات مرجعية معينة داخل إشارة مرجعية أصل. باستخدام Aspose.PDF for .NET ، يمكنك بسهولة تحديث الإشارات المرجعية الفرعية باتباع التعليمات البرمجية المصدر التالية:

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
Document pdfDocument = new Document(dataDir + "UpdateChildBookmarks.pdf");
```

## الخطوة 4: الحصول على كائن إشارة مرجعية الأصل

في هذه الخطوة ، سنحصل على كائن الإشارة المرجعية الأصل المحدد الذي نريد تحديث الإشارات المرجعية الفرعية منه. في المثال أدناه ، نسترجع الإشارة المرجعية الأصلية في الفهرس 1 (الإشارة المرجعية الثانية في مجموعة الإشارات المرجعية). يمكنك ضبط الفهرس وفقًا لاحتياجاتك. هذا هو الكود المقابل:

```csharp
OutlineItemCollection pdfOutline = pdfDocument.Outlines[1];
```

## الخطوة 5: الحصول على كائن إشارة مرجعية الطفل

الآن دعنا نحصل على كائن الإشارة المرجعية الفرعي المحدد الذي نريد تحديثه. في المثال أدناه ، نسترجع الإشارة المرجعية الفرعية في الفهرس 1 (الإشارة المرجعية الفرعية الثانية في مجموعة الإشارات المرجعية الفرعية للإشارة المرجعية الأصلية). يمكنك ضبط الفهرس وفقًا لاحتياجاتك. هذا هو الكود المقابل:

```csharp
OutlineItemCollection childOutline = pdfOutline[1];
```

## الخطوة 6: تحديث خصائص الإشارات المرجعية الفرعية

الآن دعنا نقوم بتحديث خصائص الإشارات المرجعية الفرعية مثل العنوان والنمط المائل والنمط الغامق. يمكنك تعديل هذه الخصائص وفقًا لاحتياجاتك. هذا هو الكود المقابل:

```csharp
childOutline.Title = "Updated Outline";
childOutline. Italic = true;
childOutline. Bold = true;
```

## الخطوة 7: احفظ الملف المحدث

الآن دعنا نحفظ ملف PDF المحدث باستخدام امتداد`Save` طريقة`pdfDocument` هدف. هذا هو الكود المقابل:

```csharp
dataDir = dataDir + "UpdateChildBookmarks_out.pdf";
pdfDocument.Save(dataDir);
```

### نموذج التعليمات البرمجية المصدر لتحديث الإشارات المرجعية التابعة باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "UpdateChildBookmarks.pdf");
// احصل على كائن إشارة مرجعية
OutlineItemCollection pdfOutline = pdfDocument.Outlines[1];
// الحصول على كائن المرجعية الطفل
OutlineItemCollection childOutline = pdfOutline[1];
childOutline.Title = "Updated Outline";
childOutline.Italic = true;
childOutline.Bold = true;
dataDir = dataDir + "UpdateChildBookmarks_out.pdf";            
// حفظ الإخراج
pdfDocument.Save(dataDir);
Console.WriteLine("\nChild bookmarks updated successfully.\nFile saved at " + dataDir);
```

## خاتمة

تهنئة ! لديك الآن دليل تفصيلي خطوة بخطوة لتحديث الإشارات المرجعية الفرعية باستخدام Aspose.PDF for .NET. يمكنك استخدام هذا الرمز لتعديل خصائص الإشارات المرجعية الفرعية في مستندات PDF الخاصة بك.

تأكد من إطلاعك على وثائق Aspose.PDF الرسمية لمزيد من المعلومات حول ميزات معالجة الإشارات المرجعية المتقدمة.