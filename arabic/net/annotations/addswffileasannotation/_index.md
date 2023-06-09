---
title: إضافة ملف Swf كتعليق توضيحي
linktitle: إضافة ملف Swf كتعليق توضيحي
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة ملفات SWF كتعليقات توضيحية في Aspose.PDF for .NET باستخدام هذا الدليل المفصل خطوة بخطوة.
type: docs
weight: 30
url: /ar/net/annotations/addswffileasannotation/
---
إذا كنت مطور .NET تتطلع إلى إضافة ملف SWF للوسائط المتعددة كتعليق توضيحي إلى مستند PDF الخاص بك باستخدام Aspose.PDF for .NET ، فإن هذا الدليل التفصيلي مناسب لك. في هذه المقالة ، سنشرح كيفية إضافة ملفات SWF كتعليقات توضيحية في مستندات PDF الخاصة بك باستخدام لغة البرمجة C #. 

اتبع الخطوات التالية لإضافة ملف SWF كتعليق توضيحي في مستند PDF الخاص بك باستخدام Aspose.PDF for .NET:

## الخطوة 1: حدد مسار الدليل

أولاً ، نحتاج إلى تعيين مسار الدليل حيث يتم تخزين ملف PDF وملف SWF. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

استبدل "دليل المستند" بالمسار إلى دليل المستند.

## الخطوة 2: قم بتحميل مستند PDF

بعد ذلك ، نحتاج إلى تحميل مستند PDF باستخدام الكود التالي:

```csharp
Document doc = new Document(dataDir + "AddSwfFileAsAnnotation.pdf");
```

سيقوم هذا الرمز بتحميل ملف "AddSwfFileAsAnnotation.pdf" من دليل المستندات.

## الخطوة 3: احصل على الصفحة لإضافة تعليق توضيحي

الآن ، نحتاج إلى الحصول على مرجع الصفحة التي نريد إضافة التعليق التوضيحي إليها. في هذا البرنامج التعليمي ، سنضيف التعليق التوضيحي إلى الصفحة الأولى من المستند.

```csharp
Page page = doc.Pages[1];
```

## الخطوة 4: إنشاء كائن ScreenAnnotation

 يمكننا الآن إنشاء ملف`ScreenAnnotation` كائن مع ملف SWF كوسيطة.

```csharp
ScreenAnnotation annotation = new ScreenAnnotation(page, new Aspose.Pdf.Rectangle(0, 400, 600, 700), dataDir + "input.swf");
```

 ال`ScreenAnnotation` يأخذ المُنشئ ثلاث حجج:

- `page`: الصفحة التي سيتم إضافة التعليق التوضيحي إليها.
- `rectangle`: المستطيل الذي سيتم عرض ملف SWF فيه على الصفحة.
- `dataDir + "input.swf"`: المسار إلى ملف SWF.

## الخطوة 5: أضف التعليق التوضيحي إلى الصفحة

الآن ، يمكننا إضافة التعليق التوضيحي إلى مجموعة التعليقات التوضيحية للصفحة.

```csharp
page.Annotations.Add(annotation);
```

## الخطوة 6: احفظ مستند PDF المحدث

أخيرًا ، نحتاج إلى حفظ مستند PDF المحدث مع التعليق التوضيحي باستخدام الكود التالي:

```csharp
dataDir = dataDir + "AddSwfFileAsAnnotation_out.pdf";
doc.Save(dataDir);
```

سيحفظ هذا الرمز مستند PDF المحدث مع التعليق التوضيحي كـ "AddSwfFileAsAnnotation_out.pdf" في دليل المستند.

### مثال على كود المصدر لإضافة ملف SWF كتعليق توضيحي باستخدام Aspose.PDF for .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح مستند PDF
Document doc = new Document(dataDir + "AddSwfFileAsAnnotation.pdf");

// احصل على مرجع للصفحة التي تريد إضافة التعليق التوضيحي إليها
Page page = doc.Pages[1];

// قم بإنشاء كائن ScreenAnnotation باستخدام ملف الوسائط المتعددة .swf كوسيطة
ScreenAnnotation annotation = new ScreenAnnotation(page, new Aspose.Pdf.Rectangle(0, 400, 600, 700), dataDir + "input.swf");

// أضف التعليق التوضيحي إلى مجموعة التعليقات التوضيحية للصفحة
page.Annotations.Add(annotation);

dataDir = dataDir + "AddSwfFileAsAnnotation_out.pdf";
// احفظ مستند PDF المحدث مع التعليق التوضيحي
doc.Save(dataDir);
```        
