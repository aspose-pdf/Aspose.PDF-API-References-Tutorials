---
title: عناصر البنية المضمنة
linktitle: عناصر البنية المضمنة
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: دليل خطوة بخطوة لاستخدام العناصر الهيكلية عبر الإنترنت مع Aspose.PDF لـ .NET. قم بتنظيم ملفات PDF الخاصة بك باستخدام العناوين والفقرات.
type: docs
weight: 110
url: /ar/net/programming-with-tagged-pdf/inline-structure-elements/
---
## مقدمة

إن إنشاء مستندات سهلة الوصول ومنظمة بشكل جيد أمر بالغ الأهمية في المشهد الرقمي اليوم. إذا وجدت نفسك يومًا ما تتصفح ملف PDF فقط لتضيع في بحر من النصوص، فأنت تعلم أهمية التنظيم الجيد. يمكن أن يؤدي وضع علامات على العناصر في ملف PDF إلى تعزيز إمكانية الوصول، مما يجعل من الأسهل على برامج قراءة الشاشة تفسير المحتوى. في هذا الدليل، نتعمق في استخدام Aspose.PDF لـ .NET لإنشاء مستندات PDF مُوسمة، مما يضمن أن عملك يلبي المعايير الحديثة في هيكلة المستندات.

## المتطلبات الأساسية

قبل أن نقفز إلى الحدث، دعنا نتأكد من أن لديك كل ما تحتاجه للمتابعة:

1. المعرفة الأساسية بلغة C#: المعرفة ببرمجة C# وأساسيات إطار عمل .NET أمر ضروري.
2. تم تثبيت Visual Studio: ستحتاج إلى IDE مثل Visual Studio لكتابة التعليمات البرمجية وتشغيلها.
3.  Aspose.PDF for .NET: تأكد من تنزيل Aspose.PDF for .NET وتثبيته. يمكنك الحصول عليه من[رابط التحميل](https://releases.aspose.com/pdf/net/).
4. ترخيص مؤقت: هذا اختياري، ولكن إذا كنت تريد تقييم جميع الميزات دون قيود، ففكر في الحصول على ترخيص مؤقت.[رخصة مؤقتة](https://purchase.aspose.com/temporary-license/).

بمجرد توفر هذه المتطلبات الأساسية لديك، ستكون جاهزًا لإنشاء مستند PDF المميز الأول الخاص بك!

## استيراد الحزم

للبدء، دعنا نستورد الحزم اللازمة. يتيح هذا لمشروعك الاستفادة من إمكانيات مكتبة Aspose.PDF.

1. افتح مشروع Visual Studio الخاص بك.
2. أضف مرجعًا إلى مكتبة Aspose.PDF. إذا لم تقم بإضافته بعد، فيمكنك استخدام NuGet Package Manager لتثبيته.
3. قم بتضمين المساحات التالية في الجزء العلوي من ملف C# الخاص بك:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

بفضل هذه الواردات، ستكون جاهزًا للنجاح.

## تقسيم الكود: دليل خطوة بخطوة لإنشاء ملف PDF مُوسم

الآن بعد أن قمنا بإعداد كل شيء، فلنبدأ في تحليل التعليمات البرمجية خطوة بخطوة. سننشئ ملف PDF مُوسمًا بعناصر منظمة مثل العناوين والفقرات، مما يتيح إمكانية الوصول بشكل أفضل.

### الخطوة 1: تعيين دليل المستندات

أولاً، حدد المسار الذي سيتم حفظ المستند فيه. من الجيد الحفاظ على بنية ملف منظمة.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // استبدل بالمسار الفعلي الخاص بك
```

### الخطوة 2: إنشاء نسخة من مستند PDF

 بعد ذلك، قم بإنشاء مثيل لـ`Document` الفئة، التي ستكون بمثابة الحاوية لمحتوى PDF الخاص بك.

```csharp
Document document = new Document();
```

### الخطوة 3: الوصول إلى المحتوى المُوسوم

الآن، قم بالوصول إلى المحتوى المُوسوم في المستند. وهنا يحدث السحر، فمن خلال وضع علامات على المحتوى، نعمل على تعزيز إمكانية الوصول إليه.

```csharp
ITaggedContent taggedContent = document.TaggedContent;    
```

### الخطوة 4: تعيين العنوان واللغة

يعد تعيين عنوان ولغة لمستند PDF أمرًا ضروريًا لكل من المستخدمين وقارئات الشاشة. وهذا يجعل مستندك أكثر إفادة وسهولة في الوصول إليه.

```csharp
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
```

### الخطوة 5: الحصول على عنصر البنية الجذرية

لنبدأ بإضافة العناصر إلى مستندك. أولاً، احصل على عنصر البنية الجذرية للمحتوى المُوسوم، والذي يعمل كأساس لبناء بنية مستندك.

```csharp
StructureElement rootElement = taggedContent.RootElement;
```

### الخطوة 6: إنشاء عناصر الرأس

الآن حان الوقت لإنشاء عناصر رأس الصفحة. سيساعد هذا في تنظيم المحتوى في تسلسل هرمي. سننشئ ستة مستويات من الرؤوس.

```csharp
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
```

### الخطوة 7: إضافة العناوين إلى العنصر الجذر

بعد إنشاء عناصر الرأس، قم بإضافتها إلى عنصر الجذر. يؤدي هذا إلى بناء التسلسل الهرمي الهيكلي للمستند.

```csharp
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);
```

### الخطوة 8: إضافة نص إلى كل رأس

الآن، دعنا نضيف بعض النصوص إلى كل عنوان. هذه عملية بسيطة ولكنها حيوية لجعل مستندك مفيدًا. 

```csharp
// ح1
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1. ");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 Header");
h1.AppendChild(spanH12);

