---
title: عناصر هيكل كتلة النص
linktitle: عناصر هيكل كتلة النص
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استخدام Aspose.PDF لـ .NET لإضافة عناصر بنية كتلة النص، مثل العناوين والفقرات ذات العلامات، إلى مستند PDF موجود.
type: docs
weight: 220
url: /ar/net/programming-with-tagged-pdf/text-block-structure-elements/
---
في هذا البرنامج التعليمي التفصيلي، سنرشدك عبر كود مصدر C# المقدم خطوة بخطوة لإنشاء عناصر بنية كتلة النص في مستند PDF ذي علامات باستخدام Aspose.PDF لـ .NET. اتبع الإرشادات أدناه لفهم كيفية إضافة عناوين متعددة المستويات والفقرات ذات العلامات إلى مستند PDF الخاص بك.

## الخطوة 1: تهيئة البيئة

قبل أن تبدأ، تأكد من تكوين بيئة التطوير الخاصة بك لاستخدام Aspose.PDF لـ .NET. يتضمن ذلك تثبيت مكتبة Aspose.PDF وتكوين مشروعك للرجوع إليه.

## الخطوة 2: إنشاء وثيقة PDF

في هذه الخطوة، سنقوم بإنشاء كائن مستند PDF جديد باستخدام Aspose.PDF.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بإنشاء مستند PDF
Document document = new Document();
```

لقد قمنا بإنشاء مستند PDF جديد باستخدام Aspose.PDF.

## الخطوة 3: احصل على المحتوى الموسوم وقم بتعيين العنوان واللغة

الآن دعنا نحصل على المحتوى المميز لمستند PDF ونقوم بتعيين عنوان المستند ولغته.

```csharp
// الحصول على المحتوى الموسومة
ITaggedContent taggedContent = document.TaggedContent;

// تحديد عنوان الوثيقة واللغة
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

لقد قمنا بتعيين عنوان ولغة مستند PDF الذي تم وضع علامة عليه.

## الخطوة 4: الحصول على عنصر البنية الجذرية

الآن دعنا نحصل على عنصر البنية الجذرية لمستند PDF.

```csharp
//الحصول على عنصر البنية الجذرية
StructureElement rootElement = taggedContent.RootElement;
```

لقد حصلنا على عنصر البنية الجذرية لمستند PDF.

## الخطوة 5: إضافة العناوين والفقرات

سنقوم الآن بإضافة عناوين ذات مستويات مختلفة والفقرة ذات العلامات إلى مستند PDF الخاص بنا.

```csharp
// إنشاء رؤوس من مستويات مختلفة
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);

// تعريف نص الرأس
h1.SetText("H1. Level 1 header");
h2.SetText("H2. Level 2 header");
h3.SetText("H3. Level 3 header");
h4.SetText("H4. Level 4 header");
h5.SetText("H5. Heading level 5");
h6.SetText("H6. Level 6 header");

// أضف رؤوسًا إلى عنصر البنية الجذرية
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);

// إنشاء الفقرة
ParagraphElement p = taggedContent.CreateParagraphElement();

//تعريف نص الفقرة
p.SetText("P. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean nec lectus ac sem faucibus imperdiet. Sed ut erat ac magna ullamcorper hendrerit. Cras pellentesque libero semper, gravida magna sed, luctus leo. Fusce lectus odio, laoreet Nec ullamcorper ut, molestie eu elit. Interdum et malesuada fames ac ante ipsum primis in faucibus. Aliquam lacinia sit amet elit ac consectetur. Donec cursus condimentum ligula, vitae volutpat sem tristique eget. Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit. Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");

// أضف الفقرة إلى عنصر البنية الجذرية
rootElement.AppendChild(p);
```

لقد أضفنا عناوين بمستويات مختلفة وفقرة ذات علامات تمييز إلى عنصر البنية الجذرية لمستند PDF.

## الخطوة 6: حفظ مستند PDF

الآن بعد أن انتهينا من تحرير مستند PDF، فلنحفظه في ملف.

```csharp
// احفظ مستند PDF الذي تم وضع علامة عليه
document.Save(dataDir + "ElementsDeStructureDeBlocsDeTexte.pdf");
```

لقد قمنا بحفظ وثيقة PDF ذات العلامات مع عناصر بنية كتلة النص في الدليل المحدد.

### نموذج التعليمات البرمجية المصدر لعناصر بنية كتلة النص باستخدام Aspose.PDF لـ .NET 
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
h1.SetText("H1. Header of Level 1");
h2.SetText("H2. Header of Level 2");
h3.SetText("H3. Header of Level 3");
h4.SetText("H4. Header of Level 4");
h5.SetText("H5. Header of Level 5");
h6.SetText("H6. Header of Level 6");
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean nec lectus ac sem faucibus imperdiet. Sed ut erat ac magna ullamcorper hendrerit. Cras pellentesque libero semper, gravida magna sed, luctus leo. Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit. Interdum et malesuada fames ac ante ipsum primis in faucibus. Aliquam lacinia sit amet elit ac consectetur. Donec cursus condimentum ligula, vitae volutpat sem tristique eget. Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit. Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
rootElement.AppendChild(p);

// حفظ وثيقة PDF ذات العلامات
document.Save(dataDir + "TextBlockStructureElements.pdf");
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية استخدام Aspose.PDF لـ .NET لإضافة عناصر بنية كتلة النص، مثل العناوين والفقرات ذات العلامات، إلى مستند PDF. يمكنك الآن استخدام هذه الميزات لتحسين بنية مستندات PDF الخاصة بك وإمكانية الوصول إليها.

