---
title: ربط عناصر الهيكل
linktitle: ربط عناصر الهيكل
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لاستخدام عناصر بنية الارتباط مع Aspose.PDF for .NET. قم بإنشاء ارتباطات تشعبية في مستندات PDF الخاصة بك.
type: docs
weight: 120
url: /ar/net/programming-with-tagged-pdf/link-structure-elements/
---
في هذا الدليل المفصل خطوة بخطوة ، سنوضح لك كيفية استخدام عناصر بنية الارتباط مع Aspose.PDF for .NET. Aspose.PDF هي مكتبة قوية تتيح لك إنشاء مستندات PDF ومعالجتها برمجيًا. تسمح لك عناصر بنية الارتباط بإضافة ارتباطات تشعبية إلى مستند PDF الخاص بك ، مما يسمح للمستخدمين بالنقر فوق الروابط والتنقل إلى الموارد عبر الإنترنت.

دعنا نتعمق في الكود ونتعلم كيفية استخدام عناصر بنية الارتباط مع Aspose.PDF for .NET.

## المتطلبات الأساسية

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

1. تثبيت مكتبة Aspose.PDF لـ .NET.
2. معرفة أساسية بلغة البرمجة C #.

## الخطوة الأولى: تهيئة البيئة

للبدء ، افتح بيئة التطوير C # وأنشئ مشروعًا جديدًا. تأكد من إضافة مرجع إلى مكتبة Aspose.PDF لـ .NET في مشروعك.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";
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
taggedContent.SetTitle("Example Link Items");
taggedContent.SetLanguage("fr-FR");
```

## الخطوة 5: إضافة عناصر بنية الارتباط

الآن دعنا نضيف عناصر بنية الارتباط إلى وثيقتنا. سننشئ أنواعًا مختلفة من الروابط ، بما في ذلك روابط نصية بسيطة وروابط صور وروابط متعددة الخطوط.
```csharp
// الحصول على عنصر بنية الجذر (عنصر بنية المستند)
StructureElement rootElement = taggedContent.RootElement;

// أضف فقرة مع ارتباط تشعبي
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://google.com ") ؛
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";

// أضف فقرة مع ارتباط تشعبي يحتوي على نص منسق
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com ") ؛
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";

// أضف فقرة مع ارتباط تشعبي يحتوي على نص منسق جزئيًا
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://google.com ") ؛
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("G");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText("oogle");
link3.AppendChild(span31);
link3.SetText("-");
link3.AppendChild(span32);
link3.AlternateDescriptions = "Link to Google";

// أضف فقرة مع ارتباط تشعبي متعدد الأسطر
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://google.com ") ؛
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";

// أضف فقرة مع ارتباط تشعبي يحتوي على صورة
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.com ") ؛
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

أخيرًا ، نقوم بحفظ مستند PDF الموسوم.

```csharp
// احفظ مستند PDF بعلامات
document. Save(outFile);
```

## الخطوة 7: تحقق من التوافق مع PDF / UA

 يمكننا أيضًا التحقق من توافق المستند مع PDF / UA باستخدام`Validate` طريقة`Document` فصل.

```csharp
// تحقق من التوافق مع PDF / UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```


### نموذج التعليمات البرمجية المصدر لـ Link Structure Elements باستخدام Aspose.PDF لـ .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";

// مستند الإنشاء والحصول على محتوى بتنسيق PDF ذي علامات
Document document = new Document(); 
ITaggedContent taggedContent = document.TaggedContent;

// تحديد العنوان ولغة الطبيعة للوثيقة
taggedContent.SetTitle("Link Elements Example");
taggedContent.SetLanguage("en-US");

// الحصول على عنصر بنية الجذر (عنصر بنية المستند)
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://google.com ") ؛
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com ") ؛
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://google.com ") ؛
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
link4.Hyperlink = new WebHyperlink("http://google.com ") ؛
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.com ") ؛
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
StructureAttributes linkLayoutAttributes = link5.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
StructureAttribute placementAttribute = new StructureAttribute(AttributeKey.Placement);
placementAttribute.SetNameValue(AttributeName.Placement_Block);
linkLayoutAttributes.SetAttribute(placementAttribute);
link5.AppendChild(figure5);
link5.AlternateDescriptions = "Link to Google";

// حفظ وثيقة PDF الموسومة
document.Save(outFile);

// التحقق من توافق PDF / UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```
## خاتمة

تهنئة ! لقد تعلمت كيفية استخدام عناصر بنية الارتباط مع Aspose.PDF for .NET. يمكنك الآن إنشاء ارتباطات تشعبية في مستندات PDF الخاصة بك ، مما يسمح للمستخدمين بالانتقال إلى الموارد عبر الإنترنت. جرب واستكشف المزيد من ميزات Aspose.PDF لإنشاء مستندات PDF تفاعلية وثرية.

### التعليمات

#### س: ما هي عناصر بنية الارتباط في مستند PDF ، وكيف تعمل على تحسين تفاعل المستند؟

