---
title: أضف قائمة HTML المطلوبة إلى المستندات
linktitle: أضف قائمة HTMLOrdered إلى المستندات
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة قائمة HTML مرتبة إلى مستند باستخدام Aspose.PDF for .NET.
type: docs
weight: 30
url: /ar/net/programming-with-text/add-html-ordered-list-into-documents/
---

في هذا البرنامج التعليمي ، ستتعلم كيفية استخدام مكتبة Aspose.PDF for .NET لإضافة قائمة HTML مرتبة إلى مستند. يوضح الكود المقدم الخطوات اللازمة لإنجاز هذه المهمة.

## متطلبات
قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي مترجم C # آخر مثبت على جهازك.
- Aspose.PDF لمكتبة .NET. يمكنك تنزيله من موقع Aspose الرسمي أو استخدام مدير الحزم مثل NuGet لتثبيته.

## الخطوة 1: قم بإعداد المشروع
1. قم بإنشاء مشروع C # جديد في بيئة التطوير المفضلة لديك.
2. قم بإضافة مرجع إلى Aspose.PDF لمكتبة .NET.

## الخطوة 2: استيراد مساحات الأسماء المطلوبة
في ملف التعليمات البرمجية حيث تريد إضافة قائمة HTML المرتبة ، أضف ما يلي باستخدام التوجيهات في أعلى الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## الخطوة 3: قم بتعيين دليل المستند ومسار ملف الإخراج
 في الكود ، حدد موقع السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدالها`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل حيث يتم تخزين المستندات الخاصة بك.

 بعد ذلك ، حدد السطر الذي يقول`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` واستبدالها`"AddHTMLOrderedListIntoDocuments_out.pdf"` بالاسم الذي تريده لملف PDF الناتج الخاص بك.

## الخطوة 4: إنشاء كائن مستند جديد
 تجسيد ملف`Document` عن طريق إضافة السطر التالي من التعليمات البرمجية:

```csharp
Document doc = new Document();
```

## الخطوة 5: قم بإنشاء كائن HtmlFragment بمحتوى HTML
 تجسيد`HtmlFragment` مع محتوى HTML الذي تريد إضافته إلى المستند. في الكود المقدم ، يتم تعيين محتوى HTML للمتغير`t`. يمكنك تعديل محتوى HTML حسب الحاجة.

```csharp
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li >Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
```

## الخطوة 6: أضف صفحة إلى المستند
 أضف صفحة جديدة إلى المستند باستخدام ملف`Add` طريقة`Pages` مجموعة. في الكود المقدم ، يتم تخصيص الصفحة الجديدة للمتغير`page`.

```csharp
Page page = doc.Pages.Add();
```

## الخطوة 7: أضف جزء HtmlFragment إلى الصفحة
 أضف ال`HtmlFragment` على الصفحة باستخدام`Add` طريقة`Paragraphs` مجموعة.

```csharp
page.Paragraphs.Add(t);
```

## الخطوة 8: احفظ مستند PDF
 احفظ ملف PDF الناتج باستخدام ملف`Save` طريقة`Document` هدف. حدد مسار ملف الإخراج الذي قمت بتعيينه في الخطوة 3.

```csharp
doc.Save(outFile);
```

### نموذج التعليمات البرمجية المصدر لإضافة قائمة HTMLOrdered إلى المستندات باستخدام Aspose.PDF for .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// المسار إلى وثيقة الإخراج.
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
// إنشاء كائن المستند
Document doc = new Document();
// إنشاء كائن HtmlFragment مع جزء HTML المقابل
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
// أضف صفحة في مجموعة الصفحات
Page page = doc.Pages.Add();
// إضافة HtmlFragment داخل الصفحة
page.Paragraphs.Add(t);
// حفظ ملف PDF الناتج
doc.Save(outFile);
```

## خاتمة
لقد نجحت في إضافة قائمة مرتبة بتنسيق HTML إلى مستند باستخدام Aspose.PDF لـ .NET. يمكن الآن العثور على ملف PDF الناتج في مسار ملف الإخراج المحدد.

تذكر تخصيص محتوى HTML وتعديل الكود وفقًا لمتطلباتك المحددة.