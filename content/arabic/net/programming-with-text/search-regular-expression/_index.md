---
title: البحث عن تعبير عادي في ملف PDF
linktitle: البحث عن تعبير عادي في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية البحث عن التعبيرات العادية في ملفات PDF باستخدام Aspose.PDF لـ .NET في هذا البرنامج التعليمي خطوة بخطوة. عزز إنتاجيتك باستخدام التعبيرات العادية.
type: docs
weight: 440
url: /ar/net/programming-with-text/search-regular-expression/
---
## مقدمة

عند التعامل مع مستندات PDF كبيرة الحجم، قد تجد نفسك تبحث عن أنماط أو تنسيقات معينة مثل التواريخ أو أرقام الهواتف أو غيرها من البيانات المنظمة. قد يكون البحث يدويًا في ملف PDF أمرًا مرهقًا، أليس كذلك؟ وهنا يأتي استخدام التعبيرات العادية (regex) في متناول اليد. في هذا البرنامج التعليمي، سنستكشف كيفية البحث عن نمط تعبير عادي داخل ملف PDF باستخدام Aspose.PDF لـ .NET. سيرشدك هذا الدليل خلال كل خطوة حتى تتمكن من تنفيذها بسهولة في تطبيق .NET الخاص بك.

## المتطلبات الأساسية

قبل أن نتعمق في البرنامج التعليمي خطوة بخطوة، دعنا نراجع ما تحتاج إلى وضعه في مكانه:

