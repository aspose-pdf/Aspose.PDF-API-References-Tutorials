---
title: احصل على رقم صفحة الإشارة المرجعية في ملف PDF
linktitle: احصل على رقم صفحة الإشارة المرجعية في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: احصل بسهولة على رقم صفحة الإشارة المرجعية في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 60
url: /ar/net/programming-with-bookmarks/get-bookmark-page-number/
---
يمكن أن يكون استرداد أرقام الصفحات المرتبطة بالإشارات المرجعية في ملف PDF مفيدًا للتنقل. باستخدام Aspose.PDF for .NET، يمكنك بسهولة الحصول على رقم صفحة الإشارات المرجعية باتباع كود المصدر التالي:

## الخطوة 1: استيراد المكتبات المطلوبة

قبل أن تبدأ، تحتاج إلى استيراد المكتبات اللازمة لمشروع C# الخاص بك. فيما يلي توجيه الاستيراد الضروري:

```csharp
using Aspose.Pdf.Facades;
```

## الخطوة 2: تعيين المسار إلى مجلد المستندات

 في هذه الخطوة، تحتاج إلى تحديد المسار إلى المجلد الذي يحتوي على ملف PDF الذي تريد استخراج أرقام صفحات الإشارات المرجعية منه. يستبدل`"YOUR DOCUMENT DIRECTORY"`في الكود التالي مع المسار الفعلي لمجلد المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 3: إنشاء محرر الإشارات المرجعية

 الآن سوف نقوم بإنشاء`PdfBookmarkEditor` كائن لمعالجة الإشارات المرجعية للمستند. استخدم الكود التالي:

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

## الخطوة 4: افتح ملف PDF

 في هذه الخطوة نقوم بفتح ملف PDF باستخدام ملف`BindPdf` طريقة محرر الإشارات المرجعية. هنا هو الكود المقابل:

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

## الخطوة 5: استخراج الإشارات المرجعية

 الآن سنقوم باستخراج الإشارات المرجعية من المستند باستخدام الملف`ExtractBookmarks` طريقة محرر الإشارات المرجعية. هنا هو الكود المقابل:

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

## الخطوة 6: تصفح الإشارات المرجعية واحصل على أرقام الصفحات

 أخيرًا، نقوم بالتمرير عبر الإشارات المرجعية المستخرجة ونحصل على أرقام الصفحات المرتبطة بكل إشارة مرجعية باستخدام ملف`foreach` حلقة. هنا هو الكود المقابل:

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

### نموذج التعليمات البرمجية المصدر للحصول على رقم صفحة الإشارة المرجعية باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// إنشاء محرر PdfBookmarkEditor
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

تهنئة ! الآن لديك دليل خطوة بخطوة للحصول على أرقام صفحات الإشارات المرجعية باستخدام Aspose.PDF لـ .NET. يمكنك استخدام هذا الرمز لاسترداد معلومات التنقل المرتبطة بكل إشارة مرجعية في مستندات PDF الخاصة بك.

تأكد من مراجعة وثائق Aspose.PDF الرسمية لمزيد من المعلومات حول ميزات معالجة الإشارات المرجعية المتقدمة.

### الأسئلة الشائعة للحصول على رقم صفحة الإشارة المرجعية في ملف PDF

#### س: ما هي الإشارات المرجعية في ملف PDF؟

ج: الإشارات المرجعية الموجودة في ملف PDF هي أدوات مساعدة للتنقل تتيح للمستخدمين الانتقال بسرعة إلى أقسام أو صفحات محددة داخل المستند. إنها تعزز تجربة المستخدم من خلال توفير اختصارات للمحتوى ذي الصلة.

#### س: لماذا أرغب في استرداد أرقام صفحات الإشارات المرجعية من ملف PDF؟

ج: يساعد استرداد أرقام صفحات الإشارات المرجعية المستخدمين على التنقل عبر المستند بشكل أكثر فعالية، مما يوفر إشارة واضحة إلى المكان الذي تؤدي إليه كل إشارة مرجعية. وهذا مفيد بشكل خاص للمستندات الأطول التي تحتوي على أقسام متعددة.

#### س: كيف يمكنني استيراد المكتبات اللازمة لمشروع C# الخاص بي؟

ج: لاستيراد المكتبة المطلوبة لمشروع C# الخاص بك، استخدم توجيه الاستيراد التالي:

```csharp
using Aspose.Pdf.Facades;
```

يتيح لك هذا التوجيه الاستفادة من الفئات والأساليب التي يوفرها Aspose.PDF لـ .NET.

#### س: كيف أحدد المسار إلى مجلد المستندات؟

 ج: في كود المصدر المقدم، استبدل`"YOUR DOCUMENT DIRECTORY"`بالمسار الفعلي إلى المجلد الذي يحتوي على ملف PDF الذي تريد استخراج أرقام صفحات الإشارات المرجعية منه. وهذا يضمن أن الكود يمكنه تحديد موقع ملف PDF المستهدف.

#### س: كيف أقوم بإنشاء محرر الإشارات المرجعية؟

ج: لإنشاء محرر الإشارات المرجعية، استخدم الكود التالي:

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

#### س: كيف يمكنني فتح ملف PDF لمعالجة الإشارات المرجعية؟

ج: لفتح ملف PDF لاستخراج معلومات الإشارة المرجعية، استخدم الكود التالي:

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

 يستبدل`"GetBookmarks.pdf"` مع اسم الملف الفعلي.

#### س: كيف يمكنني استخراج الإشارات المرجعية من ملف PDF؟

 ج: لاستخراج الإشارات المرجعية من ملف PDF، استخدم الملف`ExtractBookmarks` طريقة محرر الإشارات المرجعية:

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

#### س: كيف يمكنني استرداد وعرض أرقام صفحات الإشارات المرجعية؟

 ج: قم بالتمرير عبر الإشارات المرجعية المستخرجة باستخدام ملف`foreach` حلقة والوصول إلى`PageNumber` خاصية كل إشارة مرجعية لاسترداد وعرض رقم الصفحة المرتبطة بها:

```csharp
foreach (Bookmark bookmark in bookmarks)
{
    Console.WriteLine("Title: " + bookmark.Title);
    Console.WriteLine("Page Number: " + bookmark.PageNumber);
    Console.WriteLine("Page Action: " + bookmark.Action);
}
```

#### س: هل يمكنني تعديل خصائص الإشارة المرجعية باستخدام هذا الأسلوب؟

 ج: بينما يركز هذا البرنامج التعليمي على استرداد أرقام صفحات الإشارات المرجعية، يمكنك تعديل خصائص الإشارات المرجعية الأخرى باستخدام نفس الخصائص`Bookmark`الكائن والخصائص المرتبطة به.

#### س: كيف يمكنني حفظ ملف PDF المحدث بعد استخراج معلومات الإشارة المرجعية؟

ج: لا يؤدي استخراج الإشارة المرجعية إلى تعديل ملف PDF الأصلي. إذا كنت تريد حفظ أية تغييرات، فيمكنك القيام بذلك باستخدام طرق أخرى يوفرها Aspose.PDF لـ .NET.