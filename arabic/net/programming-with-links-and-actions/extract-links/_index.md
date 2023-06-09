---
title: استخراج الروابط
linktitle: استخراج الروابط
second_title: Aspose.PDF لمرجع .NET API
description: استخرج الروابط بسهولة من مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 50
url: /ar/net/programming-with-links-and-actions/extract-links/
---

يتيح لك استخراج الروابط من مستند PDF استعادة جميع روابط النص التشعبي الموجودة في المستند. باستخدام Aspose.PDF for .NET ، يمكنك بسهولة استخراج هذه الروابط باتباع التعليمات البرمجية المصدر التالية:

## الخطوة 1: استيراد المكتبات المطلوبة

قبل أن تبدأ ، تحتاج إلى استيراد المكتبات اللازمة لمشروع C # الخاص بك. فيما يلي توجيه الاستيراد الضروري:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
```

## الخطوة 2: حدد المسار إلى مجلد المستندات

 في هذه الخطوة ، تحتاج إلى تحديد المسار إلى المجلد الذي يحتوي على ملف PDF الذي تريد استخراج الروابط منه. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود التالي بالمسار الفعلي لمجلد المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 3: افتح مستند PDF

 سنفتح ملف PDF باستخدام ملف`Document` فصل. هذا هو الكود المقابل:

```csharp
Document document = new Document(dataDir + "ExtractLinks.pdf");
```

## الخطوة 4: استخراج الروابط

 في هذه الخطوة ، سنقوم باستخراج الروابط الموجودة في مستند PDF باستخدام الامتداد`AnnotationSelector` فصل. هذا هو الكود المقابل:

```csharp
Page page = document.Pages[1];
AnnotationSelector selector = new AnnotationSelector(new LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
page. Accept(selector);
IList<Annotation> list = selector. Selected;
Annotation annotation = (Annotation)list[0];
```

## الخطوة 5: احفظ المستند المحدث

الآن دعنا نحفظ ملف PDF المحدث باستخدام امتداد`Save` طريقة`document` هدف. هذا هو الكود المقابل:

```csharp
dataDir = dataDir + "ExtractLinks_out.pdf";
document. Save(dataDir);
```

### نموذج التعليمات البرمجية المصدر لاستخراج الروابط باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document document = new Document(dataDir+ "ExtractLinks.pdf");
// استخراج الإجراءات
Page page = document.Pages[1];
AnnotationSelector selector = new AnnotationSelector(new LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
page.Accept(selector);
IList<Annotation> list = selector.Selected;
Annotation annotation = (Annotation)list[0];
dataDir = dataDir + "ExtractLinks_out.pdf";
// احفظ المستند المحدث
document.Save(dataDir);
Console.WriteLine("\nLinks extracted successfully.\nFile saved at " + dataDir);
```

## خاتمة

تهنئة ! لديك الآن دليل تفصيلي خطوة بخطوة لاستخراج الروابط من مستند PDF باستخدام Aspose.PDF for .NET. يمكنك استخدام هذا الرمز لاسترداد جميع الارتباطات التشعبية الموجودة في المستند.

تأكد من مراجعة وثائق Aspose.PDF الرسمية لمزيد من المعلومات حول ميزات استخراج الارتباط المتقدمة.