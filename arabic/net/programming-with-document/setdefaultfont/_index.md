---
title: تعيين الخط الافتراضي في ملف PDF
linktitle: تعيين الخط الافتراضي في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تعيين الخط الافتراضي في ملف PDF باستخدام Aspose.PDF for .NET باستخدام هذا الدليل المفصل خطوة بخطوة.
type: docs
weight: 280
url: /ar/net/programming-with-document/setdefaultfont/
---
إذا كنت تعمل مع مستندات PDF في .NET ، فقد تواجه مشكلات حيث لا يتوفر الخط المستخدم في PDF على النظام الذي يتم عرضه أو طباعته. يمكن أن يؤدي هذا إلى ظهور النص بشكل غير صحيح أو عدم ظهوره على الإطلاق. يوفر Aspose.PDF for .NET حلاً لهذه المشكلة عن طريق السماح لك بتعيين خط افتراضي للمستند. في هذا المثال ، كيفية تعيين الخط الافتراضي باستخدام Aspose.PDF لـ .NET.

## الخطوة 1: قم بتعيين المسار إلى دليل المستند

نحتاج إلى تعيين المسار إلى الدليل حيث يوجد مستند PDF الخاص بنا. سنخزن هذا المسار في متغير يسمى "dataDir".

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل مستند PDF

 سنبدأ بتحميل مستند PDF موجود به خطوط مفقودة. في هذا المثال ، سنفترض أن مستند PDF موجود في الدليل المحدد بواسطة ملف`dataDir` عامل.

```csharp
string documentName = dataDir + "input.pdf";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
    // كود هنا
}
```

## الخطوة 3: تعيين الخط الافتراضي

 بعد ذلك ، سنقوم بتعيين الخط الافتراضي لمستند PDF باستخدام امتداد`PdfSaveOptions` فصل. في هذا المثال ، سنقوم بتعيين الخط الافتراضي على "Arial".

```csharp
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.DefaultFontName = "Arial";
```

## الخطوة 4: احفظ المستند المحدث

أخيرًا ، سنقوم بحفظ المستند المحدث في ملف جديد. في هذا المثال ، سنحفظ المستند المحدث في ملف يسمى "output_out.pdf" في نفس الدليل مثل ملف الإدخال.

```csharp
document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
```

### مثال التعليمات البرمجية المصدر لتعيين الخط الافتراضي باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// قم بتحميل مستند PDF موجود بخط مفقود
string documentName = dataDir + "input.pdf";
string newName = "Arial";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
	PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
	// حدد اسم الخط الافتراضي
	pdfSaveOptions.DefaultFontName = newName;
	document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
}
```

## خاتمة

يعد تعيين خط افتراضي في مستندات PDF باستخدام Aspose.PDF for .NET طريقة بسيطة وفعالة لضمان عرض النص بشكل صحيح ، حتى إذا كانت الخطوط الأصلية غير متوفرة. باتباع الدليل خطوة بخطوة واستخدام الكود المصدري C # ، يمكن للمطورين بسهولة تعيين الخط الافتراضي وإنشاء ملفات PDF التي توفر تجربة مشاهدة متسقة وموثوقة عبر بيئات مختلفة. هذه الميزة مفيدة بشكل خاص في السيناريوهات حيث سيتم عرض ملفات PDF أو طباعتها على أنظمة مختلفة قد تحتوي على مجموعات خطوط مختلفة مثبتة.

### الأسئلة الشائعة حول تعيين الخط الافتراضي في ملف PDF

#### س: لماذا يعد تعيين خط افتراضي مهمًا في مستندات PDF؟

ج: يعد تعيين خط افتراضي في مستندات PDF أمرًا مهمًا لأنه يضمن عرض النص بشكل صحيح حتى إذا كانت الخطوط الأصلية غير متوفرة على النظام حيث يتم عرض ملف PDF أو طباعته. يساعد في منع حدوث مشكلات مثل النص المفقود أو المشوه ، مما يضمن تجربة مشاهدة متسقة وموثوقة.

#### س: هل يمكنني اختيار أي خط على أنه الخط الافتراضي باستخدام Aspose.PDF for .NET؟

 ج: نعم ، يمكنك اختيار أي خط متوفر على النظام كخط افتراضي باستخدام Aspose.PDF for .NET. ما عليك سوى تحديد اسم الخط في ملف`DefaultFontName` ممتلكات`PdfSaveOptions` فصل.

#### س: ماذا يحدث إذا كان الخط الافتراضي المحدد غير متوفر على النظام؟

ج: إذا كان الخط الافتراضي المحدد غير متوفر على النظام ، فسيستخدم عارض PDF خطًا احتياطيًا لعرض النص. يُنصح باختيار خط متاح بشكل شائع مثل Arial أو Times New Roman لضمان التوافق عبر الأنظمة المختلفة.