---
title: إضافة HTML باستخدام DOM وPDF
linktitle: إضافة HTML باستخدام DOM والكتابة فوقه
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية إضافة محتوى HTML باستخدام DOM والكتابة فوق PDF في Aspose.PDF لـ .NET.
type: docs
weight: 50
url: /ar/net/programming-with-text/add-html-using-dom-and-overwrite/
---
سيرشدك هذا البرنامج التعليمي خلال عملية إضافة محتوى HTML باستخدام DOM (نموذج كائن المستند) في Aspose.PDF لـ .NET. بالإضافة إلى ذلك، ستتعلم كيفية استبدال الأنماط لمحتوى HTML. يوضح كود المصدر C# المقدم الخطوات اللازمة.

## متطلبات
قبل أن تبدأ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي مُجمِّع C# آخر مُثبت على جهازك.
- مكتبة Aspose.PDF لـ .NET. يمكنك تنزيلها من موقع Aspose الرسمي أو استخدام مدير حزم مثل NuGet لتثبيتها.

## الخطوة 1: إعداد المشروع
1. قم بإنشاء مشروع C# جديد في بيئة التطوير المفضلة لديك.
2. أضف مرجعًا إلى مكتبة Aspose.PDF لـ .NET.

## الخطوة 2: استيراد المساحات المطلوبة
في ملف الكود الذي تريد إضافة محتوى HTML إليه، أضف ما يلي باستخدام التوجيهات في الجزء العلوي من الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## الخطوة 3: تعيين دليل المستند ومسار ملف الإخراج
 في الكود، حدد السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدالها`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل الذي يتم تخزين مستنداتك فيه.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 4: إنشاء كائن مستند جديد
 إنشاء مثيل جديد`Document` الكائن عن طريق إضافة سطر التعليمات البرمجية التالي:

```csharp
Document doc = new Document();
```

## الخطوة 5: إضافة صفحة إلى المستند
 أضف صفحة جديدة إلى المستند باستخدام`Add` طريقة`Pages` المجموعة. في الكود المقدم، يتم تعيين الصفحة الجديدة للمتغير`page`.

```csharp
Page page = doc.Pages.Add();
```

## الخطوة 6: إنشاء HtmlFragment بمحتوى HTML
 إنشاء مثيل`HtmlFragment` الكائن وتوفير محتوى HTML المطلوب. في الكود المقدم، يتم تعيين محتوى HTML للمتغير`title`يمكنك تعديل محتوى HTML حسب الحاجة.

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

## الخطوة 7: استبدال الأنماط الخاصة بمحتوى HTML
 لاستبدال أنماط محتوى HTML، يمكنك تعديل`TextState` خصائص`HtmlFragment` في الكود المقدم، تم تغيير عائلة الخط إلى "Arial" وتم ضبط حجم الخط على 20.

```csharp
title. TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

## الخطوة 8: تعيين معلومات الهامش
اضبط الهوامش السفلية والعلوية لشظية HTML إذا لزم الأمر. في الكود المقدم، يتم تعيين الهامش السفلي على 10 والهامش العلوي على 400.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 400;
```

## الخطوة 9: أضف HtmlFragment إلى الصفحة
 أضف`HtmlFragment` الاعتراض على مجموعة الفقرات في الصفحة.

```csharp
page.Paragraphs.Add(title);
```

## الخطوة 10: احفظ مستند PDF
 احفظ مستند PDF باستخدام`Save` طريقة`Document` حدد مسار ملف الإخراج الذي قمت بتعيينه في الخطوة 3.

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

### عينة من كود المصدر لإضافة HTML باستخدام DOM والكتابة فوقها باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// إنشاء كائن مستند
Document doc = new Document();
// إضافة صفحة إلى مجموعة صفحات ملف PDF
Page page = doc.Pages.Add();
// إنشاء مثيل لـ HtmlFragment باستخدام عناصر HTML
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
//سيتم إعادة تعيين عائلة الخط من "Verdana" إلى "Arial"
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
// تعيين معلومات الهامش السفلي
title.Margin.Bottom = 10;
// تعيين معلومات الهامش العلوي
title.Margin.Top = 400;
// إضافة جزء HTML إلى مجموعة فقرات الصفحة
page.Paragraphs.Add(title);
// حفظ ملف PDF
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
// حفظ ملف PDF
doc.Save(dataDir);
```

