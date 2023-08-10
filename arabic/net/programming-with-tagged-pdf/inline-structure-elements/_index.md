---
title: عناصر الهيكل المضمنة
linktitle: عناصر الهيكل المضمنة
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لاستخدام العناصر الهيكلية عبر الإنترنت مع Aspose.PDF for .NET. قم بتنظيم ملفات PDF الخاصة بك باستخدام العناوين والفقرات.
type: docs
weight: 110
url: /ar/net/programming-with-tagged-pdf/inline-structure-elements/
---
في هذا الدليل المفصل خطوة بخطوة ، سنوضح لك كيفية استخدام عناصر البنية المضمنة مع Aspose.PDF for .NET. Aspose.PDF هي مكتبة قوية تتيح لك معالجة مستندات PDF برمجيًا. تسمح لك عناصر البنية المضمنة بإنشاء هيكل هرمي في مستند PDF الخاص بك باستخدام عناوين من مستويات وفقرات مختلفة.

دعنا نتعمق في الكود ونتعلم كيفية استخدام عناصر البنية المضمنة مع Aspose.PDF for .NET.

## المتطلبات الأساسية

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

1. تثبيت مكتبة Aspose.PDF لـ .NET.
2. معرفة أساسية بلغة البرمجة C #.

## الخطوة الأولى: تهيئة البيئة

للبدء ، افتح بيئة التطوير C # وأنشئ مشروعًا جديدًا. تأكد من إضافة مرجع إلى مكتبة Aspose.PDF لـ .NET في مشروعك.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: إنشاء المستند

 تتمثل الخطوة الأولى في إنشاء مستند PDF جديد باستخدام امتداد`Document` فصل.

```csharp
// قم بإنشاء مستند PDF
Document document = new Document();
```

## الخطوة 3: العمل مع المحتوى الذي تم وضع علامة عليه

ثم نحصل على محتوى المستند الذي تم وضع علامة عليه للعمل معه.

```csharp
// احصل على محتوى المستند بعلامات
ITaggedContent taggedContent = document.TaggedContent;
```

## الخطوة 4: حدد عنوان المستند ولغته

يمكننا الآن تعيين عنوان المستند ولغته.

```csharp
// حدد عنوان المستند ولغته
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

## الخطوة 5: أضف العناصر الهيكلية عبر الإنترنت

سنقوم الآن بإضافة عناصر هيكل مضمنة مثل عناوين المستويات والفقرات المختلفة إلى وثيقتنا.

```csharp
// احصل على عنصر بنية الجذر
StructureElement rootElement = taggedContent.RootElement;

// أضف رؤوس من مستويات مختلفة
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

// أضف محتوى إلى كل رأس
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

// أضف محتوى إلى الفقرة
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

هنا نقوم بإنشاء عناصر هيكل مضمنة ، مثل عناوين المستويات المختلفة والفقرة ، وإضافة محتوى إليها.

## الخطوة 6: احفظ مستند PDF الذي تم وضع علامة عليه

أخيرًا ، نقوم بحفظ مستند PDF الموسوم.

```csharp
// احفظ مستند PDF بعلامات
document.Save(dataDir + "InlineStructureElements.pdf");
```

### نموذج التعليمات البرمجية المصدر لعناصر البنية المضمنة باستخدام Aspose.PDF لـ .NET 

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// قم بإنشاء مستند PDF
Document document = new Document();

// الحصول على محتوى للعمل مع TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;

// تعيين العنوان واللغة للوثيقة
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");

// احصل على عنصر بنية الجذر
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

// حفظ وثيقة PDF الموسومة
document.Save(dataDir + "InlineStructureElements.pdf");

