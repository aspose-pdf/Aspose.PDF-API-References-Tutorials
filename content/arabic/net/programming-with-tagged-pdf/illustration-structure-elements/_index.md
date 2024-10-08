---
title: عناصر هيكل الرسم التوضيحي
linktitle: عناصر هيكل الرسم التوضيحي
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: قم بإنشاء ملفات PDF منظمة مع عناصر توضيحية في Aspose.PDF لـ .NET من خلال اتباع البرنامج التعليمي خطوة بخطوة.
type: docs
weight: 100
url: /ar/net/programming-with-tagged-pdf/illustration-structure-elements/
---
## مقدمة

هل أنت مستعد لإنشاء ملفات PDF مذهلة ومنظمة في تطبيقات .NET الخاصة بك؟ سواء كنت تعمل على مشروع يتطلب وضع علامات على المحتوى أو كنت ترغب ببساطة في رفع ملفات PDF الخاصة بك إلى المستوى التالي، فإن Aspose.PDF for .NET يحتوي على جميع الأدوات التي تحتاجها للعمل مع عناصر بنية التوضيح. في هذا البرنامج التعليمي، سأرشدك خلال العملية خطوة بخطوة، مع ضمان وضوح الأجزاء الأكثر تعقيدًا.

## المتطلبات الأساسية

قبل أن نتعمق في التفاصيل، دعنا نتأكد من أن لديك كل ما تحتاجه لمتابعة الأمر بسلاسة.

