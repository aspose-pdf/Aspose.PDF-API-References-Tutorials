---
title: إنشاء ارتباط التطبيق
linktitle: إنشاء ارتباط التطبيق
second_title: Aspose.PDF لمرجع .NET API
description: أنشئ روابط تطبيق بسهولة في ملفات PDF الخاصة بك باستخدام Aspose.PDF for .NET.
type: docs
weight: 20
url: /ar/net/programming-with-links-and-actions/create-application-link/
---

يتيح لك إنشاء ارتباط تطبيق في مستند PDF إنشاء روابط لتطبيقات خارجية ، مثل الملفات القابلة للتنفيذ أو عناوين URL. باستخدام Aspose.PDF for .NET ، يمكنك بسهولة إنشاء روابط التطبيق باتباع التعليمات البرمجية المصدر التالية:

## الخطوة 1: استيراد المكتبات المطلوبة

قبل أن تبدأ ، تحتاج إلى استيراد المكتبات اللازمة لمشروع C # الخاص بك. فيما يلي توجيه الاستيراد الضروري:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.InteractiveFeatures;
```

## الخطوة 2: حدد المسار إلى مجلد المستندات

في هذه الخطوة ، تحتاج إلى تحديد المسار إلى المجلد الذي يحتوي على ملف PDF الذي تريد إضافة رابط التطبيق إليه. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود التالي بالمسار الفعلي لمجلد المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 3: افتح مستند PDF

سنفتح الآن مستند PDF الذي نريد إضافة رابط تطبيق إليه باستخدام الكود التالي:

```csharp
Document document = new Document(dataDir + "CreateApplicationLink.pdf");
```

## الخطوة 4: إنشاء رابط التطبيق

 في هذه الخطوة ، سننشئ رابط التطبيق باستخدام امتداد`LinkAnnotation` حاشية. ملاحظة. سنحدد إحداثيات الارتباط ومنطقة الارتباط ، بالإضافة إلى إجراء تشغيل التطبيق. هذا هو الكود المقابل:

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link. Action = new LaunchAction(document, dataDir + "CreateApplicationLink.pdf");
page.Annotations.Add(link);
```

## الخطوة 5: احفظ الملف المحدث

الآن دعنا نحفظ ملف PDF المحدث باستخدام امتداد`Save` طريقة`document` هدف. هذا هو الكود المقابل:

```csharp
dataDir = dataDir + "CreateApplicationLink_out.pdf";
document. Save(dataDir);
```

### نموذج التعليمات البرمجية المصدر لـ Create Application Link باستخدام Aspose.PDF for .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document document = new Document( dataDir + "CreateApplicationLink.pdf");
// إنشاء رابط
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link.Action = new LaunchAction(document, dataDir + "CreateApplicationLink.pdf");
page.Annotations.Add(link);
dataDir = dataDir + "CreateApplicationLink_out.pdf";
// احفظ المستند المحدث
document.Save(dataDir);
Console.WriteLine("\nApplication link created successfully.\nFile saved at " + dataDir);
```

## خاتمة

تهنئة ! لديك الآن دليل خطوة بخطوة لإنشاء روابط التطبيق باستخدام Aspose.PDF for .NET. يمكنك استخدام هذا الرمز لإضافة روابط لتطبيقات خارجية في مستندات PDF الخاصة بك.

تأكد من مراجعة وثائق Aspose.PDF الرسمية لمزيد من المعلومات حول الميزات المتقدمة للروابط التفاعلية.