---
title: استبدال النص في تعبير عادي في ملف PDF
linktitle: استبدال تعبير Texton العادي في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية استبدال النص استنادًا إلى التعبيرات العادية في ملف PDF باستخدام Aspose.PDF لـ .NET. اتبع دليلنا خطوة بخطوة لأتمتة تغييرات النص بكفاءة.
type: docs
weight: 360
url: /ar/net/programming-with-text/replace-text-on-regular-expression/
---
## مقدمة

Aspose.PDF for .NET هي أداة رائعة تتيح للمطورين التعامل مع ملفات PDF بسهولة. ومن بين ميزاتها القوية القدرة على البحث عن نص استنادًا إلى تعبيرات منتظمة واستبداله. إذا كان عليك التعامل مع ملف PDF حيث كنت بحاجة إلى تغيير أنماط نصية معينة مثل التواريخ أو أرقام الهواتف أو الرموز، فهذا هو ما تبحث عنه بالضبط. في هذا البرنامج التعليمي، سأرشدك خلال عملية استبدال النص باستخدام التعبيرات المنتظمة في ملف PDF. وسنقسمها إلى خطوات سهلة المتابعة حتى تتمكن من دمج هذه الوظيفة بسلاسة في مشاريعك.

## المتطلبات الأساسية

قبل الغوص في الكود، دعنا نتأكد من إعداد كل شيء:

1.  Aspose.PDF for .NET: ستحتاج إلى أحدث إصدار من Aspose.PDF for .NET. يمكنك تنزيله[هنا](https://releases.aspose.com/pdf/net/).
2. IDE: Visual Studio أو أي بيئة تطوير متكاملة (IDE) متوافقة مع .NET.
3. .NET Framework: تأكد من تثبيت .NET Framework 4.0 أو إصدار أحدث.
4. مستند PDF: ملف PDF نموذجي حيث تريد البحث عن النص واستبداله.

بمجرد أن يكون كل شيء في مكانه، فأنت جاهز للبدء!

## استيراد الحزم

أول شيء يتعين علينا القيام به هو استيراد الحزم المطلوبة. وهذا يضمن قدرتنا على الوصول إلى جميع الفئات والطرق اللازمة من Aspose.PDF.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

يتيح لنا هذا العمل مع مستندات PDF ومعالجة أجزاء النص داخل المستند.

لنبدأ الآن في شرح العملية خطوة بخطوة. تابع الخطوات حتى نصل إلى استبدال النص استنادًا إلى التعبيرات العادية.

## الخطوة 1: تحميل مستند PDF

 أولاً، تحتاج إلى تحميل مستند PDF حيث ستقوم باستبدال النص. يتم ذلك باستخدام`Document` الفئة من Aspose.PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionPage.pdf");
```

 في هذه الخطوة، استبدل`"YOUR DOCUMENT DIRECTORY"`مع المسار الفعلي الذي يتم تخزين ملف PDF فيه. يفتح هذا الكود ملف PDF ويحمله إلى`pdfDocument` الكائن الذي سنقوم بمعالجته في الخطوات التالية.

## الخطوة 2: تحديد التعبيرات العادية

 الآن بعد أن قمت بتحميل المستند، فإن الخطوة التالية هي تحديد التعبير العادي الذي سيبحث عن أنماط النص التي تهمك. على سبيل المثال، إذا كنت تبحث عن استبدال نطاق سنة مثل "1999-2000"، فيمكنك استخدام التعبير العادي`\d{4}-\d{4}`.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); 
```

 هذا الخط ينشئ`TextFragmentAbsorber` سيبحث هذا عن أي رقم مكون من أربعة أرقام، متبوعًا بواصلة، ثم رقم آخر مكون من أربعة أرقام. يمكنك تعديل التعبير العادي حسب الحاجة لمطابقة حالة الاستخدام الخاصة بك.

## الخطوة 3: تمكين خيار البحث باستخدام التعبيرات العادية

 يتيح لك Aspose.PDF ضبط كيفية البحث عن النص. في هذه الحالة، سنقوم بتمكين مطابقة التعبيرات العادية باستخدام`TextSearchOptions` فصل.

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
```

 من خلال ضبط هذا الخيار على`true`، يمكنك تمكين استخدام التعبيرات العادية للبحث داخل ملف PDF.

## الخطوة 4: تطبيق الممتص على صفحة محددة

 بعد ذلك، سوف نطبق`TextFragmentAbsorber` لصفحة معينة من المستند. ينطبق هذا المثال على الصفحة الأولى.

```csharp
pdfDocument.Pages[1].Accept(textFragmentAbsorber);
```

تستخرج هذه الطريقة كل أجزاء النص التي تتطابق مع التعبير العادي من الصفحة الأولى من المستند. إذا كنت تريد البحث في المستند بالكامل، يمكنك تكرار البحث في كل الصفحات.

## الخطوة 5: تكرار واستبدال النص

الآن يأتي الجزء الممتع! سننتقل عبر أجزاء النص المستخرجة، وسنستبدل النص، وسنخصص خصائص مثل حجم الخط ونوعه ولونه.

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

foreach (TextFragment textFragment in textFragmentCollection)
{
    textFragment.Text = "New Phrase"; // استبدله بالنص الجديد
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
    textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
```

 هنا، يمكنك المرور عبر كل جزء نصي يتطابق مع التعبير العادي. لكل تطابق، يتم استبدال النص بـ`"New Phrase"`يمكنك أيضًا تخصيص الخط إلى "Verdana"، وتعيين حجم الخط إلى 22، وتغيير ألوان النص والخلفية.

## الخطوة 6: احفظ مستند PDF المحدث

بمجرد إجراء جميع التغييرات، حان الوقت لحفظ مستند PDF المعدل.

```csharp
dataDir = dataDir + "ReplaceTextonRegularExpression_out.pdf";
pdfDocument.Save(dataDir);
```

سيؤدي هذا إلى حفظ ملف PDF المحدث مع جميع بدائل النص في ملف جديد يسمى`ReplaceTextonRegularExpression_out.pdf`.

## الخطوة 7: التحقق من التغييرات

أخيرًا، للتأكد من أن كل شيء يعمل، اطبع رسالة إلى وحدة التحكم:

```csharp
Console.WriteLine("\nText replaced successfully based on a regular expression.\nFile saved at " + dataDir);
```

ستؤكد هذه الرسالة أن عملية استبدال النص تمت بنجاح وستعرض الموقع الذي تم حفظ ملف PDF الجديد فيه.

## خاتمة

لقد نجحت في استبدال نص في ملف PDF استنادًا إلى تعبيرات منتظمة باستخدام Aspose.PDF لـ .NET! سواء كنت تقوم بأتمتة معالجة المستندات أو مجرد تنظيف بعض المعلومات القديمة، فإن هذه الميزة قوية بشكل لا يصدق. باستخدام بضعة أسطر فقط من التعليمات البرمجية، يمكنك إجراء تغييرات نصية معقدة عبر مستندات كبيرة في ثوانٍ.

## الأسئلة الشائعة

### هل يمكنني استخدام تعبيرات منتظمة متعددة في مستند واحد؟
 نعم، يمكنك إنشاء العديد من`TextFragmentAbsorber` الكائنات، كل منها يحتوي على تعبيرات منتظمة مختلفة، وتطبيقها على المستند.

### هل Aspose.PDF for .NET متوافق مع .NET Core؟
نعم، يدعم Aspose.PDF لـ .NET كل من .NET Framework و.NET Core.

### هل يمكنني استبدال النص في صفحات متعددة مرة واحدة؟
بالتأكيد! بدلاً من تطبيق الممتص على صفحة واحدة، يمكنك تكراره عبر جميع الصفحات أو حتى تطبيقه على المستند بأكمله مرة واحدة.

### ماذا لو أردت البحث عن نص لا يميز بين الأحرف الكبيرة والصغيرة؟
يمكنك تعديل التعبيرات العادية لتصبح غير حساسة لحالة الأحرف عن طريق استخدام علامات التعبيرات العادية المناسبة أو تعديل خيارات البحث.

### هل يمكنني استبدال الصور في ملف PDF؟
نعم، يدعم Aspose.PDF لـ .NET أيضًا استبدال الصور ومعالجتها داخل مستندات PDF.