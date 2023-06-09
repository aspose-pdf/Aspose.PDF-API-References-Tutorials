---
title: أضف HTML باستخدام DOM والكتابة فوق
linktitle: أضف HTML باستخدام DOM والكتابة فوق
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة محتوى HTML باستخدام DOM في Aspose.PDF for .NET.
type: docs
weight: 50
url: /ar/net/programming-with-text/add-html-using-dom-and-overwrite/
---

سيرشدك هذا البرنامج التعليمي خلال عملية إضافة محتوى HTML باستخدام DOM (نموذج كائن المستند) في Aspose.PDF for .NET. بالإضافة إلى ذلك ، سوف تتعلم كيفية الكتابة فوق الأنماط لمحتوى HTML. يوضح كود المصدر C # المقدم الخطوات الضرورية.

## متطلبات
قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي مترجم C # آخر مثبت على جهازك.
- Aspose.PDF لمكتبة .NET. يمكنك تنزيله من موقع Aspose الرسمي أو استخدام مدير الحزم مثل NuGet لتثبيته.

## الخطوة 1: قم بإعداد المشروع
1. قم بإنشاء مشروع C # جديد في بيئة التطوير المفضلة لديك.
2. قم بإضافة مرجع إلى Aspose.PDF لمكتبة .NET.

## الخطوة 2: استيراد مساحات الأسماء المطلوبة
في ملف التعليمات البرمجية حيث تريد إضافة محتوى HTML ، أضف ما يلي باستخدام التوجيهات في أعلى الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## الخطوة 3: قم بتعيين دليل المستند ومسار ملف الإخراج
 في الكود ، حدد موقع السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدالها`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل حيث يتم تخزين المستندات الخاصة بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 4: إنشاء كائن مستند جديد
 تجسيد ملف`Document` عن طريق إضافة السطر التالي من التعليمات البرمجية:

```csharp
Document doc = new Document();
```

## الخطوة 5: أضف صفحة إلى المستند
 أضف صفحة جديدة إلى المستند باستخدام ملف`Add` طريقة`Pages` مجموعة. في الكود المقدم ، يتم تخصيص الصفحة الجديدة للمتغير`page`.

```csharp
Page page = doc.Pages.Add();
```

## الخطوة 6: إنشاء HtmlFragment مع محتوى HTML
 تجسيد`HtmlFragment` كائن وتوفير محتوى HTML المطلوب. في الكود المقدم ، يتم تعيين محتوى HTML للمتغير`title`. يمكنك تعديل محتوى HTML حسب الحاجة.

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

## الخطوة 7: الكتابة فوق أنماط محتوى HTML
 للكتابة فوق أنماط محتوى HTML ، يمكنك تعديل ملف`TextState` خصائص`HtmlFragment`هدف. في الكود المقدم ، تم تغيير عائلة الخط إلى "Arial" وضبط حجم الخط على 20.

```csharp
title. TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

## الخطوة 8: ضبط معلومات الهامش
اضبط الهوامش السفلية والعلوية لجزء HTML إذا لزم الأمر. في الكود المقدم ، تم تعيين الهامش السفلي على 10 والهامش العلوي مضبوطًا على 400.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 400;
```

## الخطوة 9: أضف جزء HtmlFragment إلى الصفحة
 أضف ال`HtmlFragment` تعترض على مجموعة فقرات الصفحة.

```csharp
page.Paragraphs.Add(title);
```

## الخطوة 10: احفظ مستند PDF
 احفظ مستند PDF باستخدام ملف`Save` طريقة`Document` هدف. حدد مسار ملف الإخراج الذي قمت بتعيينه في الخطوة 3.

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

### نموذج التعليمات البرمجية المصدر لإضافة HTMLUsing DOMA and Overwrite باستخدام Aspose.PDF for .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// إنشاء كائن المستند
Document doc = new Document();
// أضف صفحة إلى مجموعة صفحات من ملف PDF
Page page = doc.Pages.Add();
// إنشاء HtmlFragment مع محتويات HTML
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
//ستتم إعادة تعيين عائلة الخطوط من "Verdana" إلى "Arial"
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
// تعيين معلومات الهامش السفلي
title.Margin.Bottom = 10;
// تعيين معلومات الهامش العلوي
title.Margin.Top = 400;
// أضف جزء HTML إلى مجموعة فقرات من الصفحة
page.Paragraphs.Add(title);
// احفظ ملف PDF
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
// احفظ ملف PDF
doc.Save(dataDir);
```

## خاتمة
لقد نجحت في إضافة محتوى HTML باستخدام DOM في Aspose.PDF لـ .NET والكتابة فوق أنماط محتوى HTML. يمكن الآن العثور على ملف PDF الناتج في مسار ملف الإخراج المحدد.