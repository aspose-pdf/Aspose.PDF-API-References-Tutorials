---
title: إضافة مسافة بادئة للأسطر اللاحقة في ملف PDF
linktitle: إضافة مسافة بادئة للأسطر اللاحقة في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية إضافة مسافة بادئة للأسطر اللاحقة إلى النص في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 60
url: /ar/net/programming-with-text/add-subsequent-lines-indent/
---
سيرشدك هذا البرنامج التعليمي خلال عملية إضافة مسافة بادئة للأسطر اللاحقة إلى النص في ملف PDF باستخدام Aspose.PDF لـ .NET. يوضح كود المصدر C# المقدم الخطوات اللازمة.

## متطلبات
قبل أن تبدأ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي مُجمِّع C# آخر مُثبت على جهازك.
- مكتبة Aspose.PDF لـ .NET. يمكنك تنزيلها من موقع Aspose الرسمي أو استخدام مدير حزم مثل NuGet لتثبيتها.

## الخطوة 1: إعداد المشروع
1. قم بإنشاء مشروع C# جديد في بيئة التطوير المفضلة لديك.
2. أضف مرجعًا إلى مكتبة Aspose.PDF لـ .NET.

## الخطوة 2: استيراد المساحات المطلوبة
في ملف الكود الذي تريد إضافة مسافة بادئة للأسطر اللاحقة فيه، أضف التوجيه التالي باستخدام في الجزء العلوي من الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## الخطوة 3: تعيين دليل المستند
 في الكود، حدد السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدالها`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل الذي يتم تخزين مستنداتك فيه.

## الخطوة 4: إنشاء كائن مستند جديد
 إنشاء مثيل جديد`Document` الكائن عن طريق إضافة سطر التعليمات البرمجية التالي:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

## الخطوة 5: إضافة صفحة إلى المستند
 أضف صفحة جديدة إلى المستند باستخدام`Add` طريقة`Pages` المجموعة. في الكود المقدم، يتم تعيين الصفحة الجديدة للمتغير`page`.

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

## الخطوة 6: إنشاء TextFragment مع وضع مسافة بادئة للأسطر اللاحقة
 إنشاء مثيل`TextFragment` الكائن وتوفير النص المطلوب. في الكود المقدم، يتم تعيين النص للمتغير`text` . ثم قم بالتهيئة`TextFormattingOptions` من اجل`TextFragment` وحدد`SubsequentLinesIndent` قيمة.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog." );
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
     SubsequentLinesIndent = 20
};
```

## الخطوة 7: إضافة TextFragment إلى الصفحة
 أضف`TextFragment` الاعتراض على مجموعة الفقرات في الصفحة.

```csharp
page.Paragraphs.Add(text);
```

## الخطوة 8: كرر الخطوتين 6 و7 للخطوط الإضافية
لإضافة أسطر لاحقة بنفس المسافة البادئة، كرر الخطوتين 6 و7 لكل سطر. قم بتحديث محتوى النص حسب الحاجة.

```csharp
text = new Aspose.Pdf.Text.TextFragment("Line2");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line3");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line4");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line5");
page.Paragraphs.Add(text);
```

## الخطوة 9: احفظ مستند PDF
 احفظ مستند PDF باستخدام`Save` طريقة`Document` الكائن. حدد مسار ملف الإخراج.

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### عينة من كود المصدر لإضافة مسافة بادئة للأسطر اللاحقة باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// إنشاء كائن مستند جديد
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = document.Pages.Add();
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog.");
//قم بتفعيل TextFormattingOptions لشظية النص وحدد قيمة SubsequentLinesIndent
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
	SubsequentLinesIndent = 20
};
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line2");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line3");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line4");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line5");
page.Paragraphs.Add(text);
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## خاتمة
لقد نجحت في إضافة مسافة بادئة للأسطر اللاحقة إلى النص باستخدام Aspose.PDF لـ .NET. يمكن الآن العثور على ملف PDF الناتج في مسار ملف الإخراج المحدد.

### الأسئلة الشائعة

#### س: ما هو التركيز في هذا البرنامج التعليمي؟

ج: يوفر هذا البرنامج التعليمي دليلاً شاملاً حول كيفية إضافة مسافة بادئة للأسطر اللاحقة إلى النص في ملف PDF باستخدام مكتبة Aspose.PDF for .NET. وهو يتضمن أمثلة لأكواد المصدر بلغة C# لتوضيح الخطوات المطلوبة لتحقيق ذلك.

#### س: ما هي المساحات الأسماء التي أحتاج إلى استيرادها لهذا البرنامج التعليمي؟

أ: في ملف الكود الذي تنوي إضافة مسافة بادئة للأسطر اللاحقة، قم باستيراد المساحات التالية في بداية الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### س: كيف أحدد دليل المستند؟

 أ: في الكود، حدد السطر`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدالها`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستند الخاص بك.

#### س: كيف أقوم بإنشاء كائن مستند؟

 أ: في الخطوة 4، ستقوم بإنشاء مثيل جديد`Document` الكائن باستخدام سطر التعليمات البرمجية التالي:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

#### س: كيف أضيف صفحة إلى المستند؟

 أ: في الخطوة 5، ستضيف صفحة جديدة إلى المستند باستخدام`Add` طريقة`Pages` مجموعة:

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

#### س: كيف يمكنني إضافة مسافة بادئة للأسطر اللاحقة في النص؟

 أ: في الخطوة 6، ستقوم بإنشاء`TextFragment` الكائن وتعيين النص المطلوب إليه. بعد ذلك، ستقوم بتهيئة`TextFormattingOptions` من اجل`TextFragment` وحدد`SubsequentLinesIndent` قيمة:

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("Your text here");
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
    SubsequentLinesIndent = 20
};
```

#### س: كيف أضيف TextFragment إلى مستند PDF؟

 أ: في الخطوة 7، ستضيف`TextFragment` هدف (`text`) إلى مجموعة فقرات الصفحة:

```csharp
page.Paragraphs.Add(text);
```

#### س: هل يمكنني تكرار العملية للخطوط الإضافية؟

ج: نعم، في الخطوة 8، يمكنك تكرار العملية للأسطر الإضافية بنفس المسافة البادئة عن طريق إنشاء أسطر جديدة`TextFragment` الكائنات وإضافتها إلى مجموعة الفقرات الخاصة بالصفحة.

#### س: كيف أحفظ مستند PDF الناتج؟

 أ: بعد إضافة النص مع المسافة البادئة للأسطر اللاحقة، استخدم`Save` طريقة`Document` كائن لحفظ مستند PDF:

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

#### س: ما هو أهم ما يمكن تعلمه من هذا البرنامج التعليمي؟

ج: باتباع هذا البرنامج التعليمي، ستتعلم بنجاح كيفية تحسين قابلية قراءة النص في مستند PDF عن طريق إضافة مسافة بادئة للأسطر اللاحقة باستخدام Aspose.PDF لـ .NET. يمكن أن تكون هذه التقنية مفيدة لأنواع مختلفة من المستندات والتقارير.