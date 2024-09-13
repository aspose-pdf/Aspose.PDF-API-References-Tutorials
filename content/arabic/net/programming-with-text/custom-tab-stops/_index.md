---
title: علامات التبويب المخصصة في ملف PDF
linktitle: علامات التبويب المخصصة في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية إنشاء علامات تبويب مخصصة في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 120
url: /ar/net/programming-with-text/custom-tab-stops/
---

سيرشدك هذا البرنامج التعليمي خلال عملية إنشاء علامات تبويب مخصصة في ملف PDF باستخدام Aspose.PDF لـ .NET. يوضح كود المصدر C# المقدم الخطوات اللازمة.

## متطلبات
قبل أن تبدأ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي مُجمِّع C# آخر مُثبت على جهازك.
- مكتبة Aspose.PDF لـ .NET. يمكنك تنزيلها من موقع Aspose الرسمي أو استخدام مدير حزم مثل NuGet لتثبيتها.

## الخطوة 1: إعداد المشروع
1. قم بإنشاء مشروع C# جديد في بيئة التطوير المفضلة لديك.
2. أضف مرجعًا إلى مكتبة Aspose.PDF لـ .NET.

## الخطوة 2: استيراد المساحات المطلوبة
في ملف الكود الذي تريد إنشاء علامات تبويب مخصصة فيه، أضف التعليمات التالية باستخدام التوجيهات في الجزء العلوي من الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## الخطوة 3: تعيين دليل المستند
 في الكود، حدد السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدالها`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل الذي يتم تخزين مستنداتك فيه.

## الخطوة 4: إنشاء مثيل مستند جديد
 إنشاء مثيل جديد`Document` الكائن عن طريق إضافة سطر التعليمات البرمجية التالي:

```csharp
Document _pdfdocument = new Document();
```

## الخطوة 5: إضافة صفحة إلى المستند
 أضف صفحة جديدة إلى المستند باستخدام`Add` طريقة`Pages` المجموعة. في الكود المقدم، يتم تعيين الصفحة الجديدة للمتغير`page`.

```csharp
Page page = _pdfdocument.Pages.Add();
```

## الخطوة 6: إنشاء علامات تبويب مخصصة
 إنشاء`TabStops` الكائن وإضافة علامات تبويب مخصصة إليه. قم بتعيين نوع المحاذاة ونوع العلامة لكل علامة تبويب.

```csharp
TabStops ts = new TabStops();
TabStop ts1 = ts.Add(100);
ts1.AlignmentType = TabAlignmentType.Right;
ts1.LeaderType = TabLeaderType.Solid;

TabStop ts2 = ts.Add(200);
ts2.AlignmentType = TabAlignmentType.Center;
ts2.LeaderType = TabLeaderType.Dash;

TabStop ts3 = ts.Add(300);
ts3.AlignmentType = TabAlignmentType.Left;
ts3.LeaderType = TabLeaderType.Dot;
```

## الخطوة 7: إنشاء أجزاء نصية باستخدام علامات التبويب
 يخلق`TextFragment` الكائنات ومرر علامات التبويب المخصصة إليها. استخدم الأحرف الخاصة`#$TAB` للإشارة إلى علامات التبويب داخل النص.

```csharp
TextFragment header = new TextFragment("This is an example of forming a table with TAB stops", ts);
TextFragment text0 = new TextFragment("#$TABHead1 #$TABHead2 #$TABHead3", ts);
TextFragment text1 = new TextFragment("#$TABdata11 #$TABdata12 #$TABdata13", ts);
TextFragment text2 = new TextFragment("#$TABdata21 ", ts);
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data22 "));
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data23"));

page.Paragraphs.Add(header);
page.Paragraphs.Add(text0);
page.Paragraphs.Add(text1);
page.Paragraphs.Add(text2);
```

## الخطوة 8: احفظ مستند PDF
 احفظ مستند PDF باستخدام`Save` طريقة`Document` هدف.

