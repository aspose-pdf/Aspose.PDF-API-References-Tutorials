---
title: تدوير النص باستخدام الفقرة في ملف PDF
linktitle: تدوير النص باستخدام الفقرة في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية تدوير النص في ملف PDF باستخدام Aspose.PDF لـ .NET. اتبع هذا الدليل خطوة بخطوة لإنشاء مستنداتك.
type: docs
weight: 380
url: /ar/net/programming-with-text/rotate-text-using-paragraph/
---
## مقدمة

إن إنشاء ملفات PDF بنص ديناميكي يمكن أن يكون وسيلة جذابة لنقل المعلومات. إذا كنت تبحث عن إضافة بعض الأناقة إلى مستنداتك، فإن تدوير النص يمكن أن يساعد في التأكيد على النقاط الرئيسية أو ببساطة توفير تصميم جذاب بصريًا. في هذا الدليل، سأشرح لك كيفية تدوير النص باستخدام Aspose.PDF لـ .NET، مما يجعل مستندات PDF الخاصة بك أكثر تفاعلية وإثارة للاهتمام!

## المتطلبات الأساسية

قبل أن نتعمق في عالم تدوير النص المثير في ملفات PDF، دعنا نتأكد من إعداد كل شيء بشكل صحيح. فيما يلي المتطلبات الأساسية التي ستحتاج إليها:

