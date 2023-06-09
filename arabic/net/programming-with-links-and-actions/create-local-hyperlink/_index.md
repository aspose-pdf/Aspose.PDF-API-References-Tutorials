---
title: إنشاء ارتباط تشعبي محلي
linktitle: إنشاء ارتباط تشعبي محلي
second_title: Aspose.PDF لمرجع .NET API
description: يمكنك بسهولة إنشاء ارتباطات تشعبية محلية في ملف PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 40
url: /ar/net/programming-with-links-and-actions/create-local-hyperlink/
---

يتيح لك إنشاء ارتباطات تشعبية محلية في ملف PDF إنشاء روابط قابلة للنقر تنقل المستخدمين إلى صفحات أخرى في نفس مستند PDF. باستخدام Aspose.PDF for .NET ، يمكنك بسهولة إنشاء مثل هذه الروابط باتباع التعليمات البرمجية المصدر التالية:

## الخطوة 1: استيراد المكتبات المطلوبة

قبل أن تبدأ ، تحتاج إلى استيراد المكتبات اللازمة لمشروع C # الخاص بك. فيما يلي توجيه الاستيراد الضروري:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.InteractiveFeatures;
```

## الخطوة 2: حدد المسار إلى مجلد المستندات

 في هذه الخطوة ، تحتاج إلى تحديد المسار إلى المجلد حيث تريد حفظ ملف PDF الناتج. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود التالي بالمسار الفعلي لمجلد المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 3: إنشاء مثيل من المستند

 سنقوم بإنشاء مثيل لـ`Document` فئة لتمثيل وثيقة PDF الخاصة بنا. هذا هو الكود المقابل:

```csharp
Document doc = new Document();
```

## الخطوة 4: إضافة صفحة ونص مع ارتباطات تشعبية

في هذه الخطوة ، سنقوم بإضافة صفحة إلى مستند PDF الخاص بنا وإضافة بعض النصوص التي تحتوي على ارتباطات تشعبية محلية. سنحدد الصفحات المستهدفة لكل رابط. هذا هو الكود المقابل:

```csharp
Page page = doc.Pages.Add();

TextFragment text = new TextFragment("Link to page 7");
LocalHyperlink link = new LocalHyperlink();
link.TargetPageNumber = 7;
text. Hyperlink = link;
page.Paragraphs.Add(text);

text = new TextFragment("Link to page 1");
text. IsInNewPage = true;
link = new LocalHyperlink();
link.TargetPageNumber = 1;
text. Hyperlink = link;
page.Paragraphs.Add(text);
```

## الخطوة 5: احفظ المستند المحدث

الآن دعنا نحفظ ملف PDF المحدث باستخدام امتداد`Save` طريقة`doc` هدف. هذا هو الكود المقابل:

```csharp
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
doc.Save(dataDir);
```

### نموذج التعليمات البرمجية المصدر لـ Create Local Hyperlink باستخدام Aspose.PDF for .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// إنشاء مثيل المستند
Document doc = new Document();
// أضف صفحة إلى مجموعة صفحات من ملف PDF
Page page = doc.Pages.Add();
// إنشاء مثيل نص جزء
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("link page number test to page 7");
// إنشاء مثيل ارتباط تشعبي محلي
Aspose.Pdf.LocalHyperlink link = new Aspose.Pdf.LocalHyperlink();
// تعيين الصفحة الهدف لمثيل الارتباط
link.TargetPageNumber = 7;
// تعيين ارتباط تشعبي TextFragment
text.Hyperlink = link;
// إضافة نص إلى مجموعة فقرات الصفحة
page.Paragraphs.Add(text);
// إنشاء مثيل TextFragment جديد
text = new TextFragment("link page number test to page 1");
// يجب إضافة TextFragment على صفحة جديدة
text.IsInNewPage = true;
// إنشاء مثيل ارتباط تشعبي محلي آخر
link = new LocalHyperlink();
// تعيين الصفحة الهدف للارتباط التشعبي الثاني
link.TargetPageNumber = 1;
// تعيين ارتباط لـ TextFragment الثانية
text.Hyperlink = link;
// إضافة نص إلى مجموعة فقرات كائن الصفحة
page.Paragraphs.Add(text);    
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
// احفظ المستند المحدث
doc.Save(dataDir);
Console.WriteLine("\nLocal hyperlink created successfully.\nFile saved at " + dataDir);            
```

## خاتمة

تهنئة ! الآن لديك دليل خطوة بخطوة لإنشاء ارتباطات تشعبية محلية في ملف PDF باستخدام Aspose.PDF for .NET. يمكنك استخدام هذا الرمز لإنشاء روابط قابلة للنقر تنقل المستخدمين إلى صفحات أخرى في نفس المستند.

تأكد من مراجعة وثائق Aspose.PDF الرسمية لمزيد من المعلومات حول ميزات الارتباط التشعبي المتقدمة.