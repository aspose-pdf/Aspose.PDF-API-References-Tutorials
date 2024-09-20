---
title: عناصر بنية الرابط
linktitle: عناصر بنية الرابط
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية إنشاء عناصر بنية ارتباط في ملف PDF باستخدام Aspose.PDF لـ .NET. دليل خطوة بخطوة لإضافة روابط وصور يمكن الوصول إليها والتحقق من التوافق.
type: docs
weight: 120
url: /ar/net/programming-with-tagged-pdf/link-structure-elements/
---
## مقدمة

إن إنشاء وإدارة عناصر بنية الارتباط داخل ملف PDF أمر بالغ الأهمية بالنسبة للمستندات التي تتطلب إمكانية الوصول والتنقل السلس. في هذا البرنامج التعليمي، سنوضح لك كيفية القيام بذلك باستخدام Aspose.PDF لـ .NET. إذا كنت جديدًا على Aspose.PDF أو التعامل مع PDF بشكل عام، فلا تقلق. سأشرح كل خطوة بالتفصيل حتى تتمكن من متابعتها بسهولة!

## المتطلبات الأساسية  

قبل أن نتعمق في البرمجة، دعونا نوضح بعض الأمور أولاً. هذه هي المتطلبات الأساسية لضمان تجربة تطوير سلسة.

1.  Aspose.PDF for .NET: يمكنك تنزيل الإصدار الأحدث[هنا](https://releases.aspose.com/pdf/net/).
2. بيئة تطوير .NET: سواء كان Visual Studio أو أي IDE متوافق مع .NET، تأكد من تثبيته وتجهيزه.
3.  ترخيص Aspose: يمكنك استخدام النسخة التجريبية المجانية من Aspose.PDF[هنا](https://releases.aspose.com/) أو الحصول على[رخصة مؤقتة](https://purchase.aspose.com/temporary-license/).
4. المعرفة الأساسية بلغة C#: سنعمل مع بعض أكواد C#، لذا فإن فهم الأساسيات سيجعل الأمور أسهل كثيرًا.

## استيراد الحزم

ستحتاج إلى استيراد بعض الحزم قبل كتابة التعليمات البرمجية لعناصر بنية الرابط. ابدأ بالإشارة إلى مكتبات Aspose.PDF الضرورية في مشروعك:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

تتيح لنا هذه الاستيرادات العمل مع مستندات PDF وإضافة العلامات وإدارة عناصر الهيكل.

سنقوم الآن بإنشاء مستند PDF يحتوي على أنواع مختلفة من هياكل الروابط، وسيتم تقسيم كل خطوة لمساعدتك على فهم العملية بدقة.

## الخطوة 1: تهيئة المستند  

لنبدأ بإنشاء مستند PDF جديد وإعداد محتوى مميز لسهولة الوصول إليه.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";

// إنشاء مستند PDF جديد
Document document = new Document(); 

// استرداد واجهة TaggedContent
ITaggedContent taggedContent = document.TaggedContent;
```
  
 هنا، نقوم بتهيئة`Document` الكائن الذي يمثل ملف PDF الخاص بنا. كما نسترد أيضًا`TaggedContent` الواجهة، التي تسمح لنا بإضافة عناصر هيكلية مثل الفقرات والروابط والصور.

## الخطوة 2: تعيين العنوان واللغة  

يجب أن يحتوي كل ملف PDF على عنوان وإعداد لغة، خاصة إذا كنت تهدف إلى التوافق مع معايير PDF/UA.

```csharp
// تعيين عنوان المستند واللغة
taggedContent.SetTitle("Link Elements Example");
taggedContent.SetLanguage("en-US");
```
  
تضمن هذه الخطوة أن يكون لملف PDF الخاص بك عنوان ذو معنى وتضبط اللغة على الإنجليزية (`en-US`يعد هذا أمرًا بالغ الأهمية لإمكانية الوصول ويضمن أن تتمكن برامج قراءة الشاشة أو التقنيات المساعدة الأخرى من تفسير مستندك بشكل صحيح.

## الخطوة 3: إنشاء الفقرات وإضافتها  

في هذه الخطوة، سنضيف فقرات لاحتواء عناصر الرابط الخاصة بنا.

```csharp
// إنشاء العنصر الجذري
StructureElement rootElement = taggedContent.RootElement;

// إنشاء فقرة وإضافتها إلى العنصر الجذر
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
```
  
نقوم بإنشاء عنصر بنية الجذر، والذي يعد في الأساس الحاوية ذات المستوى الأعلى لجميع العناصر الأخرى. ثم نقوم بإنشاء فقرة (`p1`) وإضافته إلى عنصر الجذر.

## الخطوة 4: إضافة رابط بسيط  

الآن دعونا نضيف رابطًا تشعبيًا أساسيًا يشير إلى Google.

```csharp
// إنشاء عنصر رابط وإضافته إلى الفقرة
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);

// تعيين ارتباط تشعبي ونص للرابط
link1.Hyperlink = new WebHyperlink("http://"google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";
```
  
في هذه الخطوة، قمنا بإنشاء عنصر ارتباط، وضبطنا الارتباط التشعبي الخاص به على "http://google.com"، وقمنا بتوفير نص ("Google") للرابط. كما أضفنا وصفًا بديلًا لضمان إمكانية الوصول.

## الخطوة 5: إضافة رابط مع Spans  

يمكننا أيضًا إنشاء روابط بامتدادات نصية مختلفة.

```csharp
// إنشاء فقرة أخرى
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);

// إنشاء رابط باستخدام عنصر span
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://"google.com");

SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);

