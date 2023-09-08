---
title: استبدال التواجد الأول
linktitle: استبدال التواجد الأول
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استبدال التواجد الأول للنص في مستند PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 330
url: /ar/net/programming-with-text/replace-first-occurrence/
---
سنشرح في هذا البرنامج التعليمي كيفية استبدال التواجد الأول لنص معين في مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. سنجري عملية خطوة بخطوة لفتح مستند PDF، والعثور على أول ظهور لعبارة البحث، واستبدال النص، وتحديث الخصائص، وحفظ ملف PDF المعدل باستخدام كود مصدر C# المقدم.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- تم تثبيت Aspose.PDF لمكتبة .NET.
- فهم أساسي للبرمجة C#.

## الخطوة 1: إعداد دليل المستندات

 أولاً، تحتاج إلى تعيين المسار إلى الدليل حيث يوجد ملف PDF المُدخل. يستبدل`"YOUR DOCUMENT DIRECTORY"` في ال`dataDir` متغير مع المسار إلى ملف PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: افتح مستند PDF

 بعد ذلك، نقوم بفتح مستند PDF باستخدام الملف`Document` فئة من مكتبة Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

## الخطوة 3: ابحث عن التواجد الأول لعبارة البحث

 نقوم بإنشاء أ`TextFragmentAbsorber` اعترض واقبله لجميع صفحات مستند PDF للعثور على جميع مثيلات عبارة البحث.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## الخطوة 4: استبدال النص

إذا تم العثور على عبارة البحث في مستند PDF، فإننا نستعيد التواجد الأول لجزء النص ونقوم بتحديث خصائصه بالنص والتنسيق الجديدين.

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

## الخطوة 5: احفظ ملف PDF المعدل

وأخيرًا، نقوم بحفظ مستند PDF المعدل في ملف الإخراج المحدد.

```csharp
dataDir = dataDir + "ReplaceFirstOccurrence_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully.\nFile saved at " + dataDir);
```

### نموذج التعليمات البرمجية المصدر لاستبدال التكرار الأول باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
// قم بإنشاء كائن TextAbsorter للعثور على كافة مثيلات عبارة البحث المدخلة
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

في هذا البرنامج التعليمي، تعلمت كيفية استبدال التواجد الأول لنص معين في مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. باتباع الدليل خطوة بخطوة وتنفيذ كود C# المقدم، يمكنك فتح مستند PDF، والعثور على أول ظهور لعبارة بحث، واستبدال النص، وتحديث الخصائص، وحفظ ملف PDF المعدل.

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "استبدال التكرار الأول"؟

ج: يوضح البرنامج التعليمي "استبدال التكرار الأول" كيفية استخدام مكتبة Aspose.PDF لـ .NET لاستبدال التواجد الأول لنص معين في مستند PDF. فهو يوفر إرشادات خطوة بخطوة حول كيفية فتح مستند PDF، وتحديد موقع المثيل الأول لعبارة البحث، واستبدال النص، وتحديث الخصائص، وحفظ ملف PDF المعدل.

#### س: لماذا أرغب في استبدال أول ظهور للنص في مستند PDF؟

ج: يعد استبدال التواجد الأول للنص في مستند PDF مفيدًا عندما تحتاج إلى إجراء تغييرات مستهدفة على مثيلات معينة لعبارة معينة مع ترك التكرارات الأخرى دون تغيير. يُستخدم هذا الأسلوب غالبًا لتحديث النص أو تصحيحه بطريقة خاضعة للرقابة.

#### س: كيف أقوم بإعداد دليل المستندات؟

ج: لإعداد دليل المستندات:

1.  يستبدل`"YOUR DOCUMENT DIRECTORY"` في ال`dataDir` متغير مع المسار إلى الدليل حيث يوجد ملف PDF المدخل الخاص بك.

#### س: كيف يمكنني استبدال التواجد الأول لنص معين في مستند PDF؟

ج: يرشدك البرنامج التعليمي خلال العملية خطوة بخطوة:

1.  افتح مستند PDF باستخدام`Document` فصل.
2.  إنشاء`TextFragmentAbsorber` كائن وقبوله لجميع الصفحات للعثور على مثيلات عبارة البحث.
3. إذا تم العثور على عبارة البحث، فاسترجع التواجد الأول لجزء النص وقم بتحديث خصائصه بالنص والتنسيق الجديدين.
4. احفظ مستند PDF المعدل.

####  س: ما هو الغرض من الاستخدام`TextFragmentAbsorber` to find the first occurrence of the search phrase?

 ج: ال`TextFragmentAbsorber` يُستخدم لتحديد مثيلات عبارة البحث داخل مستند PDF. في هذا البرنامج التعليمي، يساعد في تحديد التواجد الأول للنص الذي يحتاج إلى الاستبدال.

#### س: كيف يمكنني تحديث خصائص جزء النص؟

ج: بمجرد تحديد موقع التواجد الأول لجزء النص، يمكنك تحديث خصائصه، مثل النص نفسه والخط وحجم الخط ولون النص. يتيح لك ذلك تخصيص مظهر النص البديل.

#### س: هل هناك قيود على استبدال أول ظهور للنص فقط؟

 ج: نعم، يركز هذا البرنامج التعليمي بشكل خاص على استبدال أول ظهور للنص. إذا كنت بحاجة إلى استبدال تكرارات متعددة لنفس النص، فيمكنك توسيع النهج من خلال التكرار خلال ملف`TextFragmentCollection` لتحديد وتحديث كل مثيل.

#### س: ما هي النتيجة المتوقعة من تنفيذ الكود المقدم؟

ج: باتباع البرنامج التعليمي وتشغيل كود C# المقدم، سوف تقوم باستبدال التواجد الأول للنص المحدد في مستند PDF. سيكون للنص البديل خصائص محدثة، مثل الخط وحجم الخط ولون النص.

#### س: هل يمكنني استخدام هذا الأسلوب لاستبدال التكرارات الأخرى لنفس النص؟

 ج: نعم، يمكنك تعديل التعليمات البرمجية للتكرار من خلال`TextFragmentCollection` لاستبدال تكرارات متعددة لنفس النص. ما عليك سوى توسيع المنطق لتحديد وتحديث كل مثيل حسب الحاجة.