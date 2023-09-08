---
title: XML إلى PDFSet مسار الصورة
linktitle: XML إلى PDFSet مسار الصورة
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لتعيين مسار الصورة عند تحويل XML إلى PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 340
url: /ar/net/document-conversion/xml-to-pdfset-image-path/
---
في هذا البرنامج التعليمي، سنرشدك خطوة بخطوة حول كيفية تعيين مسار الصورة عند تحويل ملف XML إلى PDF باستخدام مكتبة Aspose.PDF لـ .NET. سنقوم بتفصيل كود مصدر C# المقدم ونوضح لك كيفية تنفيذه في مشاريعك الخاصة. بنهاية هذا البرنامج التعليمي، يمكنك بسهولة تحديد مسار الصورة عند تحويل XML إلى PDF.

## الخطوة 1: تعيين مسارات الملفات
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string inXml = dataDir + "input.xml";
string inFile = dataDir + "aspose-logo.jpg";
string outFile = dataDir + "output_out.pdf";
```
 حدد مسارات ملفات XML المدخلة، والصورة المراد استخدامها، وملف PDF الناتج. يستبدل`"YOUR DOCUMENTS DIRECTORY"` بالمسار الذي قمت بحفظ ملفاتك فيه.

## الخطوة 2: إنشاء كائن مستند
```csharp
Document doc = new Document();
```
قم بإنشاء مثيل لكائن المستند.

## الخطوة 3: ربط ملف XML المصدر
```csharp
doc. BindXml(inXml);
```
يربط ملف XML المصدر بالمستند.

## الخطوة 4: تعيين مسار الصورة
```csharp
Image image = (Image)doc.GetObjectById("testImg");
image.File = inFile;
```
احصل على مرجع كائن الصورة من XML باستخدام معرفه وقم بتعيين مسار الصورة المراد استخدامه.

## الخطوة 5: احفظ ملف PDF الناتج
```csharp
doc.Save(outFile);
```
احفظ ملف PDF الناتج في الدليل المحدد.

### مثال على التعليمات البرمجية المصدر لـ XML إلى PDFSet Image Path باستخدام Aspose.PDF لـ .NET

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
في هذا البرنامج التعليمي، تعلمنا كيفية تعيين مسار الصورة عند تحويل XML إلى PDF باستخدام مكتبة Aspose.PDF لـ .NET. باتباع الخطوات المتوفرة، يمكنك بسهولة تحديد مسار الصورة في تحويلات XML إلى PDF الخاصة بك.

### الأسئلة الشائعة

#### س: ما هو الغرض من تحديد مسار الصورة عند تحويل XML إلى PDF؟

ج: عند تحويل XML إلى PDF، يتيح لك تعيين مسار الصورة تحديد موقع الصورة المشار إليها في XML. وهذا يضمن عرض الصورة بشكل صحيح في مستند PDF الناتج.

#### س: هل يمكنني استخدام الصور من أدلة مختلفة؟

 ج: نعم، يمكنك استخدام الصور من أدلة مختلفة عن طريق توفير مسار الملف الصحيح لكل صورة. في الكود المقدم،`inFile` يحمل المتغير المسار إلى ملف الصورة، ويمكنك تحديثه للإشارة إلى الصور في أدلة مختلفة.

#### س: هل يمكنني استخدام الصور من عنوان URL بعيد؟

ج: نعم، يمكنك استخدام الصور من عنوان URL بعيد عن طريق توفير عنوان URL بدلاً من مسار الملف المحلي. تأكد من أن التطبيق الخاص بك لديه إمكانية الوصول إلى الإنترنت لاسترداد الصورة من عنوان URL البعيد.

#### س: ما هو التنسيق الذي يجب أن يحتوي عليه ملف إدخال XML؟

ج: يجب أن يحتوي ملف XML المدخل على بنية تشير إلى الصورة باستخدام معرف. في الكود المقدم، يتم استخدام المعرف "testImg" للإشارة إلى الصورة.

#### س: هل يمكنني إضافة صور متعددة إلى ملف PDF؟

ج: نعم، يمكنك إضافة صور متعددة إلى ملف PDF عن طريق الرجوع إليها في ملف XML باستخدام معرفات مختلفة وتعيين مسارات الملف وفقًا لذلك.