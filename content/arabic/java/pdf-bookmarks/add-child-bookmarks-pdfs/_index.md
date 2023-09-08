---
title: إضافة إشارات مرجعية فرعية إلى ملفات PDF
linktitle: إضافة إشارات مرجعية فرعية إلى ملفات PDF
second_title: Aspose.PDF جافا واجهة برمجة تطبيقات معالجة PDF
description: تعرف على كيفية تحسين مستندات PDF باستخدام الإشارات المرجعية الفرعية باستخدام Aspose.PDF لـ Java. دليل خطوة بخطوة مع أمثلة التعليمات البرمجية لتحسين التنقل والتنظيم.
type: docs
weight: 11
url: /ar/java/pdf-bookmarks/add-child-bookmarks-pdfs/
---

## مقدمة لإضافة إشارات مرجعية فرعية إلى ملفات PDF

في هذه المقالة، سنستكشف كيفية إضافة إشارات مرجعية فرعية إلى مستندات PDF باستخدام Aspose.PDF لـ Java. تعد الإشارات المرجعية الفرعية طريقة ملائمة لتنظيم محتوى مستند PDF والتنقل عبره، مما يسهل على المستخدمين العثور على أقسام أو موضوعات محددة داخل المستند.

## المتطلبات الأساسية

قبل أن نتعمق في التنفيذ، تأكد من توفر المتطلبات الأساسية التالية:

- بيئة تطوير Java مثبتة على نظامك.
-  Aspose.PDF لمكتبة جافا. يمكنك تنزيله من[هنا](https://releases.aspose.com/pdf/java/).

## تهيئة البيئة

1. قم بتنزيل مكتبة Aspose.PDF لـ Java من الرابط المتوفر.
2. أضف المكتبة إلى مشروع Java الخاص بك.

الآن، لنبدأ بإنشاء مستند PDF جديد وإضافة الإشارات المرجعية الفرعية إليه خطوة بخطوة.

## إنشاء مستند PDF جديد

للبدء، نحتاج إلى تهيئة مستند PDF وإضافة صفحات إليه. إليك مقتطف الشفرة للبدء:

```java
// تهيئة مستند PDF
Document pdfDocument = new Document();

// إضافة صفحات إلى ملف PDF
pdfDocument.getPages().add();
pdfDocument.getPages().add();
```

في هذا المثال، قمنا بإنشاء مستند PDF جديد وأضفنا صفحتين إليه.

## إضافة الإشارات المرجعية للوالدين

تعمل الإشارات المرجعية الأصلية بمثابة الأقسام أو الفئات الرئيسية في مستند PDF الخاص بك. لنقم بإنشاء بعض الإشارات المرجعية الأصلية:

```java
// إنشاء الإشارات المرجعية الأصل
OutlineItemCollection outline = pdfDocument.getOutlines();
OutlineItemCollection parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 1");
outline.add(parentBookmark);

parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 2");
outline.add(parentBookmark);
```

لقد أضفنا إشارتين مرجعيتين أصليتين، "الإشارة المرجعية الأصلية 1" و"الإشارة المرجعية الأصلية 2".

## إضافة إشارات مرجعية للأطفال

حان الوقت الآن لإضافة إشارات مرجعية فرعية إلى الإشارات المرجعية الأصلية التي أنشأناها سابقًا. تمثل الإشارات المرجعية الفرعية موضوعات أو أقسامًا فرعية محددة داخل كل إشارة مرجعية رئيسية. وإليك كيف يمكنك القيام بذلك:

```java
// أضف الإشارات المرجعية الفرعية إلى الإشارة المرجعية الأصلية 1
OutlineItemCollection childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.1");
parentBookmark.add(childBookmark);

childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.2");
parentBookmark.add(childBookmark);

//أضف الإشارات المرجعية الفرعية إلى الإشارة المرجعية الأصلية 2
childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 2.1");
parentBookmark.add(childBookmark);
```

لقد أضفنا إشارات مرجعية فرعية إلى كل من "الإشارة المرجعية الأصلية 1" و"الإشارة المرجعية الأصلية 2".

## تخصيص مظهر الإشارة المرجعية

يمكنك تخصيص مظهر الإشارات المرجعية عن طريق تغيير نصها ونمطها. بالإضافة إلى ذلك، يمكنك إضافة أيقونات إلى الإشارات المرجعية للحصول على تمثيل مرئي أفضل. فيما يلي مثال لكيفية القيام بذلك:

```java
// تخصيص مظهر الإشارة المرجعية
parentBookmark.setItalic(true);
childBookmark.setForegroundColor(Color.getGreen());
childBookmark.setIcon(OutlineItemCollection.getItalicIcon());
```

في هذا المثال، جعلنا الإشارة المرجعية الأصلية مائلة، وغيرنا لون نص الإشارة المرجعية الفرعية إلى اللون الأخضر، وأضفنا رمزًا مائلًا إلى الإشارة المرجعية الفرعية.

## التعامل مع الأحداث

يمكن أن تحتوي الإشارات المرجعية أيضًا على إجراءات مرتبطة بها. على سبيل المثال، يمكنك إضافة إجراءات يتم تشغيلها عندما ينقر المستخدم على إشارة مرجعية. إليك كيفية التعامل مع أحداث النقر على الإشارات المرجعية:

```java
// إضافة إجراء إلى إشارة مرجعية
GoToAction action = new GoToAction(pdfDocument.getPages().get_Item(1));
childBookmark.setAction(action);
```

في هذا الكود، أضفنا إجراء "GoTo" إلى إشارة مرجعية فرعية ستنقل المستخدم إلى الصفحة الثانية من ملف PDF عند النقر عليه.

## حفظ ملف PDF

بمجرد إضافة جميع الإشارات المرجعية الضرورية وتخصيص مظهرها وإجراءاتها، يمكنك حفظ مستند PDF المعدل:

```java
// احفظ مستند PDF
pdfDocument.save("output.pdf");
```

مستند PDF الخاص بك مع الإشارات المرجعية الفرعية جاهز الآن.

## كود المصدر الكامل

إليك الكود المصدري الكامل لإضافة إشارات مرجعية فرعية إلى مستند PDF باستخدام Aspose.PDF لـ Java:

```java
// تهيئة مستند PDF
Document pdfDocument = new Document();

// إضافة صفحات إلى ملف PDF
pdfDocument.getPages().add();
pdfDocument.getPages().add();

// إنشاء الإشارات المرجعية الأصل
OutlineItemCollection outline = pdfDocument.getOutlines();
OutlineItemCollection parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 1");
outline.add(parentBookmark);

parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 2");
outline.add(parentBookmark);

// أضف الإشارات المرجعية الفرعية إلى الإشارة المرجعية الأصلية 1
OutlineItemCollection childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.1");
parentBookmark.add(childBookmark);

childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.2");
parentBookmark.add(childBookmark);

//أضف الإشارات المرجعية الفرعية إلى الإشارة المرجعية الأصلية 2
childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 2.1");
parentBookmark.add(childBookmark);

// تخصيص مظهر الإشارة المرجعية
parentBookmark.setItalic(true);
childBookmark.setForegroundColor(Color.getGreen());
childBookmark.setIcon(OutlineItemCollection.getItalicIcon());

// إضافة إجراء إلى إشارة مرجعية
GoToAction action = new GoToAction(pdfDocument.getPages().get_Item(1));
childBookmark.setAction(action);

// احفظ مستند PDF
pdfDocument.save("output.pdf");
```

## خاتمة

تعد إضافة إشارات مرجعية فرعية إلى ملفات PDF باستخدام Aspose.PDF لـ Java ميزة قوية تعمل على تحسين التنقل وتنظيم مستنداتك. باتباع الخطوات الموضحة في هذه المقالة، يمكنك إنشاء ملفات PDF جيدة التنظيم باستخدام الإشارات المرجعية الأصلية والفرعية، وتخصيص مظهرها، وحتى إضافة إجراءات لتحسين تجربة المستخدم.

## الأسئلة الشائعة

### كيف يمكنني تنزيل Aspose.PDF لجافا؟

 يمكنك تنزيل Aspose.PDF لـ Java من موقع الويب[هنا](https://releases.aspose.com/pdf/java/).

### هل الإشارات المرجعية الفرعية مدعومة في جميع برامج عرض PDF؟

نعم، يتم دعم الإشارات المرجعية الفرعية في معظم برامج عرض PDF الحديثة وتوفر تجربة مستخدم محسنة للتنقل عبر مستندات PDF.

### هل يمكنني تخصيص مظهر الإشارات المرجعية بشكل أكبر؟

نعم، يمكنك تخصيص مظهر الإشارات المرجعية عن طريق ضبط أنماط النص والألوان والأيقونات لتناسب تصميم المستند الخاص بك.

### ما هي الإجراءات الأخرى التي يمكنني إضافتها إلى الإشارات المرجعية؟

إلى جانب إجراءات "GoTo"، يمكنك إضافة إجراءات مثل إجراءات "URI" لفتح روابط الويب أو إجراءات "JavaScript" لتنفيذ برامج نصية مخصصة عند النقر فوق إشارة مرجعية.

### هل Aspose.PDF for Java مناسب للمشاريع التجارية؟

نعم، Aspose.PDF for Java مناسب لكل من المشاريع الشخصية والتجارية، ويقدم مجموعة واسعة من الميزات لمعالجة وإنشاء PDF.