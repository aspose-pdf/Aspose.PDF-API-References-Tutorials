---
title: إضافة قائمة HTML مرتبة إلى المستندات
linktitle: إضافة قائمة HTMLOrdered إلى المستندات
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية إضافة قائمة مرتبة HTML إلى مستند باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 30
url: /ar/net/programming-with-text/add-html-ordered-list-into-documents/
---
في هذا البرنامج التعليمي، سوف تتعلم كيفية استخدام مكتبة Aspose.PDF for .NET لإضافة قائمة مرتبة بتنسيق HTML إلى مستند. يوضح الكود المقدم الخطوات اللازمة لإنجاز هذه المهمة.

## متطلبات
قبل أن تبدأ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي مُجمِّع C# آخر مُثبت على جهازك.
- مكتبة Aspose.PDF لـ .NET. يمكنك تنزيلها من موقع Aspose الرسمي أو استخدام مدير حزم مثل NuGet لتثبيتها.

## الخطوة 1: إعداد المشروع
1. قم بإنشاء مشروع C# جديد في بيئة التطوير المفضلة لديك.
2. أضف مرجعًا إلى مكتبة Aspose.PDF لـ .NET.

## الخطوة 2: استيراد المساحات المطلوبة
في ملف الكود الذي تريد إضافة قائمة HTML المرتبة إليه، أضف ما يلي باستخدام التوجيهات في أعلى الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## الخطوة 3: تعيين دليل المستند ومسار ملف الإخراج
 في الكود، حدد السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدالها`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل الذي يتم تخزين مستنداتك فيه.

 بعد ذلك، حدد السطر الذي يقول`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` واستبدالها`"AddHTMLOrderedListIntoDocuments_out.pdf"` مع الاسم المطلوب لملف PDF الناتج.

## الخطوة 4: إنشاء كائن مستند جديد
 إنشاء مثيل جديد`Document` الكائن عن طريق إضافة سطر التعليمات البرمجية التالي:

```csharp
Document doc = new Document();
```

## الخطوة 5: إنشاء كائن HtmlFragment بمحتوى HTML
 إنشاء مثيل`HtmlFragment` الكائن الذي يحتوي على محتوى HTML الذي تريد إضافته إلى المستند. في الكود المقدم، يتم تعيين محتوى HTML للمتغير`t`يمكنك تعديل محتوى HTML حسب الحاجة.

```csharp
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li >Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
```

## الخطوة 6: إضافة صفحة إلى المستند
 أضف صفحة جديدة إلى المستند باستخدام`Add` طريقة`Pages`المجموعة. في الكود المقدم، يتم تعيين الصفحة الجديدة للمتغير`page`.

```csharp
Page page = doc.Pages.Add();
```

## الخطوة 7: أضف HtmlFragment إلى الصفحة
 أضف`HtmlFragment` الاعتراض على الصفحة باستخدام`Add` طريقة`Paragraphs` مجموعة.

```csharp
page.Paragraphs.Add(t);
```

## الخطوة 8: احفظ مستند PDF
 احفظ ملف PDF الناتج باستخدام`Save` طريقة`Document` حدد مسار ملف الإخراج الذي قمت بتعيينه في الخطوة 3.

```csharp
doc.Save(outFile);
```

### نموذج كود المصدر لإضافة قائمة HTMLOrdered إلى المستندات باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// المسار إلى المستند الناتج.
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
// إنشاء كائن مستند
Document doc = new Document();
// إنشاء كائن HtmlFragment باستخدام جزء HTML المقابل
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
// إضافة صفحة إلى مجموعة الصفحات
Page page = doc.Pages.Add();
// إضافة HtmlFragment داخل الصفحة
page.Paragraphs.Add(t);
// حفظ ملف PDF الناتج
doc.Save(outFile);
```

## خاتمة
لقد نجحت في إضافة قائمة مرتبة بتنسيق HTML إلى مستند باستخدام Aspose.PDF لـ .NET. يمكنك الآن العثور على ملف PDF الناتج في مسار ملف الإخراج المحدد.

تذكر أن تقوم بتخصيص محتوى HTML وتعديل الكود وفقًا لمتطلباتك المحددة.

### الأسئلة الشائعة

#### س: ما هو الغرض من هذا البرنامج التعليمي؟

ج: يهدف هذا البرنامج التعليمي إلى إرشادك خلال عملية إضافة قائمة مرتبة بتنسيق HTML إلى مستند باستخدام مكتبة Aspose.PDF for .NET. وهو يوفر تعليمات خطوة بخطوة ومقاطع تعليمات برمجية لمساعدتك في تحقيق هذه المهمة.

#### س: ما هي المساحات الأسماء التي أحتاج إلى استيرادها لهذا البرنامج التعليمي؟

أ: تحتاج إلى استيراد المساحات التالية في الجزء العلوي من ملف التعليمات البرمجية الخاص بك:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### س: كيف يمكنني تحديد دليل المستند ومسار ملف الإخراج؟

 أ: في الكود، حدد السطر`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدالها`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستند الخاص بك. أيضًا، ابحث عن السطر`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` واستبدالها`"AddHTMLOrderedListIntoDocuments_out.pdf"` مع اسم ملف PDF الناتج المطلوب.

#### س: هل يمكنني تخصيص محتوى HTML المضاف إلى المستند؟

 أ: بالتأكيد! في الخطوة 5، ستقوم بإنشاء`HtmlFragment` كائن اسمه`t` الذي يحتوي على محتوى HTML. يمكنك تعديل محتوى HTML داخل علامات الاقتباس العكسية لتناسب متطلباتك.

#### س: كيف أضيف قائمة HTML المرتبة إلى صفحة في المستند؟

 أ: في الخطوة 7، ستضيف`HtmlFragment` هدف (`t` ) إلى الصفحة باستخدام`Add` طريقة`Paragraphs`المجموعة. سيؤدي هذا إلى دمج القائمة المرتبة بتنسيق HTML في المستند بسلاسة.

#### س: كيف أحفظ مستند PDF الناتج؟

 ج: بعد إضافة محتوى HTML وترتيبه على الصفحة، يمكنك حفظ مستند PDF باستخدام`Save` طريقة`Document` تأكد من توفير مسار ملف الإخراج الصحيح الذي قمت بتعيينه مسبقًا.

#### س: هل يمكنك تقديم ملخص لرمز المصدر للرجوع إليه؟

ج: بالتأكيد! فيما يلي نسخة مختصرة من الكود المصدري النموذجي المقدم في هذا البرنامج التعليمي:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
Document doc = new Document();
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
Page page = doc.Pages.Add();
page.Paragraphs.Add(t);
doc.Save(outFile);
```

#### س: ما هو أهم ما يمكن تعلمه من هذا البرنامج التعليمي؟

ج: باتباع هذا البرنامج التعليمي، تكون قد تعلمت بنجاح كيفية الاستفادة من مكتبة Aspose.PDF for .NET لدمج قائمة مرتبة بتنسيق HTML في مستند. ويمكن تطبيق هذه المعرفة المكتسبة حديثًا لتحسين عمليات إنشاء المستندات ومعالجتها.