---
title: قم بتعيين عامل التكبير
linktitle: قم بتعيين عامل التكبير
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تعيين عامل التكبير / التصغير لملفات PDF باستخدام Aspose.PDF for .NET مع دليلنا المفصل خطوة بخطوة.
type: docs
weight: 340
url: /ar/net/programming-with-document/setzoomfactor/
---
Aspose.PDF for .NET هي واجهة برمجة تطبيقات قوية تسمح للمطورين بالعمل مع مستندات PDF في تطبيقاتهم .NET. إحدى الميزات التي يوفرها هي القدرة على تعيين عامل التكبير / التصغير لمستند PDF. في هذا الدليل المفصل خطوة بخطوة ، سنشرح كيفية استخدام Aspose.PDF لـ .NET لتعيين عامل التكبير / التصغير لمستند PDF باستخدام كود المصدر C # المقدم.

## الخطوة 1: قم بتعيين المسار إلى دليل المستند

 تتمثل الخطوة الأولى في تعيين المسار إلى الدليل حيث يوجد مستند PDF. يمكن القيام بذلك عن طريق ضبط ملف`dataDir` متغير إلى مسار الدليل. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

استبدل "دليل المستند" بمسار الدليل الفعلي حيث يوجد مستند PDF الخاص بك.

## الخطوة 2: إنشاء كائن مستند جديد

 للعمل مع مستند PDF باستخدام Aspose.PDF for .NET ، نحتاج إلى إنشاء ملف`Document` كائن وتحميل ملف PDF فيه. 

```csharp
Document doc = new Document(dataDir + "SetZoomFactor.pdf");
```

 هذا الرمز سيخلق`Document`الكائن وتحميل ملف PDF المسمى "SetZoomFactor.pdf" من ملف`dataDir` الدليل فيه.

## الخطوة 3: اضبط عامل الزوم

 مرة واحدة في`Document` تم إنشاء الكائن ، يمكننا ضبط عامل التكبير / التصغير لمستند PDF. في الكود التالي ، قمنا بتعيين عامل التكبير على 50٪.

```csharp
GoToAction action = new GoToAction(new XYZExplicitDestination(1, 0, 0, .5));
doc.OpenAction = action;
```

 يقوم هذا الرمز بتعيين عامل التكبير / التصغير إلى 50٪ عن طريق إنشاء ملف`GoToAction` كائن وتمرير أ`XYZExplicitDestination` مع عامل تكبير بنسبة 50٪. ال`OpenAction` ممتلكات`Document` ثم يتم تعيين الكائن على هذا`GoToAction` هدف.

## الخطوة 4: احفظ مستند PDF

 أخيرًا ، يمكننا حفظ مستند PDF المعدل في ملف جديد. في الكود التالي ، نحفظ مستند PDF في ملف جديد باسم "Zoomed_pdf_out.pdf" في`dataDir` الدليل.

```csharp
dataDir = dataDir + "Zoomed_pdf_out.pdf";
doc.Save(dataDir);
```

### مثال على الكود المصدري لـ Set Zoom Factor باستخدام Aspose.PDF for .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء كائن مستند جديد
Document doc = new Document(dataDir + "SetZoomFactor.pdf");

GoToAction action = new GoToAction(new XYZExplicitDestination(1, 0, 0, .5));
doc.OpenAction = action;
dataDir = dataDir + "Zoomed_pdf_out.pdf";
// احفظ المستند
doc.Save(dataDir);
```

## خاتمة

يوفر Aspose.PDF for .NET طريقة بسيطة وفعالة لتعيين عامل التكبير / التصغير لمستند PDF باستخدام كود C #. باتباع الخطوات المذكورة أعلاه ، يمكنك بسهولة تعديل عامل التكبير / التصغير لأي مستند PDF في تطبيق .NET الخاص بك.