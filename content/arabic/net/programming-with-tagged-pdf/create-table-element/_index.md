---
title: إنشاء عنصر الجدول
linktitle: إنشاء عنصر الجدول
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: دليل خطوة بخطوة لإنشاء عنصر مصفوفة باستخدام Aspose.PDF لـ .NET. إنشاء ملفات PDF ديناميكية تحتوي على جداول بسهولة.
type: docs
weight: 80
url: /ar/net/programming-with-tagged-pdf/create-table-element/
---
## مقدمة

هل تساءلت يومًا كيف يمكنك إنشاء عناصر جدول وتخصيصها بسهولة في ملف PDF باستخدام .NET؟ حسنًا، يعد Aspose.PDF for .NET الحل الأمثل لك! سواء كنت تقوم بأتمتة إنشاء التقارير أو إنشاء جداول ديناميكيًا لمستندات مختلفة، يوفر Aspose.PDF واجهة برمجة تطبيقات غنية للعمل مع عناصر الجدول. سيرشدك هذا الدليل خطوة بخطوة إلى كيفية إنشاء جدول وتصميمه وحتى التأكد من أنه يفي بمعايير الامتثال لـ PDF/UA. يبدو الأمر مثيرًا، أليس كذلك؟ دعنا نتعمق فيه على الفور!

## المتطلبات الأساسية