## خاتمة
لقد نجحت في إضافة محتوى HTML باستخدام DOM في Aspose.PDF لـ .NET وقمت باستبدال الأنماط الخاصة بمحتوى HTML. يمكنك الآن العثور على ملف PDF الناتج في مسار ملف الإخراج المحدد.

### الأسئلة الشائعة

#### س: ما هو التركيز في هذا البرنامج التعليمي؟

ج: تم تصميم هذا البرنامج التعليمي لإرشادك خلال عملية إضافة محتوى HTML إلى مستند PDF باستخدام نموذج كائن المستند (DOM) في Aspose.PDF لـ .NET. بالإضافة إلى ذلك، سوف تتعلم كيفية استبدال الأنماط لمحتوى HTML، مما يسمح لك بتخصيص مظهره. يوفر البرنامج التعليمي مقتطفات من التعليمات البرمجية المصدرية بلغة C# لتوضيح الخطوات المطلوبة.

#### س: ما هي المساحات الأسماء التي أحتاج إلى استيرادها لهذا البرنامج التعليمي؟

أ: في ملف الكود الذي تنوي إضافة محتوى HTML إليه، قم باستيراد المساحات التالية في بداية الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### س: كيف يمكنني تحديد دليل المستند ومسار ملف الإخراج؟

 أ: في الكود، حدد السطر`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدالها`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستند الخاص بك.

#### س: كيف أقوم بإنشاء كائن مستند؟

 أ: في الخطوة 4، ستقوم بإنشاء مثيل جديد`Document` الكائن باستخدام سطر التعليمات البرمجية التالي:

```csharp
Document doc = new Document();
```

#### س: كيف أضيف صفحة إلى المستند؟

 أ: في الخطوة 5، ستضيف صفحة جديدة إلى المستند باستخدام`Add` طريقة`Pages` مجموعة:

```csharp
Page page = doc.Pages.Add();
```

#### س: كيف يمكنني تعيين محتوى HTML باستخدام DOM؟

 أ: في الخطوة 6، ستقوم بإنشاء`HtmlFragment` الكائن وتعيين محتوى HTML المطلوب إليه. يتم تعيين محتوى HTML إلى المتغير`title`:

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

#### س: كيف يمكنني استبدال أنماط محتوى HTML؟

 أ: في الخطوة 7، ستقوم باستبدال أنماط محتوى HTML عن طريق تعديل`TextState` خصائص`HtmlFragment`على سبيل المثال، يمكنك تغيير عائلة الخط إلى "Arial" وتعيين حجم الخط إلى 20:

```csharp
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

#### س: هل يمكنني تعديل هامش المحتوى HTML؟

ج: نعم، في الخطوة 8، يمكنك ضبط الهوامش السفلية والعلوية لشظية HTML حسب الحاجة:

```csharp
title.Margin.Bottom = 10;
title.Margin.Top = 400;
```

#### س: كيف أضيف HtmlFragment إلى مستند PDF؟

 أ: في الخطوة 9، ستضيف`HtmlFragment` هدف (`title`) إلى مجموعة فقرات الصفحة:

```csharp
page.Paragraphs.Add(title);
```

#### س: كيف أحفظ مستند PDF الناتج؟

 أ: بعد إضافة محتوى HTML وتخصيص أنماطه، استخدم`Save` طريقة`Document` كائن لحفظ مستند PDF:

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

#### س: ما هو أهم ما يمكن تعلمه من هذا البرنامج التعليمي؟

ج: باتباع هذا البرنامج التعليمي، تكون قد تعلمت بنجاح كيفية دمج محتوى HTML باستخدام نموذج كائن المستند (DOM) في Aspose.PDF لـ .NET. بالإضافة إلى ذلك، اكتسبت القدرة على الكتابة فوق الأنماط لتخصيص مظهر محتوى HTML داخل مستند PDF الناتج.