-  Aspose.PDF لـ .NET: يجب أن تكون هذه المكتبة مثبتة. إذا لم تقم بتثبيتها بعد، يمكنك[تحميله هنا](https://releases.aspose.com/pdf/net/).
- IDE: Visual Studio أو أي IDE آخر متوافق مع C#.
- .NET Framework: تأكد من إعداد مشروعك باستخدام الإصدار المناسب من .NET Framework.
- المعرفة الأساسية بلغة C#: على الرغم من أن هذا الدليل مفصل، إلا أن الفهم الأساسي للغة C# سيكون مفيدًا.

### استيراد الحزم

للبدء، ستحتاج إلى استيراد المساحات الأساسية اللازمة من Aspose.PDF لـ .NET إلى مشروعك. تعد هذه الحزم ضرورية للعمل مع ملفات PDF وإجراء عمليات البحث باستخدام التعبيرات العادية.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

دعونا نقوم بتقسيم عملية البحث عن التعبيرات العادية في ملف PDF باستخدام Aspose.PDF إلى خطوات متعددة.

## الخطوة 1: إعداد دليل المستندات

 تبدأ كل عملية PDF بتحديد مكان وجود المستند. ستحتاج إلى تحديد المسار إلى ملف PDF الخاص بك، والذي يتم تخزينه في`dataDir` عامل.

### الخطوة 1.1: تحديد مسار المستند الخاص بك

```csharp
// حدد المسار إلى مستند PDF الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 يستبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي لملف PDF الخاص بك. هذه الخطوة بالغة الأهمية لأنها توجه الكود الخاص بك إلى الملف الذي تريد العمل به.

### الخطوة 1.2: افتح مستند PDF

 بعد ذلك، تحتاج إلى فتح مستند PDF باستخدام`Document` الفئة من Aspose.PDF.

```csharp
// افتح المستند
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
```

 هنا،`"SearchRegularExpressionAll.pdf"` هو ملف PDF النموذجي الذي سنقوم من خلاله بإجراء بحث التعبيرات العادية.

## الخطوة 2: إعداد TextFragmentAbsorber

 هذا هو المكان الذي يحدث فيه السحر!`TextFragmentAbsorber` تساعد الفئة في التقاط أجزاء من النص تتطابق مع نمط معين أو تعبير منتظم.

دعنا نعد الممتص للبحث عن الأنماط باستخدام تعبير عادي. في هذه الحالة، نبحث عن نمط سنوات مثل "1999-2000".

```csharp
// إنشاء كائن TextAbsorber للعثور على جميع العبارات المطابقة للتعبير العادي
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // مثل 1999-2000
```

 التعبير العادي`\\d{4}-\\d{4}` يبحث عن نمط مكون من أربعة أرقام متبوعة بواصلة وأربعة أرقام أخرى، وهو أمر طبيعي بالنسبة لنطاقات السنوات.

## الخطوة 3: تمكين البحث باستخدام التعبيرات العادية

 للتأكد من أن عملية البحث تفسر النمط كتعبير عادي، تحتاج إلى تكوين خيارات البحث باستخدام`TextSearchOptions` فصل.

```csharp
// تعيين خيار البحث النصي لتحديد استخدام التعبيرات العادية
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
```

 ضبط`TextSearchOptions` ل`true` ويضمن أن الممتص يستخدم البحث المبني على التعابير العادية بدلاً من النص العادي.

## الخطوة 4: قبول امتصاص النص

 في هذه المرحلة، يمكنك تطبيق أداة امتصاص النص على مستند PDF حتى تتمكن من إجراء عملية البحث. يتم ذلك عن طريق استدعاء`Accept` الطريقة على`Pages` غرض مستند PDF.

```csharp
// قبول الامتصاص لجميع الصفحات
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

تعمل هذه الأوامر على معالجة كافة صفحات ملف PDF، والبحث عن أي نص يتطابق مع التعبير العادي.

## الخطوة 5: استخراج النتائج وعرضها

 بعد اكتمال البحث، تحتاج إلى استخراج النتائج.`TextFragmentAbsorber` يخزن هذه النتائج في`TextFragmentCollection`يمكنك التنقل عبر هذه المجموعة للوصول إلى كل جزء نصي مطابق وعرضه.

### الخطوة 5.1: استرداد أجزاء النص المستخرجة

```csharp
// احصل على أجزاء النص المستخرجة
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

الآن بعد أن قمت بجمع الأجزاء، حان الوقت لتصفحها وعرض التفاصيل ذات الصلة مثل النص والموضع وتفاصيل الخط والمزيد.

### الخطوة 5.2: تكرار الأجزاء

```csharp
// التنقل عبر الشظايا
foreach (TextFragment textFragment in textFragmentCollection)
{
    Console.WriteLine("Text : {0} ", textFragment.Text);
    Console.WriteLine("Position : {0} ", textFragment.Position);
    Console.WriteLine("XIndent : {0} ", textFragment.Position.XIndent);
    Console.WriteLine("YIndent : {0} ", textFragment.Position.YIndent);
    Console.WriteLine("Font - Name : {0}", textFragment.TextState.Font.FontName);
    Console.WriteLine("Font - IsAccessible : {0} ", textFragment.TextState.Font.IsAccessible);
    Console.WriteLine("Font - IsEmbedded : {0} ", textFragment.TextState.Font.IsEmbedded);
    Console.WriteLine("Font - IsSubset : {0} ", textFragment.TextState.Font.IsSubset);
    Console.WriteLine("Font Size : {0} ", textFragment.TextState.FontSize);
    Console.WriteLine("Foreground Color : {0} ", textFragment.TextState.ForegroundColor);
}
```

 لكل واحد`TextFragment`تتم طباعة التفاصيل مثل حجم الخط واسم الخط وموضعه. وهذا لا يساعد فقط في العثور على النص، بل يمنحك أيضًا تنسيقه وموقعه الدقيقين.

## خاتمة

هذا كل ما في الأمر! إن البحث عن الأنماط في ملف PDF باستخدام التعبيرات العادية يعد أمرًا قويًا للغاية، وخاصة بالنسبة للنصوص المنظمة مثل التواريخ وأرقام الهواتف والأنماط المشابهة. يوفر Aspose.PDF for .NET طريقة سلسة لإجراء مثل هذه العمليات بسهولة. يمكنك الآن الاستفادة من قوة التعبيرات العادية لأتمتة البحث عن نص PDF، مما يجعل سير عملك أكثر كفاءة.

## الأسئلة الشائعة

### هل يمكنني البحث عن أنماط متعددة في ملف PDF واحد؟
 نعم، يمكنك تشغيل العديد من`TextFragmentAbsorber` الكائنات، كل منها بأنماط تعبيرات عادية مختلفة، عبر نفس ملف PDF.

### هل يدعم Aspose.PDF البحث عن الأنماط غير الحساسة لحالة الأحرف؟
 بالتأكيد! يمكنك تكوين`TextSearchOptions` لجعل البحث غير حساس لحالة الأحرف.

### هل هناك حد لحجم ملف PDF الذي يمكنني البحث فيه؟
لا يوجد حد صارم، ولكن قد يختلف الأداء اعتمادًا على حجم ملف PDF وتعقيد نمط التعبيرات العادية.

### هل يمكنني تسليط الضوء على النص الموجود في ملف PDF؟
نعم، يسمح لك Aspose.PDF بتسليط الضوء على النص أو حتى استبداله بمجرد العثور عليه باستخدام الممتص.

### كيف أتعامل مع الأخطاء إذا لم يتم العثور على النمط؟
 إذا لم يتم العثور على أي تطابقات،`TextFragmentCollection` ستكون فارغة. يمكنك التعامل مع هذا السيناريو من خلال فحص بسيط قبل تكرار النتائج.