```

## خاتمة

تهنئة ! لقد تعلمت كيفية استخدام عناصر البنية المضمنة مع Aspose.PDF for .NET. يمكنك الآن إنشاء هيكل هرمي في مستند PDF الخاص بك باستخدام عناوين من مستويات وفقرات مختلفة. اكتشف المزيد من ميزات Aspose.PDF لاكتشاف إمكاناتها الكاملة.

### التعليمات

#### س: ما هي عناصر البنية المضمنة في مستند PDF ، وكيف تساهم في إنشاء هيكل هرمي؟

ج: تُستخدم عناصر البنية المضمنة في مستند PDF ، مثل عناوين المستويات والفقرات المختلفة ، لإنشاء هيكل هرمي ينظم المحتوى ويعرضه بطريقة منظمة. تسمح لك هذه العناصر بإنشاء تسلسل هرمي واضح وتدفق المعلومات داخل المستند.

#### س: كيف يمكن لعناصر الهيكل المضمنة تحسين سهولة القراءة وتنظيم مستند PDF؟

ج: تساعد عناصر البنية المضمنة ، خاصة العناوين والفقرات ، على تحسين قابلية القراءة وتنظيم مستند PDF من خلال توفير بنية منطقية. تشير العناوين إلى مستويات مختلفة من الأهمية وتساعد القراء على التنقل في المحتوى ، بينما تقوم الفقرات بتجميع المعلومات ذات الصلة معًا.

#### س: كيف يسهل Aspose.PDF for .NET استخدام عناصر البنية المضمنة؟

ج: يقدم Aspose.PDF for .NET فئات وطرق لإنشاء عناصر بنية مضمنة ومعالجتها ، مثل العناوين والفقرات. يمكن تخصيص هذه العناصر وتنظيمها بشكل هرمي وإثرائها بالمحتوى لتحسين العرض المرئي وإمكانية الوصول إلى المستند.

####  س: ما هو الغرض من`taggedContent` object in relation to inline structure elements?

 ج: إن`taggedContent` تم الحصول عليها من`TaggedContent` ممتلكات أ`Document`، يسمح لك بالعمل مع العناصر المهيكلة ، بما في ذلك عناصر البنية المضمنة. يمكّنك من إنشاء العناوين والفقرات وتخصيصها وتنظيمها داخل المستند.

#### س: كيف تساعد عناصر البنية المضمنة في إنشاء تسلسل هرمي واضح للمستند؟

ج: تساهم عناصر البنية المضمنة ، مثل العناوين ذات المستويات المختلفة ، في إنشاء تسلسل هرمي واضح ومحدد جيدًا في المستند. يمكن للقراء التعرف بسرعة على الموضوعات الرئيسية والموضوعات الفرعية والمحتوى ذي الصلة ، مما يسهل التنقل في المستند وفهمه.

#### س: هل يمكنني تخصيص مظهر وتنسيق عناصر البنية المضمنة باستخدام Aspose.PDF for .NET؟

ج: نعم ، يمكنك تخصيص مظهر وتنسيق عناصر البنية المضمنة. يمكنك تعيين خصائص مثل أنماط الخطوط والأحجام والألوان والمحاذاة والمسافة البادئة والتباعد لتحقيق العرض التقديمي المرئي المطلوب للعناوين والفقرات.

#### س: كيف يمكنني إنشاء وإضافة عناوين بمستويات مختلفة إلى مستند PDF باستخدام عناصر بنية مضمنة في Aspose.PDF لـ .NET؟

 ج: يمكنك إنشاء عناوين لمستويات مختلفة باستخدام`CreateHeaderElement` طريقة ثم إلحاقها بعنصر بنية الجذر. بعد ذلك ، يمكنك إضافة محتوى إلى كل عنصر عنوان باستخدام`CreateSpanElement` طريقة لإنشاء مساحات من النص.

#### س: هل يمكنني استخدام عناصر البنية المضمنة لإنشاء قوائم أو نقاط نقطية أو أنواع أخرى من تنظيم المحتوى في مستند PDF؟

ج: بينما تُستخدم عناصر البنية المضمنة نفسها بشكل أساسي للعناوين والفقرات ، يمكنك استخدامها جنبًا إلى جنب مع الميزات الأخرى التي يوفرها Aspose.PDF لـ .NET لإنشاء قوائم ونقاط نقطية وجداول وأنواع أخرى من تنظيم المحتوى لتحقيق شامل هيكل الوثيقة.

#### س: كيف تساهم عناصر البنية المضمنة في إمكانية الوصول إلى المستندات؟

ج: تلعب عناصر البنية المضمنة دورًا مهمًا في تعزيز إمكانية الوصول إلى المستندات. توفر العناوين والفقرات المهيكلة بشكل صحيح تسلسلاً هرميًا واضحًا للوثائق يساعد برامج قراءة الشاشة والتقنيات المساعدة الأخرى في تفسير المحتوى ونقله بدقة إلى المستخدمين ذوي الإعاقة.

#### س: هل يمكنني استكشاف استخدامات أكثر تقدمًا لعناصر البنية المضمنة ، مثل إنشاء عناصر تفاعلية أو تضمين وسائط متعددة؟

ج: إطلاقا! بينما يركز هذا البرنامج التعليمي على إنشاء العناوين والفقرات ، يقدم Aspose.PDF for .NET ميزات متقدمة لإنشاء عناصر تفاعلية وتضمين الوسائط المتعددة وإضافة ارتباطات تشعبية والمزيد. تحقق من وثائق وأمثلة المكتبة للتعمق في هذه القدرات المتقدمة.