1.  Aspose.PDF for .NET: تأكد من تثبيت Aspose.PDF for .NET في مشروعك. يمكنك تنزيله من[موقع إلكتروني](https://releases.aspose.com/pdf/net/).
2. Visual Studio: يفترض هذا البرنامج التعليمي أنك تستخدم Visual Studio لتطوير .NET.
3. المعرفة الأساسية بلغة C#: ستساعدك المعرفة ببرمجة C# على فهم الأمثلة بشكل أفضل. إذا كنت جديدًا، فلا تقلق؛ سنشرح لك الأمر خطوة بخطوة!
4. .NET Framework: تأكد من إعداد مشروعك باستخدام إصدار مناسب من .NET Framework. يدعم Aspose.PDF إصدارات مختلفة، لذا تحقق من الوثائق للتأكد من التوافق.

بمجرد توفر هذه المتطلبات الأساسية، سنكون مستعدين لبدء كتابة بعض التعليمات البرمجية!

## استيراد الحزم

لاستخدام Aspose.PDF بشكل فعال، ستحتاج إلى استيراد المساحات الأساسية اللازمة. إليك كيفية القيام بذلك:

### افتح مشروعك

قم بتشغيل Visual Studio وافتح المشروع الذي تريد تنفيذ تدوير النص فيه في PDF.

### إضافة مرجع

انقر بزر الماوس الأيمن على مشروعك في مستكشف الحلول، ثم حدد "إدارة حزم NuGet". 

### البحث عن Aspose.PDF وتثبيته

في مدير الحزم NuGet، ابحث عن "Aspose.PDF" وقم بتثبيته. سيمكنك هذا الإجراء من الوصول إلى جميع الفئات والوظائف المتاحة في مكتبة Aspose.PDF.

### استيراد مساحة الاسم

في الجزء العلوي من ملف C# الخاص بك، تحتاج إلى استيراد مساحة اسم Aspose.PDF:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Facades;
```

وبهذا، أنت جاهز لبدء البرمجة!

حسنًا! الآن دعنا ننتقل إلى لب الموضوع - تدوير النص في ملف PDF. سنشرح التعليمات البرمجية خطوة بخطوة.

## الخطوة 1: تهيئة المستند

الخطوة الأولى هي إنشاء نسخة جديدة من مستند PDF. هذا هو المكان الذي ستحتفظ فيه بكل عملك الشاق.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // حدد دليل المستند الخاص بك
Document pdfDocument = new Document(); // تهيئة كائن المستند
```
هنا، نقوم بتحديد دليل للمستند وتهيئة كائن مستند جديد. سيعمل هذا الكائن كحاوية لملف PDF الخاص بك.

## الخطوة 2: الحصول على صفحة معينة

الآن، دعنا نضيف صفحة حيث سنقوم بتدوير النص:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add(); // الحصول على صفحة معينة
```
يضيف هذا السطر صفحة جديدة إلى ملف PDF ويسمح لنا بالبدء في إضافة المحتوى إليه.

## الخطوة 3: إنشاء فقرة نصية

الآن، دعنا ننشئ فقرة حيث سنضيف أجزاء النص:

```csharp
TextParagraph paragraph = new TextParagraph();
paragraph.Position = new Position(200, 600); // تعيين موضع الفقرة
```
هنا، نقوم بتهيئة TextParagraph وتعيين موضعها على الصفحة. تحدد الإحداثيات (200، 600) مكان بدء الفقرة على الصفحة.

## الخطوة 4: إنشاء أجزاء نصية 

الآن يأتي الجزء الممتع - إنشاء أجزاء النص! سننشئ ثلاثة أجزاء نصية، اثنان منها سيتم تدويرهما.

### 4.1: إنشاء جزء نصي مُدار

```csharp
TextFragment textFragment1 = new TextFragment("rotated text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment1.TextState.Rotation = 45; // ضبط الدوران
```
هنا، نقوم بإنشاء أول جزء نصي يحمل اسم "نص مُدار". ونحدد حجم الخط ونوعه، ثم نطبق تدويرًا بمقدار 45 درجة.

### 4.2: إنشاء جزء نصي رئيسي

الآن، دعونا نضيف جزء النص الرئيسي.

```csharp
TextFragment textFragment2 = new TextFragment("main text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
```
ستبقى هذه القطعة دون تعديل وستكون بمثابة النص الرئيسي في الفقرة.

### 4.3: إنشاء جزء نصي مدور آخر

وأخيرًا، سننشئ جزءًا آخر من النص المدور.

```csharp
TextFragment textFragment3 = new TextFragment("another rotated text");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = -45; // ضبط الدوران
```
مثل القطعة الأولى، تتميز هذه القطعة بدوران بمقدار -45 درجة، مما يضيف تباينًا بصريًا مثيرًا للاهتمام.

## الخطوة 5: إضافة أجزاء نصية إلى الفقرة

الآن، حان الوقت لإضافة كل أجزاء النص هذه إلى الفقرة التي أنشأناها سابقًا:

```csharp
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
```
 نحن ببساطة نضيف كل جزء من النص إلى فقرتنا.`AppendLine` تضمن الطريقة أن يتم تكديس كل جزء من النص عموديًا.

## الخطوة 6: إنشاء كائن TextBuilder

بعد ذلك، سوف نستخدم TextBuilder لإضافة فقرتنا إلى صفحة PDF:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendParagraph(paragraph); // قم بإضافة فقرة النص إلى صفحة PDF
```
يعمل كائن TextBuilder كأداة لتطبيق الفقرة على صفحة PDF المحددة.

## الخطوة 7: احفظ المستند

بعد كل هذا العمل الشاق، حان الوقت لحفظ المستند ورؤية ما أنشأناه!

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated2_out.pdf");
```
يقوم هذا السطر بحفظ المستند في الدليل المحدد باسم "TextFragmentTests_Rotated2_out.pdf". 

وفويلا! لديك الآن ملف PDF يحتوي على نص مُدار!

## خاتمة

إن تدوير النص في ملف PDF يمكن أن يضيف قدرًا كبيرًا من الإبداع والتركيز إلى مستنداتك. باستخدام Aspose.PDF for .NET، من السهل تنفيذه وتخصيصه ليناسب احتياجات التصميم الخاصة بك. باتباع هذا الدليل خطوة بخطوة، تعلمت كيفية إنشاء نص مدور داخل ملف PDF، مما يوفر إمكانيات جديدة لتقديم المعلومات بطريقة جذابة. 

## الأسئلة الشائعة

### ما هو Aspose.PDF لـ .NET؟
Aspose.PDF for .NET هي مكتبة قوية تسمح للمطورين بإنشاء مستندات PDF ومعالجتها وتحويلها مباشرة داخل تطبيقات .NET.

### كيف أقوم بتثبيت Aspose.PDF في مشروعي؟
 يمكنك تثبيت Aspose.PDF عبر NuGet Package Manager في Visual Studio أو عن طريق تنزيله من[صفحة تنزيلات Aspose](https://releases.aspose.com/pdf/net/).

### هل يمكنني استخدام Aspose.PDF مجانًا؟
 نعم، يقدم Aspose.PDF نسخة تجريبية مجانية. يمكنك البدء باستخدام[نسخة تجريبية مجانية](https://releases.aspose.com/) واستكشاف ميزاته.

### هل يتوفر الدعم لـ Aspose.PDF؟
 بالتأكيد! يمكنك التواصل معنا[دعم Aspose](https://forum.aspose.com/c/pdf/10) للحصول على المساعدة بشأن أي مشكلات تواجهها.

### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.PDF؟
 يمكنك شراء ترخيص مؤقت من[موقع Aspose](https://purchase.aspose.com/temporary-license/) لتجربة الميزات الكاملة للمكتبة.