---
title: إضافة HTML باستخدام الكتابة فوق DOM وPDF
linktitle: أضف HTML باستخدام DOM والكتابة فوقه
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة محتوى HTML باستخدام الكتابة فوق DOM وPDF في Aspose.PDF لـ .NET.
type: docs
weight: 50
url: /ar/net/programming-with-text/add-html-using-dom-and-overwrite/
---
سيرشدك هذا البرنامج التعليمي خلال عملية إضافة محتوى HTML باستخدام DOM (نموذج كائن المستند) في Aspose.PDF لـ .NET. بالإضافة إلى ذلك، سوف تتعلم كيفية الكتابة فوق الأنماط لمحتوى HTML. يوضح كود مصدر C# المقدم الخطوات اللازمة.

## متطلبات
قبل أن تبدأ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي مترجم C# آخر مثبت على جهازك.
- Aspose.PDF لمكتبة .NET. يمكنك تنزيله من موقع Aspose الرسمي أو استخدام مدير الحزم مثل NuGet لتثبيته.

## الخطوة 1: إعداد المشروع
1. قم بإنشاء مشروع C# جديد في بيئة التطوير المفضلة لديك.
2. قم بإضافة مرجع إلى Aspose.PDF لمكتبة .NET.

## الخطوة 2: استيراد مساحات الأسماء المطلوبة
في ملف التعليمات البرمجية الذي تريد إضافة محتوى HTML إليه، أضف ما يلي باستخدام التوجيهات الموجودة أعلى الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## الخطوة 3: قم بتعيين دليل المستند ومسار ملف الإخراج
 في الكود، حدد السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدال`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل حيث يتم تخزين المستندات الخاصة بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 4: إنشاء كائن مستند جديد
 إنشاء مثيل جديد`Document` كائن عن طريق إضافة السطر التالي من التعليمات البرمجية:

```csharp
Document doc = new Document();
```

## الخطوة 5: إضافة صفحة إلى المستند
 أضف صفحة جديدة إلى المستند باستخدام`Add` طريقة`Pages`مجموعة. في الكود المقدم، يتم تعيين الصفحة الجديدة للمتغير`page`.

```csharp
Page page = doc.Pages.Add();
```

## الخطوة 6: إنشاء HtmlFragment بمحتوى HTML
 إنشاء مثيل ل`HtmlFragment` الكائن وتوفير محتوى HTML المطلوب. في التعليمات البرمجية المقدمة، يتم تعيين محتوى HTML للمتغير`title`. يمكنك تعديل محتوى HTML حسب الحاجة.

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

## الخطوة 7: الكتابة فوق أنماط محتوى HTML
 للكتابة فوق أنماط محتوى HTML، يمكنك تعديل`TextState` خصائص`HtmlFragment` هدف. في الكود المقدم، تم تغيير عائلة الخطوط إلى "Arial" وتم ضبط حجم الخط على 20.

```csharp
title. TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

## الخطوة 8: تعيين معلومات الهامش
اضبط الهوامش السفلية والعلوية لجزء HTML إذا لزم الأمر. في الكود المقدم، تم تعيين الهامش السفلي على 10 والهامش العلوي على 400.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 400;
```

## الخطوة 9: أضف HtmlFragment إلى الصفحة
 أضف ال`HtmlFragment` الاعتراض على مجموعة الفقرات من الصفحة.

```csharp
page.Paragraphs.Add(title);
```

## الخطوة 10: احفظ مستند PDF
 احفظ مستند PDF باستخدام`Save` طريقة`Document` هدف. حدد مسار ملف الإخراج الذي قمت بتعيينه في الخطوة 3.

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

### نموذج التعليمات البرمجية المصدر لإضافة HTMLUsing DOMAnd الكتابة باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// إنشاء مثيل لكائن المستند
Document doc = new Document();
// إضافة صفحة إلى مجموعة الصفحات من ملف PDF
Page page = doc.Pages.Add();
// إنشاء مثيل لـ HtmlFragment باستخدام شبكات HTML
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
//سيتم إعادة تعيين عائلة الخطوط من "Verdana" إلى "Arial"
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
// تعيين معلومات الهامش السفلي
title.Margin.Bottom = 10;
// تعيين معلومات الهامش العلوي
title.Margin.Top = 400;
// إضافة جزء HTML إلى مجموعة الفقرات من الصفحة
page.Paragraphs.Add(title);
// حفظ ملف PDF
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
// حفظ ملف PDF
doc.Save(dataDir);
```

