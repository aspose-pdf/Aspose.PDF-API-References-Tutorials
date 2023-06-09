---
title: قم بتوسيع الإشارات المرجعية
linktitle: قم بتوسيع الإشارات المرجعية
second_title: Aspose.PDF لمرجع .NET API
description: قم بسهولة بتوسيع الإشارات المرجعية لملفات PDF الخاصة بك لتحسين التنقل باستخدام Aspose.PDF for .NET.
type: docs
weight: 50
url: /ar/net/programming-with-bookmarks/expand-bookmarks/
---

سيؤدي توسيع الإشارات المرجعية في مستند PDF إلى عرض جميع الإشارات المرجعية المفتوحة افتراضيًا. باستخدام Aspose.PDF for .NET ، يمكنك بسهولة توسيع الإشارات المرجعية باتباع التعليمات البرمجية المصدر التالية:

## الخطوة 1: استيراد المكتبات المطلوبة

قبل أن تبدأ ، تحتاج إلى استيراد المكتبات اللازمة لمشروع C # الخاص بك. فيما يلي توجيه الاستيراد الضروري:

```csharp
using Aspose.Pdf;
```

## الخطوة 2: حدد المسار إلى مجلد المستندات

 في هذه الخطوة ، تحتاج إلى تحديد المسار إلى المجلد الذي يحتوي على ملف PDF الذي تريد توسيع إشاراته المرجعية. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود التالي بالمسار الفعلي لمجلد المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 3: افتح مستند PDF

سنفتح الآن مستند PDF الذي نريد توسيع إشاراته المرجعية باستخدام الكود التالي:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## الخطوة 4: ضبط وضع عرض الصفحة

 في هذه الخطوة ، سنقوم بتعيين وضع عرض الصفحة لإظهار الإشارات المرجعية افتراضيًا. نحن نستخدم ال`PageMode` ممتلكات`doc`لتعيين وضع الصفحة المطلوب. هذا هو الكود المقابل:

```csharp
doc.PageMode = PageMode.UseOutlines;
```

## الخطوة 5: تصفح الإشارات المرجعية وقم بتوسيعها

 سنقوم الآن بتكرار كل عنصر إشارة مرجعية في مجموعة الإشارات المرجعية للمستند ونضبط الحالة المفتوحة لكل عنصر على`true` لتوسيعها بشكل افتراضي. هذا هو الكود المقابل:

```csharp
foreach(OutlineItemCollection item in doc.Outlines)
{
     item. Open = true;
}
```

## الخطوة 6: احفظ الملف المحدث

 أخيرًا ، نحفظ ملف PDF المحدث باستخدام امتداد`Save` طريقة`doc` هدف. هذا هو الكود المقابل:

```csharp
dataDir = dataDir + "ExpandBookmarks_out.pdf";
doc.Save(dataDir);
```

### نموذج التعليمات البرمجية المصدر لتوسيع الإشارات المرجعية باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document doc = new Document(dataDir + "input.pdf");
// اضبط وضع عرض الصفحة ، أي إظهار الصور المصغرة ، ملء الشاشة ، إظهار لوحة المرفقات
doc.PageMode = PageMode.UseOutlines;
// قم بالمرور عبر كل عنصر من عناصر Ouline في مجموعة الخطوط العريضة لملف PDF
foreach (OutlineItemCollection item in doc.Outlines)
{
	// تعيين حالة الفتح لعنصر المخطط التفصيلي
	item.Open = true;
}
dataDir = dataDir + "ExpandBookmarks_out.pdf";
// حفظ الإخراج
doc.Save(dataDir);
Console.WriteLine("\nBookmarks expanded successfully.\nFile saved at " + dataDir);
```

## خاتمة

تهنئة ! لديك الآن دليل تفصيلي خطوة بخطوة لتطوير الإشارات المرجعية باستخدام Aspose.PDF for .NET. يمكنك استخدام هذا الرمز لإظهار جميع الإشارات المرجعية الافتراضية في مستندات PDF الخاصة بك.

تأكد من إطلاعك على وثائق Aspose.PDF الرسمية لمزيد من المعلومات حول ميزات معالجة الإشارات المرجعية المتقدمة.