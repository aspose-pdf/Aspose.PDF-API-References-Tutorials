---
title: عناصر الهيكل المضمنة
linktitle: عناصر الهيكل المضمنة
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لاستخدام العناصر الهيكلية عبر الإنترنت مع Aspose.PDF لـ .NET. قم بتنظيم ملفات PDF الخاصة بك بالعناوين والفقرات.
type: docs
weight: 110
url: /ar/net/programming-with-tagged-pdf/inline-structure-elements/
---
في هذا الدليل خطوة بخطوة، سنوضح لك كيفية استخدام عناصر البنية المضمنة مع Aspose.PDF لـ .NET. Aspose.PDF هي مكتبة قوية تتيح لك التعامل مع مستندات PDF برمجياً. تتيح لك عناصر البنية المضمنة إنشاء بنية هرمية في مستند PDF الخاص بك باستخدام عناوين ذات مستويات وفقرات مختلفة.

دعنا نتعمق في التعليمات البرمجية ونتعلم كيفية استخدام عناصر البنية المضمنة مع Aspose.PDF لـ .NET.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

1. تم تثبيت مكتبة Aspose.PDF لـ .NET.
2. معرفة أساسية بلغة البرمجة C#.

## الخطوة 1: تهيئة البيئة

للبدء، افتح بيئة تطوير C# الخاصة بك وقم بإنشاء مشروع جديد. تأكد من إضافة مرجع إلى مكتبة Aspose.PDF لـ .NET في مشروعك.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: إنشاء الوثيقة

 الخطوة الأولى هي إنشاء مستند PDF جديد باستخدام الملف`Document` فصل.

```csharp
// قم بإنشاء مستند PDF
Document document = new Document();
```

## الخطوة 3: العمل مع المحتوى الموسوم

ثم نحصل على المحتوى المميز للمستند للعمل معه.

```csharp
// احصل على المحتوى المميز للمستند
ITaggedContent taggedContent = document.TaggedContent;
```

## الخطوة 4: تعيين عنوان المستند واللغة

يمكننا الآن تعيين عنوان المستند واللغة.

```csharp
// تحديد عنوان الوثيقة واللغة
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

## الخطوة 5: إضافة العناصر الهيكلية عبر الإنترنت

سنقوم الآن بإضافة عناصر هيكلية مضمنة مثل عناوين المستويات والفقرات المختلفة إلى وثيقتنا.

```csharp
// الحصول على عنصر هيكل الجذر
StructureElement rootElement = taggedContent.RootElement;

// إضافة رؤوس من مستويات مختلفة
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

نقوم هنا بإنشاء عناصر هيكلية مضمنة، مثل العناوين ذات المستويات المختلفة والفقرة، وإضافة محتوى إليها.

## الخطوة 6: احفظ مستند PDF الذي تم وضع علامة عليه

وأخيرًا، نقوم بحفظ مستند PDF الذي تم وضع علامة عليه.

```csharp
// احفظ مستند PDF الذي تم وضع علامة عليه
document.Save(dataDir + "InlineStructureElements.pdf");
```

### نموذج التعليمات البرمجية المصدر لعناصر البنية المضمنة باستخدام Aspose.PDF لـ .NET 

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء مستند PDF
Document document = new Document();

// احصل على محتوى للعمل مع TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;

// قم بتعيين العنوان واللغة لـ Documnet
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");

// احصل على عنصر البنية الجذرية
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

// حفظ وثيقة PDF ذات العلامات
document.Save(dataDir + "InlineStructureElements.pdf");

