---
title: عنصر جدول الأنماط
linktitle: عنصر جدول الأنماط
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية إنشاء عنصر جدول وتصميمه في Aspose.PDF لـ .NET باستخدام الإرشادات خطوة بخطوة والتصميم المخصص والتوافق مع PDF/UA.
type: docs
weight: 170
url: /ar/net/programming-with-tagged-pdf/style-table-element/
---
## مقدمة

في هذه المقالة، سنتعمق في كيفية إنشاء عنصر جدول وتصميمه باستخدام Aspose.PDF لـ .NET. ستتعلم كيفية هيكلة جدول وتطبيق أنماط مخصصة والتحقق من توافق مستندك مع تنسيق PDF/UA. بحلول نهاية هذا البرنامج التعليمي، ستتمكن من إنشاء جداول ذات مظهر احترافي في ملفات PDF الخاصة بك بسهولة!

## المتطلبات الأساسية

قبل القفز إلى البرنامج التعليمي، ستحتاج إلى التأكد من أن لديك ما يلي:

1. تم تثبيت Visual Studio أو IDE مماثل على جهازك.
2. .NET Framework أو .NET Core SDK لتشغيل التطبيق.
3.  تم تنزيل مكتبة Aspose.PDF لـ .NET والإشارة إليها في مشروعك. يمكنك الحصول على أحدث إصدار من[هنا](https://releases.aspose.com/pdf/net/).
4.  ترخيص Aspose صالح أو[رخصة مؤقتة](https://purchase.aspose.com/temporary-license/) لفتح كافة وظائف المكتبة.

## استيراد الحزم

للبدء، قم باستيراد المساحات الأساسية اللازمة إلى مشروعك:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

تغطي هذه المساحات الأسماء العمليات الأساسية لـ PDF، والمحتوى المميز، والجداول، وتنسيق النص.

الآن دعنا نستعرض عملية إنشاء جدول وتصميمه في Aspose.PDF. سنتناول كل قسم بالتفصيل حتى تتمكن من متابعته.

## الخطوة 1: إنشاء مستند PDF جديد وإعداد المحتوى المميز

في هذه الخطوة الأولى، سنقوم بإنشاء مستند PDF فارغ وإعداد المحتوى المميز له.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء مستند PDF جديد
Document document = new Document();

// إعداد المحتوى المُوسوم
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table style");
taggedContent.SetLanguage("en-US");
```

 نبدأ بإنشاء جديد`Document` الكائن الذي يمثل ملف PDF الخاص بنا.`TaggedContent`يتم استخدام الكائن لإدارة بنية المستند، وضمان الامتثال لمعايير إمكانية الوصول. نقوم بتعيين عنوان ولغة المستند لوضع العلامات المناسبة.

## الخطوة 2: تحديد العنصر الجذري

بعد ذلك، سنقوم بإنشاء عنصر البنية الجذرية، والذي يعمل كحاوية لجميع المحتوى الموجود في ملف PDF الخاص بنا.

```csharp
// الحصول على عنصر البنية الجذرية
StructureElement rootElement = taggedContent.RootElement;
```

 ال`RootElement` يعمل كحاوية أساسية لجميع العناصر المنظمة، بما في ذلك الجدول الخاص بنا. ويساعد في الحفاظ على التسلسل الهرمي الهيكلي للمستند، وهو أمر مهم لكل من التنظيم وإمكانية الوصول.

## الخطوة 3: إنشاء عنصر الجدول وتصميمه

 الآن بعد إعداد العنصر الجذر، سنقوم بإنشاء`TableElement` وتطبيق أنماط مثل لون الخلفية والحدود والمحاذاة.

```csharp
// إنشاء عنصر هيكل الجدول
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);

// تصميم الجدول
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement.Alignment = HorizontalAlignment.Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
```

 نحن ننشئ`TableElement` ، الذي يحدد بنية الجدول لدينا.`BackgroundColor`, `Border` ، و`Alignment` تسمح لنا الخصائص بتخصيص مظهر الجدول.`Broken` تضمن الخاصية أنه في حالة انقسام الجدول عبر الصفحات، فإنه سيتم انقسامه عموديًا.

## الخطوة 4: تعيين أبعاد الجدول وأنماط الخلايا

في هذه الخطوة، سنقوم بتحديد عدد الأعمدة، وحشو الخلايا، وخصائص الجدول المهمة الأخرى.

```csharp
tableElement.ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
```

 نقوم بتحديد عرض الأعمدة لضمان تباعد كل عمود في الجدول بشكل متساوي.`DefaultCellBorder`, `DefaultCellPadding` ، و`DefaultCellTextState` تحديد الأنماط الافتراضية للخلايا، بما في ذلك الحدود، والحشو، ولون النص، وحجم الخط.

## الخطوة 5: إضافة صفوف متكررة وأنماط مخصصة

يمكننا أيضًا تحديد أنماط لتكرار الصفوف وعناصر الجدول المحددة الأخرى مثل الرؤوس والتذييلات.

```csharp
tableElement.RepeatingRowsCount = 3;
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
```

 ال`RepeatingRowsCount` يضمن تكرار الصفوف الثلاثة الأولى إذا كان الجدول يمتد على عدة صفحات. نقوم بتعيين`RepeatingRowsStyle` لتطبيق لون خلفية مخصص لهذه الصفوف.

## الخطوة 6: إضافة عناصر رأس الجدول وجسمه وأسفله

الآن، دعنا نقوم بإنشاء أقسام رأس الجدول وجسمه وتذييله ونملأها بالمحتوى.

```csharp
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

// إنشاء صف الرأس
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (int colIndex = 0; colIndex < 5; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
}

// ملء نص الجدول
for (int rowIndex = 0; rowIndex < 10; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    for (int colIndex = 0; colIndex < 5; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
    }
}
```

 ينقسم الجدول إلى ثلاثة أجزاء: الرأس والجسم والتذييل. نقوم أولاً بإنشاء صف الرأس باستخدام`TableTHElement`وإضافة عناوين الأعمدة. ثم نقوم بملء نص الجدول بـ`TableTDElement`، وملء كل خلية بتسمية تتضمن موقعها.

## الخطوة 7: احفظ المستند

وأخيرًا، نقوم بحفظ مستند PDF في الدليل المحدد.

```csharp
// احفظ مستند PDF المُوسوم
document.Save(dataDir + "StyleTableElement.pdf");
```

تنهي هذه الخطوة عملية إنشاء المستند عن طريق حفظ ملف PDF بالجدول المصمم.

## الخطوة 8: التحقق من التوافق مع PDF/UA

بعد حفظ المستند، من الضروري التأكد من أنه يتوافق مع معايير PDF/UA (إمكانية الوصول الشامل).

```csharp
// التحقق من توافق PDF/UA
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

هنا، نقوم بإعادة تحميل المستند والتحقق من صحته وفقًا لمعايير PDF/UA. يضمن الامتثال أن ملف PDF الخاص بك يلبي متطلبات إمكانية الوصول، مما يجعله مناسبًا لمجموعة واسعة من المستخدمين.

## خاتمة

مع Aspose.PDF for .NET، يصبح إنشاء الجداول وتصميمها في مستندات PDF أمرًا بسيطًا وبديهيًا. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك إنشاء جداول بأنماط مخصصة والتأكد من أن ملفات PDF الخاصة بك تلبي معايير إمكانية الوصول. سواء كنت تقوم بإنشاء تقارير أو إنشاء مستندات منظمة، فإن الجداول هي أداة قوية لعرض البيانات بوضوح.

## الأسئلة الشائعة

### هل يمكنني إضافة صور داخل خلايا الجدول؟
 نعم، يمكنك إدراج الصور في خلايا الجدول باستخدام`Image` عنصر.

### كيف أقوم بتعديل عرض الأعمدة بشكل ديناميكي؟
 يمكنك ضبط`ColumnAdjustment` الممتلكات ل`AutoFitToWindow` لضبط عرض الأعمدة تلقائيًا استنادًا إلى المحتوى.

### هل الامتثال لـ PDF/UA إلزامي لجميع المستندات؟
على الرغم من أنه ليس إلزاميًا، إلا أنه يوصى به للمستندات التي تتطلب معايير إمكانية وصول عالية.

### هل يمكنني تطبيق أنماط مختلفة على صفوف محددة؟
 نعم، يمكنك تخصيص صفوف أو خلايا فردية عن طريق ضبطها`TextState` أو`BackgroundColor`.

### ما هي فائدة استخدام المحتوى المميز؟
يساعد المحتوى المميز على تحسين إمكانية الوصول إلى المستندات ويساعد في ضمان الامتثال للمعايير مثل PDF/UA.