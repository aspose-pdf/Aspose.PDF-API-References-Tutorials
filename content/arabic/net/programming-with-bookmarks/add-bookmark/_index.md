---
title: إضافة إشارة مرجعية في ملف PDF
linktitle: إضافة إشارة مرجعية في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: أضف إشارة مرجعية بسهولة في ملف PDF لتحسين التنقل باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-bookmarks/add-bookmark/
---
تتيح إضافة الإشارات المرجعية في ملف PDF التنقل السهل والسريع. باستخدام Aspose.PDF for .NET، يمكنك بسهولة إضافة إشارة مرجعية في ملف PDF باتباع التعليمات البرمجية المصدر التالية:

## الخطوة 1: استيراد المكتبات المطلوبة

قبل أن تبدأ، تحتاج إلى استيراد المكتبات اللازمة لمشروع C# الخاص بك. فيما يلي توجيه الاستيراد الضروري:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## الخطوة 2: تعيين المسار إلى مجلد المستندات

 في هذه الخطوة، تحتاج إلى تحديد المسار إلى المجلد الذي يحتوي على ملف PDF الذي تريد إضافة إشارة مرجعية إليه. يستبدل`"YOUR DOCUMENT DIRECTORY"`في الكود التالي مع المسار الفعلي لمجلد المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 3: افتح مستند PDF

سنفتح الآن مستند PDF الذي نريد إضافة إشارة مرجعية إليه باستخدام الكود التالي:

```csharp
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
```

## الخطوة 4: إنشاء كائن الإشارة المرجعية

 في هذه الخطوة، سنقوم بإنشاء كائن إشارة مرجعية باستخدام`OutlineItemCollection` فئة وقم بتعيين خصائصها مثل العنوان والسمة المائلة والسمة الغامقة والإجراء الذي سيتم تنفيذه عند النقر عليه. هنا هو الكود المقابل:

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
```

## الخطوة 5: إضافة إشارة مرجعية إلى المستند

 وأخيرًا، نضيف الإشارة المرجعية التي تم إنشاؤها إلى مجموعة الإشارات المرجعية للمستند باستخدام`Add` طريقة`Outlines` ملكية. هنا هو الكود المقابل:

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
// أضف إشارة مرجعية في مجموعة المخطط التفصيلي للمستند.
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddBookmark_out.pdf";
// حفظ الإخراج
pdfDocument.Save(dataDir);
Console.WriteLine("\nBookmark added successfully.\nFile saved at " + dataDir);
```

## خاتمة

تهنئة ! الآن لديك دليل خطوة بخطوة لإضافة إشارة مرجعية باستخدام Aspose.PDF لـ .NET. يمكنك استخدام هذا الرمز لتحسين التنقل في مستندات PDF الخاصة بك عن طريق إضافة إشارات مرجعية مخصصة.

تأكد من مراجعة وثائق Aspose.PDF الرسمية لمزيد من المعلومات حول ميزات معالجة الإشارات المرجعية المتقدمة.


### الأسئلة الشائعة لإضافة إشارة مرجعية في ملف PDF

#### س: ما هي الإشارات المرجعية في ملف PDF؟

ج: الإشارات المرجعية، والمعروفة أيضًا باسم الخطوط العريضة، هي عناصر تفاعلية توفر التنقل والبنية داخل مستند PDF. أنها تسمح للمستخدمين بالانتقال بسرعة إلى أقسام أو صفحات محددة.

#### س: لماذا أحتاج إلى إضافة إشارات مرجعية إلى ملف PDF؟

ج: تعمل إضافة الإشارات المرجعية إلى ملف PDF على تحسين تجربة المستخدم وتسهل على القراء التنقل عبر محتوى المستند. يمكن أن تكون الإشارات المرجعية بمثابة جدول محتويات أو توفر وصولاً سريعًا إلى الأقسام المهمة.

#### س: كيف يمكنني استيراد المكتبات المطلوبة لمشروع C# الخاص بي؟

ج: لاستيراد المكتبات اللازمة لمشروع C# الخاص بك، قم بتضمين توجيهات الاستيراد التالية:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

تمكنك هذه التوجيهات من الوصول إلى الفئات والأساليب اللازمة للعمل مع مستندات PDF والإشارات المرجعية.

#### س: كيف أحدد المسار إلى مجلد المستندات؟

 ج: استبدال`"YOUR DOCUMENT DIRECTORY"` في الكود المصدري المقدم مع المسار الفعلي إلى المجلد الذي يحتوي على ملف PDF الذي تريد إضافة إشارة مرجعية إليه.

#### س: كيف يمكنني فتح مستند PDF لإضافة الإشارات المرجعية؟

ج: لفتح مستند PDF لإضافة إشارات مرجعية، استخدم الكود التالي:

```csharp
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
```

 يستبدل`"AddBookmark.pdf"` مع اسم الملف الفعلي.

#### س: كيف أقوم بإنشاء كائن إشارة مرجعية؟

 ج: لإنشاء كائن إشارة مرجعية، استخدم`OutlineItemCollection` فصل. قم بتخصيص خصائصه مثل العنوان والنمط المائل والنمط الغامق والإجراء الذي سيتم تنفيذه عند النقر عليه.

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
```

####  س: ما هو الغرض من`Action` property in a bookmark?

 ج: ال`Action` تحدد الخاصية الإجراء الذي سيتم تنفيذه عند النقر فوق الإشارة المرجعية. في هذا المثال نستخدم`GoToAction`للانتقال إلى صفحة معينة (الصفحة 2 في هذه الحالة).

#### س: كيف يمكنني إضافة الإشارة المرجعية إلى المستند؟

 ج: استخدم`Add` طريقة`Outlines` الخاصية لإضافة الإشارة المرجعية التي تم إنشاؤها إلى مجموعة الإشارات المرجعية للمستند.

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

#### س: هل يمكنني إضافة إشارات مرجعية متعددة باستخدام هذه الطريقة؟

ج: نعم، يمكنك تكرار الخطوات من 4 إلى 8 لإضافة إشارات مرجعية متعددة إلى المستند. قم بتخصيص خصائص وإجراءات كل إشارة مرجعية حسب الحاجة.

#### س: كيف يمكنني حفظ ملف PDF المحدث؟

 ج: احفظ ملف PDF المحدث باستخدام الملف`Save` طريقة`pdfDocument` هدف:

```csharp
dataDir = dataDir + "AddBookmark_out.pdf";
pdfDocument.Save(dataDir);
```

#### س: كيف يمكنني التأكد من إضافة الإشارات المرجعية؟

ج: افتح ملف PDF الذي تم إنشاؤه للتحقق من إضافة الإشارات المرجعية المحددة إلى المستند.

#### س: هل هناك حد لعدد الإشارات المرجعية التي يمكنني إضافتها؟

ج: لا يوجد عمومًا حد صارم لعدد الإشارات المرجعية التي يمكنك إضافتها، ولكن خذ في الاعتبار حجم المستند وتعقيده للحصول على الأداء الأمثل.

#### س: هل يمكنني تخصيص مظهر الإشارات المرجعية؟

ج: نعم، يمكنك تخصيص مظهر الإشارة المرجعية واللون والنمط والسمات الأخرى باستخدام ميزات Aspose.PDF.