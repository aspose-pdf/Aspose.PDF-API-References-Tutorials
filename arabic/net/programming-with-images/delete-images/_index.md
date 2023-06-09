---
title: حذف الصور
linktitle: حذف الصور
second_title: Aspose.PDF لمرجع .NET API
description: احذف الصور بسهولة من ملف PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 110
url: /ar/net/programming-with-images/delete-images/
---

سيأخذك هذا الدليل خطوة بخطوة حول كيفية حذف الصور من ملف PDF باستخدام Aspose.PDF for .NET. تأكد من قيامك بالفعل بإعداد بيئتك واتبع الخطوات التالية:

## الخطوة 1: تحديد دليل المستند

 قبل أن تبدأ ، تأكد من تعيين الدليل الصحيح للمستندات. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود بالمسار إلى الدليل حيث يوجد مستند PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: افتح مستند PDF

 في هذه الخطوة ، سنفتح مستند PDF باستخدام امتداد`Document` فئة Aspose.PDF. استخدم ال`Document` منشئ ومرر المسار إلى وثيقة PDF.

```csharp
Document pdfDocument = new Document(dataDir + "DeleteImages.pdf");

```

## الخطوة 3: حذف صورة معينة

 في هذه الخطوة ، سنقوم بحذف صورة معينة من صفحة معينة. استخدم ال`Delete` طريقة مورد الصفحة`Images` كائن لحذف الصورة. في المثال أدناه ، نحذف الصورة بالفهرس 1 من الصفحة الأولى.

```csharp
pdfDocument.Pages[1].Resources.Images.Delete(1);
```

## الخطوة 4: احفظ ملف PDF المحدث

 احفظ ملف PDF المحدث باستخدام امتداد`Save` طريقة`pdfDocument` هدف. حدد مسار الإخراج لملف PDF.

```csharp
dataDir = dataDir + "DeleteImages_out.pdf";
pdfDocument.Save(dataDir);
```

### نموذج التعليمات البرمجية المصدر لحذف الصور باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir+ "DeleteImages.pdf");
//حذف صورة معينة
pdfDocument.Pages[1].Resources.Images.Delete(1);
dataDir = dataDir + "DeleteImages_out.pdf";
// احفظ ملف PDF المحدث
pdfDocument.Save(dataDir);
Console.WriteLine("\nImages deleted successfully.\nFile saved at " + dataDir); 
```

## خاتمة

تهنئة ! لقد نجحت في حذف الصور من ملف PDF باستخدام Aspose.PDF for .NET. يتم حفظ ملف PDF المحدث في الدليل المحدد. يمكنك الآن استخدام ملف PDF هذا بدون الصور المحذوفة.