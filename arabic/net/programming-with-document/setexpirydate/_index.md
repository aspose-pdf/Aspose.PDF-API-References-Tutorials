---
title: حدد تاريخ انتهاء الصلاحية
linktitle: حدد تاريخ انتهاء الصلاحية
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تعيين تاريخ انتهاء الصلاحية في مستندات PDF باستخدام Aspose.PDF for .NET مع هذا الدليل المفصل خطوة بخطوة.
type: docs
weight: 300
url: /ar/net/programming-with-document/setexpirydate/
---
Aspose.PDF for .NET مكتبة قوية توفر العديد من الميزات للعمل مع ملفات PDF. إحدى هذه الميزات هي القدرة على تحديد تاريخ انتهاء صلاحية لمستند PDF. في هذا البرنامج التعليمي ، سنرشدك خلال عملية تحديد تاريخ انتهاء صلاحية مستند PDF باستخدام Aspose.PDF لـ .NET. 

## الخطوط العريضة
1. ما هو Aspose.PDF for .NET؟
2. تعيين ميزة تاريخ انتهاء الصلاحية لـ Aspose.PDF لـ .NET
3. تهيئة البيئة
4. إنشاء مستند PDF جديد
5. إضافة صفحة إلى وثيقة PDF
6. إضافة نص إلى وثيقة PDF
7. إنشاء كائن JavaScript لضبط تاريخ انتهاء صلاحية ملف PDF
8. إعداد JavaScript كملف PDF Open Action
9. حفظ مستند PDF
10. مثال على رمز المصدر لتعيين تاريخ انتهاء الصلاحية باستخدام Aspose.PDF لـ .NET
11. خاتمة
12. أسئلة وأجوبة

## الخطوة 1: قم بتعيين المسار إلى دليل المستند

قبل أن نبدأ ، نحتاج إلى تعيين المسار إلى الدليل حيث يوجد مستند PDF الخاص بنا. سنخزن هذا المسار في متغير يسمى "dataDir".

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: إنشاء مستند PDF جديد

 لإنشاء مستند PDF جديد ، نحتاج إلى إنشاء مثيل ملف`Aspose.Pdf.Document` هدف. يمكننا القيام بذلك باستخدام الكود التالي:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## الخطوة 3: إضافة صفحة جديدة إلى وثيقة PDF

بمجرد إنشاء مستند PDF ، يمكننا إضافة صفحة جديدة إليه. يمكننا القيام بذلك باستخدام الكود التالي:

```csharp
doc.Pages.Add();
```

## الخطوة 4: إضافة نص إلى مستند PDF

 بعد إضافة صفحة إلى مستند PDF ، يمكننا إضافة نص إليها باستخدام امتداد`Paragraphs` مجموعة. يمكننا القيام بذلك باستخدام الكود التالي:

```csharp
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
```

## الخطوة 5: تحديد تاريخ انتهاء صلاحية ملف PDF باستخدام JavaScript

لتعيين تاريخ انتهاء صلاحية ملف PDF ، نحتاج إلى إنشاء كائن JavaScript. يمكننا القيام بذلك باستخدام الكود التالي:

```csharp
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");

// قم بتعيين JavaScript كإجراء مفتوح PDF
doc.OpenAction = javaScript;
```

في هذا الكود ، نحدد تاريخ انتهاء الصلاحية إلى مايو 2017.

## الخطوة السادسة: احفظ ملف PDF

 بعد تعيين تاريخ انتهاء الصلاحية ، ستحتاج إلى حفظ ملف PDF. للقيام بذلك ، يمكنك استخدام ملف`Save` طريقة`Document` الكائن وتمرير المسار إلى المكان الذي تريد حفظ ملف PDF المحدث فيه.

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
// حفظ وثيقة PDF
doc.Save(dataDir);
```

### مثال على التعليمات البرمجية المصدر لتعيين تاريخ انتهاء الصلاحية باستخدام Aspose.PDF for .NET

إليك المثال الكامل لشفرة المصدر لتحديد تاريخ انتهاء الصلاحية باستخدام Aspose.PDF for .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// إنشاء كائن المستند
	Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
	// أضف صفحة إلى مجموعة صفحات من ملف PDF
	doc.Pages.Add();
	// إضافة جزء نصي إلى مجموعة فقرات كائن الصفحة
	doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
	// قم بإنشاء كائن JavaScript لتعيين تاريخ انتهاء صلاحية ملف PDF
	JavascriptAction javaScript = new JavascriptAction(
	"var year=2017;"
	+ "var month=5;"
	+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
	+ "expiry = new Date(year, month);"
	+ "if (today.getTime() > expiry.getTime())"
	+ "app.alert('The file is expired. You need a new one.');");
	// قم بتعيين JavaScript كإجراء مفتوح PDF
	doc.OpenAction = javaScript;

	dataDir = dataDir + "SetExpiryDate_out.pdf";
	// حفظ وثيقة PDF
	doc.Save(dataDir);
	
```
