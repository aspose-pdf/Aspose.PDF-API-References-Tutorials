---
title: أضف إشارة مرجعية في ملف PDF
linktitle: أضف إشارة مرجعية في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: أضف بسهولة إشارة مرجعية في ملف PDF لتحسين التنقل باستخدام Aspose.PDF for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-bookmarks/add-bookmark/
---
تتيح إضافة إشارات مرجعية في ملف PDF التنقل السهل والسريع. باستخدام Aspose.PDF for .NET ، يمكنك بسهولة إضافة إشارة مرجعية في ملف PDF باتباع التعليمات البرمجية المصدر التالية:

## الخطوة 1: استيراد المكتبات المطلوبة

قبل أن تبدأ ، تحتاج إلى استيراد المكتبات اللازمة لمشروع C # الخاص بك. فيما يلي توجيه الاستيراد الضروري:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## الخطوة 2: حدد المسار إلى مجلد المستندات

 في هذه الخطوة ، تحتاج إلى تحديد المسار إلى المجلد الذي يحتوي على ملف PDF الذي تريد إضافة إشارة مرجعية إليه. يستبدل`"YOUR DOCUMENT DIRECTORY"`في الكود التالي بالمسار الفعلي لمجلد المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 3: افتح مستند PDF

سنفتح الآن مستند PDF الذي نريد إضافة إشارة مرجعية إليه باستخدام الكود التالي:

```csharp
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
```

## الخطوة 4: إنشاء كائن إشارة مرجعية

 في هذه الخطوة ، سننشئ كائن إشارة مرجعية باستخدام`OutlineItemCollection` class وتعيين خصائصها مثل العنوان والسمة المائلة والسمة الغامقة والإجراء المطلوب تنفيذه عند النقر فوقه. هذا هو الكود المقابل:

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
```

## الخطوة 5: أضف إشارة مرجعية إلى المستند

 أخيرًا ، نضيف الإشارة المرجعية التي تم إنشاؤها إلى مجموعة الإشارات المرجعية للمستند باستخدام امتداد`Add` طريقة`Outlines` ملكية. هذا هو الكود المقابل:

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### نموذج التعليمات البرمجية المصدر لإضافة إشارة مرجعية باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
// قم بإنشاء كائن إشارة مرجعية
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
// قم بتعيين رقم الصفحة الوجهة
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
// أضف إشارة مرجعية في مجموعة مخطط المستند.
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddBookmark_out.pdf";
// حفظ الإخراج
pdfDocument.Save(dataDir);
Console.WriteLine("\nBookmark added successfully.\nFile saved at " + dataDir);
```

## خاتمة

تهنئة ! الآن لديك دليل خطوة بخطوة لإضافة إشارة مرجعية باستخدام Aspose.PDF for .NET. يمكنك استخدام هذا الرمز لتحسين التنقل في مستندات PDF الخاصة بك عن طريق إضافة إشارات مرجعية مخصصة.

تأكد من إطلاعك على وثائق Aspose.PDF الرسمية لمزيد من المعلومات حول ميزات معالجة الإشارات المرجعية المتقدمة.


### الأسئلة الشائعة حول إضافة إشارة مرجعية في ملف PDF

#### س: ما هي الإشارات المرجعية في ملف PDF؟

ج: الإشارات المرجعية ، المعروفة أيضًا باسم الخطوط العريضة ، هي عناصر تفاعلية توفر التنقل والبنية داخل مستند PDF. إنها تسمح للمستخدمين بالانتقال بسرعة إلى أقسام أو صفحات محددة.

#### س: لماذا أحتاج إلى إضافة إشارات مرجعية إلى ملف PDF؟

ج: تؤدي إضافة إشارات مرجعية إلى ملف PDF إلى تحسين تجربة المستخدم وتسهيل تنقل القراء عبر محتوى المستند. يمكن أن تعمل الإشارات المرجعية كجدول محتويات أو توفر وصولاً سريعًا إلى الأقسام المهمة.

#### س: كيف يمكنني استيراد المكتبات المطلوبة لمشروع C # الخاص بي؟

ج: لاستيراد المكتبات الضرورية لمشروع C # ، قم بتضمين توجيهات الاستيراد التالية:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

تتيح لك هذه التوجيهات الوصول إلى الفئات والطرق اللازمة للعمل مع مستندات PDF والإشارات المرجعية.

#### س: كيف يمكنني تحديد المسار إلى مجلد المستندات؟

 ج: استبدال`"YOUR DOCUMENT DIRECTORY"` في كود المصدر المقدم مع المسار الفعلي للمجلد الذي يحتوي على ملف PDF الذي تريد إضافة إشارة مرجعية إليه.

#### س: كيف أقوم بفتح مستند PDF لإضافة إشارات مرجعية؟

ج: لفتح مستند PDF لإضافة إشارات مرجعية ، استخدم الكود التالي:

```csharp
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
```

 يستبدل`"AddBookmark.pdf"` مع اسم الملف الفعلي.

#### س: كيف أقوم بإنشاء كائن إشارة مرجعية؟

 ج: لإنشاء كائن إشارة مرجعية ، استخدم`OutlineItemCollection` فصل. قم بتخصيص خصائصه مثل العنوان ، والنمط المائل ، والنمط الغامق ، والإجراء الذي يتم تنفيذه عند النقر فوقه.

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
```

####  س: ما هو الغرض من`Action` property in a bookmark?

 ج: إن`Action` تحدد الخاصية الإجراء الذي سيتم تنفيذه عند النقر فوق الإشارة المرجعية. في هذا المثال ، نستخدم الامتداد`GoToAction`فئة للتنقل إلى صفحة معينة (الصفحة 2 في هذه الحالة).

#### س: كيف أقوم بإضافة الإشارة المرجعية إلى المستند؟

 ج: استخدم ملف`Add` طريقة`Outlines` لإضافة الإشارة المرجعية التي تم إنشاؤها إلى مجموعة الإشارات المرجعية للمستند.

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

#### س: هل يمكنني إضافة عدة إشارات مرجعية باستخدام هذه الطريقة؟

ج: نعم ، يمكنك تكرار الخطوات من 4 إلى 8 لإضافة إشارات مرجعية متعددة إلى المستند. قم بتخصيص خصائص وإجراءات كل إشارة مرجعية حسب الحاجة.

#### س: كيف أحفظ ملف PDF المحدث؟

 ج: احفظ ملف PDF المحدث باستخدام امتداد`Save` طريقة`pdfDocument` هدف:

```csharp
dataDir = dataDir + "AddBookmark_out.pdf";
pdfDocument.Save(dataDir);
```

#### س: كيف يمكنني التأكد من إضافة الإشارات المرجعية؟

ج: افتح ملف PDF الذي تم إنشاؤه للتحقق من إضافة الإشارات المرجعية المحددة إلى المستند.

#### س: هل هناك حد لعدد الإشارات المرجعية التي يمكنني إضافتها؟

ج: لا يوجد بشكل عام حد صارم لعدد الإشارات المرجعية التي يمكنك إضافتها ، ولكن ضع في اعتبارك حجم المستند ومدى تعقيده لتحقيق الأداء الأمثل.

#### س: هل يمكنني تخصيص مظهر الإشارات المرجعية؟

ج: نعم ، يمكنك تخصيص مظهر الإشارة المرجعية ولونها ونمطها وسمات أخرى باستخدام ميزات Aspose.PDF.