```

## خاتمة

تهنئة ! لقد تعلمت كيفية استخدام عناصر البنية المضمنة مع Aspose.PDF لـ .NET. يمكنك الآن إنشاء هيكل هرمي في مستند PDF الخاص بك باستخدام عناوين ذات مستويات وفقرات مختلفة. اكتشف المزيد من ميزات Aspose.PDF لاكتشاف إمكاناته الكاملة.

### الأسئلة الشائعة

#### س: ما هي عناصر البنية المضمنة في مستند PDF، وكيف تساهم في إنشاء هيكل هرمي؟

ج: يتم استخدام عناصر البنية المضمنة في مستند PDF، مثل عناوين المستويات والفقرات المختلفة، لإنشاء بنية هرمية تنظم المحتوى وتقدمه بطريقة منظمة. تسمح لك هذه العناصر بإنشاء تسلسل هرمي واضح وتدفق للمعلومات داخل المستند.

#### س: كيف يمكن لعناصر البنية المضمنة تحسين إمكانية قراءة مستند PDF وتنظيمه؟

ج: تساعد عناصر البنية المضمنة، خاصة العناوين والفقرات، على تحسين إمكانية قراءة مستند PDF وتنظيمه من خلال توفير بنية منطقية. تشير العناوين إلى مستويات مختلفة من الأهمية وتساعد القراء على التنقل في المحتوى، بينما تقوم الفقرات بتجميع المعلومات ذات الصلة معًا.

#### س: كيف يسهل Aspose.PDF for .NET استخدام عناصر البنية المضمنة؟

ج: يوفر Aspose.PDF for .NET فئات وطرق لإنشاء عناصر البنية المضمنة ومعالجتها، مثل العناوين والفقرات. يمكن تخصيص هذه العناصر وتنظيمها بشكل هرمي وإثرائها بالمحتوى لتحسين العرض المرئي وإمكانية الوصول إلى المستند.

####  س: ما هو الغرض من`taggedContent` object in relation to inline structure elements?

 ج: ال`taggedContent` الكائن الذي تم الحصول عليه من`TaggedContent` خاصية أ`Document`، يسمح لك بالعمل مع العناصر المنظمة، بما في ذلك عناصر البنية المضمنة. فهو يمكّنك من إنشاء وتخصيص وتنظيم العناوين والفقرات داخل المستند.

#### س: كيف تساعد عناصر البنية المضمنة في إنشاء تسلسل هرمي واضح للمستند؟

ج: تساهم عناصر البنية المضمنة، مثل العناوين ذات المستويات المختلفة، في إنشاء تسلسل هرمي واضح ومحدد جيدًا في المستند. يمكن للقراء التعرف بسرعة على الموضوعات الرئيسية والمواضيع الفرعية والمحتوى ذي الصلة، مما يجعل التنقل في المستند وفهمه أسهل.

#### س: هل يمكنني تخصيص مظهر وتنسيق عناصر البنية المضمنة باستخدام Aspose.PDF لـ .NET؟

ج: نعم، يمكنك تخصيص مظهر وتنسيق عناصر البنية المضمنة. يمكنك تعيين خصائص مثل أنماط الخطوط وأحجامها وألوانها والمحاذاة والمسافات البادئة والتباعد لتحقيق العرض المرئي المطلوب للعناوين والفقرات.

#### س: كيف يمكنني إنشاء وإضافة عناوين ذات مستويات مختلفة إلى مستند PDF باستخدام عناصر البنية المضمنة في Aspose.PDF لـ .NET؟

 ج: يمكنك إنشاء عناوين بمستويات مختلفة باستخدام`CreateHeaderElement` الطريقة ثم قم بإلحاقها بعنصر البنية الجذرية. وبعد ذلك، يمكنك إضافة محتوى إلى كل عنصر عنوان باستخدام الملف`CreateSpanElement` طريقة إنشاء مساحات من النص.

#### س: هل يمكنني استخدام عناصر البنية المضمنة لإنشاء قوائم أو نقاط أو أنواع أخرى من تنظيم المحتوى في مستند PDF؟

ج: على الرغم من أن عناصر البنية المضمنة نفسها تُستخدم بشكل أساسي للعناوين والفقرات، إلا أنه يمكنك استخدامها مع الميزات الأخرى التي يقدمها Aspose.PDF لـ .NET لإنشاء قوائم ونقاط نقطية وجداول وأنواع أخرى من تنظيم المحتوى من أجل تنظيم شامل هيكل الوثيقة.

#### س: كيف تساهم عناصر البنية المضمنة في إمكانية الوصول إلى المستند؟

ج: تلعب عناصر البنية المضمنة دورًا حاسمًا في تعزيز إمكانية الوصول إلى المستندات. توفر العناوين والفقرات المنظمة بشكل صحيح تسلسلاً هرميًا واضحًا للمستندات يساعد برامج قراءة الشاشة والتقنيات المساعدة الأخرى في تفسير المحتوى ونقله بدقة إلى المستخدمين ذوي الإعاقة.

#### س: هل يمكنني استكشاف المزيد من الاستخدامات المتقدمة لعناصر البنية المضمنة، مثل إنشاء عناصر تفاعلية أو تضمين الوسائط المتعددة؟

ج: بالتأكيد! بينما يركز هذا البرنامج التعليمي على إنشاء العناوين والفقرات، يقدم Aspose.PDF for .NET ميزات متقدمة لإنشاء عناصر تفاعلية وتضمين الوسائط المتعددة وإضافة ارتباطات تشعبية والمزيد. تحقق من وثائق المكتبة وأمثلتها للتعمق في هذه الإمكانات المتقدمة.