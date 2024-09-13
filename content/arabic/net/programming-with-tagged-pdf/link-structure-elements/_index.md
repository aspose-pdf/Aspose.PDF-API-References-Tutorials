---
title: عناصر بنية الرابط
linktitle: عناصر بنية الرابط
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: دليل خطوة بخطوة لاستخدام عناصر بنية الارتباط مع Aspose.PDF لـ .NET. قم بإنشاء ارتباطات تشعبية في مستندات PDF الخاصة بك.
type: docs
weight: 120
url: /ar/net/programming-with-tagged-pdf/link-structure-elements/
---
في هذا الدليل التفصيلي، سنوضح لك كيفية استخدام عناصر بنية الارتباط مع Aspose.PDF لـ .NET. Aspose.PDF هي مكتبة قوية تتيح لك إنشاء مستندات PDF ومعالجتها برمجيًا. تتيح لك عناصر بنية الارتباط إضافة ارتباطات تشعبية إلى مستند PDF الخاص بك، مما يسمح للمستخدمين بالنقر فوق الارتباطات والانتقال إلى الموارد عبر الإنترنت.

دعنا نتعمق في الكود ونتعلم كيفية استخدام عناصر بنية الارتباط مع Aspose.PDF لـ .NET.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

1. تم تثبيت مكتبة Aspose.PDF لـ .NET.
2. المعرفة الأساسية للغة البرمجة C#.

## الخطوة 1: إعداد البيئة

للبدء، افتح بيئة تطوير C# وقم بإنشاء مشروع جديد. تأكد من إضافة مرجع إلى مكتبة Aspose.PDF لـ .NET في مشروعك.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";
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
taggedContent.SetTitle("Example Link Items");
taggedContent.SetLanguage("fr-FR");
```

## الخطوة 5: إضافة عناصر بنية الرابط

الآن دعنا نضيف عناصر بنية الارتباط إلى مستندنا. سننشئ أنواعًا مختلفة من الروابط، بما في ذلك روابط نصية بسيطة وروابط صور وروابط متعددة الأسطر.
```csharp
// الحصول على عنصر البنية الجذرية (عنصر بنية المستند)
StructureElement rootElement = taggedContent.RootElement;

// أضف فقرة تحتوي على رابط تشعبي
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://"google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";

// أضف فقرة تحتوي على رابط تشعبي يحتوي على نص غني
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://"google.com");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";

// أضف فقرة تحتوي على رابط تشعبي يحتوي على نص منسق جزئيًا
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://"google.com");
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("G");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText("oogle");
link3.AppendChild(span31);
link3.SetText("-");
link3.AppendChild(span32);
link3.AlternateDescriptions = "Link to Google";

// أضف فقرة تحتوي على ارتباط تشعبي متعدد الأسطر
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://"google.com");
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";

// أضف فقرة تحتوي على رابط تشعبي يحتوي على صورة
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://"google.com");
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

## الخطوة 6: احفظ مستند PDF المُوسوم

وأخيرًا، نحفظ مستند PDF المُوسوم.

```csharp
// احفظ مستند PDF المُوسوم
document. Save(outFile);
```

## الخطوة 7: التحقق من توافق PDF/UA

 يمكننا أيضًا التحقق من المستند للتأكد من توافقه مع PDF/UA باستخدام`Validate` طريقة`Document` فصل.

```csharp
// التحقق من توافق PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```


### نموذج لمصدر التعليمات البرمجية لعناصر بنية الارتباط باستخدام Aspose.PDF لـ .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";

//إنشاء مستند والحصول على محتوى Pdf المميز
Document document = new Document(); 
ITaggedContent taggedContent = document.TaggedContent;

// تعيين لغة العنوان والطبيعة للمستند
taggedContent.SetTitle("Link Elements Example");
taggedContent.SetLanguage("en-US");

