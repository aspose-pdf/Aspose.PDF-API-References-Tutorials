---
title: إخفاء أرقام الصفحات في TOC
linktitle: إخفاء أرقام الصفحات في TOC
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إخفاء أرقام الصفحات في جدول المحتويات باستخدام Aspose.PDF لـ .NET باستخدام هذا الدليل التفصيلي خطوة بخطوة.
type: docs
weight: 220
url: /ar/net/programming-with-document/hidepagenumbersintoc/
---
في هذه المقالة، سنناقش تنفيذ ميزة إخفاء أرقام الصفحات في جدول المحتويات Aspose.PDF لـ .NET باستخدام لغة C#. سنبدأ بمقدمة موجزة عن Aspose.PDF لـ .NET ثم نتعمق في الدليل التفصيلي خطوة بخطوة لتنفيذ هذه الميزة. 

## مقدمة إلى Aspose.PDF لـ .NET

يعد Aspose.PDF for .NET مكونًا قويًا لمعالجة ملفات PDF يسمح للمطورين بإنشاء ملفات PDF وتحريرها ومعالجتها برمجيًا. فهو يوفر مجموعة واسعة من الميزات والوظائف التي تجعل من السهل العمل مع مستندات PDF. يدعم Aspose.PDF for .NET أنظمة التشغيل 32 بت و64 بت ويمكن استخدامه مع الأنظمة الأساسية .NET Framework و.NET Core وXamarin. 

## ما هي ميزة إخفاء أرقام الصفحات في جدول المحتويات؟

يعد جدول المحتويات (TOC) جزءًا أساسيًا من مستند PDF الذي يوفر للمستخدمين نظرة عامة سريعة على المحتوى. في بعض الأحيان، قد يرغب المستخدمون في إخفاء أرقام الصفحات في جدول المحتويات لجعله أكثر سهولة في الاستخدام. يوفر Aspose.PDF for .NET ميزة مضمنة لإخفاء أرقام الصفحات في جدول المحتويات. يمكن استخدام هذه الميزة لإنشاء مستندات PDF أكثر سهولة في الاستخدام. 

## المتطلبات الأساسية

لمتابعة هذا البرنامج التعليمي، سوف تحتاج إلى ما يلي:

- فيجوال ستوديو 2010 أو الأحدث
- Aspose.PDF لـ .NET مثبت على نظامك
- المعرفة الأساسية بلغة البرمجة C#

## دليل خطوة بخطوة لتنفيذ ميزة إخفاء أرقام الصفحات في جدول المحتويات

اتبع الخطوات أدناه لتنفيذ ميزة إخفاء أرقام الصفحات في جدول المحتويات باستخدام Aspose.PDF لـ .NET:

## الخطوة 1: إنشاء تطبيق وحدة تحكم C# جديد في Visual Studio

افتح Visual Studio وقم بإنشاء تطبيق وحدة تحكم C# جديد.

## الخطوة 2: إضافة مرجع إلى Aspose.PDF لـ .NET

انقر بزر الماوس الأيمن على مجلد المراجع في مشروعك وحدد إضافة مرجع. استعرض للوصول إلى الموقع حيث تم تثبيت Aspose.PDF for .NET على نظامك وأضف مرجعًا إليه.

## الخطوة 1: إنشاء مستند PDF جديد

قم بإنشاء مستند PDF جديد باستخدام الكود التالي:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
```

## الخطوة 2: إنشاء صفحة TOC

أنشئ صفحة جديدة لجدول المحتويات وأضفها إلى مستند PDF باستخدام الكود التالي:

```csharp
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
```

## الخطوة 3: إضافة قسم القائمة إلى مجموعة أقسام وثيقة PDF

أضف قسم القائمة إلى مجموعة أقسام مستند PDF باستخدام الكود التالي:

```csharp
tocPage.TocInfo = tocInfo;
```

## الخطوة 4: تحديد تنسيق قائمة المستويات الأربعة

حدد تنسيق قائمة المستويات الأربعة عن طريق ضبط إعدادات الهوامش اليسرى وتنسيق النص لكل مستوى باستخدام الكود التالي:

```csharp
tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
Page page = doc.Pages.Add();
```

## الخطوة 5: أضف أربعة عناوين في القسم

```csharp

