---
title: إضافة مسافة بادئة للأسطر اللاحقة في ملف PDF
linktitle: إضافة مسافة بادئة للأسطر اللاحقة في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة مسافة بادئة للأسطر اللاحقة إلى النص في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 60
url: /ar/net/programming-with-text/add-subsequent-lines-indent/
---
سيرشدك هذا البرنامج التعليمي خلال عملية إضافة مسافة بادئة للأسطر اللاحقة إلى النص في ملف PDF باستخدام Aspose.PDF لـ .NET. يوضح كود مصدر C# المقدم الخطوات اللازمة.

## متطلبات
قبل أن تبدأ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي مترجم C# آخر مثبت على جهازك.
- Aspose.PDF لمكتبة .NET. يمكنك تنزيله من موقع Aspose الرسمي أو استخدام مدير الحزم مثل NuGet لتثبيته.

## الخطوة 1: إعداد المشروع
1. قم بإنشاء مشروع C# جديد في بيئة التطوير المفضلة لديك.
2. قم بإضافة مرجع إلى Aspose.PDF لمكتبة .NET.

## الخطوة 2: استيراد مساحات الأسماء المطلوبة
في ملف التعليمات البرمجية الذي تريد إضافة مسافة بادئة للأسطر اللاحقة فيه، أضف ما يلي باستخدام التوجيه في أعلى الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## الخطوة 3: قم بتعيين دليل المستند
 في الكود، حدد السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدال`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل حيث يتم تخزين المستندات الخاصة بك.

## الخطوة 4: إنشاء كائن مستند جديد
 إنشاء مثيل جديد`Document` كائن عن طريق إضافة السطر التالي من التعليمات البرمجية:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

## الخطوة 5: إضافة صفحة إلى المستند
 أضف صفحة جديدة إلى المستند باستخدام`Add` طريقة`Pages`مجموعة. في الكود المقدم، يتم تعيين الصفحة الجديدة للمتغير`page`.

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

## الخطوة 6: إنشاء TextFragment مع وضع مسافة بادئة للأسطر اللاحقة
 إنشاء مثيل أ`TextFragment` الكائن وتقديم النص المطلوب. في الكود المقدم، يتم تعيين النص للمتغير`text` . ثم قم بالتهيئة`TextFormattingOptions` ل`TextFragment`وتحديد`SubsequentLinesIndent` قيمة.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog." );
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
     SubsequentLinesIndent = 20
};
```

## الخطوة 7: أضف TextFragment إلى الصفحة
 أضف ال`TextFragment` الاعتراض على مجموعة الفقرات من الصفحة.

```csharp
page.Paragraphs.Add(text);
```

## الخطوة 8: كرر الخطوتين 6 و 7 للخطوط الإضافية
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
 احفظ مستند PDF باستخدام`Save` طريقة`Document` هدف. تحديد مسار ملف الإخراج.

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### نموذج التعليمات البرمجية المصدر لإضافة مسافة بادئة للأسطر اللاحقة باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// إنشاء كائن مستند جديد
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = document.Pages.Add();
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog.");
// قم بتهيئة TextFormattingOptions لجزء النص وحدد قيمة SubsequentLinesIndent
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

#### س: ما هو محور هذا البرنامج التعليمي؟

ج: يوفر هذا البرنامج التعليمي دليلاً شاملاً حول كيفية إضافة مسافة بادئة للأسطر اللاحقة إلى النص في ملف PDF باستخدام مكتبة Aspose.PDF لـ .NET. يتضمن أمثلة على التعليمات البرمجية المصدر لـ C# لتوضيح الخطوات المطلوبة لتحقيق ذلك.

#### س: ما هي مساحات الأسماء التي أحتاج إلى استيرادها لهذا البرنامج التعليمي؟

ج: في ملف التعليمات البرمجية الذي تنوي إضافة مسافة بادئة للأسطر اللاحقة فيه، قم باستيراد مساحات الأسماء التالية في بداية الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### س: كيف أحدد دليل المستندات؟

 ج: في الكود، حدد موقع السطر`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدال`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

#### س: كيف أقوم بإنشاء كائن مستند؟

 ج: في الخطوة 4، ستقوم بإنشاء نسخة جديدة`Document` كائن باستخدام السطر التالي من التعليمات البرمجية:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

#### س: كيف يمكنني إضافة صفحة إلى المستند؟

 ج: في الخطوة 5، ستضيف صفحة جديدة إلى المستند باستخدام الملف`Add` طريقة`Pages` مجموعة:

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

#### س: كيف يمكنني إضافة مسافة بادئة للأسطر اللاحقة إلى النص؟

 ج: في الخطوة 6، ستقوم بإنشاء ملف`TextFragment` الكائن وتعيين النص المطلوب له. بعد ذلك، سوف تقوم بالتهيئة`TextFormattingOptions` ل`TextFragment`وتحديد`SubsequentLinesIndent` قيمة:

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("Your text here");
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
    SubsequentLinesIndent = 20
};
```

#### س: كيف يمكنني إضافة TextFragment إلى مستند PDF؟

 ج: في الخطوة 7، عليك إضافة`TextFragment` هدف (`text`) إلى مجموعة الفقرات من الصفحة:

```csharp
page.Paragraphs.Add(text);
```

#### س: هل يمكنني تكرار العملية لخطوط إضافية؟

 ج: نعم، في الخطوة 8، يمكنك تكرار العملية لأسطر إضافية بنفس المسافة البادئة عن طريق إنشاء خطوط جديدة`TextFragment` الكائنات وإضافتها إلى مجموعة الفقرات بالصفحة.

#### س: كيف يمكنني حفظ مستند PDF الناتج؟

 ج: بعد إضافة النص مع المسافة البادئة للأسطر اللاحقة، استخدم`Save` طريقة`Document` كائن لحفظ مستند PDF:

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

#### س: ما هي الوجبات الرئيسية من هذا البرنامج التعليمي؟

ج: باتباع هذا البرنامج التعليمي، تكون قد تعلمت بنجاح كيفية تحسين إمكانية قراءة النص في مستند PDF عن طريق إضافة مسافة بادئة للأسطر اللاحقة باستخدام Aspose.PDF لـ .NET. يمكن أن تكون هذه التقنية مفيدة لأنواع مختلفة من المستندات والتقارير.