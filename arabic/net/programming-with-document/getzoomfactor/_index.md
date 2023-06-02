---
title: احصل على عامل التكبير
linktitle: احصل على عامل التكبير
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استخدام Aspose.PDF for .NET للحصول على عامل التكبير / التصغير لملف PDF باستخدام هذا الدليل المفصل خطوة بخطوة.
type: docs
weight: 210
url: /ar/net/programming-with-document/getzoomfactor/
---
Aspose.PDF for .NET هي مكتبة لمعالجة ملفات PDF توفر العديد من الميزات لإجراء عمليات متنوعة على مستندات PDF. إحدى هذه الميزات هي القدرة على الحصول على عامل التكبير / التصغير لملف PDF. في هذا البرنامج التعليمي ، سنشرح كيفية استخدام Aspose.PDF لـ .NET للحصول على عامل التكبير / التصغير لملف PDF باستخدام الكود المصدري C #.


## الخطوة 1: إنشاء كائن مستند جديد

 تتمثل الخطوة الأولى للحصول على عامل التكبير / التصغير لملف PDF باستخدام Aspose.PDF for .NET في إنشاء نسخة جديدة من ملف`Document` هدف. ال`Document` يمثل الكائن مستند PDF يمكن تحميله من ملف أو تدفق.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء كائن مستند جديد
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");
```

 في الكود أعلاه ، أنشأنا ملف`Document` كائن عن طريق تمرير مسار ملف PDF إلى مُنشئ امتداد`Document` فصل. تحتاج إلى استبدال "دليل المستندات" بالمسار الفعلي للدليل حيث يوجد ملف PDF الخاص بك.

## الخطوة 2: إنشاء كائن GoToAction

 الخطوة التالية هي إنشاء ملف`GoToAction` هدف. أ`GoToAction` يمثل الكائن إجراءً ينتقل إلى وجهة معينة في مستند PDF. في حالتنا ، نريد الحصول على عامل التكبير / التصغير لملف PDF ، لذلك سنستخدم الامتداد`OpenAction` ممتلكات`Document` كائن للحصول على`GoToAction` هدف.

```csharp
// قم بإنشاء كائن GoToAction
GoToAction action = doc.OpenAction as GoToAction;
```

 في الكود أعلاه ، أنشأنا ملف`GoToAction` كائن عن طريق صب`OpenAction` ممتلكات`Document` يعترض على`GoToAction`.

## الخطوة 3: احصل على عامل التكبير لملف PDF

الخطوة الثالثة هي الحصول على عامل التكبير لملف PDF. يمكننا الحصول على عامل التكبير / التصغير لملف PDF من خلال الوصول إلى ملف`Destination` ممتلكات`GoToAction` كائن ثم تحويله إلى`XYZExplicitDestination` . ال`XYZExplicitDestination` تمثل class وجهة في مستند PDF تحدد الإحداثيات وعامل التكبير / التصغير للانتقال إليه.

```csharp
// احصل على عامل التكبير لملف PDF
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // قيمة تكبير الوثيقة ؛
```

 في الكود أعلاه ، وصلنا إلى ملف`Destination` ممتلكات`GoToAction` كائن ثم يلقي به`XYZExplicitDestination` . بعد ذلك ، وصلنا إلى ملف`Zoom` ممتلكات`XYZExplicitDestination` كائن للحصول على عامل التكبير / التصغير لملف PDF.

## الخطوة 4: إخراج عامل التكبير

 الخطوة الأخيرة هي إخراج عامل التكبير لملف PDF. يمكننا استخدام`System.Console.WriteLine`

```csharp
// احصل على عامل التكبير لملف PDF
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // قيمة تكبير الوثيقة ؛
```        

### مثال على كود المصدر للحصول على عامل التكبير باستخدام Aspose.PDF لـ .NET

إليك المثال الكامل لشفرة المصدر لـ Get Zoom Factor باستخدام Aspose.PDF for .NET:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء كائن مستند جديد
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");

// قم بإنشاء كائن GoToAction
GoToAction action = doc.OpenAction as GoToAction;

// احصل على عامل التكبير لملف PDF
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // قيمة تكبير الوثيقة ؛
```
