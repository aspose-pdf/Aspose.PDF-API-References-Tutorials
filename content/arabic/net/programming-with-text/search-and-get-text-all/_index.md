---
title: البحث والحصول على النص كله
linktitle: البحث والحصول على النص كله
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية البحث والحصول على نص من جميع صفحات مستند PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 420
url: /ar/net/programming-with-text/search-and-get-text-all/
---
## مقدمة

هل احتجت يومًا إلى استخراج نص معين من ملف PDF ولكنك وجدت الأمر صعبًا؟ قد تبدو ملفات PDF أحيانًا وكأنها حاويات مغلقة، مما يجعل من الصعب الحصول على المعلومات التي تحتاجها. ولكن إليك الأخبار الجيدة: باستخدام Aspose.PDF for .NET، يمكنك بسهولة البحث عن نص واسترداده من أي ملف PDF. توفر هذه المكتبة القوية كل ما تحتاجه للعمل مع ملفات PDF في تطبيقات .NET، مما يجعل استخراج النص أمرًا سهلاً. في هذا البرنامج التعليمي، سنرشدك خلال عملية البحث عن نص واستخراجه من ملف PDF باستخدام Aspose.PDF for .NET. سواء كنت تقوم ببناء أداة تحليل نص أو تحتاج فقط إلى أتمتة استخراج البيانات من تقارير PDF، فأنت في المكان الصحيح!

## المتطلبات الأساسية

قبل أن ننتقل إلى الكود، دعنا نتأكد من إعداد كل شيء:

