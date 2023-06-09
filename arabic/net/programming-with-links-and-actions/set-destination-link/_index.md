---
title: قم بتعيين ارتباط الوجهة
linktitle: قم بتعيين ارتباط الوجهة
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تعيين رابط الوجهة في ملف PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 90
url: /ar/net/programming-with-links-and-actions/set-destination-link/
---

تعرف على كيفية تعيين رابط الوجهة في ملف PDF باستخدام Aspose.PDF for .NET باستخدام هذا الدليل المفصل خطوة بخطوة.

## الخطوة الأولى: تهيئة البيئة

تأكد من قيامك بإعداد بيئة التطوير الخاصة بك باستخدام مشروع C # ومراجع Aspose.PDF المناسبة.

## الخطوة الثانية: تحميل ملف PDF

قم بتعيين مسار الدليل للمستندات الخاصة بك وقم بتحميل ملف PDF باستخدام الكود التالي:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// قم بتحميل ملف PDF
Document doc = new Document(dataDir + "UpdateLinks.pdf");
```

## الخطوة 3: تحرير رابط الوجهة

احصل على التعليق التوضيحي للرابط لتعديله باستخدام الكود التالي:

```csharp
LinkAnnotation linkAnnot = (LinkAnnotation)doc.Pages[1].Annotations[1];
```

 يمكنك ضبط ملف`[1]` الفهارس لتحديد صفحة أو تعليق توضيحي معين.

بعد ذلك ، قم بتحرير الارتباط عن طريق تغيير إجراء الارتباط وتعيين الهدف كعنوان ويب:

```csharp
linkAnnot.Action = new GoToURIAction("www.aspose.com");
```

## الخطوة 4: احفظ المستند بالرابط المحدث

احفظ المستند بالرابط المحدث باستخدام ملف`Save` طريقة:

```csharp
dataDir = dataDir + "SetDestinationLink_out.pdf";
doc.Save(dataDir);
```

## الخطوة 5: عرض النتيجة

عرض رسالة تشير إلى أنه تم تكوين ارتباط الوجهة بنجاح وتحديد موقع الملف المحفوظ:

```csharp
Console.WriteLine("\nDestination link configured successfully.\nFile saved to location: " + dataDir);
```

### نموذج التعليمات البرمجية المصدر لـ Set Destination Link باستخدام Aspose.PDF for .NET 
```csharp
try
{
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// قم بتحميل ملف PDF
	Document doc = new Document(dataDir + "UpdateLinks.pdf");
	// احصل على التعليق التوضيحي للرابط الأول من الصفحة الأولى من المستند
	LinkAnnotation linkAnnot = (LinkAnnotation)doc.Pages[1].Annotations[1];
	// رابط التعديل: تغيير إجراء الارتباط وتعيين الهدف كعنوان ويب
	linkAnnot.Action = new GoToURIAction("www.aspose.com");           
	dataDir = dataDir + "SetDestinationLink_out.pdf";
	// احفظ المستند مع الارتباط المحدث
	doc.Save(dataDir);
	Console.WriteLine("\nDestination link setup successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## خاتمة

تهنئة ! أنت تعرف الآن كيفية تعيين ارتباط الوجهة في ملف PDF باستخدام Aspose.PDF لـ .NET. استخدم هذه المعرفة لتخصيص الروابط في مستندات PDF الخاصة بك وإنشاء تجارب تفاعلية للمستخدمين.

الآن بعد أن أكملت هذا الدليل ، يمكنك تطبيق هذه المفاهيم على مشاريعك الخاصة واستكشاف المزيد من الميزات التي يوفرها Aspose.PDF لـ .NET.