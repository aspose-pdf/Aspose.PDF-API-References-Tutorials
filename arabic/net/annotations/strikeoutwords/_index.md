---
title: شطب الكلمات
linktitle: شطب الكلمات
second_title: Aspose.PDF لمرجع .NET API
description: تقدم هذه المقالة دليلاً مفصلاً خطوة بخطوة لاستخدام ميزة Aspose.PDF لـ .NET's Strike Out Words ، بما في ذلك دليل خطوة بخطوة وشروحات
type: docs
weight: 150
url: /ar/net/annotations/strikeoutwords/
---
Aspose.PDF for .NET هي مكتبة لمعالجة مستندات PDF ومعالجتها توفر ميزات متنوعة لإنشاء ملفات PDF وتعديلها وتحويلها. إحدى الميزات المفيدة التي يوفرها Aspose.PDF هي القدرة على شطب الكلمات أو العبارات في مستند PDF باستخدام الكود المصدري C #. في هذه المقالة ، سوف نقدم دليلًا تفصيليًا حول كيفية كتابة الكلمات باستخدام Aspose.PDF لـ .NET.

## الخطوة 1: تحميل مستند PDF
الخطوة الأولى هي تحميل مستند PDF الذي تريد تعديله. في هذا البرنامج التعليمي ، سنقوم بتحميل مستند PDF باسم "input.pdf" من مجلد "YOUR DOCUMENT DIRECTORY". 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "input.pdf");
```

## الخطوة 2: البحث عن أجزاء النص
لشطب كلمات أو عبارات معينة في مستند PDF ، تحتاج أولاً إلى البحث عنها. يوفر Aspose.PDF فئة TextFragmentAbsorber التي يمكن استخدامها للبحث عن جزء نص معين في مستند PDF.

```csharp
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
```

في الكود أعلاه ، نبحث عن جزء النص "Estoque" في مستند PDF. يمكنك تعديل هذا للبحث عن أي كلمة أو عبارة أخرى تريد حذفها.

## الخطوة 3: شطب أجزاء النص
بعد العثور على أجزاء النص ، فإن الخطوة التالية هي شطبها. يوفر Aspose.PDF فئة StrikeOutAnnotation التي يمكن استخدامها لإنشاء تعليق توضيحي مشطوب لجزء النص. 

```csharp
Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle((float)textFragment.Position.XIndent, (float)textFragment.Position.YIndent, (float)textFragment.Position.XIndent + (float)textFragment.Rectangle.Width, (float)textFragment.Position.YIndent + (float)textFragment.Rectangle.Height);

StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
strikeOut.Opacity = .80f;
strikeOut.Border = new Border(strikeOut);
strikeOut.Color = Aspose.Pdf.Color.Red;
textFragment.Page.Annotations.Add(strikeOut);
```

في الكود أعلاه ، نقوم بإنشاء تعليق توضيحي مشطوب لكل جزء نص وجدناه. نحن أيضًا نضع التعتيم والحدود ولون التعليق التوضيحي المشطوب.

## الخطوة 4: حفظ مستند PDF المعدل
بعد شطب أجزاء النص ، احفظ المستند المعدل.

```csharp
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

### مثال على شفرة المصدر لـ Strike Out Words باستخدام Aspose.PDF لـ .NET


```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح المستند
Document document = new Document(dataDir + "input.pdf");

// إنشاء مثيل TextFragment Absorber للبحث في جزء نص معين
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
// كرر خلال صفحات مستند PDF
for (int i = 1; i <= document.Pages.Count; i++)
{
	// احصل على الصفحة الأولى من مستند PDF
	Page page = document.Pages[1];
	page.Accept(textFragmentAbsorber);
}

// قم بإنشاء مجموعة من النص الذي تم امتصاصه
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

	// إنشاء مثيل StrikeOut Annotation
	StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
	// ضبط التعتيم على التعليق التوضيحي
	strikeOut.Opacity = .80f;
	// عيّن الحد لمثيل التعليق التوضيحي
	strikeOut.Border = new Border(strikeOut);
	// اضبط لون التعليق التوضيحي
	strikeOut.Color = Aspose.Pdf.Color.Red;
	// أضف تعليقًا توضيحيًا إلى مجموعة التعليقات التوضيحية الخاصة بـ TextFragment
	textFragment.Page.Annotations.Add(strikeOut);
}
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية استخدام Aspose.PDF لـ .NET لشطب كلمات معينة في مستند PDF. باتباع الدليل خطوة بخطوة واستخدام الكود المصدري C # المقدم ، يمكنك بسهولة تحميل مستند PDF ، والبحث عن أجزاء نصية محددة ، وإنشاء تعليقات توضيحية مشطوفة لتمييز هذه الكلمات بصريًا وشطبها. يوفر Aspose.PDF for .NET طريقة بسيطة وفعالة لمعالجة مستندات PDF برمجيًا ، مما يجعلها أداة قيمة للمطورين الذين يعملون مع ملفات PDF في تطبيقات .NET.

### التعليمات

#### س: ما هو Aspose.PDF لـ .NET؟

ج: Aspose.PDF for .NET مكتبة قوية تتيح للمطورين إنشاء مستندات PDF وتحريرها ومعالجتها برمجيًا في تطبيقات .NET. يوفر مجموعة واسعة من الميزات للعمل مع ملفات PDF ، بما في ذلك استخراج النص ومعالجة التعليقات التوضيحية وملء النماذج وغير ذلك الكثير.

#### س: هل يمكنني استخدام Aspose.PDF for .NET لشطب كلمات معينة في مستند PDF؟

ج: نعم ، يوفر Aspose.PDF for .NET وظائف للبحث عن أجزاء نصية محددة في مستند PDF ثم إنشاء تعليقات توضيحية لتعليم تلك الكلمات بصريًا وشطبها.

#### س: كيف أحدد النص الذي أرغب في شطبه في مستند PDF؟

 ج: لتحديد النص الذي تريد حذفه ، يمكنك استخدام`TextFragmentAbsorber` فئة مقدمة من Aspose.PDF لـ .NET. يسمح لك بالبحث عن جزء نصي معين في مستند PDF بناءً على المعايير التي تريدها.

#### س: هل يمكنني تخصيص مظهر التعليق التوضيحي المشطوب؟

ج: نعم ، يمكنك تخصيص خصائص متنوعة للتعليق التوضيحي المشطوب ، مثل التعتيم ونمط الحد واللون. يتيح لك ذلك تخصيص مظهر التعليق التوضيحي المشطوب وفقًا لمتطلباتك المحددة.