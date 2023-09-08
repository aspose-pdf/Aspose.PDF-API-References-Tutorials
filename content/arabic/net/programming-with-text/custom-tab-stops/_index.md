---
title: علامات التبويب المخصصة تتوقف في ملف PDF
linktitle: علامات التبويب المخصصة تتوقف في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إنشاء علامات جدولة مخصصة في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 120
url: /ar/net/programming-with-text/custom-tab-stops/
---

سيرشدك هذا البرنامج التعليمي خلال عملية إنشاء علامات جدولة مخصصة في ملف PDF باستخدام Aspose.PDF لـ .NET. يوضح كود مصدر C# المقدم الخطوات اللازمة.

## متطلبات
قبل أن تبدأ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي مترجم C# آخر مثبت على جهازك.
- Aspose.PDF لمكتبة .NET. يمكنك تنزيله من موقع Aspose الرسمي أو استخدام مدير الحزم مثل NuGet لتثبيته.

## الخطوة 1: إعداد المشروع
1. قم بإنشاء مشروع C# جديد في بيئة التطوير المفضلة لديك.
2. قم بإضافة مرجع إلى Aspose.PDF لمكتبة .NET.

## الخطوة 2: استيراد مساحات الأسماء المطلوبة
في ملف التعليمات البرمجية الذي تريد إنشاء علامات جدولة مخصصة فيه، أضف ما يلي باستخدام التوجيهات الموجودة في أعلى الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## الخطوة 3: قم بتعيين دليل المستند
 في الكود، حدد السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدال`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل حيث يتم تخزين المستندات الخاصة بك.

## الخطوة 4: إنشاء مثيل مستند جديد
 إنشاء مثيل جديد`Document` كائن عن طريق إضافة السطر التالي من التعليمات البرمجية:

```csharp
Document _pdfdocument = new Document();
```

## الخطوة 5: إضافة صفحة إلى المستند
 أضف صفحة جديدة إلى المستند باستخدام`Add` طريقة`Pages`مجموعة. في الكود المقدم، يتم تعيين الصفحة الجديدة للمتغير`page`.

```csharp
Page page = _pdfdocument.Pages.Add();
```

## الخطوة 6: إنشاء علامات جدولة مخصصة
 إنشاء`TabStops` كائن وإضافة علامات جدولة مخصصة إليه. قم بتعيين نوع المحاذاة ونوع القائد لكل علامة جدولة.

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

## الخطوة 7: إنشاء أجزاء نصية مع توقفات الجدولة
 يخلق`TextFragment` الكائنات وتمرير علامات الجدولة المخصصة إليها. استخدم الأحرف الخاصة`#$TAB` للإشارة إلى علامات الجدولة داخل النص.

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

### نموذج التعليمات البرمجية المصدر لعلامات التبويب المخصصة باستخدام Aspose.PDF لـ .NET 
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
لقد نجحت في إنشاء مستند PDF مع علامات جدولة مخصصة باستخدام Aspose.PDF لـ .NET. يمكن الآن العثور على ملف PDF الناتج في مسار ملف الإخراج المحدد.

### الأسئلة الشائعة

#### س: ما هو محور هذا البرنامج التعليمي؟

ج: يركز هذا البرنامج التعليمي على إرشادك خلال عملية إنشاء علامات جدولة مخصصة في ملف PDF باستخدام مكتبة Aspose.PDF لـ .NET. يوضح كود مصدر C# المقدم الخطوات اللازمة لتحقيق ذلك.

#### س: ما هي مساحات الأسماء التي يجب علي استيرادها لهذا البرنامج التعليمي؟

ج: في ملف التعليمات البرمجية الذي تريد إنشاء علامات جدولة مخصصة فيه، قم باستيراد مساحات الأسماء التالية في بداية الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### س: كيف أحدد دليل المستندات؟

 ج: في الكود، ابحث عن السطر`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدال`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

#### س: كيف يمكنني إنشاء مثيل مستند جديد؟

 ج: في الخطوة 4، ستقوم بإنشاء نسخة جديدة`Document` الكائن باستخدام الكود المقدم.

#### س: كيف يمكنني إضافة صفحة إلى المستند؟

 ج: في الخطوة 5، ستضيف صفحة جديدة إلى المستند باستخدام الملف`Add` طريقة`Pages` مجموعة.

#### س: كيف يمكنني إنشاء علامات جدولة مخصصة؟

 ج: في الخطوة 6، ستقوم بإنشاء ملف`TabStops` كائن وإضافة علامات جدولة مخصصة إليه. ستقوم أيضًا بتعيين أنواع المحاذاة والخطوط السابقة لكل علامة جدولة.

#### س: كيف يمكنني إنشاء أجزاء نصية تحتوي على علامات جدولة؟

 ج: في الخطوة 7، ستقوم بالإنشاء`TextFragment` الكائنات وتمرير علامات الجدولة المخصصة إليها. ستستخدم الأحرف الخاصة`#$TAB` للإشارة إلى علامات الجدولة داخل النص.

#### س: كيف أحفظ وثيقة PDF؟

 ج: في الخطوة 8، ستحفظ مستند PDF باستخدام الملف`Save` طريقة`Document` هدف.

#### س: ما هي الوجبات الرئيسية من هذا البرنامج التعليمي؟

ج: باتباع هذا البرنامج التعليمي، تعلمت كيفية إنشاء مستند PDF بعلامات جدولة مخصصة باستخدام Aspose.PDF لـ .NET. يمكن أن يكون هذا مفيدًا لتنظيم النص ومحاذاته بطريقة منظمة.