// الحصول على عنصر بنية الجذر (عنصر بنية المستند)
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://"google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://"google.com");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://"google.com");
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
link4.Hyperlink = new WebHyperlink("http://"google.com");
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://"google.com");
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
StructureAttributes linkLayoutAttributes = link5.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
StructureAttribute placementAttribute = new StructureAttribute(AttributeKey.Placement);
placementAttribute.SetNameValue(AttributeName.Placement_Block);
linkLayoutAttributes.SetAttribute(placementAttribute);
link5.AppendChild(figure5);
link5.AlternateDescriptions = "Link to Google";

// حفظ مستند PDF المُوسوم
document.Save(outFile);

// التحقق من توافق PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```
## خاتمة

تهانينا! لقد تعلمت كيفية استخدام عناصر بنية الارتباط مع Aspose.PDF لـ .NET. يمكنك الآن إنشاء ارتباطات تشعبية في مستندات PDF الخاصة بك، مما يسمح للمستخدمين بالانتقال إلى الموارد عبر الإنترنت. جرّب واستكشف المزيد من ميزات Aspose.PDF لإنشاء مستندات PDF تفاعلية ومثرية.

### الأسئلة الشائعة

#### س: ما هي عناصر بنية الارتباط في مستند PDF، وكيف تعمل على تعزيز تفاعل المستند؟

أ: تُستخدم عناصر بنية الارتباط في مستند PDF لإنشاء ارتباطات تشعبية تسمح للمستخدمين بالانتقال إلى الموارد عبر الإنترنت أو مواقع محددة داخل المستند. تعمل هذه العناصر على تعزيز التفاعل من خلال توفير روابط قابلة للنقر تمكن المستخدمين من الوصول إلى المحتوى ذي الصلة أو مواقع الويب الخارجية.

#### س: كيف يمكن لعناصر بنية الرابط أن تكون مفيدة في مستند PDF؟

أ: تعمل عناصر بنية الرابط على تحسين تجربة المستخدم من خلال جعل مستند PDF تفاعليًا. فهي توفر وصولاً سريعًا إلى معلومات إضافية أو محتوى ذي صلة أو مواقع ويب خارجية أو أقسام محددة داخل المستند، مما يحسن التنقل ويسهل استرجاع المعلومات.

#### س: هل يمكنني إنشاء أنواع مختلفة من الارتباطات التشعبية باستخدام عناصر بنية الارتباط في Aspose.PDF لـ .NET؟

ج: نعم، يمكنك إنشاء أنواع مختلفة من الارتباطات التشعبية باستخدام عناصر بنية الارتباطات. يتيح لك Aspose.PDF for .NET إنشاء ارتباطات تشعبية بنص عادي ونص غني وصور وأوصاف متعددة الأسطر، مما يوفر تنوعًا في كيفية الارتباط بالمحتوى الخارجي أو المواقع داخل المستند.

#### س: كيف أقوم بإعداد وتكوين عناصر بنية الارتباط في مستند PDF باستخدام Aspose.PDF لـ .NET؟

 أ: لاستخدام عناصر بنية الرابط، تحتاج أولاً إلى إنشاء مستند PDF جديد باستخدام`Document` الصف. ثم، احصل على المحتوى المُوسوم باستخدام`TaggedContent`خاصية المستند. ومن هناك، يمكنك إنشاء عناصر بنية الارتباط وتخصيصها وإضافتها إلى عنصر البنية الجذرية.

#### س: كيف يمكنني إنشاء ارتباط نصي بسيط باستخدام عناصر بنية الارتباط؟
 أ: يمكنك إنشاء ارتباط نصي بسيط عن طريق إنشاء`LinkElement` ووضعها`Hyperlink` الممتلكات إلى`WebHyperlink` باستخدام عنوان URL الذي تريد الارتباط به. يمكنك أيضًا تعيين نص العرض للرابط باستخدام`SetText` طريقة.

#### س: هل من الممكن إنشاء ارتباطات تشعبية مع الصور باستخدام عناصر بنية الارتباط؟

 ج: نعم، يمكنك إنشاء ارتباطات تشعبية بالصور باستخدام عناصر بنية الارتباط. يمكنك إنشاء`LinkElement` ثم قم بإضافة`FigureElement` مع صورة لها. يتيح لك هذا إنشاء ارتباط تشعبي قائم على صورة.

#### س: كيف يمكنني التأكد من أن مستند PDF الخاص بي الذي يحتوي على روابط تشعبية يتوافق مع معيار PDF/UA لإمكانية الوصول؟

 أ: يوفر Aspose.PDF لـ .NET القدرة على التحقق من امتثال مستند PDF الخاص بك لمعيار PDF/UA باستخدام`Validate` طريقة`Document`يضمن هذا إمكانية وصول المستخدمين ذوي الإعاقة إلى الروابط التشعبية الموجودة في المستند.

#### س: ما هي الأوصاف البديلة لعناصر بنية الرابط، ولماذا هي مهمة؟

أ: توفر الأوصاف البديلة (النص البديل) لعناصر بنية الرابط أوصافًا نصية للروابط التشعبية. تعد هذه الأوصاف ضرورية لسهولة الوصول، حيث تسمح للمستخدمين الذين يعانون من إعاقات بصرية بفهم غرض الرابط ووجهته.

#### س: هل يمكنني تخصيص مظهر وسلوك الارتباطات التشعبية التي تم إنشاؤها باستخدام عناصر بنية الارتباط؟

ج: بينما تركز عناصر بنية الارتباط بشكل أساسي على إنشاء ارتباطات تشعبية، يمكنك تخصيص مظهر وسلوك الارتباطات التشعبية بشكل أكبر باستخدام ميزات أخرى يوفرها Aspose.PDF لـ .NET. ويتضمن ذلك تحديد الألوان والأنماط وإجراءات الارتباط.

#### س: كيف تساهم عناصر بنية الرابط في جعل مستندات PDF أكثر تفاعلية وسهولة في الاستخدام؟

أ: تعمل عناصر بنية الارتباط على تحويل مستندات PDF الثابتة إلى تجارب تفاعلية من خلال إضافة ارتباطات تشعبية قابلة للنقر. تعمل هذه التفاعلية على تحسين مشاركة المستخدم، وتمكين التنقل السلس بين المحتوى ذي الصلة، وتعزيز قابلية استخدام المستند بشكل عام.