```csharp
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

### عينة من كود المصدر لعلامات التبويب المخصصة باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document _pdfdocument = new Document();
Page page = _pdfdocument.Pages.Add();
Aspose.Pdf.Text.TabStops ts = new Aspose.Pdf.Text.TabStops();
Aspose.Pdf.Text.TabStop ts1 = ts.Add(100);
ts1.AlignmentType = TabAlignmentType.Right;
ts1.LeaderType = TabLeaderType.Solid;
Aspose.Pdf.Text.TabStop ts2 = ts.Add(200);
ts2.AlignmentType = TabAlignmentType.Center;
ts2.LeaderType = TabLeaderType.Dash;
Aspose.Pdf.Text.TabStop ts3 = ts.Add(300);
ts3.AlignmentType = TabAlignmentType.Left;
ts3.LeaderType = TabLeaderType.Dot;
TextFragment header = new TextFragment("This is a example of forming table with TAB stops", ts);
TextFragment text0 = new TextFragment("#$TABHead1 #$TABHead2 #$TABHead3", ts);
TextFragment text1 = new TextFragment("#$TABdata11 #$TABdata12 #$TABdata13", ts);
TextFragment text2 = new TextFragment("#$TABdata21 ", ts);
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data22 "));
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data23"));
page.Paragraphs.Add(header);
page.Paragraphs.Add(text0);
page.Paragraphs.Add(text1);
page.Paragraphs.Add(text2);
dataDir = dataDir + "CustomTabStops_out.pdf";
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

## خاتمة
لقد نجحت في إنشاء مستند PDF بعلامات تبويب مخصصة باستخدام Aspose.PDF لـ .NET. يمكنك الآن العثور على ملف PDF الناتج في مسار ملف الإخراج المحدد.

### الأسئلة الشائعة

#### س: ما هو التركيز في هذا البرنامج التعليمي؟

ج: يركز هذا البرنامج التعليمي على إرشادك خلال عملية إنشاء علامات تبويب مخصصة في ملف PDF باستخدام مكتبة Aspose.PDF for .NET. يوضح كود المصدر C# المقدم الخطوات اللازمة لتحقيق ذلك.

#### س: ما هي المساحات الأسماء التي ينبغي لي استيرادها لهذا البرنامج التعليمي؟

أ: في ملف الكود الذي تريد إنشاء علامات تبويب مخصصة فيه، قم باستيراد المساحات التالية في بداية الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### س: كيف أحدد دليل المستند؟

 أ: في الكود، ابحث عن السطر`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدالها`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستند الخاص بك.

#### س: كيف أقوم بإنشاء مثيل مستند جديد؟

 أ: في الخطوة 4، ستقوم بإنشاء مثيل جديد`Document` الكائن باستخدام الكود المقدم.

#### س: كيف أضيف صفحة إلى المستند؟

 أ: في الخطوة 5، ستضيف صفحة جديدة إلى المستند باستخدام`Add` طريقة`Pages` مجموعة.

#### س: كيف أقوم بإنشاء علامات تبويب مخصصة؟

 أ: في الخطوة 6، ستقوم بإنشاء`TabStops` الكائن وإضافة علامات تبويب مخصصة إليه. كما يمكنك أيضًا تعيين أنواع المحاذاة والخطوط الرئيسية لكل علامة تبويب.

#### س: كيف أقوم بإنشاء أجزاء نصية باستخدام علامات التبويب؟

 أ: في الخطوة 7، سوف تقوم بإنشاء`TextFragment` الكائنات وتمرير علامات التبويب المخصصة إليها. ستستخدم الأحرف الخاصة`#$TAB` للإشارة إلى علامات التبويب داخل النص.

#### س: كيف أحفظ مستند PDF؟

 أ: في الخطوة 8، ستحفظ مستند PDF باستخدام`Save` طريقة`Document` هدف.

#### س: ما هو الدرس الرئيسي المستفاد من هذا البرنامج التعليمي؟

ج: باتباع هذا البرنامج التعليمي، ستتعلم كيفية إنشاء مستند PDF بعلامات تبويب مخصصة باستخدام Aspose.PDF for .NET. يمكن أن يكون هذا مفيدًا لتنظيم النص ومحاذاته بطريقة منظمة.