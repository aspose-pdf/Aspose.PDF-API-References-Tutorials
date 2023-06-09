---
title: صفحات إلى صور
linktitle: صفحات إلى صور
second_title: Aspose.PDF لمرجع .NET API
description: قم بتحويل صفحات مستند PDF بسهولة إلى صور باستخدام Aspose.PDF for .NET.
type: docs
weight: 200
url: /ar/net/programming-with-images/pages-to-images/
---

في هذا البرنامج التعليمي ، سنوجهك خطوة بخطوة لتحويل صفحات مستند PDF إلى صور فردية باستخدام مكتبة Aspose.PDF لـ .NET. يوضح لك كود المصدر C # المقدم كيفية فتح مستند PDF وإنشاء صور من كل صفحة وحفظها. سنشرح كل خطوة بالتفصيل لمساعدتك على فهم العملية بعمق.

## المتطلبات الأساسية
قبل أن تبدأ ، تأكد من أن لديك العناصر التالية:
- المعرفة الأساسية بلغة البرمجة C #.
- تثبيت مكتبة Aspose.PDF لـ .NET في مشروعك.
- وثيقة PDF التي تريد تحويلها إلى صور.

## الخطوة 1: إعداد المشروع
1. قم بإنشاء مشروع C # جديد في بيئة التطوير المفضلة لديك.
2. أضف مرجعًا إلى مكتبة Aspose.PDF في مشروعك.

## الخطوة 2: استيراد مساحات الأسماء الضرورية
في بداية ملف C # الخاص بك ، قم باستيراد مساحات الأسماء المطلوبة للوصول إلى فئات وطرق Aspose.PDF. هنا مثال :
```csharp
using System;
using Aspose.Pdf;
using System.IO;
```

## الخطوة 3: تهيئة المتغيرات والمسارات
قبل إجراء التحويل ، نحتاج إلى تكوين المتغيرات والمسارات اللازمة.
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```
 تأكد من استبدال`"YOUR DOCUMENTS DIRECTORY"` مع المسار الفعلي إلى دليل المستندات الخاص بك.

## الخطوة 4: تحويل الصفحات إلى صور
لتحويل صفحات مستند PDF إلى صور ، اتبع الخطوات التالية:
1.  افتح مستند PDF باستخدام ملف`Document` فصل.
```csharp
Document pdfDocument = new Document(dataDir + "PagesToImages.pdf");
```
2.  كرر كل صفحة من صفحات المستند باستخدام ملف`for` حلقة.
```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
//كود لتحويل كل صفحة إلى صورة
}
```
3. داخل الحلقة ، قم بإنشاء دفق ملف لكل صورة لحفظها.
```csharp
using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".jpg", FileMode.Create))
{
// كود لتحويل الصفحة إلى صورة
}
```
4.  داخل`using` كتلة ، إنشاء`Resolution` كائن لتعيين دقة الصورة.
```csharp
Resolution resolution = new Resolution(300);
```
5.  إنشاء`JpegDevice` كائن باستخدام الدقة والجودة المحددين.
```csharp
JpegDevice jpegDevice = new JpegDevice(resolution, 100);
```
6.  استخدم ال`Process` طريقة`jpegDevice` كائن لتحويل صفحة معينة إلى صورة وحفظ الصورة في الدفق.
```csharp
jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
```
7. أغلق تدفق الصور.
```csharp
imageStream.Close();
```
8. كرر هذه الخطوات لكل صفحة من المستند.
9. اعرض رسالة نجاح في نهاية العملية.
```csharp
Console.WriteLine("PDF pages converted to individual images successfully!");
```

### نموذج التعليمات البرمجية المصدر لـ Pages To Images باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "PagesToImages.pdf");
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
	using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".jpg", FileMode.Create))
	{
		// إنشاء جهاز JPEG بسمات محددة
		// العرض ، الارتفاع ، الدقة ، الجودة
		// الجودة [0-100] ، 100 هي الحد الأقصى
		// إنشاء كائن القرار
		Resolution resolution = new Resolution(300);
		// JpegDevice jpegDevice = جديد JpegDevice (500 ، 700 ، القرار ، 100) ؛
		JpegDevice jpegDevice = new JpegDevice(resolution, 100);
		// قم بتحويل صفحة معينة وحفظ الصورة للدفق
		jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
		// إغلاق الدفق
		imageStream.Close();
	}
}
System.Console.WriteLine("PDF pages are converted to individual images successfully!");
```

## خاتمة
باتباع هذا الدليل المفصل خطوة بخطوة ، تعلمت كيفية تحويل صفحات مستند PDF إلى صور فردية باستخدام مكتبة Aspose.PDF لـ .NET. تتضمن هذه العملية إعداد المشروع ، واستيراد مساحات الأسماء الضرورية ، وتهيئة المتغيرات والمسارات ، وتحويل الصفحات إلى صور. يمكنك الآن دمج هذا الرمز في مشاريعك الخاصة وتعديله ليناسب احتياجاتك الخاصة.