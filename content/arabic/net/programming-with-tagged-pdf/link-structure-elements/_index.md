---
title: عناصر هيكل الارتباط
linktitle: عناصر هيكل الارتباط
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لاستخدام عناصر بنية الارتباط مع Aspose.PDF لـ .NET. قم بإنشاء ارتباطات تشعبية في مستندات PDF الخاصة بك.
type: docs
weight: 120
url: /ar/net/programming-with-tagged-pdf/link-structure-elements/
---
في هذا الدليل خطوة بخطوة، سنوضح لك كيفية استخدام عناصر بنية الارتباط مع Aspose.PDF لـ .NET. Aspose.PDF هي مكتبة قوية تتيح لك إنشاء مستندات PDF ومعالجتها برمجيًا. تتيح لك عناصر بنية الارتباط إضافة ارتباطات تشعبية إلى مستند PDF الخاص بك، مما يسمح للمستخدمين بالنقر فوق الارتباطات والانتقال إلى الموارد عبر الإنترنت.

دعنا نتعمق في التعليمات البرمجية ونتعلم كيفية استخدام عناصر بنية الارتباط مع Aspose.PDF لـ .NET.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

1. تم تثبيت مكتبة Aspose.PDF لـ .NET.
2. معرفة أساسية بلغة البرمجة C#.

## الخطوة 1: تهيئة البيئة

للبدء، افتح بيئة تطوير C# الخاصة بك وقم بإنشاء مشروع جديد. تأكد من إضافة مرجع إلى مكتبة Aspose.PDF لـ .NET في مشروعك.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";
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
taggedContent.SetTitle("Example Link Items");
taggedContent.SetLanguage("fr-FR");
```

## الخطوة 5: إضافة عناصر هيكل الارتباط

الآن دعونا نضيف عناصر بنية الارتباط إلى وثيقتنا. سنقوم بإنشاء أنواع مختلفة من الروابط، بما في ذلك الروابط النصية البسيطة، وروابط الصور، والروابط متعددة الأسطر.
```csharp
// الحصول على عنصر البنية الجذرية (عنصر بنية الوثيقة)
StructureElement rootElement = taggedContent.RootElement;

// إضافة فقرة مع ارتباط تشعبي
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";

// أضف فقرة تحتوي على ارتباط تشعبي يحتوي على نص منسق
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";

// أضف فقرة تحتوي على ارتباط تشعبي يحتوي على نص منسق جزئيًا
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("G");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText("oogle");
link3.AppendChild(span31);
link3.SetText("-");
link3.AppendChild(span32);
link3.AlternateDescriptions = "Link to Google";

// إضافة فقرة مع ارتباط تشعبي متعدد الأسطر
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://google.com");
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";

// أضف فقرة تحتوي على ارتباط تشعبي يحتوي على صورة
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.com");
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
StructureAttributes linkLayoutAttributes = link5.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
StructureAttribute placementAttribute = new StructureAttribute(AttributeKey.Placement);
placementAttribute.SetNameValue(AttributeName.Placement_Block);
linkLayoutAttributes.SetAttribute(placementAttribute);
link5.AppendChild(figure5);
link5.AlternateDescriptions = "Link to Google";
```

## الخطوة 6: احفظ مستند PDF الذي تم وضع علامة عليه

وأخيرًا، نقوم بحفظ مستند PDF الذي تم وضع علامة عليه.

```csharp
// احفظ مستند PDF الذي تم وضع علامة عليه
document. Save(outFile);
```

## الخطوة 7: التحقق من توافق PDF/UA

 يمكننا أيضًا التحقق من توافق المستند مع PDF/UA باستخدام ملف`Validate` طريقة`Document` فصل.

```csharp
// تحقق من توافق PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```


### نموذج التعليمات البرمجية المصدر لعناصر بنية الارتباط باستخدام Aspose.PDF لـ .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";

// إنشاء مستند والحصول على محتوى Pdf ذو علامة
Document document = new Document(); 
ITaggedContent taggedContent = document.TaggedContent;

// تحديد العنوان واللغة الطبيعية للمستند
taggedContent.SetTitle("Link Elements Example");
taggedContent.SetLanguage("en-US");

// الحصول على عنصر بنية الجذر (عنصر بنية المستند)
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("G");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText("oogle");
link3.AppendChild(span31);
link3.SetText("-");
link3.AppendChild(span32);
link3.AlternateDescriptions = "Link to Google";
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://google.com");
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.com");
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
StructureAttributes linkLayoutAttributes = link5.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
StructureAttribute placementAttribute = new StructureAttribute(AttributeKey.Placement);
placementAttribute.SetNameValue(AttributeName.Placement_Block);
linkLayoutAttributes.SetAttribute(placementAttribute);
link5.AppendChild(figure5);
link5.AlternateDescriptions = "Link to Google";

// حفظ وثيقة PDF ذات العلامات
document.Save(outFile);

// التحقق من توافق PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```
## خاتمة

تهنئة ! لقد تعلمت كيفية استخدام عناصر بنية الارتباط مع Aspose.PDF لـ .NET. يمكنك الآن إنشاء ارتباطات تشعبية في مستندات PDF الخاصة بك، مما يسمح للمستخدمين بالانتقال إلى الموارد عبر الإنترنت. قم بتجربة واستكشاف المزيد من ميزات Aspose.PDF لإنشاء مستندات PDF تفاعلية ومثرية.

