---
title: إضافة والبحث عن نص مخفي
linktitle: إضافة والبحث عن نص مخفي
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لإضافة النص المخفي والبحث فيه في مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 20
url: /ar/net/programming-with-text/add-and-search-hidden-text/
---

في هذا البرنامج التعليمي ، سنرشدك إلى كيفية إضافة النص المخفي والبحث فيه في مستند PDF باستخدام Aspose.PDF for .NET. اتبع هذه الخطوات لإجراء هذه العملية بسهولة.

## 1. المتطلبات الأساسية

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي بيئة تطوير أخرى مثبتة ومهيأة.
- معرفة أساسية بلغة البرمجة C #.
- تثبيت مكتبة Aspose.PDF لـ .NET. يمكنك تنزيله من موقع Aspose الرسمي.

## 2. إنشاء وثيقة PDF مع النص المخفي

للبدء ، استخدم الكود التالي لإنشاء مستند PDF جديد يحتوي على نص مخفي:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// قم بإنشاء مستند
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
// تعيين خاصية النص - غير مرئي
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
```

تأكد من توفير المسار المطلوب واسم الملف لمستند PDF.

## 3. ابحث عن نص في المستند

بعد ذلك ، سنبحث في النص المخفي في مستند PDF. استخدم الكود التالي:

```csharp
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb.Visit(doc.Pages[1]);
foreach(TextFragment fragment in absorber.TextFragments)
{
// افعل شيئًا مع الأجزاء
Console.WriteLine("Text '{0}' at position {1}, invisibility: {2} ",
fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

سيؤدي هذا إلى البحث في النص المخفي في الصفحة الثانية من مستند PDF وعرض المعلومات ذات الصلة.

### نموذج التعليمات البرمجية المصدر لـ Add And Search Hidden Text باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//إنشاء وثيقة مع النص المخفي
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
//تعيين خاصية النص - غير مرئي
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
//نص البحث في المستند
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
absorber.Visit(doc.Pages[1]);
foreach (TextFragment fragment in absorber.TextFragments)
{
	//افعل شيئًا به شظايا
	Console.WriteLine("Text '{0}' on pos {1} invisibility: {2} ",
	fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

## خاتمة

تهنئة ! لقد نجحت في إضافة النص المخفي والعثور عليه في مستند PDF باستخدام Aspose.PDF for .NET. يمكنك الآن تطبيق هذه الطريقة على مشاريعك الخاصة لمعالجة النص المخفي والبحث فيه في ملفات PDF.