---
title: وضع نص حول الصورة في ملف PDF
linktitle: وضع نص حول الصورة في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية وضع نص حول الصور في ملفات PDF باستخدام Aspose.PDF for .NET. اتبع دليلنا خطوة بخطوة لإنشاء ملفات PDF احترافية تحتوي على صور ونصوص جنبًا إلى جنب.
type: docs
weight: 260
url: /ar/net/programming-with-text/placing-text-around-image/
---
## مقدمة

هل سبق لك أن حاولت وضع نص حول صورة في ملف PDF ولكنك وجدت الأمر صعبًا؟ إذا كان الأمر كذلك، فأنت في المكان الصحيح! يجعل Aspose.PDF for .NET هذه العملية بسيطة، حيث يسمح لك بوضع نص بجوار الصور باستخدام بضعة أسطر فقط من التعليمات البرمجية. سواء كنت تقوم بإنشاء تقارير أو مستندات أو عروض تقديمية، فإن هذه الميزة هي طريقة رائعة لتحسين تخطيط المحتوى الخاص بك وجعله أكثر جاذبية بصريًا. اليوم، سنشرح كيفية استخدام Aspose.PDF for .NET لوضع نص حول الصور في مستند PDF.

## المتطلبات الأساسية

قبل أن ننتقل إلى الكود، دعنا نتأكد من إعداد كل شيء. إليك ما ستحتاج إليه:

