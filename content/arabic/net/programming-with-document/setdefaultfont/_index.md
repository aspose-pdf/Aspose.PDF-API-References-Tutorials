---
title: تعيين الخط الافتراضي في ملف PDF
linktitle: تعيين الخط الافتراضي في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تعيين الخط الافتراضي في ملف PDF باستخدام Aspose.PDF لـ .NET باستخدام هذا الدليل التفصيلي خطوة بخطوة.
type: docs
weight: 280
url: /ar/net/programming-with-document/setdefaultfont/
---
إذا كنت تعمل مع مستندات PDF في .NET، فقد تواجه مشكلات حيث لا يتوفر الخط المستخدم في ملف PDF على النظام الذي يتم عرضه أو طباعته فيه. يمكن أن يؤدي هذا إلى ظهور النص بشكل غير صحيح أو عدم ظهوره على الإطلاق. يوفر Aspose.PDF for .NET حلاً لهذه المشكلة عن طريق السماح لك بتعيين خط افتراضي للمستند. في هذا المثال، كيفية تعيين الخط الافتراضي باستخدام Aspose.PDF لـ .NET.

## الخطوة 1: قم بتعيين المسار إلى دليل المستند

نحتاج إلى تعيين المسار إلى الدليل الذي يوجد به مستند PDF الخاص بنا. سنقوم بتخزين هذا المسار في متغير يسمى "dataDir".

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل مستند PDF

 سنبدأ بتحميل مستند PDF موجود به خطوط مفقودة. في هذا المثال، سنفترض أن مستند PDF موجود في الدليل المحدد بواسطة الملف`dataDir` عامل.

```csharp
string documentName = dataDir + "input.pdf";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
    // الكود يذهب هنا
}
```

## الخطوة 3: تعيين الخط الافتراضي

 بعد ذلك، سنقوم بتعيين الخط الافتراضي لمستند PDF باستخدام الملف`PdfSaveOptions` فصل. في هذا المثال، سنقوم بتعيين الخط الافتراضي إلى "Arial".

```csharp
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.DefaultFontName = "Arial";
```

## الخطوة 4: احفظ المستند المحدث

وأخيرًا، سنقوم بحفظ المستند المحدث في ملف جديد. في هذا المثال، سنقوم بحفظ المستند المحدث في ملف يسمى "output_out.pdf" في نفس الدليل مثل ملف الإدخال.

```csharp
document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
```

### مثال على كود المصدر لتعيين الخط الافتراضي باستخدام Aspose.PDF لـ .NET

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

يعد تعيين خط افتراضي في مستندات PDF باستخدام Aspose.PDF لـ .NET طريقة بسيطة وفعالة لضمان عرض النص بشكل صحيح، حتى إذا لم تكن الخطوط الأصلية متوفرة. من خلال اتباع الدليل خطوة بخطوة واستخدام كود مصدر C# المقدم، يمكن للمطورين بسهولة تعيين الخط الافتراضي وإنشاء ملفات PDF التي توفر تجربة عرض متسقة وموثوقة عبر بيئات مختلفة. تعتبر هذه الميزة مفيدة بشكل خاص في السيناريوهات التي سيتم فيها عرض ملفات PDF أو طباعتها على أنظمة مختلفة قد تكون بها مجموعات خطوط مختلفة مثبتة.

### الأسئلة الشائعة لتعيين الخط الافتراضي في ملف PDF

#### س: لماذا يعد تعيين الخط الافتراضي مهمًا في مستندات PDF؟

ج: يعد تعيين الخط الافتراضي في مستندات PDF أمرًا مهمًا لأنه يضمن عرض النص بشكل صحيح حتى إذا لم تكن الخطوط الأصلية متوفرة على النظام الذي يتم فيه عرض ملف PDF أو طباعته. فهو يساعد على منع حدوث مشكلات مثل النص المفقود أو المشوه، مما يضمن تجربة مشاهدة متسقة وموثوقة.

#### س: هل يمكنني اختيار أي خط ليكون الخط الافتراضي باستخدام Aspose.PDF لـ .NET؟

 ج: نعم، يمكنك اختيار أي خط متوفر على النظام كخط افتراضي باستخدام Aspose.PDF لـ .NET. ما عليك سوى تحديد اسم الخط في ملف`DefaultFontName` ملكية`PdfSaveOptions` فصل.

#### س: ماذا يحدث إذا كان الخط الافتراضي المحدد غير متوفر على النظام؟

ج: إذا لم يكن الخط الافتراضي المحدد متاحًا على النظام، فسيستخدم عارض PDF خطًا احتياطيًا لعرض النص. يُنصح باختيار خط متاح بشكل شائع مثل Arial أو Times New Roman لضمان التوافق عبر الأنظمة المختلفة.