---
title: HTML إلى PDF
linktitle: HTML إلى PDF
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لتحويل HTML إلى PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 50
url: /ar/net/document-conversion/html-to-pdf/
---

في هذا البرنامج التعليمي ، سنرشدك خلال عملية تحويل ملف HTML إلى PDF باستخدام Aspose.PDF for .NET. HTML (HyperText Markup Language) هي لغة ترميز تُستخدم في هيكلة محتوى الويب وتقديمه. باتباع الخطوات أدناه ، ستتمكن من تحويل ملفات HTML إلى تنسيق PDF.

## المتطلبات الأساسية
قبل أن تبدأ ، تأكد من تلبية المتطلبات الأساسية التالية:

- المعرفة الأساسية بلغة البرمجة C #.
- تثبيت مكتبة Aspose.PDF لـ .NET على نظامك.
- بيئة تطوير مثل Visual Studio.

## الخطوة الأولى: تحميل ملف HTML
في هذه الخطوة ، سنقوم بتحميل ملف HTML باستخدام Aspose.PDF for .NET. اتبع الكود أدناه:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

HtmlLoadOptions options = new HtmlLoadOptions();
options.CustomLoaderOfExternalResources = new LoadOptions.ResourceLoadingStrategy(SamePictureLoader);

Document pdfDocument = new Document(dataDir + "HTMLToPDF.html", options);
```

 تأكد من استبدال`"YOUR DOCUMENTS DIRECTORY"` مع الدليل الفعلي حيث يوجد ملف HTML الخاص بك.

## الخطوة 2: خيارات تحميل HTML
الآن بعد أن قمنا بتحميل ملف HTML ، يمكننا تحديد خيارات تحميل محددة. استخدم الكود التالي:

```csharp
options.CustomLoaderOfExternalResources = new LoadOptions.ResourceLoadingStrategy(SamePictureLoader);
```

يخبر الكود أعلاه Aspose.PDF أن يستخدم إستراتيجية تحميل مخصصة للموارد الخارجية ، مثل الصور. يمكنك تخصيص هذه السياسة لتناسب احتياجاتك.

## الخطوة 3: تحويل HTML إلى PDF
بعد تحميل ملف HTML وتحديد خيارات التحميل ، يمكننا متابعة التحويل إلى PDF. استخدم الكود التالي:

```csharp
pdfDocument.Save("HTMLToPDF_out.pdf");
```

### مثال على كود المصدر لـ HTML إلى PDF باستخدام Aspose.PDF لـ .NET

```csharp
try
{
	
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	HtmlLoadOptions options = new HtmlLoadOptions();
	options.CustomLoaderOfExternalResources = new LoadOptions.ResourceLoadingStrategy(SamePictureLoader);

	Document pdfDocument = new Document(dataDir + "HTMLToPDF.html", options);
	pdfDocument.Save("HTMLToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## خاتمة
في هذا البرنامج التعليمي ، قمنا بتغطية العملية خطوة بخطوة. خطوة تحويل ملف HTML إلى PDF باستخدام Aspose.PDF for .NET. باتباع الإرشادات الموضحة أعلاه ، يجب أن تكون الآن قادرًا على تحويل ملفات HTML إلى تنسيق PDF. يمكن أن تكون هذه الميزة مفيدة عندما تحتاج إلى إنشاء مستندات PDF من محتوى HTML.

