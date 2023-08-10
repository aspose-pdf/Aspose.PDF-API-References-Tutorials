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

### مثال على التعليمات البرمجية المصدر لـ XML إلى مسار صورة مجموعة PDF باستخدام Aspose.PDF لـ .NET

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

### التعليمات

#### س: ما هو الغرض من تعيين مسار الصورة عند تحويل XML إلى PDF؟

ج: عند تحويل XML إلى PDF ، يتيح لك تعيين مسار الصورة تحديد موقع الصورة المشار إليها في XML. يضمن ذلك عرض الصورة بشكل صحيح في مستند PDF الناتج.

#### س: هل يمكنني استخدام صور من أدلة مختلفة؟

 ج: نعم ، يمكنك استخدام صور من أدلة مختلفة من خلال توفير مسار الملف الصحيح لكل صورة. في الكود المقدم ، فإن ملف`inFile` متغير يحمل المسار إلى ملف الصورة ، ويمكنك تحديثه للإشارة إلى الصور في أدلة مختلفة.

#### س: هل يمكنني استخدام الصور من عنوان URL بعيد؟

ج: نعم ، يمكنك استخدام صور من عنوان URL بعيد عن طريق توفير عنوان URL بدلاً من مسار ملف محلي. تأكد من أن التطبيق الخاص بك لديه وصول إلى الإنترنت لاسترداد الصورة من عنوان URL البعيد.

#### س: ما هو التنسيق الذي يجب أن يحتوي عليه ملف XML للإدخال؟

ج: يجب أن يحتوي ملف XML للإدخال على بنية تشير إلى الصورة باستخدام المعرف. في الكود المقدم ، يتم استخدام المعرف "testImg" للإشارة إلى الصورة.

#### س: هل يمكنني إضافة صور متعددة إلى ملف PDF؟

ج: نعم ، يمكنك إضافة صور متعددة إلى ملف PDF بالرجوع إليها في ملف XML باستخدام معرفات مختلفة وتعيين مسارات الملف وفقًا لذلك.