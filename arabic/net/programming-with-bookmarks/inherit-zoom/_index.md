---
title: توارث التكبير
linktitle: توارث التكبير
second_title: Aspose.PDF لمرجع .NET API
description: ورث بسهولة الإشارة المرجعية في ملفات PDF الخاصة بك باستخدام Aspose.PDF for .NET.
type: docs
weight: 90
url: /ar/net/programming-with-bookmarks/inherit-zoom/
---

يتيح لك توريث التكبير في مستند PDF تحديد مستوى تكبير افتراضي للإشارات المرجعية. باستخدام Aspose.PDF for .NET ، يمكنك بسهولة وراثة التكبير باتباع التعليمات البرمجية المصدر التالية:

## الخطوة 1: استيراد المكتبات المطلوبة

قبل أن تبدأ ، تحتاج إلى استيراد المكتبات اللازمة لمشروع C # الخاص بك. فيما يلي توجيه الاستيراد الضروري:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## الخطوة 2: حدد المسار إلى مجلد المستندات

في هذه الخطوة ، تحتاج إلى تحديد المسار إلى المجلد الذي يحتوي على ملف PDF الذي تريد أن ترث التكبير منه. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود التالي بالمسار الفعلي لمجلد المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 3: افتح مستند PDF

سنقوم الآن بفتح مستند PDF الذي نريد أن نرث التكبير باستخدام الكود التالي:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## الخطوة 4: احصل على مجموعة الإشارات المرجعية

 في هذه الخطوة ، سنحصل على مجموعة من الإشارات المرجعية أو معالم المستند باستخدام امتداد`Outlines` ممتلكات`doc` هدف. هذا هو الكود المقابل:

```csharp
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
```

## الخطوة 5: تعيين مستوى التكبير

 الآن سنقوم بتعيين مستوى التكبير / التصغير عن طريق إنشاء ملف`XYZExplicitDestination` كائن بإحداثيات x و y و z المحددة. هنا نستخدم الإحداثيات (100 ، 100 ، 0) بتكبير 2. وهنا الكود المقابل:

```csharp
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
```

## الخطوة 6: إضافة مستوى التكبير إلى الإشارات المرجعية

 في هذه الخطوة ، نضيف`XYZExplicitDestination` كإجراء على الإشارات المرجعية لـ`item` مجموعة. هذا هو الكود المقابل:

```csharp
item. Action = new GoToAction(dest);
```

## الخطوة 7: أضف الإشارات المرجعية المحدثة إلى المستند

 أخيرًا ، نضيف الإشارات المرجعية المحدثة إلى مجموعة الإشارات المرجعية للمستند باستخدام امتداد`Add` طريقة`doc.Outlines` هدف. هذا هو الكود المقابل:

```csharp
doc. Outlines. Add(item);
```

## الخطوة 8: احفظ الملف المحدث

الآن دعنا نحفظ ملف PDF المحدث باستخدام امتداد`Save` طريقة`doc` هدف. هذا هو الكود المقابل:

```csharp
dataDir = dataDir + "InheritZoom_out.pdf";
doc.Save(dataDir);
```

### عينة من التعليمات البرمجية المصدر لـ Inherit Zoom باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document doc = new Document(dataDir + "input.pdf");
// احصل على مخططات / مجموعة إشارات مرجعية لملف PDF
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
// اضبط مستوى التكبير على 0
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
// أضف XYZExplicitDestination كإجراء لتحديد مجموعة من ملفات PDF
item.Action = new GoToAction(dest);
// أضف عنصرًا إلى مجموعة الخطوط العريضة لملف PDF
doc.Outlines.Add(item);
dataDir = dataDir + "InheritZoom_out.pdf";
// حفظ الإخراج
doc.Save(dataDir);
Console.WriteLine("\nBookmarks updated successfully.\nFile saved at " + dataDir);
```

## خاتمة

تهنئة ! الآن لديك دليل خطوة بخطوة لـ Inherit Zoom باستخدام Aspose.PDF for .NET. يمكنك استخدام هذا الرمز لتحديد مستوى التكبير الافتراضي للإشارات المرجعية في مستندات PDF الخاصة بك.

تأكد من إطلاعك على وثائق Aspose.PDF الرسمية لمزيد من المعلومات حول ميزات معالجة الإشارات المرجعية المتقدمة.