---
title: إضافة وبحث النص المخفي في ملف PDF
linktitle: إضافة وبحث النص المخفي في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لإضافة نص مخفي والبحث فيه في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 20
url: /ar/net/programming-with-text/add-and-search-hidden-text/
---
في هذا البرنامج التعليمي، سنرشدك إلى كيفية إضافة النص المخفي والبحث فيه في ملف PDF باستخدام Aspose.PDF for .NET. اتبع هذه الخطوات لتنفيذ هذه العملية بسهولة.

## 1. المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- تم تثبيت وتكوين Visual Studio أو أي بيئة تطوير أخرى.
- معرفة أساسية بلغة البرمجة C#.
- تم تثبيت مكتبة Aspose.PDF لـ .NET. يمكنك تنزيله من موقع Aspose الرسمي.

## 2. إنشاء مستند PDF بنص مخفي

للبدء، استخدم الكود التالي لإنشاء مستند PDF جديد يحتوي على نص مخفي:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// قم بإنشاء مستند
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
// تعيين خاصية النص - غير مرئية
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
```

تأكد من توفير المسار واسم الملف المطلوبين لمستند PDF.

## 3. ابحث عن نص في المستند

بعد ذلك، سوف نقوم بالبحث في النص المخفي في وثيقة PDF. استخدم الكود التالي:

```csharp
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb.Visit(doc.Pages[1]);
foreach(TextFragment fragment in absorber.TextFragments)
{
//افعل شيئًا بالشظايا
Console.WriteLine("Text '{0}' at position {1}, invisibility: {2} ",
fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

سيؤدي هذا إلى البحث في النص المخفي في الصفحة الثانية من مستند PDF وعرض المعلومات ذات الصلة.

### نموذج التعليمات البرمجية المصدر لإضافة نص مخفي والبحث فيه باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//إنشاء مستند بنص مخفي
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
//تعيين خاصية النص - غير مرئية
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
//البحث عن نص في الوثيقة
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
absorber.Visit(doc.Pages[1]);
foreach (TextFragment fragment in absorber.TextFragments)
{
	//افعل شيئًا بالشظايا
	Console.WriteLine("Text '{0}' on pos {1} invisibility: {2} ",
	fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

## خاتمة

تهنئة ! لقد نجحت في إضافة النص المخفي والعثور عليه في مستند PDF باستخدام Aspose.PDF لـ .NET. يمكنك الآن تطبيق هذه الطريقة على مشاريعك الخاصة لمعالجة النص المخفي والبحث فيه في ملفات PDF.

### الأسئلة الشائعة

#### س: ما هو Aspose.PDF لـ .NET؟

ج: Aspose.PDF for .NET هي مكتبة قوية تمكّن المطورين من إنشاء مستندات PDF ومعالجتها وتحويلها ضمن تطبيقات .NET.

#### س: هل يمكن استخدام النص المخفي لأغراض وضع العلامات المائية؟

ج: بالتأكيد! يمكن أن يكون النص المخفي بمثابة وسيلة فعالة لوضع علامة مائية على مستندات PDF، مما يضيف طبقة إضافية من الأمان.

#### س: هل من الممكن الكشف عن النص المخفي في وثيقة PDF؟

ج: نعم، يمكن تحقيق عملية البحث عن النص المخفي والكشف عنه داخل مستند PDF باستخدام التقنيات الموضحة في هذا البرنامج التعليمي.

#### س: ما هي الوظائف الأخرى التي يقدمها Aspose.PDF لـ .NET؟

ج: بعيدًا عن معالجة النص المخفي، يوفر Aspose.PDF for .NET مجموعة واسعة من الميزات، بما في ذلك إنشاء PDF وتحويله وتشفيره والمزيد.