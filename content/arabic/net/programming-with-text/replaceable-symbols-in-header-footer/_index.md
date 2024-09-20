---
title: الرموز القابلة للاستبدال في رأس الصفحة وتذييلها
linktitle: الرموز القابلة للاستبدال في رأس الصفحة وتذييلها
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية استخدام الرموز القابلة للاستبدال في رأس وتذييل مستند PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 320
url: /ar/net/programming-with-text/replaceable-symbols-in-header-footer/
---
## مقدمة

عند العمل بملفات PDF، هناك أوقات تحتاج فيها إلى تخصيص الرؤوس والتذييلات بمحتوى ديناميكي مثل أرقام الصفحات أو أسماء التقارير أو التواريخ المولدة. لحسن الحظ، يبسط Aspose.PDF for .NET هذه العملية، مما يسمح لك بإنشاء ملفات PDF برموز محدثة تلقائيًا في الرؤوس والتذييلات، مثل أرقام الصفحات أو تفاصيل إنشاء التقرير. سترشدك هذه المقالة خلال عملية استبدال الرموز في الرؤوس والتذييلات باستخدام Aspose.PDF for .NET خطوة بخطوة، بطريقة ليست بسيطة فحسب، بل إنها أيضًا فعالة بشكل لا يصدق.

## المتطلبات الأساسية

قبل الغوص في الدليل خطوة بخطوة، تأكد من أن لديك ما يلي:

-  مكتبة Aspose.PDF لـ .NET –[تحميل](https://releases.aspose.com/pdf/net/) أو الحصول على[نسخة تجريبية مجانية](https://releases.aspose.com/).
- Visual Studio أو أي C# IDE مثبت على نظامك.
- المعرفة الأساسية بتطوير C# و.NET.
-  صالحة[رخصة](https://purchase.aspose.com/temporary-license/) بالنسبة لـ Aspose.PDF، أو يمكنك استخدام الإصدار التجريبي.

## استيراد الحزم

للبدء، تحتاج إلى استيراد مساحات الأسماء الضرورية التي ستمكن من وظيفة Aspose.PDF لـ .NET. فيما يلي الاستيراد الضروري:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

تعتبر هذه ضرورية للتعامل مع إنشاء ملفات PDF، ومعالجة النصوص، وإدارة الرأس والتذييل.

دعنا نقوم بتقسيم الكود المثال إلى خطوات سهلة الفهم.

## الخطوة 1: إعداد المستند والصفحة

أولاً، نحتاج إلى تهيئة المستند وإضافة صفحة إليه. وهذا يمهد الطريق لإضافة رؤوس الصفحات وتذييلاتها.

```csharp
// إعداد دليل المستندات
string dataDir = "YOUR DOCUMENT DIRECTORY";

// تهيئة كائن المستند
Document doc = new Document();

// إضافة صفحة إلى المستند
Page page = doc.Pages.Add();
```

 هنا، نقوم بإعداد مستند PDF باستخدام`Document` الصف وإضافة صفحة بها`doc.Pages.Add()`ستحتوي هذه الصفحة على الرأس والتذييل والمحتوى الآخر.

## الخطوة 2: تكوين هوامش الصفحة

بعد ذلك، سنقوم بتحديد هوامش الصفحة للتأكد من أن المحتوى الخاص بنا لا يصل إلى الحافة.

```csharp
// تكوين الهوامش
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

 هنا، قمنا بتحديد الهوامش العلوية والسفلية واليسرى واليمنى باستخدام`MarginInfo` الصف وتطبيقه على الصفحة باستخدام`page.PageInfo.Margin`.

## الخطوة 3: إنشاء وتكوين الرأس

الآن، لنقم بإنشاء رأس الصفحة وإضافته إلى الصفحة. سيتضمن الرأس عنوان التقرير واسمه.

```csharp
// إنشاء رأس الصفحة
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;

// تعيين هوامش الرأس
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;

// إضافة عنوان إلى الرأس
TextFragment t1 = new TextFragment("report title");
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
hfFirst.Paragraphs.Add(t1);

// إضافة اسم التقرير إلى الرأس
TextFragment t2 = new TextFragment("Report_Name");
t2.TextState.Font = FontRepository.FindFont("Arial");
t2.TextState.FontSize = 12;
t2.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
hfFirst.Paragraphs.Add(t2);
```

 لقد أضفنا اثنين`TextFragment` الكائنات الموجودة في الرأس: واحدة لعنوان التقرير وأخرى لاسم التقرير. يتم تنسيق النص باستخدام`TextState` خصائص مثل الخط والحجم والمحاذاة.

## الخطوة 4: إنشاء التذييل وتكوينه

الآن حان الوقت لإعداد التذييل، الذي سيحمل محتوى ديناميكيًا مثل أرقام الصفحات وتاريخ الإنشاء.

```csharp
// إنشاء تذييل
HeaderFooter hfFoot = new HeaderFooter();
page.Footer = hfFoot;

// تعيين هوامش التذييل
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;

// إضافة محتوى التذييل
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("Report Name");
TextFragment t5 = new TextFragment("Page $p of $P");
```

في التذييل، قمنا بتضمين أجزاء لتاريخ التوليد واسم التقرير وأرقام الصفحات الديناميكية (`$p` و`$P` تمثل رقم الصفحة الحالية والعدد الإجمالي للصفحات، على التوالي).

## الخطوة 5: إنشاء جدول في التذييل

يمكنك أيضًا إضافة عناصر أكثر تعقيدًا، مثل الجداول في التذييل، لتنظيم بياناتك بشكل أفضل.

```csharp
// إنشاء جدول للتذييل
Table tab2 = new Table();
hfFoot.Paragraphs.Add(tab2);
tab2.ColumnWidths = "165 172 165";

// إنشاء صفوف وخلايا للجدول
Row row3 = tab2.Rows.Add();
row3.Cells.Add();
row3.Cells.Add();
row3.Cells.Add();

// تعيين المحاذاة لكل خلية
row3.Cells[0].Alignment = Aspose.Pdf.HorizontalAlignment.Left;
row3.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
row3.Cells[2].Alignment = Aspose.Pdf.HorizontalAlignment.Right;

// إضافة محتوى إلى خلايا الجدول
row3.Cells[0].Paragraphs.Add(t3);
row3.Cells[1].Paragraphs.Add(t4);
row3.Cells[2].Paragraphs.Add(t5);
```

يؤدي كتلة التعليمات البرمجية هذه إلى إنشاء جدول مكون من 3 أعمدة في التذييل، حيث يحتوي كل عمود على معلومات مختلفة، مثل تاريخ الإنشاء، واسم التقرير، وأرقام الصفحات.

## الخطوة 6: إضافة المحتوى إلى الصفحة

بالإضافة إلى الرؤوس والتذييلات، يمكنك إضافة محتوى إلى نص صفحة PDF. هنا، نضيف جدولاً يحتوي على بعض النصوص المؤقتة.

```csharp
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
page.Paragraphs.Add(table);

// إضافة محتوى الجدول
for (int i = 0; i <= 10; i++)
{
    Row row = table.Rows.Add();
    for (int c = 0; c <= 2; c++)
    {
        Cell cell = row.Cells.Add("Content " + c);
        cell.Margin = new MarginInfo { Left = 30, Top = 10, Bottom = 10 };
    }
}
```

يضيف هذا الكود جدولًا بسيطًا بثلاثة أعمدة إلى الصفحة. يمكنك تعديله ليناسب احتياجاتك المحددة.

## الخطوة 7: احفظ ملف PDF

بمجرد إعداد كل شيء، فإن الخطوة الأخيرة هي حفظ مستند PDF في الموقع المطلوب.

```csharp
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("Symbols replaced successfully in header and footer. File saved at " + dataDir);
```

 تحدد مسار الملف وتحفظ المستند باستخدام`doc.Save()`هذا كل شيء! لقد نجحت في إنشاء ملف PDF يحتوي على رؤوس وتذييلات مخصصة.

## خاتمة

إن استبدال الرموز في الرؤوس والتذييلات باستخدام Aspose.PDF لـ .NET ليس بالأمر السهل فحسب، بل إنه قوي أيضًا. باتباع الدليل المفصل أعلاه، يمكنك بسهولة تخصيص ملفات PDF الخاصة بك بمحتوى ديناميكي، مثل أرقام الصفحات وأسماء التقارير والتاريخ. هذه الطريقة مرنة للغاية، مما يسمح لك بإدراج الجداول وتعديل التنسيق والتحكم في التخطيط ليناسب متطلباتك المحددة.

## الأسئلة الشائعة

### هل يمكنني تخصيص الخطوط للرؤوس والتذييلات؟  
نعم، يمكنك تخصيص الخطوط والأحجام والألوان والأنماط للنصوص الموجودة في الرؤوس والتذييلات بالكامل.

### كيف أضيف الصور إلى الرؤوس والتذييلات؟  
 يمكنك استخدام`ImageStamp` لإدراج الصور في الرؤوس والتذييلات.

### هل من الممكن إضافة ارتباطات تشعبية في الرؤوس أو التذييلات؟  
 نعم يمكنك الاستخدام`TextFragment` مع وجود ارتباط تشعبي عن طريق ضبط`Hyperlink` ملكية.

### هل يمكنني استخدام رؤوس مختلفة للصفحات الفردية والزوجية؟  
نعم، يسمح لك Aspose.PDF بتحديد رؤوس وتذييلات مختلفة للصفحات الفردية والزوجية.

### كيف أقوم بتعديل مواضع الرأس والتذييل؟  
يمكنك ضبط الهوامش وخصائص المحاذاة للتحكم في موضع الرؤوس والتذييلات.