ج: تُستخدم عناصر بنية الارتباط في مستند PDF لإنشاء ارتباطات تشعبية تتيح للمستخدمين التنقل إلى الموارد عبر الإنترنت أو مواقع محددة داخل المستند. تعمل هذه العناصر على تحسين التفاعل من خلال توفير روابط قابلة للنقر تمكن المستخدمين من الوصول إلى المحتوى ذي الصلة أو مواقع الويب الخارجية.

#### س: كيف يمكن أن تكون عناصر بنية الارتباط مفيدة في مستند PDF؟

ج: تعمل عناصر بنية الارتباط على تحسين تجربة المستخدم من خلال جعل مستند PDF تفاعليًا. أنها توفر وصولاً سريعًا إلى معلومات إضافية ، أو محتوى ذي صلة ، أو مواقع ويب خارجية ، أو أقسام محددة داخل المستند ، مما يؤدي إلى تحسين التنقل وتسهيل استرجاع المعلومات.

#### س: هل يمكنني إنشاء أنواع مختلفة من الارتباطات التشعبية باستخدام عناصر بنية الارتباط في Aspose.PDF for .NET؟

ج: نعم ، يمكنك إنشاء أنواع مختلفة من الارتباطات التشعبية باستخدام عناصر بنية الارتباط. يتيح لك Aspose.PDF for .NET إنشاء ارتباطات تشعبية بنص عادي ونص منسق وصور وأوصاف متعددة الأسطر ، مما يوفر تنوعًا في كيفية الارتباط بمحتوى خارجي أو مواقع داخل المستند.

#### س: كيف أقوم بإعداد عناصر بنية الارتباط وتهيئتها في مستند PDF باستخدام Aspose.PDF لـ .NET؟

 ج: لاستخدام عناصر بنية الارتباط ، تحتاج أولاً إلى إنشاء مستند PDF جديد باستخدام ملف`Document` فصل. بعد ذلك ، احصل على المحتوى الذي تم وضع علامة عليه باستخدام امتداد`TaggedContent`ملكية المستند. من هناك ، يمكنك إنشاء عناصر بنية الارتباط وتخصيصها وإضافتها إلى عنصر بنية الجذر.

#### س: كيف يمكنني إنشاء ارتباط تشعبي نصي بسيط باستخدام عناصر بنية الارتباط؟
 ج: يمكنك إنشاء ارتباط تشعبي نصي بسيط عن طريق إنشاء ملف`LinkElement` ووضعها`Hyperlink` ملكية ل`WebHyperlink` بعنوان URL الذي تريد الارتباط به. يمكنك أيضًا تعيين نص عرض الارتباط باستخدام ملف`SetText` طريقة.

#### س: هل من الممكن إنشاء ارتباطات تشعبية بالصور باستخدام عناصر بنية الارتباط؟

 ج: نعم ، يمكنك إنشاء ارتباطات تشعبية بالصور باستخدام عناصر بنية الارتباط. سوف تقوم بإنشاء ملف`LinkElement` ثم قم بإلحاق أ`FigureElement` مع صورة لها. هذا يسمح لك بإنشاء ارتباط تشعبي قائم على الصورة.

#### س: كيف يمكنني التأكد من أن مستند PDF الذي يحتوي على ارتباطات تشعبية متوافق مع معيار PDF / UA لإمكانية الوصول؟

 ج: يوفر Aspose.PDF for .NET القدرة على التحقق من توافق مستند PDF الخاص بك مع معيار PDF / UA باستخدام`Validate` طريقة`Document`فصل. يضمن ذلك إمكانية وصول المستخدمين ذوي الاحتياجات الخاصة إلى الارتباطات التشعبية الخاصة بالمستند.

#### س: ما هي الأوصاف البديلة لعناصر بنية الارتباط ، ولماذا هي مهمة؟

ج: توفر الأوصاف البديلة (نص بديل) لعناصر بنية الارتباط أوصافًا نصية للارتباطات التشعبية. هذه الأوصاف ضرورية لإمكانية الوصول ، مما يسمح للمستخدمين الذين يعانون من إعاقات بصرية بفهم الغرض من الارتباط ووجهته.

#### س: هل يمكنني تخصيص مظهر وسلوك الارتباطات التشعبية التي تم إنشاؤها باستخدام عناصر بنية الارتباط؟

ج: بينما تركز عناصر بنية الارتباط بشكل أساسي على إنشاء ارتباطات تشعبية ، يمكنك تخصيص مظهر وسلوك الارتباطات التشعبية بشكل أكبر باستخدام الميزات الأخرى التي يوفرها Aspose.PDF لـ .NET. يتضمن ذلك تحديد الألوان والأنماط وإجراءات الارتباط.

#### س: كيف تساهم عناصر بنية الارتباط في جعل مستندات PDF أكثر تفاعلية وسهولة في الاستخدام؟

ج: تعمل عناصر بنية الارتباط على تحويل مستندات PDF الثابتة إلى تجارب تفاعلية عن طريق إضافة ارتباطات تشعبية قابلة للنقر. يعمل هذا التفاعل على تحسين تفاعل المستخدم ، وتمكين التنقل السلس بين المحتوى ذي الصلة ، وتعزيز قابلية استخدام المستند بشكل عام.