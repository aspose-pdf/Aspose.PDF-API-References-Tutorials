---
title: إخفاء أرقام الصفحات في جدول المحتويات
linktitle: إخفاء أرقام الصفحات في جدول المحتويات
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية إخفاء أرقام الصفحات في جدول المحتويات باستخدام Aspose.PDF لـ .NET من خلال هذا الدليل خطوة بخطوة.
type: docs
weight: 220
url: /ar/net/programming-with-document/hidepagenumbersintoc/
---
في هذه المقالة، سنناقش تنفيذ ميزة إخفاء أرقام الصفحات في جدول المحتويات في Aspose.PDF لـ .NET باستخدام C#. سنبدأ بمقدمة موجزة عن Aspose.PDF لـ .NET ثم ننتقل إلى الدليل خطوة بخطوة لتنفيذ هذه الميزة. 

## مقدمة إلى Aspose.PDF لـ .NET

يعد Aspose.PDF for .NET مكونًا قويًا لمعالجة ملفات PDF يتيح للمطورين إنشاء ملفات PDF وتحريرها ومعالجتها برمجيًا. وهو يوفر مجموعة واسعة من الميزات والوظائف التي تسهل العمل مع مستندات PDF. يدعم Aspose.PDF for .NET أنظمة التشغيل 32 بت و64 بت ويمكن استخدامه مع منصات .NET Framework و.NET Core وXamarin. 

## ما هي ميزة إخفاء أرقام الصفحات في جدول المحتويات؟

يُعد جدول المحتويات (TOC) جزءًا أساسيًا من مستند PDF يوفر للمستخدمين نظرة عامة سريعة على المحتوى. في بعض الأحيان، قد يرغب المستخدمون في إخفاء أرقام الصفحات في جدول المحتويات لجعله أكثر سهولة في الاستخدام. يوفر Aspose.PDF for .NET ميزة مدمجة لإخفاء أرقام الصفحات في جدول المحتويات. يمكن استخدام هذه الميزة لإنشاء مستندات PDF أكثر سهولة في الاستخدام. 

## المتطلبات الأساسية

لمتابعة هذا البرنامج التعليمي، ستحتاج إلى ما يلي:

- فيجوال ستوديو 2010 أو أحدث
- تم تثبيت Aspose.PDF لـ .NET على نظامك
- المعرفة الأساسية بلغة البرمجة C#

## دليل خطوة بخطوة لتنفيذ ميزة إخفاء أرقام الصفحات في جدول المحتويات

اتبع الخطوات التالية لتنفيذ ميزة إخفاء أرقام الصفحات في جدول المحتويات باستخدام Aspose.PDF لـ .NET:

## الخطوة 1: إنشاء تطبيق وحدة تحكم C# جديد في Visual Studio

افتح Visual Studio وقم بإنشاء تطبيق وحدة تحكم C# جديد.

## الخطوة 2: إضافة مرجع إلى Aspose.PDF لـ .NET

انقر بزر الماوس الأيمن على مجلد المراجع في مشروعك وحدد إضافة مرجع. انتقل إلى الموقع الذي تم تثبيت Aspose.PDF for .NET فيه على نظامك وأضف مرجعًا إليه.

## الخطوة 1: إنشاء مستند PDF جديد

قم بإنشاء مستند PDF جديد باستخدام الكود التالي:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
```

## الخطوة 2: إنشاء صفحة جدول المحتويات

قم بإنشاء صفحة جديدة لجدول المحتويات وأضفها إلى مستند PDF باستخدام الكود التالي:

```csharp
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
```

## الخطوة 3: إضافة قسم القائمة إلى مجموعة أقسام مستند PDF

قم بإضافة قسم القائمة إلى مجموعة الأقسام في مستند PDF باستخدام الكود التالي:

```csharp
tocPage.TocInfo = tocInfo;
```

## الخطوة 4: تحديد تنسيق قائمة المستويات الأربعة

قم بتحديد تنسيق قائمة المستويات الأربعة عن طريق ضبط الهوامش اليسرى وإعدادات تنسيق النص لكل مستوى باستخدام الكود التالي:

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
//أضف قسم القائمة إلى مجموعة أقسام مستند PDF
tocPage.TocInfo = tocInfo;
//قم بتحديد تنسيق قائمة المستويات الأربعة عن طريق ضبط الهوامش اليسرى و
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

في هذا البرنامج التعليمي، استكشفنا كيفية العمل مع بيانات التعريف XMP في مستند PDF باستخدام Aspose.PDF for .NET. توفر بيانات التعريف XMP معلومات قيمة حول مستند PDF، بما في ذلك عنوانه ومؤلفه وتاريخ إنشائه والمزيد. يتيح Aspose.PDF for .NET للمطورين الوصول إلى هذه البيانات التعريفية ومعالجتها، مما يوفر واجهة برمجة تطبيقات مرنة وقوية للعمل مع مستندات PDF.

### الأسئلة الشائعة

#### س: ما هي بيانات XMP الوصفية في مستند PDF؟

ج: تُعد بيانات التعريف XMP (منصة البيانات التعريفية القابلة للتوسيع) في مستند PDF تنسيقًا قياسيًا لتخزين معلومات التعريف الخاصة بالمستند. وتتضمن تفاصيل مثل عنوان المستند والمؤلف وتاريخ الإنشاء والكلمات الرئيسية والمزيد. توفر بيانات التعريف XMP طريقة منظمة وموحدة لتخزين المعلومات الخاصة بمستند PDF ومشاركتها.

#### س: هل يمكنني تعديل بيانات XMP الخاصة بمستند PDF باستخدام Aspose.PDF لـ .NET؟

 ج: نعم، يمكنك تعديل بيانات تعريف XMP لمستند PDF برمجيًا باستخدام Aspose.PDF لـ .NET. يمكنك الوصول إلى`Info` ممتلكات`Document` الكائن الذي يتيح لك الوصول إلى خصائص بيانات XMP التعريفية. يمكنك بعد ذلك تحديث قيم هذه الخصائص لتعديل بيانات XMP التعريفية لمستند PDF.

#### س: هل يمكنني استخراج خصائص بيانات XMP المخصصة من مستند PDF باستخدام Aspose.PDF لـ .NET؟

 ج: نعم، يمكنك استخراج خصائص بيانات تعريف XMP المخصصة من مستند PDF باستخدام Aspose.PDF لـ .NET. يمكنك استخدام`Metadata` ممتلكات`Document`الكائن الذي يوفر إمكانية الوصول إلى جميع خصائص بيانات XMP الوصفية لمستند PDF. يمكنك بعد ذلك استخراج خصائص مخصصة واستخدام قيمها حسب الحاجة.