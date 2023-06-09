---
title: الحصول على رقم الصفحة المرجعية
linktitle: الحصول على رقم الصفحة المرجعية
second_title: Aspose.PDF لمرجع .NET API
description: احصل بسهولة على أرقام الصفحات المرجعية من ملفات PDF الخاصة بك باستخدام Aspose.PDF for .NET.
type: docs
weight: 60
url: /ar/net/programming-with-bookmarks/get-bookmark-page-number/
---

يمكن أن يكون استرداد أرقام الصفحات المرتبطة بالإشارات المرجعية في مستند PDF مفيدًا للتنقل. باستخدام Aspose.PDF for .NET ، يمكنك بسهولة الحصول على رقم صفحة الإشارات المرجعية باتباع التعليمات البرمجية المصدر التالية:

## الخطوة 1: استيراد المكتبات المطلوبة

قبل أن تبدأ ، تحتاج إلى استيراد المكتبات اللازمة لمشروع C # الخاص بك. فيما يلي توجيه الاستيراد الضروري:

```csharp
using Aspose.Pdf.Facades;
```

## الخطوة 2: حدد المسار إلى مجلد المستندات

 في هذه الخطوة ، تحتاج إلى تحديد المسار إلى المجلد الذي يحتوي على ملف PDF الذي تريد استخراج أرقام الصفحات المرجعية منه. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود التالي بالمسار الفعلي لمجلد المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 3: إنشاء محرر الإشارات المرجعية

 الآن سنقوم بإنشاء ملف`PdfBookmarkEditor` كائن لمعالجة الإشارات المرجعية للمستند. استخدم الكود التالي:

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

## الخطوة 4: افتح ملف PDF

 في هذه الخطوة ، نفتح ملف PDF باستخدام امتداد`BindPdf` طريقة محرر الإشارات المرجعية. هذا هو الكود المقابل:

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

## الخطوة 5: استخراج الإشارات المرجعية

 الآن سنقوم باستخراج الإشارات المرجعية من المستند باستخدام امتداد`ExtractBookmarks` طريقة محرر الإشارات المرجعية. هذا هو الكود المقابل:

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

## الخطوة 6: تصفح الإشارات المرجعية والحصول على أرقام الصفحات

 أخيرًا ، نقوم بتكرار الإشارات المرجعية المستخرجة ونحصل على أرقام الصفحات المرتبطة بكل إشارة مرجعية باستخدام ملف`foreach` حلقة. هذا هو الكود المقابل:

```csharp
foreach (Bookmark bookmark in bookmarks)
{
     string strLevelSeprator = string.Empty;
     for (int i = 1; i < bookmark.Level; i++)
     {
         strLevelSeprator += "----";
     }
     Console.WriteLine("{0}Title: {1}", strLevelSeprator, bookmark.Title);
     Console.WriteLine("{0}Page number: {1}", strLevelSeprator, bookmark.PageNumber);
     Console.WriteLine("{0}Page Action: {1}", strLevelSeprator, bookmark.Action);
}
```

### نموذج التعليمات البرمجية المصدر للحصول على رقم الصفحة المرجعية باستخدام Aspose.PDF for .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// قم بإنشاء PdfBookmarkEditor
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
// افتح ملف PDF
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
// استخراج الإشارات المرجعية
Aspose.Pdf.Facades.Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
foreach (Aspose.Pdf.Facades.Bookmark bookmark in bookmarks)
{
	string strLevelSeprator = string.Empty;
	for (int i = 1; i < bookmark.Level; i++)
	{
		strLevelSeprator += "----";
	}
	Console.WriteLine("{0}Title: {1}", strLevelSeprator, bookmark.Title);
	Console.WriteLine("{0}Page Number: {1}", strLevelSeprator, bookmark.PageNumber);
	Console.WriteLine("{0}Page Action: {1}", strLevelSeprator, bookmark.Action);
}
```

## خاتمة

تهنئة ! الآن لديك دليل خطوة بخطوة للحصول على أرقام الصفحات المرجعية باستخدام Aspose.PDF for .NET. يمكنك استخدام هذا الرمز لاسترداد معلومات التنقل المرتبطة بكل إشارة مرجعية في مستندات PDF الخاصة بك.

تأكد من إطلاعك على وثائق Aspose.PDF الرسمية لمزيد من المعلومات حول ميزات معالجة الإشارات المرجعية المتقدمة.