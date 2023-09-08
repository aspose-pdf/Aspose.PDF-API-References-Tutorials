---
title: تخصيص أرقام الصفحات أثناء إضافة جدول المحتويات
linktitle: تخصيص أرقام الصفحات أثناء إضافة جدول المحتويات
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تخصيص أرقام الصفحات أثناء إضافة جدول محتويات (TOC) باستخدام Aspose.PDF لـ .NET باستخدام هذا الدليل خطوة بخطوة ومثال التعليمات البرمجية.
type: docs
weight: 100
url: /ar/net/programming-with-document/customizepagenumbeswhileaddingtoc/
---
في هذا البرنامج التعليمي، سنستكشف كيفية تخصيص أرقام الصفحات أثناء إضافة جدول محتويات (TOC) باستخدام Aspose.PDF لـ .NET. سنقدم لك إرشادات خطوة بخطوة، بالإضافة إلى مثال التعليمات البرمجية، لمساعدتك في تحقيق ذلك.

## الخطوة 1: تحميل ملف PDF موجود

أولاً، نحتاج إلى تحميل ملف PDF موجود. في هذا البرنامج التعليمي، سوف نستخدم الملف "42824.pdf" الموجود في دليل "دليل المستندات الخاص بك". استبدل مسار الدليل هذا بالمسار الفعلي لدليل المستند.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
Document doc = new Document(inFile);
```

## الخطوة 2: إضافة صفحة جدول المحتويات

 بعد ذلك، نحتاج إلى إضافة صفحة جديدة في بداية المستند لتكون بمثابة صفحة جدول المحتويات. يمكننا تحقيق ذلك باستخدام`Insert()` طريقة`Pages` جمع من`Document` هدف.

```csharp
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
```

## الخطوة 3: إنشاء كائن TOC

 لإنشاء كائن TOC، نحتاج أولاً إلى إنشاء ملف`TocInfo` الكائن وتعيين خصائصه. في هذا البرنامج التعليمي، سنقوم بتعيين عنوان جدول المحتويات إلى "جدول المحتويات" وبادئة رقم الصفحة إلى "P".

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
```

## الخطوة 4: إنشاء إدخالات جدول المحتويات

لإنشاء إدخالات جدول المحتويات، نحتاج إلى المرور عبر جميع صفحات المستند، باستثناء صفحة جدول المحتويات، وإنشاء كائن عنوان لكل صفحة. يمكننا بعد ذلك إضافة كائن العنوان إلى صفحة جدول المحتويات وتحديد الصفحة الوجهة الخاصة به.

```csharp
for (int i = 1; i < doc.Pages.Count; i++)
{
    // إنشاء كائن العنوان
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);
    // حدد الصفحة الوجهة لكائن العنوان
    heading2.DestinationPage = doc.Pages[i + 1];
    // صفحة الوجهة
    heading2.Top = doc.Pages[i + 1].Rect.Height;
    // تنسيق الوجهة
    segment2.Text = "Page " + i.ToString();
    // أضف عنوانًا إلى الصفحة التي تحتوي على جدول المحتويات
    tocPage.Paragraphs.Add(heading2);
}
```

## الخطوة 5: حفظ المستند المحدث

وأخيرًا، نحتاج إلى حفظ المستند المحدث في ملف جديد. يمكننا تحقيق ذلك باستخدام`Save()` طريقة`Document` هدف.

```csharp
doc.Save(outFile);
```

### مثال على التعليمات البرمجية المصدر لتخصيص أرقام الصفحات أثناء إضافة جدول المحتويات باستخدام Aspose.PDF لـ .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
// قم بتحميل ملفات PDF الموجودة
Document doc = new Document(inFile);
// الوصول إلى الصفحة الأولى من ملف PDF
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
// قم بإنشاء كائن لتمثيل معلومات جدول المحتويات
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
// قم بتعيين عنوان جدول المحتويات
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
for (int i = 1; i<doc.Pages.Count; i++)
{
	// إنشاء كائن العنوان
	Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
	TextSegment segment2 = new TextSegment();
	heading2.TocPage = tocPage;
	heading2.Segments.Add(segment2);
	// حدد الصفحة الوجهة لكائن العنوان
	heading2.DestinationPage = doc.Pages[i + 1];
	// صفحة الوجهة
	heading2.Top = doc.Pages[i + 1].Rect.Height;
	// تنسيق الوجهة
	segment2.Text = "Page " + i.ToString();
	// أضف عنوانًا إلى الصفحة التي تحتوي على جدول المحتويات
	tocPage.Paragraphs.Add(heading2);
}

// احفظ المستند المحدث
doc.Save(outFile);
```

## خاتمة

في هذا البرنامج التعليمي، قدمنا إرشادات خطوة بخطوة حول كيفية تخصيص أرقام الصفحات أثناء إضافة جدول محتويات باستخدام Aspose.PDF لـ .NET. لقد قدمنا أيضًا مثالًا للتعليمات البرمجية التي يمكنك استخدامها كمرجع عند تنفيذ هذه الميزة في ملفك

### الأسئلة الشائعة

#### س: ما هو جدول المحتويات (TOC) في مستند PDF؟

ج: يعد جدول المحتويات (TOC) الموجود في مستند PDF وسيلة مساعدة للتنقل توفر قائمة منظمة بأقسام الوثيقة أو فصولها بالإضافة إلى أرقام الصفحات المقابلة لها. فهو يسمح للقراء بالانتقال بسرعة إلى أقسام محددة داخل المستند.

#### س: لماذا أرغب في تخصيص أرقام الصفحات في جدول المحتويات؟

ج: يمكن أن يكون تخصيص أرقام الصفحات في جدول المحتويات مفيدًا عندما تريد استخدام تنسيق معين لترقيم الصفحات أو تضمين معلومات إضافية مع أرقام الصفحات. يسمح لك بإنشاء جدول محتويات أكثر تخصيصًا وغنيًا بالمعلومات.

#### س: هل يمكنني تضمين ارتباطات تشعبية في جدول المحتويات للارتباط بأقسام أو صفحات معينة داخل مستند PDF؟

ج: نعم، يسمح لك Aspose.PDF for .NET بإنشاء ارتباطات تشعبية في جدول المحتويات التي ترتبط بأقسام أو صفحات محددة داخل مستند PDF. يؤدي ذلك إلى تحسين التفاعل والتنقل في مستند PDF.

#### س: هل يتوافق Aspose.PDF for .NET مع معايير PDF/A؟

ج: نعم، يدعم Aspose.PDF for .NET معايير PDF/A، بما في ذلك PDF/A-1، وPDF/A-2، وPDF/A-3. يسمح لك بإنشاء مستندات PDF تتوافق مع متطلبات الأرشفة والحفظ على المدى الطويل.

#### س: هل يمكنني إضافة المزيد من التنسيق إلى إدخالات جدول المحتويات، مثل أنماط الخطوط أو الألوان؟

ج: نعم، يمكنك إضافة تنسيق إضافي إلى إدخالات جدول المحتويات، مثل أنماط الخطوط والألوان وأحجام الخطوط، باستخدام Aspose.PDF لـ .NET. يتيح لك ذلك تخصيص مظهر جدول المحتويات وفقًا لمتطلباتك.