for (int Level = 1; Level != 5; Level++)
{ 
	Heading heading2 = new Heading(Level); 
	TextSegment segment2 = new TextSegment(); 
	heading2.TocPage = tocPage; 
	heading2.Segments.Add(segment2); 
	heading2.IsAutoSequence = true; 
	segment2.Text = "this is heading of level " + Level; 
	heading2.IsInList = true; 
	page.Paragraphs.Add(heading2); 
}
doc.Save(outFile);

```

### مثال على كود المصدر لإخفاء أرقام الصفحات في جدول المحتويات باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
//أضف قسم القائمة إلى مجموعة أقسام مستند Pdf
tocPage.TocInfo = tocInfo;
//حدد تنسيق قائمة المستويات الأربعة عن طريق تعيين الهوامش اليسرى و
//إعدادات تنسيق النص لكل مستوى

tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
Page page = doc.Pages.Add();
//أضف أربعة عناوين في القسم
for (int Level = 1; Level != 5; Level++)
	{ 
		Heading heading2 = new Heading(Level); 
		TextSegment segment2 = new TextSegment(); 
		heading2.TocPage = tocPage; 
		heading2.Segments.Add(segment2); 
		heading2.IsAutoSequence = true; 
		segment2.Text = "this is heading of level " + Level; 
		heading2.IsInList = true; 
		page.Paragraphs.Add(heading2); 
	}
doc.Save(outFile);
```

## خاتمة

في هذا البرنامج التعليمي، اكتشفنا كيفية العمل مع بيانات تعريف XMP في مستند PDF باستخدام Aspose.PDF لـ .NET. توفر بيانات تعريف XMP معلومات قيمة حول مستند PDF، بما في ذلك عنوانه ومؤلفه وتاريخ إنشائه والمزيد. يسمح Aspose.PDF for .NET للمطورين بالوصول إلى هذه البيانات الوصفية ومعالجتها، مما يوفر واجهة برمجة تطبيقات مرنة وقوية للعمل مع مستندات PDF.

### الأسئلة الشائعة

#### س: ما هي بيانات تعريف XMP الموجودة في مستند PDF؟

ج: تعد بيانات تعريف XMP (منصة بيانات التعريف القابلة للتوسيع) الموجودة في مستند PDF تنسيقًا قياسيًا لتخزين معلومات بيانات التعريف الخاصة بالمستند. يتضمن تفاصيل مثل عنوان المستند والمؤلف وتاريخ الإنشاء والكلمات الرئيسية والمزيد. توفر بيانات تعريف XMP طريقة منظمة وموحدة لتخزين المعلومات حول مستند PDF ومشاركتها.

#### س: هل يمكنني تعديل بيانات XMP التعريفية لمستند PDF باستخدام Aspose.PDF لـ .NET؟

 ج: نعم، يمكنك تعديل بيانات تعريف XMP لمستند PDF برمجيًا باستخدام Aspose.PDF لـ .NET. يمكنك الوصول إلى`Info` ملكية`Document` الكائن، والذي يتيح لك الوصول إلى خصائص بيانات تعريف XMP. يمكنك بعد ذلك تحديث قيم هذه الخصائص لتعديل بيانات تعريف XMP الخاصة بمستند PDF.

#### س: هل يمكنني استخراج خصائص بيانات تعريف XMP المخصصة من مستند PDF باستخدام Aspose.PDF لـ .NET؟

 ج: نعم، يمكنك استخراج خصائص بيانات تعريف XMP المخصصة من مستند PDF باستخدام Aspose.PDF لـ .NET. يمكنك استخدام ال`Metadata` ملكية`Document`كائن، والذي يوفر الوصول إلى كافة خصائص بيانات تعريف XMP الخاصة بمستند PDF. يمكنك بعد ذلك استخراج الخصائص المخصصة واستخدام قيمها حسب الحاجة.