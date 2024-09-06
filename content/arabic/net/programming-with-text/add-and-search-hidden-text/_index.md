---
title: إضافة وبحث النص المخفي في ملف PDF
linktitle: إضافة وبحث النص المخفي في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: دليل خطوة بخطوة لإضافة نص مخفي والبحث عنه في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 20
url: /ar/net/programming-with-text/add-and-search-hidden-text/
---
في هذا البرنامج التعليمي، سنوضح لك كيفية إضافة نص مخفي والبحث عنه في ملف PDF باستخدام Aspose.PDF for .NET. اتبع الخطوات التالية لإجراء هذه العملية بسهولة.

## 1. المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- تم تثبيت وتكوين Visual Studio أو أي بيئة تطوير أخرى.
- المعرفة الأساسية للغة البرمجة C#.
- تم تثبيت مكتبة Aspose.PDF لـ .NET. يمكنك تنزيلها من موقع Aspose الرسمي.

## 2. إنشاء مستند PDF بنص مخفي

للبدء، استخدم الكود التالي لإنشاء مستند PDF جديد يحتوي على نص مخفي:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// إنشاء مستند
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

بعد ذلك، سنبحث عن النص المخفي في مستند PDF. استخدم الكود التالي:

```csharp
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb.Visit(doc.Pages[1]);
foreach(TextFragment fragment in absorber.TextFragments)
{
//افعل شيئا مع الشظايا
Console.WriteLine("Text '{0}' at position {1}, invisibility: {2} ",
fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

سيؤدي هذا إلى البحث عن النص المخفي في الصفحة الثانية من مستند PDF وعرض المعلومات ذات الصلة.

### عينة من كود المصدر لإضافة النص المخفي والبحث عنه باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//إنشاء مستند يحتوي على نص مخفي
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
//البحث عن النص في المستند
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
absorber.Visit(doc.Pages[1]);
foreach (TextFragment fragment in absorber.TextFragments)
{
	//افعل شيئا ما بالشظايا
	Console.WriteLine("Text '{0}' on pos {1} invisibility: {2} ",
	fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

## خاتمة

مبروك! لقد نجحت في إضافة والعثور على نص مخفي في مستند PDF باستخدام Aspose.PDF for .NET. يمكنك الآن تطبيق هذه الطريقة على مشاريعك الخاصة للتعامل مع النصوص المخفية والبحث عنها في ملفات PDF.

### الأسئلة الشائعة

#### س: ما هو Aspose.PDF لـ .NET؟

ج: Aspose.PDF for .NET عبارة عن مكتبة قوية تتيح للمطورين إنشاء مستندات PDF ومعالجتها وتحويلها داخل تطبيقات .NET.

#### س: هل يمكن استخدام النص المخفي لأغراض العلامة المائية؟

ج: بالتأكيد! يمكن أن يكون النص المخفي بمثابة وسيلة فعالة لإضافة علامة مائية إلى مستندات PDF، مما يضيف طبقة إضافية من الأمان.

#### س: هل من الممكن إظهار النص المخفي في مستند PDF؟

ج: نعم، يمكن تحقيق عملية البحث عن النص المخفي داخل مستند PDF وإظهاره باستخدام التقنيات الموضحة في هذا البرنامج التعليمي.

#### س: ما هي الوظائف الأخرى التي يقدمها Aspose.PDF لـ .NET؟

ج: بالإضافة إلى معالجة النصوص المخفية، يوفر Aspose.PDF لـ .NET مجموعة واسعة من الميزات، بما في ذلك إنشاء ملفات PDF وتحويلها وتشفيرها والمزيد.