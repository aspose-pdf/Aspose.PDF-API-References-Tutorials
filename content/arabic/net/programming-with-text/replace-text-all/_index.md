---
title: استبدال النص بالكامل في ملف PDF
linktitle: استبدال النص بالكامل في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية استبدال كل النص في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 350
url: /ar/net/programming-with-text/replace-text-all/
---
في هذا البرنامج التعليمي، سنشرح كيفية استبدال كل النص في ملف PDF باستخدام مكتبة Aspose.PDF لـ .NET. وسنقدم دليلًا خطوة بخطوة مع الكود المصدري C# الضروري.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- تم تثبيت Aspose.PDF لمكتبة .NET.
- فهم أساسي لبرمجة C#.

## الخطوة 1: إعداد دليل المستندات

 قم بتعيين المسار إلى الدليل الذي يوجد به ملف PDF المدخل. استبدل`"YOUR DOCUMENT DIRECTORY"` في`dataDir` متغير يحتوي على المسار إلى ملف PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: تحميل مستند PDF

 قم بتحميل مستند PDF باستخدام`Document` الفئة من مكتبة Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextAll.pdf");
```

## الخطوة 3: البحث عن النص واستبداله

 إنشاء`TextFragmentAbsorber` كائن للعثور على جميع حالات عبارة البحث المدخلة. اقبل الممتص لجميع صفحات مستند PDF لاستخراج أجزاء النص.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## الخطوة 4: استبدال النص

قم بالتنقل عبر أجزاء النص المستخرجة واستبدال النص حسب الحاجة. قم بتحديث النص والخصائص الأخرى مثل الخط وحجم الخط ولون المقدمة ولون الخلفية.

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

## الخطوة 5: احفظ ملف PDF المعدّل

احفظ مستند PDF المعدّل في ملف الإخراج المحدد.

```csharp
dataDir = dataDir + "ReplaceTextAll_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully.\nFile saved at " + dataDir);
```

### عينة من كود المصدر لاستبدال النص بالكامل باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// فتح المستند
Document pdfDocument = new Document(dataDir + "ReplaceTextAll.pdf");
// إنشاء كائن TextAbsorber للعثور على جميع حالات عبارة البحث المدخلة
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// قبول الممتص لجميع الصفحات
pdfDocument.Pages.Accept(textFragmentAbsorber);
// احصل على أجزاء النص المستخرجة
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// التنقل عبر الشظايا
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

في هذا البرنامج التعليمي، تعلمت كيفية استبدال كل النص في مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. باتباع الدليل خطوة بخطوة وتنفيذ التعليمات البرمجية C# المقدمة، يمكنك تحميل مستند PDF والبحث عن النص المطلوب واستبداله وحفظ ملف PDF المعدل.

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "استبدال النص بالكامل في ملف PDF"؟

أ: يهدف البرنامج التعليمي "استبدال النص بالكامل في ملف PDF" إلى إرشادك خلال عملية استخدام مكتبة Aspose.PDF لـ .NET لاستبدال جميع حالات نص معين في مستند PDF. وهو يوفر دليلاً خطوة بخطوة مع عينة من التعليمات البرمجية بلغة C#.

#### س: لماذا أرغب في استبدال كافة نسخ النص في مستند PDF؟

ج: قد يكون استبدال جميع حالات نص معين في مستند PDF ضروريًا عندما تحتاج إلى تحديث أو توحيد المحتوى في المستند بأكمله. يمكن أن تكون هذه العملية مفيدة بشكل خاص لضمان الاتساق في محتوى المستند وتنسيقه.

#### س: كيف أقوم بإعداد دليل المستندات؟

أ: لإعداد دليل المستندات:

1.  يستبدل`"YOUR DOCUMENT DIRECTORY"` في`dataDir` متغير يحتوي على المسار إلى الدليل الذي يوجد به ملف PDF المدخل الخاص بك.

#### س: كيف يمكنني استبدال جميع حالات النص في مستند PDF؟

أ: يرشدك البرنامج التعليمي خلال الخطوات التالية:

1.  قم بتحميل مستند PDF باستخدام`Document` فصل.
2.  إنشاء`TextFragmentAbsorber` كائن للعثور على جميع حالات عبارة البحث المدخلة. اقبل الممتص لجميع صفحات مستند PDF لاستخراج أجزاء النص.
3. قم بالتنقل عبر أجزاء النص المستخرجة واستبدال النص. قم بتحديث خصائص أخرى مثل الخط وحجم الخط ولون المقدمة ولون الخلفية حسب الحاجة.
4. احفظ مستند PDF المعدّل.

#### س: هل يمكنني استبدال النص بناءً على بحث حساس لحالة الأحرف؟

 ج: نعم، يمكنك تعديل`TextFragmentAbsorber` ابحث عن نص لإجراء بحث حساس لحالة الأحرف. ما عليك سوى تقديم النص الدقيق الذي تريد البحث عنه، وسيقوم الممتص بمطابقته وفقًا لذلك.

#### س: هل استبدال الخط اختياري عند استبدال النص؟

ج: نعم، استبدال الخط اختياري. إذا لم تحدد خطًا جديدًا، فسيحتفظ النص بخط جزء النص الأصلي.

#### س: كيف يمكنني استبدال النص في أقسام محددة من مستند PDF؟

ج: يمكنك تعديل الحلقة عبر أجزاء النص لتشمل عبارات شرطية بناءً على موضع أجزاء النص. بهذه الطريقة، يمكنك اختيار استبدال النص فقط في أقسام محددة من ملف PDF.

#### س: ما هي النتيجة المتوقعة من تنفيذ الكود المقدم؟

ج: باتباع البرنامج التعليمي وتشغيل كود C# المقدم، ستستبدل جميع حالات النص المحدد في مستند PDF. سيحتوي النص المستبدل على الخصائص التي حددتها، مثل الخط وحجم الخط ولون المقدمة ولون الخلفية.

#### س: هل يمكنني استخدام هذا النهج لاستبدال العناصر غير النصية، مثل الصور أو التعليقات التوضيحية؟

ج: لا، يركز هذا البرنامج التعليمي بشكل خاص على استبدال النص في مستند PDF. إذا كنت بحاجة إلى استبدال عناصر غير نصية، فستحتاج إلى اتباع إجراءات مختلفة أو استخدام ميزات Aspose.PDF الأخرى.