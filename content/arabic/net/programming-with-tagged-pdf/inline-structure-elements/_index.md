---
title: عناصر البنية المضمنة
linktitle: عناصر البنية المضمنة
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: دليل خطوة بخطوة لاستخدام العناصر الهيكلية عبر الإنترنت مع Aspose.PDF لـ .NET. قم بتنظيم ملفات PDF الخاصة بك باستخدام العناوين والفقرات.
type: docs
weight: 110
url: /ar/net/programming-with-tagged-pdf/inline-structure-elements/
---
في هذا الدليل التفصيلي، سنوضح لك كيفية استخدام عناصر البنية المضمنة مع Aspose.PDF لـ .NET. Aspose.PDF هي مكتبة قوية تتيح لك التعامل مع مستندات PDF برمجيًا. تتيح لك عناصر البنية المضمنة إنشاء بنية هرمية في مستند PDF الخاص بك باستخدام عناوين بمستويات وفقرات مختلفة.

دعنا نتعمق في الكود ونتعلم كيفية استخدام عناصر البنية المضمنة مع Aspose.PDF لـ .NET.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

1. تم تثبيت مكتبة Aspose.PDF لـ .NET.
2. المعرفة الأساسية للغة البرمجة C#.

## الخطوة 1: إعداد البيئة

للبدء، افتح بيئة تطوير C# وقم بإنشاء مشروع جديد. تأكد من إضافة مرجع إلى مكتبة Aspose.PDF لـ .NET في مشروعك.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: إنشاء المستند

 الخطوة الأولى هي إنشاء مستند PDF جديد باستخدام`Document` فصل.

```csharp
// إنشاء مستند PDF
Document document = new Document();
```

## الخطوة 3: العمل مع المحتوى المُوسوم

وبعد ذلك نحصل على المحتوى المميز للمستند للعمل عليه.

```csharp
// احصل على المحتوى المميز للوثيقة
ITaggedContent taggedContent = document.TaggedContent;
```

## الخطوة 4: تعيين عنوان المستند واللغة

يمكننا الآن تعيين عنوان المستند واللغة.

```csharp
// تحديد عنوان المستند واللغة
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

## الخطوة 5: إضافة العناصر الهيكلية عبر الإنترنت

سنقوم الآن بإضافة عناصر هيكلية مضمنة مثل عناوين المستويات المختلفة والفقرات إلى مستندنا.

```csharp
// الحصول على عنصر البنية الجذرية
StructureElement rootElement = taggedContent.RootElement;

// إضافة رؤوس مستويات مختلفة
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);

// إضافة محتوى إلى كل رأس
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1.");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 header");
h1.AppendChild(spanH12);

SpanElement spanH21 = taggedContent.CreateSpanElement();
spanH21.SetText("H2.");
h2.AppendChild(spanH21);
SpanElement spanH22 = taggedContent.CreateSpanElement();
spanH22.SetText("Level 2 header");
h2.AppendChild(spanH22);

SpanElement spanH31 = taggedContent.CreateSpanElement();
spanH31.SetText("H3.");
h3.AppendChild(spanH31);
SpanElement spanH32 = taggedContent.CreateSpanElement();
spanH32.SetText("Level 3 header");
h3.AppendChild(spanH32);

SpanElement spanH41 = taggedContent.CreateSpanElement();
spanH41.SetText("H4.");
h4.AppendChild(spanH41);
SpanElement spanH42 = taggedContent.CreateSpanElement();
spanH42.SetText("Level 4 header");
h4.AppendChild(spanH42);

SpanElement spanH51 = taggedContent.CreateSpanElement();
spanH51.SetText("H5.");
h5.AppendChild(spanH51);
SpanElement spanH52 = taggedContent.CreateSpanElement();
spanH52.SetText("Level 5 header");
h5.AppendChild(spanH52);

SpanElement spanH61 = taggedContent.CreateSpanElement();
spanH61.SetText("H6.");
h6.AppendChild(spanH61);
SpanElement spanH62 = taggedContent.CreateSpanElement();
spanH62.SetText("Heading level 6");
h6.AppendChild(spanH62);

// أضف فقرة
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P.");
rootElement.AppendChild(p);

