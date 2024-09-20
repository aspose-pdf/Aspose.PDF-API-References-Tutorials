---
title: صف جدول الأنماط
linktitle: صف جدول الأنماط
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية تصميم صفوف الجدول في ملف PDF باستخدام Aspose.PDF لـ .NET من خلال دليل خطوة بخطوة لتحسين تنسيق مستندك بسهولة.
type: docs
weight: 180
url: /ar/net/programming-with-tagged-pdf/style-table-row/
---
## مقدمة

عندما يتعلق الأمر بإنشاء مستندات PDF جيدة البنية ومنسقة بشكل جميل، فإن Aspose.PDF for .NET هو الحل الأمثل. سواء كنت تقوم بأتمتة التقارير أو الفواتير أو إنشاء جداول ديناميكية، فإن تنسيق الجداول بأنماط مختلفة هو مفتاح الحصول على مستند مصقول. في هذا البرنامج التعليمي، سنتعمق في تصميم صف جدول باستخدام Aspose.PDF for .NET. ولا تقلق، سأرشدك خطوة بخطوة، تمامًا مثل محادثة جيدة أثناء تناول القهوة!

## المتطلبات الأساسية

قبل أن ننتقل إلى التفاصيل الدقيقة، دعنا نتأكد من أنك قد أعددت كل ما لديك. ستحتاج إلى:

1. مكتبة Aspose.PDF لـ .NET  
    إذا لم يكن لديك بالفعل، يمكنك الحصول عليه من[هنا](https://releases.aspose.com/pdf/net/) يمكنك أيضًا الحصول على[نسخة تجريبية مجانية](https://releases.aspose.com/) للبدء.
2. بيئة التطوير  
   قم بإعداد Visual Studio أو أي بيئة تطوير متكاملة C# من اختيارك. ستحتاج أيضًا إلى تثبيت .NET، ولكنني أتوقع أنك على دراية بذلك بالفعل.
3. المعرفة الأساسية بلغة C# و.NET  
   إن الفهم الجيد للغة C# سيجعل هذا البرنامج التعليمي سهلاً. ولكن لا تقلق، سأشرح كل خطوة بالتفصيل!

## استيراد الحزم

قبل أن نتمكن من بدء العمل باستخدام Aspose.PDF، نحتاج إلى استيراد المساحات الأساسية اللازمة. في مشروع C# الخاص بك، تأكد من تضمين ما يلي:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

وهذه ضرورية لإنشاء الجدول وتصميمه، وبالطبع، للعمل مع المحتوى المميز من أجل التوافق.

الآن دعنا نقوم بتقسيم المهمة خطوة بخطوة، حتى تتمكن من تصميم صفوف الجدول الخاص بك مثل المحترفين!

## الخطوة 1: إنشاء مستند PDF جديد

أولاً وقبل كل شيء: لنقم بإنشاء مستند PDF جديد. سيحتوي هذا المستند على جميع صفوف الجدول المصممة.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء مستند
Document document = new Document();
```

 هنا، نقوم ببساطة بتهيئة ملف جديد`Document` الكائن الذي سيمثل ملف PDF الخاص بنا. تأكد من تعيين مسار الدليل الذي ستحفظ فيه ملفات الإخراج الخاصة بك.

## الخطوة 2: العمل مع المحتوى المُوسوم

لهيكلة ملف PDF الخاص بك لسهولة الوصول إليه، سنعمل مع المحتوى المُوسوم. يساعد هذا في إنشاء عناصر منظمة مثل الجداول، مما يضمن توافقها مع معايير إمكانية الوصول مثل PDF/UA.

```csharp
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table row style");
taggedContent.SetLanguage("en-US");
```

هنا، نقوم بتعيين العنوان واللغة للمحتوى المُوسوم في ملف PDF. الأمر أشبه بإعطاء ملف PDF اسمًا وإخباره باللغة التي يجب أن يتحدث بها!

## الخطوة 3: تحديد بنية الجدول

بعد ذلك، دعنا نحدد بنية الجدول الذي سننشئه. يحتاج كل جدول إلى رأس وجسم وتذييل - تمامًا مثل منشور مدونة منظم جيدًا!

```csharp
// الحصول على عنصر البنية الجذرية
StructureElement rootElement = taggedContent.RootElement;

// إنشاء عنصر هيكل الجدول
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

ما نقوم به هنا هو إنشاء جدول برأس (`THead`)، جسم (`TBody`)، والتذييل (`TFoot`). هذه العناصر سوف تحتوي على صفوفنا.

## الخطوة 4: إضافة صف رأس الجدول

الجداول التي لا تحتوي على رؤوس تشبه الكتب التي لا تحتوي على عناوين. فلنبدأ بإنشاء صف الرؤوس أولاً لتوفير السياق للبيانات.

```csharp
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (int colIndex = 0; colIndex < 3; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText(String.Format("Head {0}", colIndex));
}
```

هنا، نقوم بالمرور عبر ثلاث خلايا رأسية وإضافةها (`TableTHElement`)، مع إعطاء كل منها نصًا وصفيًا. الأمر بسيط، أليس كذلك؟

## الخطوة 5: إضافة صفوف الجسم المصممة

الآن يأتي الجزء الممتع - تصميم الصفوف! فلنقم بإنشاء سبعة صفوف بأنماط مخصصة. وسنحدد ألوان الخلفية والحدود والحشو ومحاذاة النص.

```csharp
for (int rowIndex = 0; rowIndex < 7; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    trElement.AlternativeText = String.Format("Row {0}", rowIndex);
    trElement.BackgroundColor = Color.LightGoldenrodYellow;
    trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
    trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
    trElement.MinRowHeight = 100.0;
    trElement.FixedRowHeight = 120.0;
    trElement.IsInNewPage = (rowIndex % 3 == 1);
    trElement.IsRowBroken = true;

    for (int colIndex = 0; colIndex < 3; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
    }
}
```

- لون الخلفية: استخدمنا لونًا أصفر ذهبيًا فاتحًا للحصول على لمسة احترافية ودافئة.
- الحدود: يحصل كل صف على حدود خارجية باللون الرمادي الداكن وحدود خلايا زرقاء لمظهر حاد.
- الارتفاع والحشو: تم تعيين ارتفاعات الصفوف، وتمت إضافة الحشو للحصول على مظهر نظيف.
- فواصل الصفحات: لجعل الجدول أكثر قابلية للقراءة، يبدأ كل صف ثاني في صفحة جديدة.

## الخطوة 6: إضافة صف التذييل

تمامًا مثل الرأس، يعمل التذييل على تثبيت الجدول. فلنقم بإنشاء واحد.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
for (int colIndex = 0; colIndex < 3; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText(String.Format("Foot {0}", colIndex));
}
```

نقوم ببساطة بالمرور عبر ثلاث خلايا في التذييل وإضافة جزء من النص. النص البديل للتذييل هو "Foot Row" لجعله متاحًا.

## الخطوة 7: احفظ مستند PDF

الآن بعد أن تم إعداد الطاولة بالكامل، حان الوقت لحفظ تحفتك الفنية!

```csharp
document.Save(dataDir + "StyleTableRow.pdf");
```

بهذه الطريقة، سيتم حفظ ملف PDF الخاص بك مع جميع صفوف الجدول الجميلة التي قمنا بتصميمها للتو.

## الخطوة 8: التحقق من التوافق مع PDF/UA

لضمان التزام ملف PDF الخاص بنا بمعايير إمكانية الوصول، سنقوم بالتحقق من توافقه مع PDF/UA.

```csharp
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));
```

يضمن هذا أن يتوافق ملف PDF الخاص بك مع معيار PDF/UA، مما يجعله متاحًا للجميع. سهولة الوصول هي اسم اللعبة!

## خاتمة

والآن، لقد انتهيت! فباستخدام بضعة أسطر فقط من التعليمات البرمجية، يمكنك إنشاء جدول مصمم بالكامل في ملف PDF باستخدام Aspose.PDF for .NET. من الرؤوس إلى التذييلات، قمنا بتصميم كل صف، وإضافة عناصر إمكانية الوصول، وحتى التحقق من صحة المستند للتأكد من توافقه مع المعايير. سواء كنت تعمل على تقارير الشركة أو العروض التقديمية أو تستمتع فقط بملفات PDF، فإن هذا الدليل يغطيك. الآن، انطلق وابدأ في تصميم جداولك مثل المحترفين!

## الأسئلة الشائعة

### هل يمكنني تغيير نوع الخط الخاص بالجدول أيضًا؟  
 نعم! يمكنك تعديل نمط الخط باستخدام`TextState` كائن لكل خلية، مما يسمح بالتخصيص الكامل.

### كيف أضيف المزيد من الأعمدة إلى جدولي؟  
 فقط قم بتعديل`colCount`متغير وإضافة المزيد من الخلايا في الحلقات للرؤوس والجسم والتذييلات.

### ماذا يحدث إذا لم أقم بتعيين ارتفاع الصف؟  
إذا لم تقم بتعيين ارتفاع الصف، فسيتم تعديل الجدول تلقائيًا استنادًا إلى المحتوى.

### هل يمكنني استخدام هذا لعدد ديناميكي من الصفوف؟  
بالتأكيد! يمكنك جلب البيانات من قاعدة بيانات أو أي مصدر آخر وتعديل عدد الصفوف والأعمدة بشكل ديناميكي.

### هل استخدام Aspose.PDF لـ .NET مجاني؟  
 يعد Aspose.PDF for .NET منتجًا مرخصًا، ولكن يمكنك تجربته باستخدام[نسخة تجريبية مجانية](https://releases.aspose.com/) أو الحصول على[رخصة مؤقتة](https://purchase.aspose.com/temporary-license/).