1.  Aspose.PDF لـ .NET – ستحتاج إلى تثبيت مكتبة Aspose.PDF. هل ليس لديك هذه المكتبة بعد؟ يمكنك[تحميله هنا](https://releases.aspose.com/pdf/net/) إذا كنت تريد اختباره أولاً، يمكنك الحصول على[نسخة تجريبية مجانية](https://releases.aspose.com/).
2. Visual Studio – سوف نقوم بالبرمجة باستخدام C#، لذا تأكد من تثبيت Visual Studio أو أي IDE متوافق.
3. .NET Framework – تأكد من أن لديك إصدارًا متوافقًا مع Aspose.PDF لـ .NET.
4.  الترخيص المؤقت - يأتي Aspose.PDF مع بعض القيود في وضع التجربة، لذا احصل عليه[رخصة مؤقتة](https://purchase.aspose.com/temporary-license/) لفتح الميزات الكاملة.

هذا كل شيء! الآن دعنا نستورد مساحات الأسماء الضرورية وننتقل إلى مرحلة البرمجة.

## استيراد مساحات الأسماء

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

هذا هو الأساس—بدون استيراد هذه المساحات الاسمية، لا يمكننا التفاعل مع ميزات Aspose.PDF أو التعامل مع محتوى PDF المُوسوم. دعنا الآن نوضح الخطوات بالتفصيل.

## الخطوة 1: إعداد دليل المستندات الخاص بك

قبل أن تبدأ في إنشاء ملف PDF، يتعين عليك تحديد المسار إلى دليل المستندات الذي سيتم حفظ الملف فيه. هذا هو المجلد على نظامك حيث يتم تخزين الصور أو الأصول الأخرى.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 هذه الخطوة بسيطة، ولكنها ضرورية. فأنت تخبر البرنامج بمكان العثور على الملفات التي ستعمل عليها وتخزينها. الأمر أشبه بامتلاك قاعدة أساسية لملفات PDF الخاصة بك. استبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي على جهازك.

## الخطوة 2: إنشاء مستند PDF جديد

الآن، حان الوقت لإنشاء مستند PDF. في هذه الخطوة، سننشئ مستند PDF فارغًا، وسنعمل على تعديله وتحسينه في الخطوات التالية.
 إنشاء المستند

```csharp
Document document = new Document();
```

يؤدي هذا الخط كل المهام السحرية. فهو ينشئ ملف PDF جديدًا فارغًا تمامًا، وينتظر منك إضافة محتوى إليه. فكر في الأمر كما لو كنت تفتح لوحة قماشية جديدة.

## الخطوة 3: الوصول إلى محتوى PDF المُوسوم

للعمل مع عناصر بنية الرسم التوضيحي، نحتاج إلى الاستفادة من المحتوى المُوسوم في المستند. يتيح لنا هذا تحديد علامات محددة، مما يجعل ملف PDF أكثر هيكلة وسهولة في الوصول إليه.

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

 هذا هو المكان الذي يحدث فيه السحر!`TaggedContent` يتيح لنا الكائن تحديد كيفية تفسير العناصر في ملف PDF. إذا كنت تعمل في مجال إمكانية الوصول أو البنية، فإن هذه الخطوة بالغة الأهمية.

## الخطوة 4: تعيين عنوان المستند واللغة

نحن نعمل على إنشاء ملف PDF منظم، لذا من الضروري تحديد عنوان ولغة. وهذا لا يساعد فقط في إمكانية الوصول، بل يجعل المستند أكثر احترافية وقابلية للبحث.

```csharp
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
```

من خلال تحديد عنوان ولغة، فإنك تمنح ملف PDF الخاص بك بعض الشخصية. سيظهر العنوان في خصائص المستند، ويضمن ضبط اللغة التوافق مع برامج قراءة الشاشة وأدوات إمكانية الوصول الأخرى.

## الخطوة 5: إنشاء عنصر الرسم التوضيحي (الشكل)

الآن يأتي الجزء المثير للاهتمام، وهو إضافة رسم توضيحي! في هذه الحالة، سننشئ عنصرًا للشكل يتضمن صورة ووصفًا نصيًا بديلاً وعنوانًا.

```csharp
IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
```

يقوم هذا الكود بإنشاء عنصر شكل جديد وإضافته إلى عنصر الجذر في المستند. فكر في هذا الأمر كأنك تضيف عنصرًا نائبًا للصورة إلى مستندك.

## الخطوة 6: إضافة نص بديل وعنوان وصورة

لضمان إمكانية الوصول إلى ملف PDF الخاص بك، ستحتاج إلى تضمين نص بديل وعنوان للرسم التوضيحي الخاص بك. وسنقوم أيضًا بإرفاق صورة.

```csharp
figure1.AlternativeText = "Figure One";
figure1.Title = "Image 1";
figure1.SetTag("Fig1");
figure1.SetImage(dataDir + "image.jpg");
```

 هذه هي اللمسة الأخيرة. سنضيف نصًا وصفيًا بديلاً لصورتنا (وهو مفيد لقارئات الشاشة)، وعنوانًا، ونضبط ملف الصورة الفعلي.`SetTag`تضع الطريقة علامات على الشكل، مما يجعل من السهل الرجوع إليه لاحقًا.

 ملاحظة هامة: تأكد من أن مسار الصورة في`SetImage` يشير إلى ملف صورة صالح على جهازك.

## الخطوة 7: حفظ مستند PDF المُوسوم

بمجرد إضافة كل المحتوى وتنظيمه، حان الوقت لحفظ ملف PDF. هذه الخطوة تنهي كل شيء وتولد الملف الفعلي.

```csharp
document.Save(dataDir + "IllustrationStructureElements.pdf");
```

الأمر بسيط، أليس كذلك؟ يأخذ هذا الأمر كل العمل الذي قمت به وينشئ ملف PDF جديدًا في الدليل الذي حددته سابقًا. الآن، تحقق من المجلد، وستحصل على ملف PDF منظم يحتوي على عناصر توضيحية!

## خاتمة

تهانينا! لقد تعلمت للتو كيفية إنشاء ملف PDF مُوسم بعناصر هيكلية توضيحية باستخدام Aspose.PDF لـ .NET. يضمن هذا النهج أن ملفات PDF الخاصة بك ليست جذابة بصريًا فحسب، بل إنها منظمة أيضًا ويمكن الوصول إليها بسهولة. من خلال وضع علامات على المحتوى وإضافة نص بديل، فإنك تضمن أن الجميع، بما في ذلك أولئك الذين يستخدمون تقنيات المساعدة، يمكنهم الاستمتاع بمستنداتك.

## الأسئلة الشائعة

### ما هو محتوى PDF المُوسوم؟
ملف PDF المُوسم هو ملف PDF يتضمن علامات أو تسميات لتحديد عناصر مختلفة، مثل العناوين والفقرات والأشكال، مما يجعل المستند أكثر سهولة في الوصول إليه.

### كيف يساعد إعداد النص البديل؟
يوفر النص البديل أوصافًا للصور، والتي يمكن لبرامج قراءة الشاشة قراءتها، مما يحسن إمكانية الوصول إليها للمستخدمين ضعاف البصر.

### هل يمكنني إضافة صور متعددة إلى ملف PDF مُوسوم؟
 نعم! يمكنك إنشاء العديد من`FigureElement` الكائنات وأضف كل واحد منها إلى مستندك، تمامًا كما فعلنا مع الصورة الفردية.

### هل أحتاج إلى ترخيص لاستخدام Aspose.PDF لـ .NET؟
 نعم، Aspose.PDF هي مكتبة مدفوعة، ولكن يمكنك الحصول عليها[رخصة مؤقتة](https://purchase.aspose.com/temporary-license/) أو ابدأ بـ[نسخة تجريبية مجانية](https://releases.aspose.com/).

### هل من الممكن تعديل عنصر الشكل بعد إنشاء ملف PDF؟
بمجرد حفظ ملف PDF، لا يمكنك تعديله بشكل مباشر، ولكن يمكنك إعادة فتح المستند وإجراء التغييرات وحفظه مرة أخرى باستخدام Aspose.PDF.