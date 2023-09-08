---
title: ضبط تاريخ انتهاء الصلاحية في ملف PDF
linktitle: ضبط تاريخ انتهاء الصلاحية في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تعيين تاريخ انتهاء الصلاحية في ملف PDF باستخدام Aspose.PDF لـ .NET باستخدام هذا الدليل التفصيلي خطوة بخطوة.
type: docs
weight: 300
url: /ar/net/programming-with-document/setexpirydate/
---
Aspose.PDF for .NET هي مكتبة قوية توفر ميزات متنوعة للعمل مع ملفات PDF. إحدى هذه الميزات هي القدرة على تحديد تاريخ انتهاء الصلاحية لمستند PDF. في هذا البرنامج التعليمي، سنرشدك خلال عملية تحديد تاريخ انتهاء الصلاحية لمستند PDF باستخدام Aspose.PDF لـ .NET. 

## الخطوة 1: قم بتعيين المسار إلى دليل المستند

قبل أن نبدأ، نحتاج إلى تعيين المسار إلى الدليل الذي يوجد به مستند PDF الخاص بنا. سنقوم بتخزين هذا المسار في متغير يسمى "dataDir".

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: إنشاء مستند PDF جديد

 لإنشاء مستند PDF جديد، نحتاج إلى إنشاء نسخة جديدة`Aspose.Pdf.Document` هدف. يمكننا القيام بذلك باستخدام الكود التالي:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## الخطوة 3: إضافة صفحة جديدة إلى مستند PDF

بمجرد إنشاء مستند PDF، يمكننا إضافة صفحة جديدة إليه. يمكننا القيام بذلك باستخدام الكود التالي:

```csharp
doc.Pages.Add();
```

## الخطوة 4: إضافة نص إلى وثيقة PDF

بعد إضافة صفحة إلى مستند PDF، يمكننا إضافة نص إليها باستخدام الملف`Paragraphs` مجموعة. يمكننا القيام بذلك باستخدام الكود التالي:

```csharp
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
```

## الخطوة 5: تحديد تاريخ انتهاء صلاحية ملف PDF باستخدام JavaScript

لتعيين تاريخ انتهاء صلاحية ملف PDF، نحتاج إلى إنشاء كائن JavaScript. يمكننا القيام بذلك باستخدام الكود التالي:

```csharp
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");

// قم بتعيين JavaScript كإجراء مفتوح لملف PDF
doc.OpenAction = javaScript;
```

في هذا الكود، نقوم بتحديد تاريخ انتهاء الصلاحية إلى مايو 2017.

## الخطوة 6: احفظ ملف PDF

 بعد تحديد تاريخ انتهاء الصلاحية، ستحتاج إلى حفظ ملف PDF. للقيام بذلك، يمكنك استخدام`Save` طريقة`Document` كائن وتمرير المسار إلى المكان الذي تريد حفظ ملف PDF المحدث فيه.

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
// حفظ وثيقة PDF
doc.Save(dataDir);
```

### مثال على التعليمات البرمجية المصدر لتعيين تاريخ انتهاء الصلاحية باستخدام Aspose.PDF لـ .NET

فيما يلي المثال الكامل للتعليمة البرمجية المصدر لتحديد تاريخ انتهاء الصلاحية باستخدام Aspose.PDF لـ .NET:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء مثيل لكائن المستند
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// إضافة صفحة إلى مجموعة الصفحات من ملف PDF
doc.Pages.Add();
// إضافة جزء نص إلى مجموعة الفقرات من كائن الصفحة
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
// قم بإنشاء كائن JavaScript لتعيين تاريخ انتهاء صلاحية PDF
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");
// قم بتعيين JavaScript كإجراء مفتوح لملف PDF
doc.OpenAction = javaScript;

dataDir = dataDir + "SetExpiryDate_out.pdf";
// حفظ وثيقة PDF
doc.Save(dataDir);
```

## خاتمة

يعد تحديد تاريخ انتهاء صلاحية مستند PDF باستخدام Aspose.PDF لـ .NET ميزة مفيدة للتأكد من أن المستند صالح لفترة محددة فقط. باتباع الدليل الموضح خطوة بخطوة واستخدام كود مصدر C# المقدم، يمكن للمطورين بسهولة تعيين تاريخ انتهاء الصلاحية وإنشاء ملفات PDF ذات صلاحية محدودة المدة. يمكن أن تكون هذه الميزة مفيدة بشكل خاص للمستندات التي يلزم الوصول إليها أو توزيعها لمدة محدودة.

### الأسئلة الشائعة لتحديد تاريخ انتهاء الصلاحية في ملف PDF

#### س: هل يمكنني تحديد تاريخ انتهاء مختلف لمستند PDF؟

 ج: نعم، يمكنك تعيين تاريخ انتهاء صلاحية مختلف لمستند PDF عن طريق تعديل كود JavaScript في الخطوة 5. في المثال المقدم، تم تعيين تاريخ انتهاء الصلاحية على مايو 2017. لتعيين تاريخ انتهاء صلاحية مختلف، تحتاج إلى تعديل`year` و`month` المتغيرات في كود JavaScript إلى السنة والشهر المطلوبين.

#### س: ماذا يحدث عند انتهاء صلاحية مستند PDF؟

ج: عند انتهاء صلاحية مستند PDF، كما هو محدد في كود JavaScript، سيعرض العارض رسالة تنبيه تشير إلى انتهاء صلاحية الملف وأن المستخدم يحتاج إلى ملف جديد. سيتم عرض رسالة التنبيه هذه عند فتح ملف PDF.

#### س: هل يمكنني استخدام وقت محدد لتاريخ انتهاء الصلاحية بدلاً من التاريخ فقط؟

 ج: نعم، يمكنك تحديد وقت محدد لتاريخ انتهاء الصلاحية في كود JavaScript. عن طريق تعديل`expiry` متغير في كود جافا سكريبت ليشمل الوقت المطلوب، يمكنك ضبط وقت محدد لتاريخ انتهاء الصلاحية.