-  Aspose.PDF لـ .NET: يمكنك تنزيله من[هنا](https://releases.aspose.com/pdf/net/).
- Visual Studio: تأكد من تثبيت الإصدار الأحدث لمتابعة العمل بسلاسة.
- .NET Framework: يستخدم هذا المثال .NET، لذا تأكد من إعداد البيئة لديك لتطوير .NET.
-  رخصة مؤقتة: يمكنك طلب رخصة مؤقتة[هنا](https://purchase.aspose.com/temporary-license/) إذا كنت تقوم بتقييم المنتج.

إذا لم تقم بإعداد Aspose.PDF لـ .NET بعد، فاتبع تعليمات التثبيت الموجودة في[التوثيق](https://reference.aspose.com/pdf/net/).

## استيراد مساحات الأسماء

قبل أن نبدأ في كتابة التعليمات البرمجية، نحتاج إلى استيراد مساحات الأسماء الضرورية. إليك مقتطف التعليمات البرمجية للقيام بذلك:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

 هذه المساحات الأساسية ضرورية لأنها توفر الوصول إلى فئات مثل`Document`, `Page`, `Image` ، و`HtmlFragment`، والذي سنستخدمه لإنشاء ملف PDF ومعالجته.

الآن بعد أن قمنا بإعداد المسرح، دعنا نوضح كيفية وضع نص حول صورة في ملف PDF باستخدام Aspose.PDF لـ .NET. سنوضح لك هذه العملية خطوة بخطوة.

## الخطوة 1: إنشاء كائن المستند

 أولاً، تحتاج إلى إنشاء مستند PDF. في Aspose.PDF، يتم ذلك عن طريق إنشاء مثيل لـ`Document` هذا الكائن سيكون بمثابة الأساس لكل المحتوى الذي سنضيفه.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

هنا، قمنا بإنشاء مستند PDF فارغ. لا يحتوي هذا المستند على أي صفحات حتى الآن، ولكن لا تقلق، فسنضيف صفحة في الخطوة التالية.

## الخطوة 2: إضافة صفحة إلى المستند

الآن بعد أن حصلنا على المستند، حان الوقت لإضافة صفحة. فكر في هذا الأمر باعتباره إنشاء ورقة فارغة حيث ستضيف المحتوى الخاص بك.

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

يضيف هذا الكود صفحة جديدة إلى المستند. بشكل افتراضي، تكون الصفحة فارغة، لكننا على وشك تغيير ذلك.

## الخطوة 3: إنشاء جدول لتنظيم المحتوى

للحفاظ على محاذاة الصورة والنص بشكل صحيح، سنستخدم جدولًا. يمكن أن تساعد الجداول الموجودة في ملفات PDF في تنظيم تخطيطك، تمامًا كما هو الحال في مستندات Word أو HTML.

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

يؤدي هذا المقطع إلى إنشاء جدول وإضافته إلى الصفحة. اعتبر الجدول بمثابة الإطار لمحاذاة صورتك ونصك.

## الخطوة 4: تعيين عرض الأعمدة للجدول

الآن بعد أن أضفنا جدولاً، نحتاج إلى تحديد عرض الأعمدة. وهذا يضمن أن حجم الصورة والنص مناسبان على الصفحة.

```csharp
table1.ColumnWidths = "120 270";
```

يحدد هذا السطر عرض عمودين — أحدهما للصورة والآخر للنص. اضبط هذه القيم إذا كانت الصورة أو النص يحتاجان إلى مساحة أكبر أو أقل.

## الخطوة 5: تحديد الهوامش والحشو

للتأكد من أن كل شيء يبدو أنيقًا، دعنا نضيف بعض الهوامش والحشو إلى الجدول.

```csharp
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
table1.DefaultCellPadding = margin;
```

تضمن هذه الإعدادات أن يكون الجدول الخاص بك متباعدًا بشكل متسق، مما يجعل المحتوى جذابًا بصريًا.

## الخطوة 6: إدراج صورة في الجدول

الآن، لننتقل إلى الجزء الممتع، وهو إضافة صورة. في هذه الحالة، سنضيف شعار Aspose، ولكن لا تتردد في استخدام أي صورة تريدها.

```csharp
Aspose.Pdf.Row row1 = table1.Rows.Add();
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

وهذا ما يحدث:
- نقوم بتحميل الصورة من الدليل المحدد.
- قمنا بتحديد ارتفاع وعرض الصورة.
- وأخيرًا نضيف الصورة إلى الخلية الأولى في الجدول.

## الخطوة 7: إضافة نص بجوار الصورة

الآن بعد أن أصبحت الصورة جاهزة، فلنضف بعض النص بجوارها. في هذا المثال، سنستخدم نصًا بتنسيق HTML لتنسيق المحتوى.

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF document reporting component that enables .NET applications to <b>create PDF documents from scratch</b> without utilizing Adobe Acrobat.</font>";

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

تضيف هذه الكتلة عنوانًا ووصفًا منسقين في الخلية المجاورة للصورة. يمكنك تنسيق النص باستخدام علامات HTML لمزيد من التخصيص.

## الخطوة 8: ضبط المحاذاة الرأسية

افتراضيًا، قد لا يتم محاذاة المحتوى في خلايا الجدول بالطريقة التي تريدها. في هذه الحالة، نريد التأكد من محاذاة النص إلى أعلى الخلية.

```csharp
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
```

ويضمن هذا أن يكون النص في أعلى الخلية، مما يحافظ على التصميم نظيفًا واحترافيًا.

## الخطوة 9: أضف المزيد من النص أسفل الصورة والوصف

قد ترغب في تضمين المزيد من المحتوى أسفل الصورة والنص. دعنا نضيف صفًا آخر إلى الجدول لهذا الغرض.

```csharp
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
SecondRow.Cells[0].ColSpan = 2;
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

هنا، أضفنا صفًا آخر بنص إضافي، يمتد على كلا العمودين للحفاظ على التوازن في التخطيط.

## الخطوة 10: احفظ مستند PDF

وأخيرًا، نحتاج إلى حفظ المستند حتى تتمكن من عرض التغييرات.

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

يؤدي هذا إلى حفظ ملف PDF مع الصورة والنص بتنسيق كما نريد.

## خاتمة

قد يبدو وضع النص حول الصور في ملف PDF مهمة شاقة، ولكن Aspose.PDF for .NET يبسط العملية. من خلال الاستفادة من الجداول والصور والنصوص المصممة، يمكنك إنشاء ملفات PDF ذات مظهر احترافي بأقل جهد. باستخدام بضعة أسطر فقط من التعليمات البرمجية، يمكنك وضع المحتوى بالضبط حيث تريد، مما يمنح مستنداتك مظهرًا مصقولًا ومنظمًا جيدًا.

## الأسئلة الشائعة

### هل يمكنني استخدام هذه الطريقة لوضع صور متعددة مع النص؟
نعم، قم ببساطة بإضافة المزيد من الصفوف والخلايا إلى جدولك لتضمين صور ونصوص إضافية.

### هل يمكنني تغيير محاذاة الصورة؟
بالتأكيد! يمكنك تعديل محاذاة الصورة عن طريق ضبط خصائص محاذاة الخلية.

### كيف أقوم بتنسيق النص بشكل أكبر؟
 يمكنك استخدام علامات HTML داخل`HtmlFragment` كائن لتطبيق أنماط مختلفة مثل الخط العريض أو المائل أو الخطوط المختلفة.

### هل يمكنني التحكم بالمسافة بين النص والصورة؟
 نعم، باستخدام`MarginInfo` يسمح لك الكائن بالتحكم في الحشو والهوامش بين العناصر.

### هل من الممكن إضافة روابط للنص؟
 بالتأكيد! يمكنك تضمين ارتباطات تشعبية في النص بتنسيق HTML باستخدام`<a>` العلامة.