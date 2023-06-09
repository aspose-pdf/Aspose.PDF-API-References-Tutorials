---
title: نص البحث ورسم مستطيل
linktitle: نص البحث ورسم مستطيل
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية البحث عن نص في ملف PDF ، ورسم مستطيلات حول النص الموجود ، وحفظ المستند المعدل باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 460
url: /ar/net/programming-with-text/search-text-and-draw-rectangle/
---

يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.PDF لـ .NET للبحث عن نص معين في مستند PDF ورسم مستطيل حول النص الموجود وحفظ المستند المعدل. يوضح كود المصدر C # المقدم العملية خطوة بخطوة.

## المتطلبات الأساسية

قبل الشروع في البرنامج التعليمي ، تأكد من أن لديك ما يلي:

- المعرفة الأساسية بلغة البرمجة C #.
- تثبيت Aspose.PDF لمكتبة .NET. يمكنك الحصول عليه من موقع Aspose أو استخدام NuGet لتثبيته في مشروعك.

## الخطوة 1: قم بإعداد المشروع

ابدأ بإنشاء مشروع C # جديد في بيئة التطوير المتكاملة المفضلة لديك (IDE) وأضف مرجعًا إلى Aspose.PDF لمكتبة .NET.

## الخطوة 2: استيراد مساحات الأسماء الضرورية

أضف التعليمات التالية باستخدام التوجيهات في بداية ملف C # لاستيراد مساحات الأسماء المطلوبة:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
```

## الخطوة 3: قم بتعيين المسار إلى دليل المستند

 عيّن المسار إلى دليل المستند الخاص بك باستخدام ملف`dataDir` عامل:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 يستبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستند الخاص بك.

## الخطوة 4: قم بتحميل مستند PDF

 قم بتحميل مستند PDF باستخدام ملف`Document` فصل:

```csharp
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 يستبدل`"SearchAndGetTextFromAll.pdf"` بالاسم الفعلي لملف PDF الخاص بك.

## الخطوة 5: إنشاء TextFragmentAbsorber

 إنشاء`TextFragmentAbsorber` كائن للعثور على جميع حالات إدخال عبارة البحث:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 يستبدل`@"[\S]+"` بنمط التعبير العادي الذي تريده.

## الخطوة 6: تمكين البحث عن التعبير العادي

تمكين البحث عن التعبير العادي عن طريق تعيين`TextSearchOptions` خاصية الممتص:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

## الخطوة 7: ابحث في جميع الصفحات

قبول الممتص لجميع صفحات المستند:

```csharp
document.Pages.Accept(textAbsorber);
```

## الخطوة 8: ارسم مستطيلاً حول النص الموجود

 إنشاء`PdfContentEditor` كائن وحلقة خلال أجزاء النص المستردة ، ورسم مستطيل حول كل مقطع نص:

```csharp
var editor = new PdfContentEditor(document);
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
    }
}
```

## الخطوة 9: احفظ المستند المعدل

احفظ المستند المعدل:

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

 تأكد من استبداله`"SearchTextAndDrawRectangle_out.pdf"` باسم ملف الإخراج المطلوب.

### عينة من التعليمات البرمجية المصدر للبحث عن نص ورسم مستطيل باستخدام Aspose.PDF for .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// قم بإنشاء كائن TextAbsorber للعثور على جميع العبارات المطابقة للتعبير العادي
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
document.Pages.Accept(textAbsorber); 
var editor = new PdfContentEditor(document); 
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
			DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
	}
}
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
Console.WriteLine("\nRectangle drawn successfully on searched text.\nFile saved at " + dataDir);
```

## خاتمة

تهانينا! لقد تعلمت بنجاح كيفية البحث عن نص معين في مستند PDF ، ورسم مستطيل حول النص الذي تم العثور عليه ، وحفظ المستند المعدل باستخدام Aspose.PDF for .NET. قدم هذا البرنامج التعليمي دليلاً تفصيليًا ، بدءًا من إعداد المشروع وحتى تنفيذ الإجراءات المطلوبة. يمكنك الآن دمج هذا الرمز في مشاريع C # الخاصة بك لمعالجة النص ورسم المستطيلات في ملفات PDF.