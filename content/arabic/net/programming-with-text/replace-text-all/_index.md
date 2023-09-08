---
title: استبدال النص الكل في ملف PDF
linktitle: استبدال النص الكل في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استبدال كل النص في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 350
url: /ar/net/programming-with-text/replace-text-all/
---
سنشرح في هذا البرنامج التعليمي كيفية استبدال كل النص في ملف PDF باستخدام مكتبة Aspose.PDF لـ .NET. سنقدم دليلًا خطوة بخطوة بالإضافة إلى كود مصدر C# الضروري.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- تم تثبيت Aspose.PDF لمكتبة .NET.
- الفهم الأساسي للبرمجة C#.

## الخطوة 1: إعداد دليل المستندات

 قم بتعيين المسار إلى الدليل حيث يوجد ملف PDF المدخل. يستبدل`"YOUR DOCUMENT DIRECTORY"` في ال`dataDir` متغير مع المسار إلى ملف PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل مستند PDF

 قم بتحميل مستند PDF باستخدام`Document` فئة من مكتبة Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextAll.pdf");
```

## الخطوة 3: البحث عن النص واستبداله

 إنشاء`TextFragmentAbsorber` كائن للعثور على كافة مثيلات عبارة البحث المدخلة. اقبل الممتص لجميع صفحات مستند PDF لاستخراج أجزاء النص.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## الخطوة 4: استبدال النص

قم بالمراجعة خلال أجزاء النص المستخرجة واستبدل النص كما هو مطلوب. قم بتحديث النص والخصائص الأخرى مثل الخط وحجم الخط ولون المقدمة ولون الخلفية.

```csharp
foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
{
    textFragment.Text = "TEXT";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
    textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
```

## الخطوة 5: احفظ ملف PDF المعدل

احفظ مستند PDF المعدل في ملف الإخراج المحدد.

```csharp
dataDir = dataDir + "ReplaceTextAll_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully.\nFile saved at " + dataDir);
```

### نموذج التعليمات البرمجية المصدر لاستبدال النص الكل باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "ReplaceTextAll.pdf");
// قم بإنشاء كائن TextAbsorter للعثور على كافة مثيلات عبارة البحث المدخلة
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// قبول الممتص لجميع الصفحات
pdfDocument.Pages.Accept(textFragmentAbsorber);
// احصل على أجزاء النص المستخرجة
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// حلقة من خلال الشظايا
foreach (TextFragment textFragment in textFragmentCollection)
{
	// تحديث النص والخصائص الأخرى
	textFragment.Text = "TEXT";
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
dataDir = dataDir + "ReplaceTextAll_out.pdf";
// احفظ مستند PDF الناتج.
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced  successfully.\nFile saved at " + dataDir);
```

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية استبدال كل النص في مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. باتباع الدليل خطوة بخطوة وتنفيذ كود C# المقدم، يمكنك تحميل مستند PDF والبحث عن النص المطلوب واستبداله وحفظ ملف PDF المعدل.

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "استبدال النص الكل في ملف PDF"؟

ج: يهدف البرنامج التعليمي "استبدال النص الكل في ملف PDF" إلى إرشادك خلال عملية استخدام مكتبة Aspose.PDF لـ .NET لاستبدال كافة مثيلات نص معين في مستند PDF. فهو يوفر دليلاً خطوة بخطوة مع نموذج كود C#.

#### س: لماذا أرغب في استبدال كافة مثيلات النص في مستند PDF؟

ج: قد يكون استبدال كافة مثيلات نص معين في مستند PDF ضروريًا عندما تحتاج إلى تحديث المحتوى أو توحيده في المستند بأكمله. يمكن أن تكون هذه العملية مفيدة بشكل خاص لضمان الاتساق في محتوى المستند وتنسيقه.

#### س: كيف أقوم بإعداد دليل المستندات؟

ج: لإعداد دليل المستندات:

1.  يستبدل`"YOUR DOCUMENT DIRECTORY"` في ال`dataDir` متغير مع المسار إلى الدليل حيث يوجد ملف PDF المدخل الخاص بك.

#### س: كيف يمكنني استبدال كافة مثيلات النص في مستند PDF؟

ج: يرشدك البرنامج التعليمي خلال الخطوات التالية:

1.  قم بتحميل مستند PDF باستخدام`Document` فصل.
2.  إنشاء`TextFragmentAbsorber` كائن للعثور على كافة مثيلات عبارة البحث المدخلة. اقبل الممتص لجميع صفحات مستند PDF لاستخراج أجزاء النص.
3. قم بالمرور عبر أجزاء النص المستخرجة واستبدل النص. قم بتحديث الخصائص الأخرى مثل الخط وحجم الخط ولون المقدمة ولون الخلفية كما هو مطلوب.
4. احفظ مستند PDF المعدل.

#### س: هل يمكنني استبدال النص بناءً على بحث حساس لحالة الأحرف؟

 ج: نعم، يمكنك تعديل`TextFragmentAbsorber` البحث عن نص لإجراء بحث حساس لحالة الأحرف. ما عليك سوى تقديم النص الدقيق الذي تريد البحث عنه، وسيقوم برنامج الامتصاص بمطابقته وفقًا لذلك.

#### س: هل استبدال الخط اختياري عند استبدال النص؟

ج: نعم، استبدال الخط أمر اختياري. إذا لم تحدد خطًا جديدًا، فسيحتفظ النص بخط جزء النص الأصلي.

#### س: كيف يمكنني استبدال النص في أقسام معينة من مستند PDF؟

ج: يمكنك تعديل الحلقة عبر أجزاء النص لتضمين عبارات شرطية بناءً على موضع أجزاء النص. بهذه الطريقة، يمكنك اختيار استبدال النص فقط في أقسام معينة من ملف PDF.

#### س: ما هي النتيجة المتوقعة من تنفيذ الكود المقدم؟

ج: باتباع البرنامج التعليمي وتشغيل كود C# المقدم، سوف تقوم باستبدال كافة مثيلات النص المحدد في مستند PDF. سيكون للنص المستبدل الخصائص التي حددتها، مثل الخط وحجم الخط ولون المقدمة ولون الخلفية.

#### س: هل يمكنني استخدام هذا الأسلوب لاستبدال العناصر غير النصية، مثل الصور أو التعليقات التوضيحية؟

ج: لا، يركز هذا البرنامج التعليمي بشكل خاص على استبدال النص في مستند PDF. إذا كنت بحاجة إلى استبدال عناصر غير نصية، فستحتاج إلى اتباع إجراءات مختلفة أو استخدام ميزات Aspose.PDF أخرى.