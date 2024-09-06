---
title: تعيين الخط الافتراضي في ملف PDF
linktitle: تعيين الخط الافتراضي في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية تعيين الخط الافتراضي في ملف PDF باستخدام Aspose.PDF لـ .NET باستخدام هذا الدليل خطوة بخطوة.
type: docs
weight: 280
url: /ar/net/programming-with-document/setdefaultfont/
---
إذا كنت تعمل مع مستندات PDF في .NET، فقد تواجه مشكلات حيث لا يتوفر الخط المستخدم في ملف PDF على النظام الذي يتم عرضه أو طباعته عليه. وقد يؤدي هذا إلى ظهور النص بشكل غير صحيح أو عدم ظهوره على الإطلاق. يوفر Aspose.PDF for .NET حلاً لهذه المشكلة من خلال السماح لك بتعيين خط افتراضي للمستند. في هذا المثال، كيفية تعيين الخط الافتراضي باستخدام Aspose.PDF for .NET.

## الخطوة 1: تعيين المسار إلى دليل المستند

نحتاج إلى تحديد المسار إلى الدليل الذي يوجد به مستند PDF الخاص بنا. سنخزن هذا المسار في متغير يسمى "dataDir".

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: تحميل مستند PDF

 سنبدأ بتحميل مستند PDF موجود به خطوط مفقودة. في هذا المثال، سنفترض أن مستند PDF موجود في الدليل المحدد بواسطة`dataDir` عامل.

```csharp
string documentName = dataDir + "input.pdf";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
    // الكود يذهب هنا
}
```

## الخطوة 3: تعيين الخط الافتراضي

 بعد ذلك، سنقوم بتعيين الخط الافتراضي لمستند PDF باستخدام`PdfSaveOptions`في هذا المثال، سنقوم بتعيين الخط الافتراضي إلى "Arial".

```csharp
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.DefaultFontName = "Arial";
```

## الخطوة 4: احفظ المستند المحدث

أخيرًا، سنحفظ المستند المحدّث في ملف جديد. في هذا المثال، سنحفظ المستند المحدّث في ملف باسم "output_out.pdf" في نفس الدليل الذي يحتوي على ملف الإدخال.

```csharp
document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
```

### مثال على كود المصدر لتعيين الخط الافتراضي باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// تحميل مستند PDF موجود بخط مفقود
string documentName = dataDir + "input.pdf";
string newName = "Arial";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
	PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
	// تحديد اسم الخط الافتراضي
	pdfSaveOptions.DefaultFontName = newName;
	document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
}
```

## خاتمة

إن تعيين خط افتراضي في مستندات PDF باستخدام Aspose.PDF for .NET هو طريقة بسيطة وفعالة لضمان عرض النص بشكل صحيح، حتى إذا لم تكن الخطوط الأصلية متاحة. باتباع الدليل خطوة بخطوة واستخدام كود المصدر C# المقدم، يمكن للمطورين تعيين الخط الافتراضي بسهولة وإنشاء ملفات PDF توفر تجربة عرض متسقة وموثوقة عبر بيئات مختلفة. هذه الميزة مفيدة بشكل خاص في السيناريوهات التي سيتم فيها عرض ملفات PDF أو طباعتها على أنظمة مختلفة قد تحتوي على مجموعات خطوط مختلفة مثبتة.

### الأسئلة الشائعة حول تعيين الخط الافتراضي في ملف PDF

#### س: لماذا يعد تعيين الخط الافتراضي أمرًا مهمًا في مستندات PDF؟

ج: يعد تعيين خط افتراضي في مستندات PDF أمرًا مهمًا لأنه يضمن عرض النص بشكل صحيح حتى إذا لم تكن الخطوط الأصلية متاحة على النظام الذي يتم عرض أو طباعة ملف PDF عليه. ويساعد ذلك في منع المشكلات مثل النص المفقود أو المشوه، مما يضمن تجربة عرض متسقة وموثوقة.

#### س: هل يمكنني اختيار أي خط كخط افتراضي باستخدام Aspose.PDF لـ .NET؟

 ج: نعم، يمكنك اختيار أي خط متوفر على النظام كخط افتراضي باستخدام Aspose.PDF لـ .NET. ما عليك سوى تحديد اسم الخط في`DefaultFontName` ممتلكات`PdfSaveOptions` فصل.

#### س: ماذا يحدث إذا لم يكن الخط الافتراضي المحدد متاحًا على النظام؟

ج: إذا لم يكن الخط الافتراضي المحدد متاحًا على النظام، فسيستخدم عارض PDF خطًا احتياطيًا لعرض النص. يُنصح باختيار خط متاح بشكل شائع مثل Arial أو Times New Roman لضمان التوافق عبر الأنظمة المختلفة.