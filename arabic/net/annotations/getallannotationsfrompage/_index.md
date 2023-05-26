---
title: احصل على جميع التعليقات التوضيحية من الصفحة
linktitle: احصل على جميع التعليقات التوضيحية من الصفحة
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استخدام Aspose.PDF for .NET لاسترداد جميع التعليقات التوضيحية من صفحة PDF باستخدام هذا الدليل المفصل خطوة بخطوة.
type: docs
weight: 70
url: /ar/net/annotations/getallannotationsfrompage/
---
ستوجهك هذه المقالة خلال عملية استخراج جميع التعليقات التوضيحية من صفحة PDF باستخدام Aspose.PDF for .NET. Aspose.PDF for .NET هي مكتبة تتيح للمطورين إنشاء مستندات PDF وتحريرها وتحويلها. بمساعدة هذا الدليل ، ستتمكن من الحصول على جميع التعليقات التوضيحية من صفحة PDF معينة باستخدام كود المصدر C # المقدم.

اتبع الخطوات التالية حول كيفية الحصول على جميع التعليقات التوضيحية لصفحة PDF باستخدام Aspose.PDF for .NET:

## الخطوة 1: المسار إلى دليل المستندات

تتمثل الخطوة الأولى في الحصول على جميع التعليقات التوضيحية من صفحة PDF باستخدام Aspose.PDF for .NET في تعيين المسار إلى دليل المستندات حيث يتم تخزين ملفات PDF الخاصة بك. يمكنك القيام بذلك عن طريق تعديل سطر التعليمات البرمجية التالي:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
## الخطوة 2: يتم تخزين ملفات PDF الخاصة بك

استبدل "دليل المستندات الخاص بك" بالمسار إلى المجلد حيث يتم تخزين ملفات PDF الخاصة بك. على سبيل المثال:

```csharp
string dataDir = @"C:\Users\JohnDoe\Documents\PDFs\";
```

## الخطوة 3: افتح المستند

الخطوة التالية هي فتح مستند PDF الذي يحتوي على التعليقات التوضيحية التي تريد استخراجها. يمكنك القيام بذلك عن طريق إضافة الكود التالي:

```csharp
Document pdfDocument = new Document(dataDir + "GetAllAnnotationsFromPage.pdf");
```

يقوم هذا السطر من التعليمات البرمجية بتهيئة مثيل جديد لفئة المستند وتحميل مستند PDF "GetAllAnnotationsFromPage.pdf". استبدل اسم الملف هذا باسم ملف PDF الخاص بك.

## الخطوة 4: تكرار جميع التعليقات التوضيحية

بمجرد فتح مستند PDF ، يمكنك تكرار جميع التعليقات التوضيحية في صفحة معينة. على سبيل المثال ، لتكرار جميع التعليقات التوضيحية في الصفحة الأولى من مستند PDF ، أضف الكود التالي:

```csharp
foreach (MarkupAnnotation annotation in pdfDocument.Pages[1].Annotations)
{
    // يظهر الرمز هنا
}
```

يتكرر هذا الرمز من خلال جميع التعليقات التوضيحية في الصفحة الأولى من مستند PDF ويخصص كل تعليق توضيحي لمتغير "التعليق التوضيحي".

## الخطوة 5: احصل على خصائص التعليقات التوضيحية

لاستخراج خصائص كل تعليق توضيحي ، يمكنك إضافة الكود التالي داخل حلقة foreach:

```csharp
Console.WriteLine("Title : {0} ", annotation.Title);
Console.WriteLine("Subject : {0} ", annotation.Subject);
Console.WriteLine("Contents : {0} ", annotation.Contents);
```

يكتب هذا الرمز العنوان والموضوع والمحتويات لكل تعليق توضيحي إلى وحدة التحكم.

### مثال التعليمات البرمجية المصدر للحصول على كافة التعليقات التوضيحية من الصفحة باستخدام Aspose.PDF لـ .NET

إليك الكود المصدري الكامل للحصول على جميع التعليقات التوضيحية من صفحة PDF باستخدام Aspose.PDF for .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// افتح المستند
	Document pdfDocument = new Document(dataDir + "GetAllAnnotationsFromPage.pdf");

	// حلقة خلال جميع التعليقات التوضيحية
	foreach (MarkupAnnotation annotation in pdfDocument.Pages[1].Annotations)
	{
		// احصل على خصائص التعليقات التوضيحية
		Console.WriteLine("Title : {0} ", annotation.Title);
		Console.WriteLine("Subject : {0} ", annotation.Subject);
		Console.WriteLine("Contents : {0} ", annotation.Contents);                
	}

```
