---
title: استخراج النص المميز في ملف PDF
linktitle: استخراج النص المميز في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استخراج النص المميز في ملف PDF باستخدام Aspose.PDF لـ .NET باستخدام هذا الدليل التفصيلي خطوة بخطوة.
type: docs
weight: 60
url: /ar/net/annotations/extracthighlightedtext/
---
لاستخراج النص المميز في ملف PDF، يمكنك استخدام Aspose.PDF for .NET API. توفر واجهة برمجة التطبيقات هذه طريقة بسيطة لاسترداد كل النص الذي تم تمييزه في المستند.

## الخطوة 1: قم بتحميل مستند PDF

 الخطوة الأولى في استخراج النص المميز في ملف PDF هي تحميل المستند باستخدام Aspose.PDF لـ .NET API. يمكنك القيام بذلك عن طريق إنشاء مثيل جديد لـ`Document` class وتمرير المسار إلى مستند PDF كمعلمة. 

```csharp
// المسار إلى دليل المستندات.
string dataDir ="YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");
```

## الخطوة 2: قم بتكرار جميع التعليقات التوضيحية

 الخطوة التالية هي تكرار جميع التعليقات التوضيحية في مستند PDF. يمكنك القيام بذلك باستخدام`foreach` حلقة، مثل ذلك:

```csharp
foreach (Annotation annotation in doc.Pages[1].Annotations)
{
	// الكود يذهب هنا
}
```

## الخطوة 3: تصفية التعليقات التوضيحية لترميز النص

 داخل`foreach` حلقة، ستحتاج إلى تصفية جميع التعليقات التوضيحية التي ليست تعليقات توضيحية لترميز النص. يمكنك القيام بذلك عن طريق التحقق مما إذا كان التعليق التوضيحي هو مثيل لـ`TextMarkupAnnotation` فصل.

```csharp
if (annotation is TextMarkupAnnotation)
{
	// الكود يذهب هنا
}
```

## الخطوة 4: استرداد أجزاء النص المميزة

 بمجرد تصفية جميع التعليقات التوضيحية لترميز النص، يمكنك استرداد أجزاء النص المميزة لكل تعليق توضيحي. يمكنك القيام بذلك عن طريق الاتصال بـ`GetMarkedTextFragments()` الطريقة على`TextMarkupAnnotation` هدف.

```csharp
TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
```

## الخطوة 5: عرض النص المميز

 وأخيرا، يمكنك عرض النص المميز للمستخدم. يمكنك القيام بذلك عن طريق التكرار خلال كل منها`TextFragment` كائن في`TextFragmentCollection` والاتصال ب`Text` ملكية.

```csharp
foreach (TextFragment tf in collection)
{
	Console.WriteLine(tf.Text);
}
```

### مثال على التعليمات البرمجية المصدر لاستخراج النص المميز باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir ="YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");

foreach (Annotation annotation in doc.Pages[1].Annotations)
{
	if (annotation is TextMarkupAnnotation)
	{
		TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
		TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
		foreach (TextFragment tf in collection)
		{
			Console.WriteLine(tf.Text);
		}
	}
}
```

## خاتمة

في هذا البرنامج التعليمي، اكتشفنا كيفية استخراج النص المميز من مستند PDF باستخدام Aspose.PDF لـ .NET. باتباع الدليل الموضح خطوة بخطوة واستخدام كود مصدر C# المقدم، يمكن للمطورين بسهولة استخراج النص المميز وإدارته في مستندات PDF الخاصة بهم.

### الأسئلة الشائعة لاستخراج النص المميز في ملف PDF

#### س: ما هي التعليقات التوضيحية لترميز النص في مستند PDF؟

ج: التعليقات التوضيحية لترميز النص هي تعليقات توضيحية تقوم بتمييز نص معين أو وضع علامة عليه في مستند PDF. تتضمن أمثلة التعليقات التوضيحية لترميز النص التمييزات والتسطير والشطب.

#### س: هل يمكنني استخراج النص من أنواع أخرى من التعليقات التوضيحية باستخدام Aspose.PDF لـ .NET؟

ج: نعم، يوفر Aspose.PDF for .NET طرقًا متنوعة لاستخراج النص من أنواع مختلفة من التعليقات التوضيحية، بما في ذلك التعليقات التوضيحية لترميز النص، والتعليقات التوضيحية النصية المجانية، والمزيد.

#### س: هل يدعم Aspose.PDF for .NET استخراج النص من ملفات PDF المحمية بكلمة مرور؟

 ج: نعم، يدعم Aspose.PDF for .NET استخراج النص من ملفات PDF المحمية بكلمة مرور. يتعين عليك تقديم كلمة المرور الصحيحة عند تحميل مستند PDF باستخدام ملف`Document` فصل.

#### س: هل يمكنني تصفية النص المميز بناءً على معايير أخرى، مثل اللون أو المؤلف؟

ج: نعم، يمكنك تصفية النص المميز بناءً على معايير أخرى، مثل اللون أو المؤلف أو تاريخ الإنشاء. يوفر Aspose.PDF for .NET طرقًا للوصول إلى التعليقات التوضيحية وتصفيتها استنادًا إلى خصائصها.

#### س: هل من الممكن حفظ النص المميز المستخرج في ملف منفصل؟

ج: نعم، يمكنك حفظ النص المميز المستخرج في ملف منفصل أو تخزينه في بنية بيانات لمزيد من المعالجة أو التحليل.
