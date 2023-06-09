---
title: إنشاء ارتباط الوثيقة
linktitle: إنشاء ارتباط الوثيقة
second_title: Aspose.PDF لمرجع .NET API
description: أنشئ روابط لمستندات PDF الأخرى بسهولة باستخدام Aspose.PDF for .NET.
type: docs
weight: 30
url: /ar/net/programming-with-links-and-actions/create-document-link/
---

يتيح لك الارتباط بمستند آخر في ملف PDF إنشاء روابط قابلة للنقر تعيد توجيه المستخدمين إلى مستندات PDF أخرى. باستخدام Aspose.PDF for .NET ، يمكنك بسهولة إنشاء مثل هذه الروابط باتباع التعليمات البرمجية المصدر التالية:

## الخطوة 1: استيراد المكتبات المطلوبة

قبل أن تبدأ ، تحتاج إلى استيراد المكتبات اللازمة لمشروع C # الخاص بك. فيما يلي توجيه الاستيراد الضروري:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.InteractiveFeatures;
```

## الخطوة 2: حدد المسار إلى مجلد المستندات

 في هذه الخطوة ، تحتاج إلى تحديد المسار إلى المجلد الذي يحتوي على ملف PDF الذي تريد إضافة رابط إلى مستند آخر إليه. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود التالي بالمسار الفعلي لمجلد المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 3: افتح مستند PDF

سنفتح الآن مستند PDF الذي نريد إضافة رابط إلى مستند آخر إليه باستخدام الكود التالي:

```csharp
Document document = new Document(dataDir + "CreateDocumentLink.pdf");
```

## الخطوة 4: قم بإنشاء رابط إلى مستند آخر

 في هذه الخطوة ، سننشئ رابطًا إلى مستند آخر باستخدام ملف`LinkAnnotation` حاشية. ملاحظة. سنحدد إحداثيات الارتباط ومنطقة الارتباط ، بالإضافة إلى إجراء التنقل إلى مستند خارجي. هذا هو الكود المقابل:

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link. Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
```

## الخطوة 5: احفظ الملف المحدث

الآن دعنا نحفظ ملف PDF المحدث باستخدام امتداد`Save` طريقة`document` هدف. هذا هو الكود المقابل:

```csharp
dataDir = dataDir + "CreateDocumentLink_out.pdf";
document. Save(dataDir);
```

### نموذج التعليمات البرمجية المصدر لـ Create Document Link باستخدام Aspose.PDF for .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document document = new Document(dataDir+ "CreateDocumentLink.pdf");
// إنشاء رابط
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link.Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
dataDir = dataDir + "CreateDocumentLink_out.pdf";
// احفظ المستند المحدث
document.Save(dataDir);
Console.WriteLine("\nDocument link created successfully.\nFile saved at " + dataDir);            
```

## خاتمة

تهنئة ! لديك الآن دليل تفصيلي للربط بمستندات أخرى باستخدام Aspose.PDF for .NET. يمكنك استخدام هذا الرمز لإنشاء روابط قابلة للنقر في ملفات PDF الخاصة بك ، وإعادة توجيه المستخدمين إلى مستندات أخرى.

تأكد من مراجعة وثائق Aspose.PDF الرسمية لمزيد من المعلومات حول الميزات المتقدمة للروابط التفاعلية.