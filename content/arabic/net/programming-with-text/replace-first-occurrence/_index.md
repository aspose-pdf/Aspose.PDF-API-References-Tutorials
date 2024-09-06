---
title: استبدال أول حدوث
linktitle: استبدال أول حدوث
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية استبدال الظهور الأول للنص في مستند PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 330
url: /ar/net/programming-with-text/replace-first-occurrence/
---
في هذا البرنامج التعليمي، سنشرح كيفية استبدال أول ظهور لنص معين في مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. سنمر بعملية فتح مستند PDF خطوة بخطوة، والعثور على أول ظهور لعبارة البحث، واستبدال النص، وتحديث الخصائص، وحفظ ملف PDF المعدّل باستخدام كود المصدر C# المقدم.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- تم تثبيت مكتبة Aspose.PDF لـ .NET.
- فهم أساسي لبرمجة C#.

## الخطوة 1: إعداد دليل المستندات

 أولاً، تحتاج إلى تعيين المسار إلى الدليل الذي يحتوي على ملف PDF المدخل. استبدل`"YOUR DOCUMENT DIRECTORY"` في`dataDir` متغير يحتوي على المسار إلى ملف PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: افتح مستند PDF

 بعد ذلك، نفتح مستند PDF باستخدام`Document` الفئة من مكتبة Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

## الخطوة 3: ابحث عن الظهور الأول لعبارة البحث

 نحن ننشئ`TextFragmentAbsorber` الكائن وقبوله لجميع صفحات مستند PDF للعثور على جميع حالات عبارة البحث.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## الخطوة 4: استبدال النص

إذا تم العثور على عبارة البحث في مستند PDF، فإننا نستعيد أول ظهور لجزء النص ونقوم بتحديث خصائصه بالنص الجديد والتنسيق.

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
if (textFragmentCollection.Count > 0)
{
    TextFragment textFragment = textFragmentCollection[1];
    textFragment.Text = "New Phrase";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
}
```

## الخطوة 5: احفظ ملف PDF المعدّل

وأخيرًا، نقوم بحفظ مستند PDF المعدّل في ملف الإخراج المحدد.

```csharp
dataDir = dataDir + "ReplaceFirstOccurrence_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully.\nFile saved at " + dataDir);
```

### عينة من كود المصدر لاستبدال أول حدوث باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// فتح المستند
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
// إنشاء كائن TextAbsorber للعثور على جميع حالات عبارة البحث المدخلة
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// قبول الممتص لجميع الصفحات
pdfDocument.Pages.Accept(textFragmentAbsorber);
// احصل على أجزاء النص المستخرجة
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
if (textFragmentCollection.Count > 0)
{
	// احصل على أول ظهور للنص واستبدله
	TextFragment textFragment = textFragmentCollection[1];
	// تحديث النص والخصائص الأخرى
	textFragment.Text = "New Phrase";
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	dataDir = dataDir + "ReplaceFirstOccurrence_out.pdf";
	pdfDocument.Save(dataDir);                 
	Console.WriteLine("\nText replaced successfully.\nFile saved at " + dataDir);
}
```

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية استبدال أول ظهور لنص معين في مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. باتباع الدليل خطوة بخطوة وتنفيذ التعليمات البرمجية C# المقدمة، يمكنك فتح مستند PDF، والعثور على أول ظهور لعبارة بحث، واستبدال النص، وتحديث الخصائص، وحفظ ملف PDF المعدل.

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "استبدال الظهور الأول"؟

ج: يوضح البرنامج التعليمي "استبدال أول ظهور" كيفية استخدام مكتبة Aspose.PDF لـ .NET لاستبدال أول ظهور لنص معين في مستند PDF. ويوفر تعليمات خطوة بخطوة حول كيفية فتح مستند PDF، وتحديد أول ظهور لعبارة بحث، واستبدال النص، وتحديث الخصائص، وحفظ ملف PDF المعدل.

#### س: لماذا أرغب في استبدال الظهور الأول للنص في مستند PDF؟

ج: يعد استبدال أول ظهور للنص في مستند PDF مفيدًا عندما تحتاج إلى إجراء تغييرات مستهدفة على حالات محددة من عبارة معينة مع ترك حالات أخرى دون مساس. غالبًا ما يتم استخدام هذا النهج لتحديث أو تصحيح النص بطريقة خاضعة للرقابة.

#### س: كيف أقوم بإعداد دليل المستندات؟

أ: لإعداد دليل المستندات:

1.  يستبدل`"YOUR DOCUMENT DIRECTORY"` في`dataDir` متغير يحتوي على المسار إلى الدليل الذي يوجد به ملف PDF المدخل الخاص بك.

#### س: كيف يمكنني استبدال الظهور الأول لنص معين في مستند PDF؟

أ: يرشدك البرنامج التعليمي خلال العملية خطوة بخطوة:

1.  افتح مستند PDF باستخدام`Document` فصل.
2.  إنشاء`TextFragmentAbsorber` الكائن وقبوله لجميع الصفحات للعثور على مثيلات عبارة البحث.
3. إذا تم العثور على عبارة البحث، فاسترد أول ظهور لجزء النص وقم بتحديث خصائصه بالنص الجديد والتنسيق.
4. احفظ مستند PDF المعدّل.

####  س: ما هو الغرض من الاستخدام؟`TextFragmentAbsorber` to find the first occurrence of the search phrase?

 أ: ال`TextFragmentAbsorber` تُستخدم لتحديد حالات عبارة البحث داخل مستند PDF. في هذا البرنامج التعليمي، تساعد في تحديد أول ظهور للنص الذي يحتاج إلى الاستبدال.

#### س: كيف أقوم بتحديث خصائص جزء النص؟

ج: بمجرد تحديد أول ظهور لشظية النص، يمكنك تحديث خصائصها، مثل النص نفسه والخط وحجم الخط ولون النص. يتيح لك هذا تخصيص مظهر النص البديل.

#### س: هل هناك حد لاستبدال الظهور الأول للنص فقط؟

 ج: نعم، يركز هذا البرنامج التعليمي بشكل خاص على استبدال أول ظهور للنص. إذا كنت بحاجة إلى استبدال ظهورات متعددة لنفس النص، فيمكنك توسيع النهج من خلال التكرار عبر`TextFragmentCollection` لتحديد كل حالة وتحديثها.

#### س: ما هي النتيجة المتوقعة من تنفيذ الكود المقدم؟

ج: باتباع البرنامج التعليمي وتشغيل كود C# المقدم، ستستبدل أول ظهور للنص المحدد في مستند PDF. سيحتوي النص البديل على خصائص محدثة، مثل الخط وحجم الخط ولون النص.

#### س: هل يمكنني استخدام هذا النهج لاستبدال نسخ أخرى من نفس النص؟

 ج: نعم، يمكنك تعديل الكود للتنقل عبر`TextFragmentCollection` لاستبدال تكرارات متعددة لنفس النص. ما عليك سوى توسيع المنطق لتحديد كل تكرار وتحديثه حسب الحاجة.