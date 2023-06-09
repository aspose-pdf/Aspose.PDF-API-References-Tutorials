---
title: تعيين الارتباط الهدف
linktitle: تعيين الارتباط الهدف
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تعيين رابط هدف في ملف PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 100
url: /ar/net/programming-with-links-and-actions/set-target-link/
---

تعرف على كيفية تعيين رابط هدف في ملف PDF باستخدام Aspose.PDF for .NET باستخدام هذا الدليل المفصل خطوة بخطوة.

## الخطوة الأولى: تهيئة البيئة

تأكد من قيامك بإعداد بيئة التطوير الخاصة بك باستخدام مشروع C # ومراجع Aspose.PDF المناسبة.

## الخطوة الثانية: تحميل ملف PDF

قم بتعيين مسار الدليل للمستندات الخاصة بك وقم بتحميل ملف PDF باستخدام الكود التالي:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// قم بتحميل ملف PDF
Document document = new Document(dataDir + "UpdateLinks.pdf");
```

## الخطوة 3: تحرير الارتباط الهدف

احصل على التعليق التوضيحي للرابط لتعديله باستخدام الكود التالي:

```csharp
LinkAnnotation linkAnnot = (LinkAnnotation)document.Pages[1].Annotations[1];
GoToRemoteAction goToR = (GoToRemoteAction)linkAnnot.Action;
```

 يمكنك ضبط ملف`[1]` الفهارس لتحديد صفحة أو تعليق توضيحي معين.

بعد ذلك ، قم بتحديث الوجهة دون تحديث الملف:

```csharp
goToR.Destination = new XYZExplicitDestination(2, 0, 0, 1.5);
```

وإذا كنت تريد أيضًا تحديث الملف:

```csharp
goToR.File = new FileSpecification(dataDir + "input.pdf");
```

## الخطوة 4: احفظ المستند بالرابط المحدث

احفظ المستند بالرابط المحدث باستخدام ملف`Save` طريقة:

```csharp
dataDir = dataDir + "SetTargetLink_out.pdf";
document. Save(dataDir);
```

## الخطوة 5: عرض النتيجة

عرض رسالة تشير إلى أنه تم تكوين الارتباط الهدف بنجاح وتحديد موقع الملف المحفوظ:

```csharp
Console.WriteLine("\nConfiguration of target link successful.\nFile saved at location: " + dataDir);
```

### نموذج التعليمات البرمجية المصدر لـ Set Target Link باستخدام Aspose.PDF for .NET 
```csharp
try
{
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// قم بتحميل ملف PDF
	Document document = new Document(dataDir + "UpdateLinks.pdf");
	LinkAnnotation linkAnnot = (LinkAnnotation)document.Pages[1].Annotations[1];
	GoToRemoteAction goToR = (GoToRemoteAction)linkAnnot.Action;
	// وجهة تحديث السطر التالي ، لا تقم بتحديث الملف
	goToR.Destination = new XYZExplicitDestination(2, 0, 0, 1.5);
	// ملف تحديث السطر التالي
	goToR.File = new FileSpecification(dataDir +  "input.pdf");
	dataDir = dataDir + "SetTargetLink_out.pdf";
	// احفظ المستند مع الارتباط المحدث
	document.Save(dataDir);
	Console.WriteLine("\nTarget link setup successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## خاتمة

تهنئة ! أنت تعرف الآن كيفية تعيين رابط هدف في ملف PDF باستخدام Aspose.PDF لـ .NET. استخدم هذه المعرفة لتخصيص الروابط في مستندات PDF الخاصة بك وإنشاء تجارب تفاعلية للمستخدمين.

الآن بعد أن أكملت هذا الدليل ، يمكنك تطبيق هذه المفاهيم على مشاريعك الخاصة واستكشاف المزيد من الميزات التي يوفرها Aspose.PDF لـ .NET.