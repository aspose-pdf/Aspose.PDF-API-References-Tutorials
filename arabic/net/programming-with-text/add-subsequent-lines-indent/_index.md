---
title: إضافة أسطر لاحقة مسافة بادئة
linktitle: إضافة أسطر لاحقة مسافة بادئة
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة مسافة بادئة للأسطر اللاحقة إلى النص باستخدام Aspose.PDF for .NET.
type: docs
weight: 60
url: /ar/net/programming-with-text/add-subsequent-lines-indent/
---

سيرشدك هذا البرنامج التعليمي خلال عملية إضافة مسافة بادئة للأسطر اللاحقة إلى النص باستخدام Aspose.PDF for .NET. يوضح كود المصدر C # المقدم الخطوات الضرورية.

## متطلبات
قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي مترجم C # آخر مثبت على جهازك.
- Aspose.PDF لمكتبة .NET. يمكنك تنزيله من موقع Aspose الرسمي أو استخدام مدير الحزم مثل NuGet لتثبيته.

## الخطوة 1: قم بإعداد المشروع
1. قم بإنشاء مشروع C # جديد في بيئة التطوير المفضلة لديك.
2. قم بإضافة مرجع إلى Aspose.PDF لمكتبة .NET.

## الخطوة 2: استيراد مساحات الأسماء المطلوبة
في ملف التعليمات البرمجية حيث تريد إضافة مسافة بادئة للأسطر اللاحقة ، أضف ما يلي باستخدام التوجيه في أعلى الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## الخطوة 3: قم بتعيين دليل المستند
 في الكود ، حدد موقع السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدالها`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل حيث يتم تخزين المستندات الخاصة بك.

## الخطوة 4: إنشاء كائن مستند جديد
 تجسيد ملف`Document` عن طريق إضافة السطر التالي من التعليمات البرمجية:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

## الخطوة 5: أضف صفحة إلى المستند
 أضف صفحة جديدة إلى المستند باستخدام ملف`Add` طريقة`Pages` مجموعة. في الكود المقدم ، يتم تخصيص الصفحة الجديدة للمتغير`page`.

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

## الخطوة 6: قم بإنشاء جزء نص بمسافة بادئة للأسطر التالية
 تجسيد أ`TextFragment` الكائن وتقديم النص المطلوب. في الكود المقدم ، يتم تعيين النص إلى المتغير`text` . ثم قم بالتهيئة`TextFormattingOptions` ل`TextFragment` وحدد ال`SubsequentLinesIndent` قيمة.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog." );
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
     SubsequentLinesIndent = 20
};
```

## الخطوة 7: أضف جزء النص إلى الصفحة
 أضف ال`TextFragment` تعترض على مجموعة فقرات الصفحة.

```csharp
page.Paragraphs.Add(text);
```

## الخطوة 8: كرر الخطوتين 6 و 7 للحصول على أسطر إضافية
لإضافة أسطر لاحقة بنفس المسافة البادئة ، كرر الخطوتين 6 و 7 لكل سطر. قم بتحديث محتوى النص حسب الحاجة.

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
 احفظ مستند PDF باستخدام ملف`Save` طريقة`Document` هدف. حدد مسار ملف الإخراج.

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### نموذج التعليمات البرمجية المصدر لإضافة مسافة بادئة للخطوط اللاحقة باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// إنشاء كائن مستند جديد
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = document.Pages.Add();
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog.");
//قم بتهيئة TextFormattingOptions لجزء النص وحدد قيمة SubsequentLinesIndent
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