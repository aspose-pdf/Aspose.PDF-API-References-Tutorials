---
title: النص والصورة كفقرة
linktitle: النص والصورة كفقرة
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة نص وصورة كفقرات مضمنة في مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 530
url: /ar/net/programming-with-text/text-and-image-as-paragraph/
---

يشرح هذا البرنامج التعليمي كيفية إضافة نص وصورة كفقرات مضمنة في مستند PDF باستخدام Aspose.PDF for .NET. يوضح كود المصدر C # المقدم العملية خطوة بخطوة.

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
using Aspose.Pdf.Drawing;
```

## الخطوة 3: قم بتعيين المسار إلى دليل المستند

 عيّن المسار إلى دليل المستند الخاص بك باستخدام ملف`dataDir` عامل:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 يستبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستند الخاص بك.

## الخطوة 4: قم بإنشاء مستند وصفحة جديدتين

 إنشاء ملف`Document` كائن وإضافة صفحة إلى مجموعة صفحاته:

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## الخطوة 5: قم بإنشاء جزء نص وإضافته كفقرة

 إنشاء`TextFragment`كائن وإضافته إلى مجموعة فقرات الصفحة:

```csharp
TextFragment text = new TextFragment("Hello World.. ");
page.Paragraphs.Add(text);
```

## الخطوة 6: أضف صورة كفقرة مضمنة

 يخترع`Aspose.Pdf.Image` كائن وتعيينها كفقرة مضمنة بحيث تظهر مباشرة بعد الفقرة السابقة:

```csharp
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
image.IsInLineParagraph = true;
image.File = dataDir + "aspose-logo.jpg";
image.FixHeight = 30; // اختياري: اضبط ارتفاع الصورة
image.FixWidth = 100; // اختياري: اضبط عرض الصورة
page.Paragraphs.Add(image);
```

 يستبدل`"aspose-logo.jpg"` باستخدام اسم ملف الصورة الفعلي واضبط ارتفاع الصورة وعرضها الاختياريين حسب الرغبة.

## الخطوة 7: أضف جزء نص آخر كفقرة مضمنة

 أعد تهيئة ملف`TextFragment` كائن بمحتوى مختلف وإضافته كفقرة مضمنة:

```csharp
text = new TextFragment(" Hello Again..");
text.IsInLineParagraph = true;
page.Paragraphs.Add(text);
```

## الخطوة 8: احفظ مستند PDF

احفظ مستند PDF المعدل:

```csharp
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
```

 تأكد من استبداله`"TextAndImageAsParagraph_out.pdf"` باسم ملف الإخراج المطلوب.

### عينة من التعليمات البرمجية المصدر لـ Text And Image As Paragraph باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// مثيل المستند
Document doc = new Document();
// إضافة صفحة إلى مجموعة صفحات مثيل المستند
Page page = doc.Pages.Add();
// قم بإنشاء TextFragmnet
TextFragment text = new TextFragment("Hello World.. ");
// إضافة جزء نصي إلى مجموعة فقرات كائن الصفحة
page.Paragraphs.Add(text);
// قم بإنشاء مثيل صورة
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
// قم بتعيين الصورة كفقرة مضمنة بحيث تظهر بعد ذلك مباشرة
// كائن الفقرة السابقة (جزء نص)
image.IsInLineParagraph = true;
// حدد مسار ملف الصورة
image.File = dataDir + "aspose-logo.jpg";
// ضبط ارتفاع الصورة (اختياري)
image.FixHeight = 30;
// ضبط عرض الصورة (اختياري)
image.FixWidth = 100;
//إضافة صورة إلى مجموعة فقرات كائن الصفحة
page.Paragraphs.Add(image);
// إعادة تهيئة كائن TextFragment بمحتويات مختلفة
text = new TextFragment(" Hello Again..");
// قم بتعيين TextFragment كفقرة مضمنة
text.IsInLineParagraph = true;
// أضف TextFragment الذي تم إنشاؤه حديثًا إلى مجموعة فقرات الصفحة
page.Paragraphs.Add(text);
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nText and image added successfully as an inline paragraphs.\nFile saved at " + dataDir);
```

## خاتمة

تهانينا! لقد تعلمت بنجاح كيفية إضافة نص وصورة كفقرات مضمنة في مستند PDF باستخدام Aspose.PDF for .NET. قدم هذا البرنامج التعليمي دليلاً تفصيليًا ، بدءًا من إعداد المشروع وحتى حفظ المستند المعدل. يمكنك الآن دمج هذا الرمز في مشاريع C # الخاصة بك لتخصيص تنسيق النص والصور في ملفات PDF.