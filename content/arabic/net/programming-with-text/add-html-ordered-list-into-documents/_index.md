---
title: إضافة قائمة مرتبة بتنسيق HTML إلى المستندات
linktitle: إضافة قائمة HTMLOrdered إلى المستندات
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة قائمة مرتبة بتنسيق HTML إلى مستند باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 30
url: /ar/net/programming-with-text/add-html-ordered-list-into-documents/
---
ستتعلم في هذا البرنامج التعليمي كيفية استخدام مكتبة Aspose.PDF for .NET لإضافة قائمة HTML مرتبة إلى مستند. يوضح الكود المقدم الخطوات اللازمة لإنجاز هذه المهمة.

## متطلبات
قبل أن تبدأ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي مترجم C# آخر مثبت على جهازك.
- Aspose.PDF لمكتبة .NET. يمكنك تنزيله من موقع Aspose الرسمي أو استخدام مدير الحزم مثل NuGet لتثبيته.

## الخطوة 1: إعداد المشروع
1. قم بإنشاء مشروع C# جديد في بيئة التطوير المفضلة لديك.
2. قم بإضافة مرجع إلى Aspose.PDF لمكتبة .NET.

## الخطوة 2: استيراد مساحات الأسماء المطلوبة
في ملف التعليمات البرمجية الذي تريد إضافة قائمة HTML المرتبة إليه، أضف ما يلي باستخدام التوجيهات الموجودة في أعلى الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## الخطوة 3: قم بتعيين دليل المستند ومسار ملف الإخراج
 في الكود، حدد السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدال`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل حيث يتم تخزين المستندات الخاصة بك.

 بعد ذلك، حدد موقع السطر الذي يقول`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` واستبدال`"AddHTMLOrderedListIntoDocuments_out.pdf"` بالاسم المطلوب لملف PDF الناتج.

## الخطوة 4: إنشاء كائن مستند جديد
 إنشاء مثيل جديد`Document` كائن عن طريق إضافة السطر التالي من التعليمات البرمجية:

```csharp
Document doc = new Document();
```

## الخطوة 5: إنشاء كائن HtmlFragment بمحتوى HTML
 إنشاء مثيل ل`HtmlFragment` كائن يحتوي على محتوى HTML الذي تريد إضافته إلى المستند. في التعليمات البرمجية المقدمة، يتم تعيين محتوى HTML للمتغير`t`. يمكنك تعديل محتوى HTML حسب الحاجة.

```csharp
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li >Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
```

## الخطوة 6: إضافة صفحة إلى المستند
 أضف صفحة جديدة إلى المستند باستخدام`Add` طريقة`Pages`مجموعة. في الكود المقدم، يتم تعيين الصفحة الجديدة للمتغير`page`.

```csharp
Page page = doc.Pages.Add();
```

## الخطوة 7: أضف HtmlFragment إلى الصفحة
 أضف ال`HtmlFragment` الاعتراض على الصفحة باستخدام`Add` طريقة`Paragraphs` مجموعة.

```csharp
page.Paragraphs.Add(t);
```

## الخطوة 8: احفظ مستند PDF
 احفظ ملف PDF الناتج باستخدام ملف`Save` طريقة`Document` هدف. حدد مسار ملف الإخراج الذي قمت بتعيينه في الخطوة 3.

```csharp
doc.Save(outFile);
```

### نموذج التعليمات البرمجية المصدر لإضافة قائمة HTMLOrdered إلى المستندات باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// المسار إلى مستند الإخراج.
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
// إنشاء مثيل لكائن المستند
Document doc = new Document();
// إنشاء كائن HtmlFragment مع جزء HTML المطابق
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
// إضافة صفحة في مجموعة الصفحات
Page page = doc.Pages.Add();
// أضف HtmlFragment داخل الصفحة
page.Paragraphs.Add(t);
// حفظ ملف PDF الناتج
doc.Save(outFile);
```

## خاتمة
لقد قمت بنجاح بإضافة قائمة HTML مرتبة إلى مستند باستخدام Aspose.PDF لـ .NET. يمكن الآن العثور على ملف PDF الناتج في مسار ملف الإخراج المحدد.

تذكر تخصيص محتوى HTML وضبط الكود وفقًا لمتطلباتك المحددة.

### الأسئلة الشائعة

#### س: ما هو الغرض من هذا البرنامج التعليمي؟

ج: يهدف هذا البرنامج التعليمي إلى إرشادك خلال عملية إضافة قائمة HTML مرتبة إلى مستند باستخدام مكتبة Aspose.PDF for .NET. فهو يوفر إرشادات خطوة بخطوة ومقتطفات التعليمات البرمجية لمساعدتك في تحقيق هذه المهمة.

#### س: ما هي مساحات الأسماء التي أحتاج إلى استيرادها لهذا البرنامج التعليمي؟

ج: تحتاج إلى استيراد مساحات الأسماء التالية في أعلى ملف التعليمات البرمجية الخاص بك:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### س: كيف يمكنني تحديد دليل المستند ومسار ملف الإخراج؟

 ج: في الكود، حدد موقع السطر`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدال`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى دليل المستندات الخاص بك. ابحث أيضًا عن الخط`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` واستبدال`"AddHTMLOrderedListIntoDocuments_out.pdf"` مع اسم ملف PDF الناتج المطلوب.

#### س: هل يمكنني تخصيص محتوى HTML الذي تتم إضافته إلى المستند؟

 ج: بالتأكيد! في الخطوة 5، ستقوم بإنشاء`HtmlFragment` الكائن المسمى`t` الذي يحمل محتوى HTML. يمكنك تعديل محتوى HTML داخل العلامات الخلفية ليناسب متطلباتك.

#### س: كيف يمكنني إضافة قائمة HTML المرتبة إلى صفحة في المستند؟

 ج: في الخطوة 7، عليك إضافة`HtmlFragment` هدف (`t` ) إلى الصفحة باستخدام`Add` طريقة`Paragraphs`مجموعة. سيؤدي هذا إلى دمج قائمة HTML المطلوبة في المستند بسلاسة.

#### س: كيف يمكنني حفظ مستند PDF الناتج؟

 ج: بعد إضافة محتوى HTML وترتيبه على الصفحة، يمكنك حفظ مستند PDF باستخدام الملف`Save` طريقة`Document` هدف. تأكد من توفير مسار ملف الإخراج الصحيح الذي قمت بتعيينه مسبقًا.

#### س: هل يمكنك تقديم ملخص لنموذج التعليمات البرمجية المصدر كمرجع؟

ج: بالتأكيد! فيما يلي نسخة مختصرة من نموذج التعليمات البرمجية المصدر المقدم في هذا البرنامج التعليمي:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
Document doc = new Document();
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
Page page = doc.Pages.Add();
page.Paragraphs.Add(t);
doc.Save(outFile);
```

#### س: ما هي الوجبات الرئيسية من هذا البرنامج التعليمي؟

ج: باتباع هذا البرنامج التعليمي، تكون قد تعلمت بنجاح كيفية الاستفادة من مكتبة Aspose.PDF لـ .NET لدمج قائمة HTML مرتبة في مستند. يمكن تطبيق هذه المعرفة المكتشفة حديثًا لتحسين عمليات إنشاء المستندات ومعالجتها.