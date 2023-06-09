---
title: أضف ارتباط تشعبي
linktitle: أضف ارتباط تشعبي
second_title: Aspose.PDF لمرجع .NET API
description: أضف ارتباطات تشعبية تفاعلية بسهولة في ملفات PDF الخاصة بك باستخدام Aspose.PDF for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-links-and-actions/add-hyperlink/
---

تسمح لك إضافة ارتباطات تشعبية في مستند PDF بإنشاء ارتباطات تشعبية تفاعلية لصفحات أو مواقع ويب أو وجهات أخرى في المستند. باستخدام Aspose.PDF for .NET ، يمكنك بسهولة إضافة ارتباطات تشعبية باتباع التعليمات البرمجية المصدر التالية:

## الخطوة 1: استيراد المكتبات المطلوبة

قبل أن تبدأ ، تحتاج إلى استيراد المكتبات اللازمة لمشروع C # الخاص بك. فيما يلي توجيه الاستيراد الضروري:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

## الخطوة 2: حدد المسار إلى مجلد المستندات

 في هذه الخطوة ، تحتاج إلى تحديد المسار إلى المجلد الذي يحتوي على ملف PDF الذي تريد إضافة ارتباط تشعبي إليه. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود التالي بالمسار الفعلي لمجلد المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 3: افتح مستند PDF

سنفتح الآن مستند PDF الذي نريد إضافة ارتباط تشعبي إليه باستخدام الكود التالي:

```csharp
Document document = new Document(dataDir + "AddHyperlink.pdf");
```

## الخطوة 4: إنشاء ارتباط

 في هذه الخطوة ، سننشئ ارتباطًا تشعبيًا باستخدام الامتداد`LinkAnnotation` حاشية. ملاحظة. سنحدد تفاصيل الاتصال ومنطقة الارتباط ونوع الارتباط ومحتوى الارتباط. هذا هو الكود المقابل:

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
Border border = new Border(link);
border. Width = 0;
link. Border = border;
link. Action = new GoToURIAction("www.aspose.com");
page.Annotations.Add(link);
```

## الخطوة 5: أضف نصًا إضافيًا

 بالإضافة إلى الارتباط التشعبي ، يمكننا أيضًا إضافة نص إضافي باستخدام الامتداد`FreeTextAnnotation` حاشية. ملاحظة. سنحدد الإحداثيات ومظهر النص ومحتوى النص. هذا هو الكود المقابل:

```csharp
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(document.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), new DefaultAppearance(Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman"), 10, System .Drawing.Color.Blue));
textAnnotation.Contents = "Link to Aspose website";
textAnnotation. Border = border;
document.Pages[1].Annotations.Add(textAnnotation);
```

## الخطوة 6: احفظ الملف المحدث

الآن دعنا نحفظ ملف PDF المحدث باستخدام امتداد`Save` طريقة`document` هدف. هذا هو الكود المقابل:

```csharp
dataDir = dataDir + "AddHyperlink_out.pdf";
document. Save(dataDir);
```

### نموذج التعليمات البرمجية المصدر لإضافة ارتباط تشعبي باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document document = new Document(dataDir + "AddHyperlink.pdf");
// إنشاء رابط
Page page = document.Pages[1];
//إنشاء رابط التعليق التوضيحي
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
// إنشاء كائن حد لـ LinkAnnotation
Border border = new Border(link);
// اضبط قيمة عرض الحد على 0
border.Width = 0;
// قم بتعيين حدود LinkAnnotation
link.Border = border;
// حدد نوع الارتباط كعنوان URI بعيد
link.Action = new GoToURIAction("www.aspose.com");
// أضف تعليقًا توضيحيًا للرابط إلى مجموعة التعليقات التوضيحية للصفحة الأولى من ملف PDF
page.Annotations.Add(link);
// قم بإنشاء تعليق توضيحي مجاني للنص
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(document.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), new DefaultAppearance(Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman"), 10, System.Drawing.Color.Blue));
// ستتم إضافة سلسلة كنص مجاني
textAnnotation.Contents = "Link to Aspose website";
// قم بتعيين الحدود للتعليق التوضيحي للنص الحر
textAnnotation.Border = border;
// أضف تعليقًا توضيحيًا لـ FreeText إلى مجموعة التعليقات التوضيحية للصفحة الأولى من المستند
document.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddHyperlink_out.pdf";
// احفظ المستند المحدث
document.Save(dataDir);
Console.WriteLine("\nHyperlink added successfully.\nFile saved at " + dataDir);            
```

## خاتمة

تهنئة ! لديك الآن دليل خطوة بخطوة لإضافة ارتباطات تشعبية باستخدام Aspose.PDF for .NET. يمكنك استخدام هذا الرمز لإنشاء روابط تفاعلية في مستندات PDF الخاصة بك.