قبل أن نبدأ، ستحتاج إلى بعض الأشياء:
1.  Aspose.PDF لـ .NET: قم بتنزيل أحدث إصدار من[تنزيل Aspose.PDF لـ .NET](https://releases.aspose.com/pdf/net/).
2. بيئة التطوير: أي بيئة تطوير متكاملة تدعم .NET (على سبيل المثال، Visual Studio).
3. المعرفة الأساسية بلغة C#: يُنصح بالإلمام ببرمجة C#.

 أخيرًا، لا تنس ترخيص Aspose.PDF. إذا لم يكن لديك ترخيص، فيمكنك استخدام[نسخة تجريبية مجانية](https://releases.aspose.com/) أو اطلب[رخصة مؤقتة](https://purchase.aspose.com/temporary-license/) لاختبار كل شيء.

## استيراد الحزم

أولاً وقبل كل شيء، دعنا نستورد الحزم اللازمة. سيسمح لنا هذا بالعمل مع كافة الفئات ذات الصلة لإنشاء الجداول في مستندات PDF.

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

في هذا القسم، سنقوم بتقسيم عملية إنشاء جدول إلى عدة خطوات. تركز كل خطوة على أجزاء مختلفة من عملية إنشاء الجدول وتخصيصه.

## الخطوة 1: إنشاء مستند PDF جديد

أول شيء يتعين علينا القيام به هو إنشاء مستند PDF جديد. سيعمل هذا المستند كحاوية لجدولنا.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء مستند PDF جديد
Document document = new Document();
```

 هنا، نقوم بتهيئة مثيل جديد من`Document` الصف الذي سيكون ملف PDF الفارغ الخاص بنا. لا تنس تحديد مسار الملف الخاص بك!

## الخطوة 2: إعداد المحتوى المُوسوم

بعد ذلك، نحتاج إلى تمكين المحتوى المُوسوم، مما يضمن إمكانية الوصول إلى الجدول. تعد ملفات PDF المُوسومة مطلوبة للامتثال لمعايير PDF/UA (إمكانية الوصول الشاملة).

```csharp
// تمكين المحتوى المُوسوم
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Table");
taggedContent.SetLanguage("en-US");
```

تحدد هذه الخطوة عنوان المستند واللغة، مما يضمن امتثال الجدول لمعايير إمكانية الوصول. يعد توفير مستندات يمكن الوصول إليها أمرًا بالغ الأهمية لتجربة المستخدم والمتطلبات القانونية في بعض الصناعات.

## الخطوة 3: إنشاء عنصر الجدول

والآن يأتي الجزء الممتع - إنشاء الجدول نفسه!

```csharp
// الحصول على عنصر البنية الجذرية
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

 هنا، نحن نستخدم`RootElement` من المحتوى المُوسوم لإضافته إلى جدولنا. وهذا يعني في الأساس إضافة جدول كعقدة فرعية إلى بنية المستند.

## الخطوة 4: تخصيص حدود الجدول والرؤوس

لا تريد أن تبدو طاولتك باهتة، أليس كذلك؟ دعنا نضيف بعض الأناقة!

```csharp
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

 نحن نقوم بتحديد الحدود وإضافة الرؤوس والجسم والتذييلات إلى الجدول. لاحظ استخدام`BorderInfo` لتزيين حدود الجدول باللون الأزرق الداكن.

## الخطوة 5: إضافة صفوف وخلايا إلى الجدول

الآن، لنبدأ في ملء الجدول بالصفوف والخلايا. هذا الجزء من العملية هو المكان الذي نحدد فيه تخطيط الجدول.

### الخطوة 5.1: إنشاء صف الرأس

```csharp
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
headTrElement.BackgroundColor = Color.LightGray;

for (int colIndex = 0; colIndex < 4; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
    thElement.BackgroundColor = Color.GreenYellow;
    thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
    thElement.Alignment = HorizontalAlignment.Right;
}
```

 نحن نقوم بإنشاء صف رأس يحتوي على 4 أعمدة، ويتم تصميم كل خلية رأس بلون خلفية`GreenYellow`لقد قمنا أيضًا بتعيين حدود ومحاذاة للرؤوس.

### الخطوة 5.2: إضافة صفوف النص

```csharp
for (int rowIndex = 0; rowIndex < 50; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    trElement.AlternativeText = $"Row {rowIndex}";

    for (int colIndex = 0; colIndex < 4; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
        tdElement.BackgroundColor = Color.Yellow;
        tdElement.Alignment = HorizontalAlignment.Center;
    }
}
```

هنا، نقوم بإنشاء 50 صفًا و4 أعمدة بشكل ديناميكي، ونملأها بالنص ونصمم الخلايا. تم تعيين لون الخلفية باللون الأصفر، مع وضع النص في المنتصف.

### الخطوة 5.3: إضافة صف التذييل

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
footTrElement.BackgroundColor = Color.LightSeaGreen;

for (int colIndex = 0; colIndex < 4; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText($"Foot {colIndex}");
    tdElement.Alignment = HorizontalAlignment.Center;
}
```

 لإكمال الجدول، نضيف تذييلًا بنص مركزي و`LightSeaGreen` خلفية.

## الخطوة 6: التحقق من التوافق مع PDF/UA

بمجرد إنشاء الجدول، من المهم التأكد من أن ملف PDF متوافق مع PDF/UA.

```csharp
document.Save(dataDir + "CreateTableElement.pdf");

// التحقق من صحة توافق PDF/UA
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

يحفظ هذا المقطع ملف PDF ويتحقق مما إذا كان يفي بمعايير الامتثال لـ PDF/UA. إذا كان المستند متوافقًا، فيمكن للمستخدمين ذوي الإعاقة الوصول إليه.

## خاتمة

تهانينا! لقد نجحت في إنشاء جدول مخصص بالكامل في ملف PDF باستخدام Aspose.PDF لـ .NET. بدءًا من تصميم الجدول وحتى ضمان التوافق مع PDF/UA، أصبح لديك الآن أساس قوي لإنشاء جداول ديناميكية في مستندات PDF الخاصة بك. لا تنس استكشاف الميزات الشاملة لـ Aspose.PDF لتحسين مستنداتك بشكل أكبر!

## الأسئلة الشائعة

### هل يمكنني تخصيص الخط ونمط النص الخاص بالجدول؟
نعم، يسمح لك Aspose.PDF بتخصيص الخطوط وأنماط النص والمحاذاة بالكامل باستخدام`TextState` فصل.

### كيف أضيف المزيد من الأعمدة أو الصفوف بشكل ديناميكي؟
 يمكنك تعديل عدد الأعمدة أو الصفوف عن طريق تعديل`rowIndex` و`colIndex` في الحلقات.

### هل من الممكن دمج الخلايا في الجدول؟
 نعم يمكنك استخدام`ColSpan` و`RowSpan` خصائص لدمج الخلايا عبر الأعمدة أو الصفوف.

### ما هو التوافق مع PDF/UA؟
يضمن توافق PDF/UA إمكانية وصول المستخدمين ذوي الإعاقة إلى المستند، والالتزام بمعايير إمكانية الوصول الدولية.

### كيف يمكنني اختبار التوافق مع PDF/UA في Aspose.PDF؟
 يمكنك استخدام`Validate` طريقة للتحقق من أن المستند يتوافق مع معايير PDF/UA.