link2.AlternateDescriptions = "Link to Google";
```
  
هنا، استخدمنا عنصر span لتضمين جزء من النص داخل الرابط، مما يسمح لنا بتخصيص كيفية ظهور أجزاء معينة من الرابط.

## الخطوة 6: رابط متعدد الأسطر  

ماذا لو كان نص الرابط الخاص بك طويلاً للغاية؟ لا تقلق، يمكنك تقسيمه إلى عدة أسطر.

```csharp
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);

LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://"google.com");
link4.SetText("The multiline link: Google Google Google Google Google...");
link4.AlternateDescriptions = "Link to Google (multiline)";
```
  
في هذه الحالة، قمنا بإنشاء رابط متعدد الأسطر ببساطة عن طريق تعيين قيمة نصية طويلة، وسيتم التفاف النص تلقائيًا عبر أسطر متعددة.

## الخطوة 7: إضافة صورة إلى الرابط  

وأخيرًا، يمكنك أيضًا إضافة صور داخل الرابط.

```csharp
// إنشاء فقرة جديدة وعنصر رابط
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);

LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://"google.com");

// أضف صورة إلى الرابط
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
link5.AppendChild(figure5);

link5.AlternateDescriptions = "Link to Google";
```
  
توضح هذه الخطوة كيفية تعزيز الروابط الخاصة بك باستخدام صورة. في هذه الحالة، أضفنا أيقونة Google داخل الرابط. كما عملنا على ضمان إمكانية الوصول من خلال تعيين نص بديل للصورة.

## الخطوة 8: التحقق من صحة ملف PDF للتأكد من توافقه  

إذا كنت تهدف إلى التوافق مع معيار إمكانية الوصول PDF/UA، فمن الأفضل التحقق من صحة مستندك.

```csharp
// حفظ مستند PDF
document.Save(outFile);

// التحقق من صحة المستند للتأكد من توافقه مع PDF/UA
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```
  
لقد قمنا بحفظ المستند وتحققنا من صحته وفقًا لمعيار PDF/UA، والذي يضمن أن ملف PDF يلبي متطلبات إمكانية الوصول.

## خاتمة  

في هذا البرنامج التعليمي، قمنا بتغطية كيفية إنشاء مستندات PDF منظمة باستخدام Aspose.PDF لـ .NET. بدءًا من إضافة ارتباطات تشعبية أساسية إلى هياكل أكثر تعقيدًا مثل الامتدادات والارتباطات متعددة الأسطر وحتى الصور، يوفر هذا الدليل أساسًا قويًا للتعامل مع عناصر الارتباط في ملفات PDF الخاصة بك. مع الاستفادة الإضافية من توافق PDF/UA، أصبحت الآن مجهزًا لإنشاء ملفات PDF يمكن الوصول إليها والتنقل فيها.

## الأسئلة الشائعة

### هل يمكنني إضافة هياكل أكثر تعقيدًا مثل الجداول داخل الروابط؟  
لا، الروابط مخصصة في المقام الأول للنصوص والصور، ولكن يمكنك تضمين عناصر معقدة بالقرب منها.

### هل التحقق من صحة PDF/UA إلزامي؟  
ليس دائمًا، ولكن يوصى به بشدة إذا كنت مهتمًا بإمكانية الوصول.

### ماذا يحدث إذا كان مسار ملف الصورة غير صحيح؟  
لن يعرض المستند الصورة، وقد يتسبب في حدوث خطأ أثناء العرض.

### هل يمكنني تنسيق النص الموجود داخل الرابط؟  
نعم، يمكنك تطبيق أنماط النص باستخدام عناصر span.

### هل من الممكن إنشاء روابط داخلية للمستندات؟  
بالتأكيد! يمكنك الارتباط بأقسام محددة داخل نفس المستند.