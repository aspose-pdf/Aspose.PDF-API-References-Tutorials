---
title: XPS إلى PDF
linktitle: XPS إلى PDF
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لتحويل ملف XPS إلى PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 350
url: /ar/net/document-conversion/xps-to-pdf/
---

في هذا البرنامج التعليمي ، سنرشدك إلى كيفية تحويل ملف XPS إلى PDF باستخدام مكتبة Aspose.PDF لـ .NET خطوة بخطوة. سنقوم بتفصيل كود المصدر C # المقدم ونوضح لك كيفية تنفيذه في مشاريعك الخاصة. بنهاية هذا البرنامج التعليمي ، ستتمكن من تحويل ملفات XPS بسهولة إلى مستندات PDF.

## الخطوة 1: تعيين دليل المستندات
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```
 يستبدل`"YOUR DOCUMENTS DIRECTORY"` بالمسار حيث حفظت ملفاتك.

## الخطوة 2: إنشاء كائن LoadOptions باستخدام خيارات تحميل XPS
```csharp
Aspose.Pdf.LoadOptions options = new XpsLoadOptions();
```
قم بإنشاء مثيل لكائن LoadOptions باستخدام خيارات تحميل XPS.

## الخطوة 3: قم بإنشاء كائن المستند
```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "XPSToPDF.xps", options);
```
قم بإنشاء كائن مستند يحدد ملف XPS للإدخال وخيارات التحميل.

## الخطوة 4: احفظ مستند PDF الناتج
```csharp
document.Save(dataDir + "XPSToPDF_out.pdf");
```
احفظ مستند PDF الناتج في الدليل المحدد.

### مثال على شفرة المصدر لـ XPS إلى PDF باستخدام Aspose.Words for .NET

```csharp
try
{
	
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// إنشاء كائن LoadOption باستخدام خيار تحميل XPS
	Aspose.Pdf.LoadOptions options = new XpsLoadOptions();

	// إنشاء كائن الوثيقة
	Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "XPSToPDF.xps", options);

	// احفظ مستند PDF الناتج
	document.Save(dataDir + "XPSToPDF_out.pdf");
	
}
catch(Exception ex)
   
{
	Console.WriteLine(ex.Message);
}
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية تحويل ملف XPS إلى PDF باستخدام مكتبة Aspose.PDF لـ .NET. باتباع الخطوات المقدمة ، يمكنك بسهولة إجراء هذا التحويل في تطبيقاتك الخاصة. احصل على نتائج دقيقة واحترافية عند تحويل ملفات XPS إلى PDF.