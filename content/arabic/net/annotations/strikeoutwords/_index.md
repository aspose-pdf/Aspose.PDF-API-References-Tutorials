---
title: شطب الكلمات
linktitle: شطب الكلمات
second_title: Aspose.PDF لمرجع .NET API
description: توفر هذه المقالة دليلاً خطوة بخطوة لاستخدام Aspose.PDF لميزة Strike Out Words الخاصة بـ .NET، بما في ذلك الدليل والشروحات خطوة بخطوة
type: docs
weight: 150
url: /ar/net/annotations/strikeoutwords/
---
Aspose.PDF for .NET عبارة عن مكتبة لمعالجة ومعالجة مستندات PDF توفر ميزات متنوعة لإنشاء ملفات PDF وتعديلها وتحويلها. إحدى الميزات المفيدة التي يوفرها Aspose.PDF هي القدرة على شطب الكلمات أو العبارات في مستند PDF باستخدام كود مصدر C#. في هذه المقالة، سنقدم دليلًا خطوة بخطوة حول كيفية شطب الكلمات باستخدام Aspose.PDF لـ .NET.

## الخطوة 1: تحميل وثيقة PDF
الخطوة الأولى هي تحميل مستند PDF الذي تريد تعديله. في هذا البرنامج التعليمي، سنقوم بتحميل مستند PDF باسم "input.pdf" من مجلد "YOUR DOCUMENT DIRECTORY". 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "input.pdf");
```

## الخطوة 2: البحث عن أجزاء النص
لشطب كلمات أو عبارات محددة في مستند PDF، عليك أولاً البحث عنها. يوفر Aspose.PDF فئة TextFragmentAbsorter التي يمكن استخدامها للبحث عن جزء نص معين في مستند PDF.

```csharp
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
```

في الكود أعلاه، نبحث عن جزء النص "Estoque" في مستند PDF. يمكنك تعديل هذا للبحث عن أي كلمة أو عبارة أخرى تريد شطبها.

## الخطوة 3: شطب أجزاء النص
بعد العثور على أجزاء النص، فإن الخطوة التالية هي شطبها. يوفر Aspose.PDF فئة StrikeOutAnnotation التي يمكن استخدامها لإنشاء تعليق توضيحي مشطب لجزء النص. 

```csharp
Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle((float)textFragment.Position.XIndent, (float)textFragment.Position.YIndent, (float)textFragment.Position.XIndent + (float)textFragment.Rectangle.Width, (float)textFragment.Position.YIndent + (float)textFragment.Rectangle.Height);

StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
strikeOut.Opacity = .80f;
strikeOut.Border = new Border(strikeOut);
strikeOut.Color = Aspose.Pdf.Color.Red;
textFragment.Page.Annotations.Add(strikeOut);
```

في الكود أعلاه، نقوم بإنشاء تعليق توضيحي مشطوب لكل جزء نص وجدناه. نحن نقوم بتعيين العتامة والحدود واللون للتعليق التوضيحي المشطب أيضًا.

## الخطوة 4: حفظ مستند PDF المعدل
بعد شطب أجزاء النص، قم بحفظ المستند المعدل.

```csharp
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

### مثال على التعليمات البرمجية المصدر لـ Strike Out Words باستخدام Aspose.PDF لـ .NET


```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح المستند
Document document = new Document(dataDir + "input.pdf");

// قم بإنشاء مثيل TextFragment Absorter للبحث في جزء نص معين
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
// التكرار من خلال صفحات وثيقة PDF
for (int i = 1; i <= document.Pages.Count; i++)
{
	// احصل على الصفحة الأولى من وثيقة PDF
	Page page = document.Pages[1];
	page.Accept(textFragmentAbsorber);
}

// إنشاء مجموعة من النص الممتص
Aspose.Pdf.Text.TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

//كرر على المجموعة أعلاه
for (int j = 1; j <= textFragmentCollection.Count; j++)
{
	Aspose.Pdf.Text.TextFragment textFragment = textFragmentCollection[j];

	// احصل على أبعاد مستطيلة لكائن TextFragment
	Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle(
				(float)textFragment.Position.XIndent,
				(float)textFragment.Position.YIndent,
				(float)textFragment.Position.XIndent +
				(float)textFragment.Rectangle.Width,
				(float)textFragment.Position.YIndent +
				(float)textFragment.Rectangle.Height);

	// إنشاء مثيل للتعليق التوضيحي StrikeOut
	StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
	// ضبط العتامة للتعليق التوضيحي
	strikeOut.Opacity = .80f;
	// قم بتعيين الحدود لمثيل التعليق التوضيحي
	strikeOut.Border = new Border(strikeOut);
	// ضبط لون التعليق التوضيحي
	strikeOut.Color = Aspose.Pdf.Color.Red;
	// أضف تعليقًا توضيحيًا إلى مجموعة التعليقات التوضيحية في TextFragment
	textFragment.Page.Annotations.Add(strikeOut);
}
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية استخدام Aspose.PDF لـ .NET لشطب كلمات محددة في مستند PDF. من خلال اتباع الدليل خطوة بخطوة واستخدام كود مصدر C# المتوفر، يمكنك بسهولة تحميل مستند PDF والبحث عن أجزاء نصية محددة وإنشاء تعليقات توضيحية مشطبة لوضع علامة بصرية على تلك الكلمات وشطبها. يوفر Aspose.PDF for .NET طريقة بسيطة وفعالة لمعالجة مستندات PDF برمجيًا، مما يجعله أداة قيمة للمطورين الذين يعملون مع ملفات PDF في تطبيقات .NET.

### الأسئلة الشائعة

#### س: ما هو Aspose.PDF لـ .NET؟

ج: Aspose.PDF for .NET هي مكتبة قوية تتيح للمطورين إنشاء مستندات PDF وتحريرها ومعالجتها برمجيًا في تطبيقات .NET. فهو يوفر مجموعة واسعة من الميزات للعمل مع ملفات PDF، بما في ذلك استخراج النص ومعالجة التعليقات التوضيحية وملء النماذج وغير ذلك الكثير.

#### س: هل يمكنني استخدام Aspose.PDF لـ .NET لشطب كلمات معينة في مستند PDF؟

ج: نعم، يوفر Aspose.PDF for .NET وظيفة للبحث عن أجزاء نصية محددة في مستند PDF ثم إنشاء تعليقات توضيحية مشطبة لوضع علامة مرئية على تلك الكلمات وشطبها.

#### س: كيف أحدد النص الذي أريد شطبه في مستند PDF؟

 ج: لتحديد النص الذي تريد شطبه، يمكنك استخدام`TextFragmentAbsorber` فئة مقدمة من Aspose.PDF لـ .NET. يسمح لك بالبحث عن جزء نص محدد في مستند PDF بناءً على المعايير التي تريدها.

#### س: هل يمكنني تخصيص مظهر التعليق التوضيحي المشطوب؟

ج: نعم، يمكنك تخصيص خصائص مختلفة للتعليق التوضيحي المشطب، مثل العتامة ونمط الحدود واللون. يسمح لك هذا بتخصيص مظهر التعليق التوضيحي المشطوب وفقًا لمتطلباتك المحددة.