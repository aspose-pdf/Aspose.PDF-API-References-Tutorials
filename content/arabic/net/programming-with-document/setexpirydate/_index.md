---
title: تعيين تاريخ انتهاء الصلاحية في ملف PDF
linktitle: تعيين تاريخ انتهاء الصلاحية في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية تعيين تاريخ انتهاء الصلاحية في ملف PDF باستخدام Aspose.PDF لـ .NET من خلال هذا الدليل خطوة بخطوة.
type: docs
weight: 300
url: /ar/net/programming-with-document/setexpirydate/
---
Aspose.PDF for .NET هي مكتبة قوية توفر ميزات متنوعة للعمل مع ملفات PDF. إحدى هذه الميزات هي القدرة على تحديد تاريخ انتهاء صلاحية مستند PDF. في هذا البرنامج التعليمي، سنوضح لك عملية تحديد تاريخ انتهاء صلاحية مستند PDF باستخدام Aspose.PDF for .NET. 

## الخطوة 1: تعيين المسار إلى دليل المستند

قبل أن نبدأ، نحتاج إلى تحديد المسار إلى الدليل الذي يوجد به مستند PDF الخاص بنا. سنخزن هذا المسار في متغير يسمى "dataDir".

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: إنشاء مستند PDF جديد

 لإنشاء مستند PDF جديد، نحتاج إلى إنشاء مثيل جديد`Aspose.Pdf.Document` يمكننا القيام بذلك باستخدام الكود التالي:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## الخطوة 3: إضافة صفحة جديدة إلى مستند PDF

بمجرد إنشاء مستند PDF، يمكننا إضافة صفحة جديدة إليه. يمكننا القيام بذلك باستخدام الكود التالي:

```csharp
doc.Pages.Add();
```

## الخطوة 4: إضافة نص إلى مستند PDF

 بعد إضافة صفحة إلى مستند PDF، يمكننا إضافة نص إليها باستخدام`Paragraphs` المجموعة. يمكننا القيام بذلك باستخدام الكود التالي:

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

// تعيين JavaScript كإجراء فتح PDF
doc.OpenAction = javaScript;
```

في هذا الكود قمنا بتعيين تاريخ انتهاء الصلاحية إلى مايو 2017.

## الخطوة 6: احفظ ملف PDF

 بعد تحديد تاريخ انتهاء الصلاحية، يتعين عليك حفظ ملف PDF. للقيام بذلك، يمكنك استخدام`Save` طريقة`Document` قم بإنشاء الكائن وتمريره في المسار الذي تريد حفظ ملف PDF المحدث فيه.

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
// حفظ مستند PDF
doc.Save(dataDir);
```

### مثال على كود المصدر لتعيين تاريخ انتهاء الصلاحية باستخدام Aspose.PDF لـ .NET

فيما يلي مثال كامل لمصدر الكود لتعيين تاريخ انتهاء الصلاحية باستخدام Aspose.PDF لـ .NET:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء كائن مستند
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// إضافة صفحة إلى مجموعة صفحات ملف PDF
doc.Pages.Add();
// إضافة جزء من النص إلى مجموعة فقرات كائن الصفحة
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
// إنشاء كائن JavaScript لتعيين تاريخ انتهاء صلاحية ملف PDF
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");
// تعيين JavaScript كإجراء فتح PDF
doc.OpenAction = javaScript;

dataDir = dataDir + "SetExpiryDate_out.pdf";
// حفظ مستند PDF
doc.Save(dataDir);
```

## خاتمة

إن تحديد تاريخ انتهاء صلاحية مستند PDF باستخدام Aspose.PDF for .NET يعد ميزة مفيدة لضمان صلاحية المستند لفترة محددة فقط. باتباع الدليل خطوة بخطوة واستخدام كود المصدر C# المقدم، يمكن للمطورين بسهولة تحديد تاريخ انتهاء الصلاحية وإنشاء ملفات PDF بصلاحية محدودة زمنيًا. يمكن أن تكون هذه الميزة مفيدة بشكل خاص للمستندات التي تحتاج إلى الوصول إليها أو توزيعها لمدة محدودة.

### الأسئلة الشائعة حول تاريخ انتهاء الصلاحية المحدد في ملف PDF

#### س: هل يمكنني تعيين تاريخ انتهاء صلاحية مختلف لمستند PDF؟

 ج: نعم، يمكنك تعيين تاريخ انتهاء صلاحية مختلف لمستند PDF عن طريق تعديل كود JavaScript في الخطوة 5. في المثال المقدم، تم تعيين تاريخ انتهاء الصلاحية على مايو 2017. لتعيين تاريخ انتهاء صلاحية مختلف، تحتاج إلى تعديل`year` و`month` المتغيرات في كود JavaScript للسنة والشهر المطلوبين.

#### س: ماذا يحدث عندما تنتهي صلاحية مستند PDF؟

ج: عند انتهاء صلاحية مستند PDF، كما هو محدد في كود JavaScript، سيعرض المشاهد رسالة تنبيه تشير إلى انتهاء صلاحية الملف وأن المستخدم يحتاج إلى ملف جديد. ستظهر رسالة التنبيه هذه عند فتح ملف PDF.

#### س: هل يمكنني استخدام وقت محدد لتاريخ انتهاء الصلاحية بدلاً من التاريخ فقط؟

 ج: نعم، يمكنك تعيين وقت محدد لتاريخ انتهاء الصلاحية في كود JavaScript. من خلال تعديل`expiry` من خلال إضافة متغير في كود JavaScript ليتضمن الوقت المطلوب، يمكنك تعيين وقت محدد لتاريخ انتهاء الصلاحية.