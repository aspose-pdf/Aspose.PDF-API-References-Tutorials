---
title: XML إلى PDFSet Image Path
linktitle: XML إلى PDFSet Image Path
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لتعيين مسار الصورة عند تحويل XML إلى PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 340
url: /ar/net/document-conversion/xml-to-pdfset-image-path/
---

في هذا البرنامج التعليمي ، سنرشدك خطوة بخطوة حول كيفية تعيين مسار الصورة عند تحويل ملف XML إلى PDF باستخدام مكتبة Aspose.PDF لـ .NET. سنقوم بتفصيل كود المصدر C # المقدم ونوضح لك كيفية تنفيذه في مشاريعك الخاصة. بنهاية هذا البرنامج التعليمي ، يمكنك بسهولة تحديد مسار الصورة عند تحويل XML إلى PDF.

## الخطوة 1: تعيين مسارات الملفات
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string inXml = dataDir + "input.xml";
string inFile = dataDir + "aspose-logo.jpg";
string outFile = dataDir + "output_out.pdf";
```
 حدد مسارات ملفات XML المدخلة والصورة المراد استخدامها وملف PDF الناتج. يستبدل`"YOUR DOCUMENTS DIRECTORY"` بالمسار حيث حفظت ملفاتك.

## الخطوة 2: إنشاء كائن مستند
```csharp
Document doc = new Document();
```
قم بإنشاء مثيل لكائن المستند.

## الخطوة 3: اربط ملف XML المصدر
```csharp
doc. BindXml(inXml);
```
يربط ملف XML المصدر بالمستند.

## الخطوة 4: تعيين مسار الصورة
```csharp
Image image = (Image)doc.GetObjectById("testImg");
image.File = inFile;
```
احصل على مرجع كائن الصورة من XML باستخدام المعرف الخاص به وقم بتعيين مسار الصورة المراد استخدامها.

## الخطوة 5: احفظ ملف PDF الناتج
```csharp
doc.Save(outFile);
```
احفظ ملف PDF الناتج في الدليل المحدد.

### مثال على شفرة المصدر لـ XML إلى مسار صورة مجموعة PDF باستخدام Aspose.Words for .NET

```csharp
try
{
	
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	string inXml = dataDir + "input.xml";
	string inFile = dataDir + "aspose-logo.jpg";
	string outFile = dataDir + "output_out.pdf";
	Document doc = new Document();
	doc.BindXml(inXml);
	Image image = (Image)doc.GetObjectById("testImg");
	image.File = inFile;
	doc.Save(outFile);
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية تعيين مسار الصورة عند تحويل XML إلى PDF باستخدام مكتبة Aspose.PDF لـ .NET. باتباع الخطوات المقدمة ، يمكنك بسهولة تحديد مسار الصورة في تحويلات XML إلى PDF الخاصة بك.