### الأسئلة الشائعة

#### س: ما هي عناصر بنية الارتباط في مستند PDF، وكيف تعمل على تحسين تفاعل المستند؟

ج: يتم استخدام عناصر بنية الارتباط في مستند PDF لإنشاء ارتباطات تشعبية تسمح للمستخدمين بالانتقال إلى الموارد عبر الإنترنت أو مواقع محددة داخل المستند. تعمل هذه العناصر على تحسين التفاعل من خلال توفير روابط قابلة للنقر تمكن المستخدمين من الوصول إلى المحتوى ذي الصلة أو مواقع الويب الخارجية.

#### س: كيف يمكن أن تكون عناصر بنية الارتباط مفيدة في مستند PDF؟

ج: تعمل عناصر بنية الارتباط على تحسين تجربة المستخدم من خلال جعل مستند PDF تفاعليًا. وهي توفر وصولاً سريعًا إلى معلومات إضافية أو محتوى ذي صلة أو مواقع ويب خارجية أو أقسام محددة داخل المستند، مما يؤدي إلى تحسين التنقل وتسهيل استرجاع المعلومات.

#### س: هل يمكنني إنشاء أنواع مختلفة من الارتباطات التشعبية باستخدام عناصر بنية الارتباط في Aspose.PDF لـ .NET؟

ج: نعم، يمكنك إنشاء أنواع مختلفة من الارتباطات التشعبية باستخدام عناصر بنية الارتباط. يسمح لك Aspose.PDF for .NET بإنشاء ارتباطات تشعبية بنص عادي ونص منسق وصور وأوصاف متعددة الأسطر، مما يوفر تنوعًا في كيفية الارتباط بالمحتوى الخارجي أو المواقع داخل المستند.

#### س: كيف يمكنني إعداد عناصر بنية الارتباط وتهيئتها في مستند PDF باستخدام Aspose.PDF لـ .NET؟

 ج: لاستخدام عناصر بنية الارتباط، تحتاج أولاً إلى إنشاء مستند PDF جديد باستخدام ملف`Document` فصل. ثم، احصل على المحتوى الموسوم باستخدام`TaggedContent`خاصية الوثيقة. ومن هناك، يمكنك إنشاء عناصر بنية الارتباط وتخصيصها وإضافتها إلى عنصر البنية الجذرية.

#### س: كيف يمكنني إنشاء ارتباط تشعبي نصي بسيط باستخدام عناصر بنية الارتباط؟
 ج: يمكنك إنشاء ارتباط تشعبي نصي بسيط عن طريق إنشاء ملف`LinkElement` ووضعها`Hyperlink` الملكية إلى أ`WebHyperlink` باستخدام عنوان URL الذي تريد الارتباط به. يمكنك أيضًا تعيين نص العرض للارتباط باستخدام`SetText` طريقة.

#### س: هل من الممكن إنشاء ارتباطات تشعبية بالصور باستخدام عناصر بنية الارتباط؟

 ج: نعم، يمكنك إنشاء ارتباطات تشعبية تحتوي على صور باستخدام عناصر بنية الارتباط. سوف تقوم بإنشاء ملف`LinkElement` ومن ثم إلحاق أ`FigureElement` مع صورة لها. يتيح لك هذا إنشاء ارتباط تشعبي يعتمد على الصورة.

#### س: كيف يمكنني التأكد من أن مستند PDF الخاص بي الذي يحتوي على ارتباطات تشعبية متوافق مع معيار PDF/UA الخاص بإمكانية الوصول؟

 ج: يوفر Aspose.PDF for .NET القدرة على التحقق من امتثال مستند PDF الخاص بك لمعيار PDF/UA باستخدام`Validate` طريقة`Document`فصل. وهذا يضمن أن الارتباطات التشعبية للمستند يمكن الوصول إليها من قبل المستخدمين ذوي الإعاقة.

#### س: ما هي الأوصاف البديلة لعناصر بنية الارتباط، وما سبب أهميتها؟

ج: توفر الأوصاف البديلة (النص البديل) لعناصر بنية الارتباط أوصافًا نصية للارتباطات التشعبية. تعتبر هذه الأوصاف ضرورية لإمكانية الوصول، مما يسمح للمستخدمين ذوي الإعاقة البصرية بفهم الغرض من الارتباط ووجهته.

#### س: هل يمكنني تخصيص مظهر وسلوك الارتباطات التشعبية التي تم إنشاؤها باستخدام عناصر بنية الارتباط؟

ج: بينما تركز عناصر بنية الارتباط بشكل أساسي على إنشاء الارتباطات التشعبية، يمكنك تخصيص مظهر الارتباطات التشعبية وسلوكها بشكل أكبر باستخدام الميزات الأخرى التي يوفرها Aspose.PDF لـ .NET. يتضمن ذلك تحديد الألوان والأنماط وإجراءات الارتباط.

#### س: كيف تساهم عناصر بنية الارتباط في جعل مستندات PDF أكثر تفاعلية وسهلة الاستخدام؟

ج: تعمل عناصر بنية الارتباط على تحويل مستندات PDF الثابتة إلى تجارب تفاعلية عن طريق إضافة ارتباطات تشعبية قابلة للنقر. يعمل هذا التفاعل على تحسين تفاعل المستخدم، ويتيح التنقل السلس بين المحتوى ذي الصلة، ويعزز سهولة استخدام المستند بشكل عام.