---
title: استخراج النص المميز في ملف PDF
linktitle: استخراج النص المميز في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استخراج النص المميز في ملف PDF باستخدام Aspose.PDF for .NET باستخدام هذا الدليل المفصل خطوة بخطوة.
type: docs
weight: 60
url: /ar/net/annotations/extracthighlightedtext/
---
لاستخراج النص المميز في ملف PDF ، يمكنك استخدام Aspose.PDF لـ .NET API. توفر واجهة برمجة التطبيقات هذه طريقة بسيطة لاسترداد كل النص الذي تم تمييزه في المستند.

## الخطوة 1: قم بتحميل مستند PDF

 تتمثل الخطوة الأولى لاستخراج النص المميز في ملف PDF في تحميل المستند باستخدام Aspose.PDF for .NET API. يمكنك القيام بذلك عن طريق إنشاء مثيل جديد لملف`Document` class وتمرير المسار إلى مستند PDF كمعامل. 

```csharp
// المسار إلى دليل المستندات.
string dataDir ="YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");
```

## الخطوة 2: تكرار جميع التعليقات التوضيحية

 الخطوة التالية هي تكرار جميع التعليقات التوضيحية في مستند PDF. يمكنك القيام بذلك باستخدام ملف`foreach` حلقة ، مثل ذلك:

```csharp
foreach (Annotation annotation in doc.Pages[1].Annotations)
{
	// يظهر الرمز هنا
}
```

## الخطوة 3: تصفية التعليقات التوضيحية لترميز النص

 داخل`foreach` حلقة ، ستحتاج إلى تصفية جميع التعليقات التوضيحية التي ليست تعليقات توضيحية نصية. يمكنك القيام بذلك عن طريق التحقق مما إذا كان التعليق التوضيحي مثيلاً لملف`TextMarkupAnnotation` فصل.

```csharp
if (annotation is TextMarkupAnnotation)
{
	// يظهر الرمز هنا
}
```

## الخطوة 4: استرجع أجزاء النص المميزة

 بمجرد تصفية جميع التعليقات التوضيحية لترميز النص ، يمكنك استرداد أجزاء النص المميزة لكل تعليق توضيحي. يمكنك القيام بذلك عن طريق الاتصال بـ`GetMarkedTextFragments()` طريقة على`TextMarkupAnnotation` هدف.

```csharp
TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
```

## الخطوة 5: اعرض النص المميز

 أخيرًا ، يمكنك عرض النص المميز للمستخدم. يمكنك القيام بذلك عن طريق تكرار كل منها`TextFragment` كائن في`TextFragmentCollection` واستدعاء`Text` ملكية.

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

في هذا البرنامج التعليمي ، اكتشفنا كيفية استخراج النص المميز من مستند PDF باستخدام Aspose.PDF for .NET. باتباع الدليل خطوة بخطوة واستخدام الكود المصدري C # المقدم ، يمكن للمطورين بسهولة استخراج وإدارة النص المميز في مستندات PDF الخاصة بهم.

### الأسئلة الشائعة لاستخراج النص المميز في ملف PDF

#### س: ما هي التعليقات التوضيحية للترميز النصي في مستند PDF؟

ج: التعليقات التوضيحية لتوصيف النص عبارة عن تعليقات توضيحية تبرز نصًا معينًا أو تحدده في مستند PDF. تتضمن أمثلة التعليقات التوضيحية لترميز النص الإبرازات والتسطير والخط.

#### س: هل يمكنني استخراج نص من أنواع التعليقات التوضيحية الأخرى باستخدام Aspose.PDF for .NET؟

ج: نعم ، يوفر Aspose.PDF for .NET طرقًا مختلفة لاستخراج النص من أنواع مختلفة من التعليقات التوضيحية ، بما في ذلك التعليقات التوضيحية لترميز النص والتعليقات التوضيحية النصية المجانية والمزيد.

#### س: هل يدعم Aspose.PDF for .NET استخراج النص من ملفات PDF المحمية بكلمة مرور؟

ج: نعم ، يدعم Aspose.PDF for .NET استخراج النص من ملفات PDF المحمية بكلمة مرور. تحتاج إلى توفير كلمة المرور الصحيحة عند تحميل مستند PDF باستخدام ملف`Document` فصل.

#### س: هل يمكنني تصفية النص المميز بناءً على معايير أخرى ، مثل اللون أو المؤلف؟

ج: نعم ، يمكنك تصفية النص المميز بناءً على معايير أخرى ، مثل اللون أو المؤلف أو تاريخ الإنشاء. يوفر Aspose.PDF for .NET طرقًا للوصول إلى التعليقات التوضيحية وتصفيتها بناءً على خصائصها.

#### س: هل من الممكن حفظ النص المميز المستخرج في ملف منفصل؟

ج: نعم ، يمكنك حفظ النص المميز المستخرج في ملف منفصل أو تخزينه في بنية بيانات لمزيد من المعالجة أو التحليل.
