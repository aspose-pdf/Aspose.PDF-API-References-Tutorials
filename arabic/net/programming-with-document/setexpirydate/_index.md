---
title: قم بتعيين تاريخ انتهاء الصلاحية في ملف PDF
linktitle: قم بتعيين تاريخ انتهاء الصلاحية في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تعيين تاريخ انتهاء الصلاحية في ملف PDF باستخدام Aspose.PDF for .NET مع هذا الدليل المفصل خطوة بخطوة.
type: docs
weight: 300
url: /ar/net/programming-with-document/setexpirydate/
---
Aspose.PDF for .NET مكتبة قوية توفر العديد من الميزات للعمل مع ملفات PDF. إحدى هذه الميزات هي القدرة على تحديد تاريخ انتهاء صلاحية لمستند PDF. في هذا البرنامج التعليمي ، سنرشدك خلال عملية تحديد تاريخ انتهاء صلاحية مستند PDF باستخدام Aspose.PDF لـ .NET. 

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

## خاتمة

يعد تحديد تاريخ انتهاء صلاحية مستند PDF باستخدام Aspose.PDF for .NET ميزة مفيدة لضمان صلاحية المستند لفترة محددة فقط. باتباع الدليل خطوة بخطوة واستخدام الكود المصدري C # المقدم ، يمكن للمطورين بسهولة تعيين تاريخ انتهاء الصلاحية وإنشاء ملفات PDF بصلاحية محدودة الوقت. يمكن أن تكون هذه الميزة مفيدة بشكل خاص للمستندات التي تحتاج إلى الوصول إليها أو توزيعها لفترة محدودة.

### الأسئلة الشائعة حول تاريخ انتهاء الصلاحية المحدد في ملف PDF

#### س: هل يمكنني تحديد تاريخ انتهاء صلاحية مختلف لمستند PDF؟

 ج: نعم ، يمكنك تعيين تاريخ انتهاء صلاحية مختلف لمستند PDF عن طريق تعديل كود JavaScript في الخطوة 5. في المثال المقدم ، يتم تعيين تاريخ انتهاء الصلاحية على May 2017. لتعيين تاريخ انتهاء صلاحية مختلف ، تحتاج إلى تعديل`year` و`month` المتغيرات في كود JavaScript للسنة والشهر المطلوبين.

#### س: ماذا يحدث عند انتهاء صلاحية مستند PDF؟

ج: عند انتهاء صلاحية مستند PDF ، كما هو محدد في كود JavaScript ، سيعرض العارض رسالة تنبيه تشير إلى انتهاء صلاحية الملف وأن المستخدم بحاجة إلى ملف جديد. ستظهر رسالة التنبيه هذه عند فتح ملف PDF.

#### س: هل يمكنني استخدام وقت محدد لتاريخ انتهاء الصلاحية بدلاً من التاريخ فقط؟

 ج: نعم ، يمكنك ضبط وقت محدد لتاريخ انتهاء الصلاحية في كود JavaScript. عن طريق تعديل`expiry` متغير في كود JavaScript لتضمين الوقت المطلوب ، يمكنك تعيين وقت محدد لتاريخ انتهاء الصلاحية.