// كرر الخطوات من H2 إلى H6 كما هو موضح أعلاه
```

### الخطوة 9: إنشاء عنصر الفقرة

بعد ذلك، دعنا نضيف عنصر فقرة. سيعمل هذا العنصر كمنطقة المحتوى الرئيسية لملف PDF الخاص بك. 

```csharp
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P. ");
rootElement.AppendChild(p);
```

### الخطوة 10: إضافة نص إلى الفقرة

الآن بعد أن أصبح لدينا عنصر الفقرة، حان الوقت لملئه بالنص. يمكنك إضافة عدة فقرات لتشمل المحتوى الخاص بك.

```csharp
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit. ");
p.AppendChild(span1);
// استمر في إضافة مسافات إضافية حسب الحاجة
```

### الخطوة 11: احفظ مستند PDF المُوسوم

أخيرًا، بعد إضافة كل المحتوى، تحتاج إلى حفظ المستند. لننهي الأمر!

```csharp
document.Save(dataDir + "InlineStructureElements.pdf");
```

والآن، أصبح لديك مستند PDF مميز ومنظم وسهل الوصول إليه.

## خاتمة

قد يبدو إنشاء مستندات PDF مُوسمة أمرًا شاقًا، ولكن مع Aspose.PDF لـ .NET، أصبح الأمر سهلاً للغاية! باتباع هذا الدليل التفصيلي، تكون قد أتقنت أساسيات هيكلة المستندات. تذكر أن وضع العلامات بشكل صحيح على ملف PDF الخاص بك يعزز إمكانية الوصول إليه، مما يضمن وصول المحتوى القيم الخاص بك إلى جمهور أوسع. لذا، امض قدمًا واجعل ملفات PDF الخاصة بك ليس جميلة فحسب، بل وسهلة الاستخدام أيضًا!

## الأسئلة الشائعة

### ما هو ملف PDF المُوسوم؟
ملف PDF المُوسم هو ملف PDF يتضمن معلومات حول بنية المستند، مما يجعله أكثر سهولة في الوصول إليه بالنسبة للمستخدمين ذوي الإعاقة.

### لماذا تعتبر العلامات مهمة في ملفات PDF؟
يعمل وضع العلامات على تعزيز إمكانية الوصول، مما يسمح لقارئات الشاشة بتفسير المستند بوضوح، وبالتالي توفير تجربة أفضل للمستخدمين ذوي الإعاقة.

### هل يمكنني استخدام Aspose.PDF مجانًا؟
 نعم، يمكنك تقييم Aspose.PDF لـ .NET من خلال[نسخة تجريبية مجانية](https://releases.aspose.com/).

### أين يمكنني الحصول على الدعم لـ Aspose.PDF؟
 يمكن الوصول إلى الدعم من خلال[منتدى دعم Aspose](https://forum.aspose.com/c/pdf/10).

### كيف يمكنني شراء ترخيص Aspose.PDF لـ .NET؟
 يمكنك شراء الترخيص مباشرة من[صفحة الشراء](https://purchase.aspose.com/buy).