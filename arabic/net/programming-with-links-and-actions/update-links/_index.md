---
title: روابط التحديث
linktitle: روابط التحديث
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تحديث الروابط في ملف PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 120
url: /ar/net/programming-with-links-and-actions/update-links/
---

تعرف على كيفية تحديث الروابط في ملف PDF باستخدام Aspose.PDF for .NET باستخدام هذا الدليل المفصل خطوة بخطوة.

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

## الخطوة الثالثة: تحرير الرابط

احصل على التعليق التوضيحي للرابط لتعديله باستخدام الكود التالي:

```csharp
LinkAnnotation linkAnnot = (LinkAnnotation)doc.Pages[1].Annotations[1];
```

 يمكنك ضبط ملف`[1]` الفهارس لتحديد صفحة أو تعليق توضيحي معين.

بعد ذلك ، قم بتعديل الارتباط عن طريق تغيير الوجهة:

```csharp
GoToAction goToAction = (GoToAction)linkAnnot.Action;
goToAction.Destination = new Aspose.Pdf.Annotations.XYZExplicitDestination(1, 1, 2, 2);
```

تمثل المعلمة الأولى موضوع المستند ، بينما تمثل المعلمة الثانية رقم الصفحة الوجهة. الوسيطة الخامسة هي عامل التكبير عند عرض الصفحة المعنية. عند الضبط على 2 ، سيتم عرض الصفحة بنسبة تكبير 200٪.

## الخطوة 4: احفظ المستند بالرابط المحدث

احفظ المستند بالرابط المحدث باستخدام ملف`Save` طريقة:

```csharp
dataDir = dataDir + "PDFLINK_Modified_UpdateLinks_out.pdf";
doc.Save(dataDir);
```

## الخطوة 5: عرض النتيجة

عرض رسالة تشير إلى أنه تم تحديث الروابط بنجاح وتحديد موقع الملف المحفوظ:

```csharp
Console.WriteLine("\nLinks updated successfully.\nFile saved to location: " + dataDir);
```

### نموذج التعليمات البرمجية المصدر لتحديث الارتباطات باستخدام Aspose.PDF لـ .NET 
```csharp
try
{
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// قم بتحميل ملف PDF
	Document doc = new Document(dataDir + "UpdateLinks.pdf");
	// احصل على التعليق التوضيحي للرابط الأول من الصفحة الأولى من المستند
	LinkAnnotation linkAnnot = (LinkAnnotation)doc.Pages[1].Annotations[1];
	// رابط التعديل: تغيير وجهة الارتباط
	GoToAction goToAction = (GoToAction)linkAnnot.Action;
	// حدد وجهة كائن الارتباط
	// المعلمة الأولى هي كائن المستند ، والثانية هي رقم الصفحة الوجهة.
	// الوسيطة 5ht هي عامل التكبير عند عرض الصفحة المعنية. عند استخدام 2 ، سيتم عرض الصفحة بنسبة تكبير 200٪
	goToAction.Destination = new Aspose.Pdf.Annotations.XYZExplicitDestination(1, 1, 2, 2);
	dataDir = dataDir + "PDFLINK_Modified_UpdateLinks_out.pdf";
	// احفظ المستند مع الارتباط المحدث
	doc.Save(dataDir);
	Console.WriteLine("\nLinks updated successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## خاتمة

تهنئة ! أنت تعرف الآن كيفية تحديث الروابط في ملف PDF باستخدام Aspose.PDF for .NET. استخدم هذه المعرفة لتخصيص الروابط في مستندات PDF الخاصة بك وإنشاء تجارب تفاعلية للمستخدمين.

الآن بعد أن أكملت هذا الدليل ، يمكنك تطبيق هذه المفاهيم على مشاريعك الخاصة واستكشاف المزيد من الميزات التي يوفرها Aspose.PDF لـ .NET.