1. Aspose.PDF for .NET: ستحتاج إلى تنزيل Aspose.PDF for .NET وتثبيته. يمكنك الحصول عليه من صفحة التنزيل[هنا](https://releases.aspose.com/pdf/net/).
2. بيئة .NET: تأكد من إعداد .NET Framework أو .NET Core على جهاز التطوير الخاص بك.
3. المعرفة الأساسية بلغة C##: يوصى ببعض المعرفة بلغة C# والعمل مع مشاريع .NET.
4.  مستند PDF: ملف PDF نموذجي سنستخرج منه النص. في هذا المثال، سنستخدم`SearchAndGetTextFromAll.pdf`.

## استيراد الحزم

قبل كتابة أي كود، يجب عليك استيراد المساحات الأساسية اللازمة إلى مشروعك للعمل مع Aspose.PDF.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

توفر هذه المساحات الاسمية إمكانية الوصول إلى نموذج كائن المستند الخاص بملف PDF وتسمح لنا بالتعامل مع النص داخل الملف.

دعونا نقسم العملية إلى خطوات بسيطة حتى تتمكن من متابعتها بسهولة.

## الخطوة 1: تعيين دليل المستندات

أولاً وقبل كل شيء، عليك تحديد المسار إلى الدليل الذي يوجد به ملف PDF. يساعد هذا التطبيق في تحديد الملف الذي ستستخرج النص منه.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

-  ال`dataDir` يجب أن يشير المتغير إلى الدليل الذي يوجد به`SearchAndGetTextFromAll.pdf` تم تخزين الملف.
-  يستبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي على جهازك.

## الخطوة 2: افتح مستند PDF

بعد ذلك، سنفتح مستند PDF باستخدام Aspose.PDF`Document` هدف.

```csharp
// فتح المستند
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

-  نقوم بإنشاء مثيل جديد لـ`Document` الصف عن طريق تمرير مسار الملف الكامل لملف PDF.
- سيؤدي هذا إلى تحميل ملف PDF في الذاكرة، مما يجعله جاهزًا للمعالجة.

## الخطوة 3: إنشاء ممتص نص

 ال`TextFragmentAbsorber` يتم استخدام الكائن للبحث عن نص معين داخل ملف PDF. في هذه الحالة، سنبحث عن كلمة "نص".

```csharp
// إنشاء كائن TextAbsorber للعثور على جميع حالات عبارة البحث المدخلة
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

-  ال`TextFragmentAbsorber` يتم تهيئة السلسلة بالسلسلة`"text"`وهذا يعني أنه سيبحث عن أي ظهور لكلمة "نص" داخل مستند PDF.

## الخطوة 4: قبول الامتصاص لجميع الصفحات

الآن، سنقوم بتوجيه مستند PDF لقبول الممتص والبحث عن النص عبر جميع صفحاته.

```csharp
// قبول الممتص لجميع الصفحات
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

-  ال`Accept` يتم تطبيق الطريقة على صفحات المستند. سيؤدي هذا إلى البحث في كافة الصفحات عن النص المحدد.

## الخطوة 5: استخراج أجزاء النص

بمجرد أن يقوم الممتص بمسح المستند، يمكننا استرجاع أجزاء النص المستخرجة.

```csharp
// احصل على أجزاء النص المستخرجة
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

-  ال`TextFragments` ممتلكات`TextFragmentAbsorber` يقوم بإرجاع مجموعة من كافة أجزاء النص التي تطابق مصطلح البحث.

## الخطوة 6: تكرار أجزاء النص

الآن بعد أن أصبح لدينا مجموعة من أجزاء النص، سنقوم بالمرور عليها واستخراج التفاصيل.

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

-  ال`foreach` تتكرر الحلقة خلال كل`TextFragment` في المجموعة.
- نقوم بطباعة خصائص مختلفة لكل جزء، مثل النص الفعلي، وموقعه على الصفحة، وتفاصيل الخط، وحجم الخط.
-  ال`XIndent` و`YIndent` تعطي الخصائص الإحداثيات الدقيقة لشظية النص داخل ملف PDF.

## خاتمة

والآن، لقد انتهينا! فباستخدام بضعة أسطر من التعليمات البرمجية، نجحنا في البحث واستخراج نص من ملف PDF باستخدام Aspose.PDF لـ .NET. تتيح لك مرونة Aspose.PDF التعامل مع ملفات PDF بطرق عديدة، مما يجعلها خيارًا ممتازًا للمطورين الذين يحتاجون إلى حلول PDF قوية في بيئات .NET. يمكنك بسهولة توسيع هذا المثال للبحث عن كلمات أخرى، أو استخراج المزيد من التفاصيل، أو حتى التعامل مع محتوى PDF بناءً على احتياجاتك. نأمل أن يكون هذا الدليل قد أعطاك نهجًا واضحًا ومباشرًا للعمل مع ملفات PDF. انطلق وجربه مع ملفات PDF الخاصة بك!

## الأسئلة الشائعة

### هل يمكنني البحث عن كلمات متعددة في وقت واحد؟  
 نعم يمكنك تعديل`TextFragmentAbsorber` للبحث عن عبارات متعددة عن طريق تعديل سلسلة البحث وفقًا لذلك.

### ماذا لو كان النص يمتد على عدة أسطر؟  
سيظل برنامج Aspose.PDF يتعرف على النص ويستخرجه حتى لو كان يتكون من عدة أسطر. ويمكنك التعامل مع هذه الأجزاء بشكل فردي.

### كيف أحفظ النص المستخرج في ملف؟  
 يمكنك كتابة النص المستخرج إلى ملف باستخدام عمليات الإدخال/الإخراج القياسية لملف C#، مثل`StreamWriter`.

### هل يدعم Aspose.PDF استخراج النص من ملفات PDF الممسوحة ضوئيًا؟  
لا يدعم Aspose.PDF تقنية التعرف الضوئي على الحروف. بالنسبة لملفات PDF الممسوحة ضوئيًا، ستحتاج إلى أداة التعرف الضوئي على الحروف للتعرف على النص.

### كيف أتعامل مع ملفات PDF المشفرة؟  
إذا كان ملف PDF الخاص بك محميًا بكلمة مرور، فيمكنك إلغاء قفله باستخدام Aspose.PDF عن طريق تقديم كلمة المرور عند تحميل المستند.