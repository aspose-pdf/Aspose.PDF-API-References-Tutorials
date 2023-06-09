---
title: حدد الصفحة عند المشاهدة
linktitle: حدد الصفحة عند المشاهدة
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تحديد صفحة عند عرض ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 110
url: /ar/net/programming-with-links-and-actions/specify-page-when-viewing/
---

تعرف على كيفية تحديد صفحة عند عرض ملف PDF باستخدام Aspose.PDF for .NET مع هذا الدليل المفصل خطوة بخطوة.

## الخطوة الأولى: تهيئة البيئة

تأكد من قيامك بإعداد بيئة التطوير الخاصة بك باستخدام مشروع C # ومراجع Aspose.PDF المناسبة.

## الخطوة الثانية: تحميل ملف PDF

قم بتعيين مسار الدليل للمستندات الخاصة بك وقم بتحميل ملف PDF باستخدام الكود التالي:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// قم بتحميل ملف PDF
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
```

## الخطوة الثالثة: تحديد الصفحة المستهدفة

احصل على نسخة الصفحة الهدف باستخدام الكود التالي:

```csharp
Page page2 = doc.Pages[2];
```

 يمكنك ضبط الفهرس`[2]` لتحديد الصفحة المطلوبة.

## الخطوة 4: تكوين إعداد التكبير / التصغير

قم بإنشاء متغير لتعيين عامل تكبير الصفحة الهدف:

```csharp
double zoom = 1;
```

يمكنك ضبط قيمة التكبير وفقًا لاحتياجاتك.

## الخطوة 5: قم بإنشاء إجراء التنقل

قم بإنشاء مثيل لإجراء التنقل باستخدام الصفحة الهدف المحددة:

```csharp
GoToAction action = new GoToAction(doc.Pages[2]);
```

## الخطوة 6: تحديد الوجهة

اضبط الوجهة للانتقال إلى الصفحة المستهدفة باستخدام الإحداثيات والتكبير / التصغير:

```csharp
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
```

## الخطوة 7: تكوين إجراء فتح المستند

قم بتعيين إجراء فتح المستند مع إجراء التنقل الذي تم إنشاؤه:

```csharp
doc. OpenAction = action;
```

## الخطوة 8: احفظ المستند المحدث

 احفظ المستند المحدث باستخدام ملف`Save` طريقة:

```csharp
doc.Save(dataDir + "goto2page_out.pdf");
```

### نموذج التعليمات البرمجية المصدر لتحديد الصفحة عند العرض باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// قم بتحميل ملف PDF
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
// احصل على مثيل الصفحة الثانية من المستند
Page page2 = doc.Pages[2];
// قم بإنشاء المتغير لتعيين عامل التكبير / التصغير للصفحة المستهدفة
double zoom = 1;
// قم بإنشاء مثيل GoToAction
GoToAction action = new GoToAction(doc.Pages[2]);
// انتقل إلى 2 صفحة
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
// قم بتعيين إجراء فتح المستند
doc.OpenAction = action;
// احفظ المستند المحدث
doc.Save(dataDir + "goto2page_out.pdf");
```

## خاتمة

تهنئة ! أنت تعرف الآن كيفية تحديد صفحة عند عرض ملف PDF باستخدام Aspose.PDF لـ .NET. استخدم هذه المعرفة لتخصيص تجربة عرض المستخدم في مستندات PDF الخاصة بك.

الآن بعد أن أكملت هذا الدليل ، يمكنك تطبيق هذه المفاهيم على مشاريعك الخاصة واستكشاف المزيد من الميزات التي يوفرها Aspose.PDF لـ .NET.