### الأسئلة الشائعة

#### س: ما هو التركيز الرئيسي لهذا البرنامج التعليمي على إنشاء عناصر بنية كتلة النص في وثيقة PDF ذات علامات باستخدام Aspose.PDF لـ .NET؟

ج: يركز هذا البرنامج التعليمي على إرشادك خلال عملية إضافة عناصر بنية كتلة النص، بما في ذلك العناوين متعددة المستويات والفقرات ذات العلامات، إلى مستند PDF ذو علامات باستخدام Aspose.PDF لـ .NET. يوفر البرنامج التعليمي إرشادات خطوة بخطوة وأمثلة على التعليمات البرمجية المصدر لـ C# لمساعدتك في تحسين بنية مستندات PDF الخاصة بك وإمكانية الوصول إليها.

#### س: ما هي المتطلبات الأساسية لمتابعة هذا البرنامج التعليمي حول عناصر بنية كتلة النص باستخدام Aspose.PDF لـ .NET؟

ج: قبل أن تبدأ، تأكد من أنك قمت بإعداد بيئة التطوير الخاصة بك لاستخدام Aspose.PDF لـ .NET. يتضمن ذلك تثبيت مكتبة Aspose.PDF وتكوين مشروعك للرجوع إليه.

#### س: كيف يمكنني إنشاء مستند PDF جديد وإضافة عناصر بنية كتلة النص باستخدام Aspose.PDF لـ .NET؟

ج: يوفر البرنامج التعليمي أمثلة على التعليمات البرمجية المصدر لـ C# التي توضح كيفية إنشاء مستند PDF جديد وإضافة عناوين متعددة المستويات وفقرات ذات علامات باستخدام Aspose.PDF لـ .NET.

#### س: ما أهمية إضافة عناصر بنية كتلة النص إلى مستند PDF؟

ج: تؤدي إضافة عناصر بنية كتلة النص، مثل العناوين والفقرات ذات العلامات، إلى تحسين البنية الدلالية لمستند PDF. يعمل هذا على تحسين إمكانية الوصول لقارئات الشاشة والتقنيات المساعدة الأخرى، مما يسهل على المستخدمين التنقل وفهم المحتوى.

#### س: كيف يمكنني تعيين عنوان ولغة مستند PDF ذي علامات تمييز باستخدام Aspose.PDF لـ .NET؟

ج: يشتمل البرنامج التعليمي على أمثلة التعليمات البرمجية المصدر لـ C# التي توضح كيفية تعيين عنوان ولغة مستند PDF ذي علامات باستخدام Aspose.PDF لـ .NET.

#### س: كيف يمكنني إنشاء عناوين متعددة المستويات في وثيقة PDF ذات علامات باستخدام Aspose.PDF لـ .NET؟

 ج: يوفر البرنامج التعليمي أمثلة على التعليمات البرمجية المصدر لـ C# التي توضح كيفية إنشاء عناوين ذات مستويات مختلفة باستخدام`CreateHeaderElement()` الطريقة وإلحاقها بعنصر البنية الجذرية لمستند PDF الذي تم وضع علامة عليه.

#### س: كيف يمكنني إضافة فقرات ذات علامات تمييز إلى مستند PDF باستخدام Aspose.PDF لـ .NET؟

ج: يتضمن البرنامج التعليمي أمثلة على التعليمات البرمجية المصدر لـ C# التي توضح كيفية إنشاء فقرة باستخدام`CreateParagraphElement()` الطريقة وإضافة نص مميز إليها باستخدام`SetText()` طريقة. يتم بعد ذلك إلحاق الفقرة بعنصر البنية الجذرية لمستند PDF الذي تم وضع علامة عليه.

#### س: هل يمكنني تخصيص مظهر وتنسيق عناصر بنية كتلة النص التي أقوم بإضافتها إلى مستند PDF؟

ج: نعم، يمكنك تخصيص مظهر وتنسيق عناصر بنية كتلة النص باستخدام الخصائص والأساليب المتنوعة التي يوفرها Aspose.PDF لـ .NET. يمكنك ضبط أنماط الخطوط وأحجامها وألوانها ومحاذاتها وسمات التنسيق الأخرى لتلبية متطلباتك المحددة.

#### س: كيف يساعد نموذج التعليمات البرمجية المصدر المقدم في البرنامج التعليمي في إضافة عناصر بنية كتلة النص إلى مستند PDF؟

ج: يعتبر نموذج التعليمات البرمجية المصدر المقدم بمثابة مرجع عملي لتنفيذ إنشاء عناصر بنية كتلة النص في مستند PDF باستخدام Aspose.PDF لـ .NET. يمكنك استخدام هذا الرمز كنقطة بداية وتعديله وفقًا لاحتياجاتك.

#### س: كيف يمكنني تحسين وتخصيص مستندات PDF الخاصة بي بما يتجاوز عناصر بنية كتلة النص باستخدام Aspose.PDF لـ .NET؟

ج: يوفر Aspose.PDF for .NET نطاقًا واسعًا من الميزات لمعالجة مستندات PDF، بما في ذلك إضافة الصور والجداول والارتباطات التشعبية والتعليقات التوضيحية وحقول النماذج والعلامات المائية والتوقيعات الرقمية والمزيد. يمكنك استكشاف الوثائق والموارد الرسمية لفهم شامل لقدرات المكتبة.