---
title: تعيين الخط الافتراضي
linktitle: تعيين الخط الافتراضي
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تعيين الخط الافتراضي لمستند PDF باستخدام Aspose.PDF for .NET باستخدام هذا الدليل المفصل خطوة بخطوة.
type: docs
weight: 280
url: /ar/net/programming-with-document/setdefaultfont/
---
إذا كنت تعمل مع مستندات PDF في .NET ، فقد تواجه مشكلات حيث لا يتوفر الخط المستخدم في PDF على النظام الذي يتم عرضه أو طباعته. يمكن أن يؤدي هذا إلى ظهور النص بشكل غير صحيح أو عدم ظهوره على الإطلاق. يوفر Aspose.PDF for .NET حلاً لهذه المشكلة عن طريق السماح لك بتعيين خط افتراضي للمستند. في هذا المثال ، كيفية تعيين الخط الافتراضي باستخدام Aspose.PDF لـ .NET.

## الخطوة 1: قم بتعيين المسار إلى دليل المستند

نحتاج إلى تعيين المسار إلى الدليل حيث يوجد مستند PDF الخاص بنا. سنخزن هذا المسار في متغير يسمى "dataDir".

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل مستند PDF

 سنبدأ بتحميل مستند PDF موجود به خطوط مفقودة. في هذا المثال ، سنفترض أن مستند PDF موجود في الدليل المحدد بواسطة ملف`dataDir` عامل.

```csharp
string documentName = dataDir + "input.pdf";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
    // كود هنا
}
```

## الخطوة 3: تعيين الخط الافتراضي

 بعد ذلك ، سنقوم بتعيين الخط الافتراضي لمستند PDF باستخدام امتداد`PdfSaveOptions`فصل. في هذا المثال ، سنقوم بتعيين الخط الافتراضي على "Arial".

```csharp
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.DefaultFontName = "Arial";
```

## الخطوة 4: احفظ المستند المحدث

أخيرًا ، سنقوم بحفظ المستند المحدث في ملف جديد. في هذا المثال ، سنحفظ المستند المحدث في ملف يسمى "output_out.pdf" في نفس الدليل مثل ملف الإدخال.

```csharp
document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
```

### مثال التعليمات البرمجية المصدر لتعيين الخط الافتراضي باستخدام Aspose.PDF لـ .NET

```csharp
	
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// قم بتحميل مستند PDF موجود بخط مفقود
	string documentName = dataDir + "input.pdf";
	string newName = "Arial";
	using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
	using (Document document = new Document(fs))
	{
		PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
		// حدد اسم الخط الافتراضي
		pdfSaveOptions.DefaultFontName = newName;
		document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
	}
	
```