// إضافة محتوى إلى الفقرة
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit.");
p.AppendChild(span1);
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Aenean nec lectus ac sem faucibus imperdiet.");
p.AppendChild(span2);
SpanElement span3 = taggedContent.CreateSpanElement();
span3.SetText("Sed ut erat ac magna ullamcorper hendrerit.");
p.AppendChild(span3);
SpanElement span4 = taggedContent.CreateSpanElement();
span4.SetText("Cras pellentesque libero semper, gravida magna sed, luctus leo.");
p.AppendChild(span4);
SpanElement span5 = taggedContent.CreateSpanElement();
span5.SetText("Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit.");
p.AppendChild(span5);
SpanElement span6 = taggedContent.CreateSpanElement();
span6.SetText("Interdum et malesuada fames ac ante ipsum primis in faucibus. ");
p.AppendChild(span6);
SpanElement span7 = taggedContent.CreateSpanElement();
span7.SetText("Aliquam lacinia sit amet elit ac consectetur. So cursus condimentum ligula, vitae volutpat sem tristique eget. ");
p.AppendChild(span7);
SpanElement span8 = taggedContent.CreateSpanElement();
span8.SetText("Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. ");
p.AppendChild(span8);
SpanElement span9 = taggedContent.CreateSpanElement();
span9.SetText("Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit.");
p.AppendChild(span9);
SpanElement span10 = taggedContent.CreateSpanElement();
span10.SetText("Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
p.AppendChild(span10);
```

هنا نقوم بإنشاء عناصر هيكلية مضمنة، مثل عناوين المستويات المختلفة والفقرة، ونضيف المحتوى إليها.

## الخطوة 6: احفظ مستند PDF المُوسوم

وأخيرًا، نحفظ مستند PDF المُوسوم.

```csharp
// احفظ مستند PDF المُوسوم
document.Save(dataDir + "InlineStructureElements.pdf");
```

### عينة من كود المصدر لعناصر البنية المضمنة باستخدام Aspose.PDF لـ .NET 

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء مستند PDF
Document document = new Document();

// احصل على محتوى للعمل باستخدام TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;

// تعيين العنوان واللغة لـDocumnet
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");

// الحصول على عنصر البنية الجذرية
StructureElement rootElement = taggedContent.RootElement;
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1. ");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 Header");
h1.AppendChild(spanH12);
SpanElement spanH21 = taggedContent.CreateSpanElement();
spanH21.SetText("H2. ");
h2.AppendChild(spanH21);
SpanElement spanH22 = taggedContent.CreateSpanElement();
spanH22.SetText("Level 2 Header");
h2.AppendChild(spanH22);
SpanElement spanH31 = taggedContent.CreateSpanElement();
spanH31.SetText("H3. ");
h3.AppendChild(spanH31);
SpanElement spanH32 = taggedContent.CreateSpanElement();
spanH32.SetText("Level 3 Header");
h3.AppendChild(spanH32);
SpanElement spanH41 = taggedContent.CreateSpanElement();
spanH41.SetText("H4. ");
h4.AppendChild(spanH41);
SpanElement spanH42 = taggedContent.CreateSpanElement();
spanH42.SetText("Level 4 Header");
h4.AppendChild(spanH42);
SpanElement spanH51 = taggedContent.CreateSpanElement();
spanH51.SetText("H5. ");
h5.AppendChild(spanH51);
SpanElement spanH52 = taggedContent.CreateSpanElement();
spanH52.SetText("Level 5 Header");
h5.AppendChild(spanH52);
SpanElement spanH61 = taggedContent.CreateSpanElement();
spanH61.SetText("H6. ");
h6.AppendChild(spanH61);
SpanElement spanH62 = taggedContent.CreateSpanElement();
spanH62.SetText("Level 6 Header");
h6.AppendChild(spanH62);
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P. ");
rootElement.AppendChild(p);
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit. ");
p.AppendChild(span1);
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Aenean nec lectus ac sem faucibus imperdiet. ");
p.AppendChild(span2);
SpanElement span3 = taggedContent.CreateSpanElement();
span3.SetText("Sed ut erat ac magna ullamcorper hendrerit. ");
p.AppendChild(span3);
SpanElement span4 = taggedContent.CreateSpanElement();
span4.SetText("Cras pellentesque libero semper, gravida magna sed, luctus leo. ");
p.AppendChild(span4);
SpanElement span5 = taggedContent.CreateSpanElement();
span5.SetText("Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit. ");
p.AppendChild(span5);
SpanElement span6 = taggedContent.CreateSpanElement();
span6.SetText("Interdum et malesuada fames ac ante ipsum primis in faucibus. ");
p.AppendChild(span6);
SpanElement span7 = taggedContent.CreateSpanElement();
span7.SetText("Aliquam lacinia sit amet elit ac consectetur. Donec cursus condimentum ligula, vitae volutpat sem tristique eget. ");
p.AppendChild(span7);
SpanElement span8 = taggedContent.CreateSpanElement();
span8.SetText("Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. ");
p.AppendChild(span8);
SpanElement span9 = taggedContent.CreateSpanElement();
span9.SetText("Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit. ");
p.AppendChild(span9);
SpanElement span10 = taggedContent.CreateSpanElement();
span10.SetText("Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
p.AppendChild(span10);

// حفظ مستند PDF المُوسوم
document.Save(dataDir + "InlineStructureElements.pdf");

```

## خاتمة

تهانينا! لقد تعلمت كيفية استخدام عناصر البنية المضمنة مع Aspose.PDF لـ .NET. يمكنك الآن إنشاء بنية هرمية في مستند PDF الخاص بك باستخدام عناوين بمستويات وفقرات مختلفة. استكشف المزيد من ميزات Aspose.PDF لاكتشاف إمكاناته الكاملة.

### الأسئلة الشائعة

#### س: ما هي عناصر البنية المضمنة في مستند PDF، وكيف تساهم في إنشاء بنية هرمية؟

أ: تُستخدم عناصر البنية المضمنة في مستند PDF، مثل عناوين المستويات والفقرات المختلفة، لإنشاء بنية هرمية تنظم المحتوى وتعرضه بطريقة منظمة. تتيح لك هذه العناصر إنشاء تسلسل هرمي واضح وتدفق للمعلومات داخل المستند.

#### س: كيف يمكن لعناصر البنية المضمنة تعزيز قابلية القراءة وتنظيم مستند PDF؟

أ: تساعد عناصر البنية المضمنة، وخاصة العناوين والفقرات، على تحسين قابلية القراءة وتنظيم مستند PDF من خلال توفير بنية منطقية. تشير العناوين إلى مستويات مختلفة من الأهمية وتساعد القراء على التنقل عبر المحتوى، بينما تجمع الفقرات المعلومات ذات الصلة معًا.

#### س: كيف يسهل Aspose.PDF لـ .NET استخدام عناصر البنية المضمنة؟

ج: يوفر Aspose.PDF for .NET فئات وطرقًا لإنشاء عناصر بنية مضمنة ومعالجتها، مثل العناوين والفقرات. ويمكن تخصيص هذه العناصر وتنظيمها هرميًا وإثرائها بالمحتوى لتحسين العرض المرئي وإمكانية الوصول إلى المستند.

####  س: ما هو الغرض من`taggedContent` object in relation to inline structure elements?

 أ: ال`taggedContent` الشيء الذي تم الحصول عليه من`TaggedContent` ممتلكات شخص ما`Document`يتيح لك العمل مع العناصر المنظمة، بما في ذلك عناصر البنية المضمنة. كما يتيح لك إنشاء العناوين والفقرات وتخصيصها وتنظيمها داخل المستند.

#### س: كيف تساعد عناصر البنية المضمنة في إنشاء تسلسل هرمي واضح للمستندات؟

أ: تساهم عناصر البنية المضمنة، مثل العناوين ذات المستويات المختلفة، في إنشاء تسلسل هرمي واضح ومحدد جيدًا في المستند. ويمكن للقراء تحديد الموضوعات الرئيسية والموضوعات الفرعية والمحتوى ذي الصلة بسرعة، مما يجعل المستند أسهل في التنقل والفهم.

#### س: هل يمكنني تخصيص مظهر وتنسيق عناصر البنية المضمنة باستخدام Aspose.PDF لـ .NET؟

ج: نعم، يمكنك تخصيص مظهر وتنسيق عناصر البنية المضمنة. يمكنك تعيين خصائص مثل أنماط الخطوط وأحجامها وألوانها ومحاذاة الخطوط والمسافة البادئة والتباعد لتحقيق العرض المرئي المطلوب للعناوين والفقرات.

#### س: كيف أقوم بإنشاء وإضافة عناوين بمستويات مختلفة إلى مستند PDF باستخدام عناصر البنية المضمنة في Aspose.PDF لـ .NET؟

 أ: يمكنك إنشاء عناوين بمستويات مختلفة باستخدام`CreateHeaderElement` الطريقة ثم قم بإضافتها إلى عنصر البنية الجذرية. بعد ذلك، يمكنك إضافة محتوى إلى كل عنصر عنوان باستخدام`CreateSpanElement` طريقة لإنشاء فترات من النص.

#### س: هل يمكنني استخدام عناصر البنية المضمنة لإنشاء قوائم أو نقاط أو أنواع أخرى من تنظيم المحتوى في مستند PDF؟

ج: على الرغم من أن عناصر البنية المضمنة تُستخدم في المقام الأول للعناوين والفقرات، إلا أنه يمكنك استخدامها مع ميزات أخرى يوفرها Aspose.PDF لـ .NET لإنشاء قوائم ونقاط وجداول وأنواع أخرى من تنظيم المحتوى للحصول على بنية مستند شاملة.

#### س: كيف تساهم عناصر البنية المضمنة في إمكانية الوصول إلى المستندات؟

أ: تلعب عناصر البنية المضمنة دورًا حاسمًا في تحسين إمكانية الوصول إلى المستندات. توفر العناوين والفقرات المنظمة بشكل صحيح تسلسلًا هرميًا واضحًا للمستندات يساعد برامج قراءة الشاشة وغيرها من التقنيات المساعدة في تفسير المحتوى ونقله بدقة للمستخدمين ذوي الإعاقة.

#### س: هل يمكنني استكشاف استخدامات أكثر تقدمًا لعناصر البنية المضمنة، مثل إنشاء عناصر تفاعلية أو تضمين الوسائط المتعددة؟

ج: بالتأكيد! في حين يركز هذا البرنامج التعليمي على إنشاء العناوين والفقرات، يوفر Aspose.PDF for .NET ميزات متقدمة لإنشاء عناصر تفاعلية، وتضمين الوسائط المتعددة، وإضافة ارتباطات تشعبية، والمزيد. راجع وثائق المكتبة وأمثلتها للتعمق في هذه القدرات المتقدمة.