## خاتمة
لقد نجحت في إضافة محتوى HTML باستخدام DOM في Aspose.PDF لـ .NET وقمت بالكتابة فوق الأنماط الخاصة بمحتوى HTML. يمكن الآن العثور على ملف PDF الناتج في مسار ملف الإخراج المحدد.

### الأسئلة الشائعة

#### س: ما هو محور هذا البرنامج التعليمي؟

ج: تم تصميم هذا البرنامج التعليمي لإرشادك خلال عملية إضافة محتوى HTML إلى مستند PDF باستخدام نموذج كائن المستند (DOM) في Aspose.PDF لـ .NET. بالإضافة إلى ذلك، ستتعلم كيفية الكتابة فوق أنماط محتوى HTML، مما يسمح لك بتخصيص مظهره. يوفر البرنامج التعليمي مقتطفات من التعليمات البرمجية المصدر لـ C# لتوضيح الخطوات المطلوبة.

#### س: ما هي مساحات الأسماء التي أحتاج إلى استيرادها لهذا البرنامج التعليمي؟

ج: في ملف التعليمات البرمجية الذي تنوي إضافة محتوى HTML إليه، قم باستيراد مساحات الأسماء التالية في بداية الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### س: كيف يمكنني تحديد دليل المستند ومسار ملف الإخراج؟

 ج: في الكود، حدد موقع السطر`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدال`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

#### س: كيف أقوم بإنشاء كائن مستند؟

 ج: في الخطوة 4، ستقوم بإنشاء نسخة جديدة`Document` كائن باستخدام السطر التالي من التعليمات البرمجية:

```csharp
Document doc = new Document();
```

#### س: كيف يمكنني إضافة صفحة إلى المستند؟

 ج: في الخطوة 5، ستضيف صفحة جديدة إلى المستند باستخدام الملف`Add` طريقة`Pages` مجموعة:

```csharp
Page page = doc.Pages.Add();
```

#### س: كيف يمكنني ضبط محتوى HTML باستخدام DOM؟

 ج: في الخطوة 6، ستقوم بإنشاء`HtmlFragment` الكائن وقم بتعيين محتوى HTML المطلوب إليه. يتم تعيين محتوى HTML للمتغير`title`:

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

#### س: كيف يمكنني الكتابة فوق أنماط محتوى HTML؟

 ج: في الخطوة 7، ستقوم بالكتابة فوق أنماط محتوى HTML عن طريق تعديل ملف`TextState` خصائص`HtmlFragment` هدف. على سبيل المثال، يمكنك تغيير عائلة الخطوط إلى "Arial" وتعيين حجم الخط إلى 20:

```csharp
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

#### س: هل يمكنني ضبط هامش محتوى HTML؟

ج: نعم، في الخطوة 8، يمكنك ضبط الهوامش السفلية والعلوية لجزء HTML حسب الحاجة:

```csharp
title.Margin.Bottom = 10;
title.Margin.Top = 400;
```

#### س: كيف يمكنني إضافة HtmlFragment إلى مستند PDF؟

 ج: في الخطوة 9، ستضيف`HtmlFragment` هدف (`title`) إلى مجموعة الفقرات من الصفحة:

```csharp
page.Paragraphs.Add(title);
```

#### س: كيف يمكنني حفظ مستند PDF الناتج؟

 ج: بعد إضافة محتوى HTML وتخصيص أنماطه، استخدم ملف`Save` طريقة`Document` كائن لحفظ مستند PDF:

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

#### س: ما هي الوجبات الرئيسية من هذا البرنامج التعليمي؟

ج: باتباع هذا البرنامج التعليمي، تكون قد تعلمت بنجاح كيفية دمج محتوى HTML باستخدام نموذج كائن المستند (DOM) في Aspose.PDF لـ .NET. بالإضافة إلى ذلك، لقد اكتسبت القدرة على الكتابة فوق الأنماط لتخصيص مظهر محتوى HTML داخل مستند PDF الناتج.