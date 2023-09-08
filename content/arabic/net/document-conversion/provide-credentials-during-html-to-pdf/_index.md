---
title: توفير بيانات الاعتماد أثناء HTML إلى PDF
linktitle: توفير بيانات الاعتماد أثناء HTML إلى PDF
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لتحويل HTML إلى PDF من خلال توفير بيانات الاعتماد مع Aspose.PDF لـ .NET.
type: docs
weight: 240
url: /ar/net/document-conversion/provide-credentials-during-html-to-pdf/
---
في هذا البرنامج التعليمي، سنرشدك خلال عملية تحويل ملف HTML إلى PDF مع توفير بيانات الاعتماد عند الوصول إلى عنوان URL آمن باستخدام Aspose.PDF لـ .NET. باتباع الخطوات أدناه، ستتمكن من تحويل محتوى HTML إلى PDF باستخدام بيانات الاعتماد المناسبة.

## المتطلبات الأساسية
قبل البدء، تأكد من استيفاء المتطلبات الأساسية التالية:

- المعرفة الأساسية بلغة البرمجة C#.
- مكتبة Aspose.PDF لـ .NET مثبتة على نظامك.
- بيئة تطوير مثل Visual Studio.

## الخطوة 1: جلب محتوى HTML آمن
في هذه الخطوة، سنقوم بإحضار محتوى HTML آمن من عنوان URL باستخدام بيانات الاعتماد المناسبة. استخدم الكود التالي:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بإنشاء طلب لعنوان URL.
WebRequest request = WebRequest.Create("http://My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
// إذا لزم الأمر للخادم، قم بتعيين بيانات الاعتماد.
request.Credentials = CredentialCache.DefaultCredentials;
// احصل على الرد.
HttpWebResponse response = (HttpWebResponse)request.GetResponse();

// احصل على الدفق الذي يحتوي على المحتوى الذي أرجعه الخادم.
Stream dataStream = response. GetResponseStream();
// افتح الدفق باستخدام StreamReader لسهولة الوصول إليه.
StreamReader reader = new StreamReader(dataStream);
// اقرأ المحتوى.
string responseFromServer = reader.ReadToEnd();
reader. Close();
dataStream.Close();
response. Close();
```

 تأكد من استبدال`"YOUR DOCUMENTS DIRECTORY"` باستخدام الدليل الفعلي الذي تريد حفظ ملف PDF الناتج فيه.

## الخطوة 2: تحويل HTML إلى PDF عن طريق توفير بيانات الاعتماد
سنقوم الآن بتحميل محتوى HTML المسترد وتحويله إلى تنسيق PDF مع توفير بيانات الاعتماد المناسبة. استخدم الكود التالي:

```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));

HtmlLoadOptions options = new HtmlLoadOptions("http://My.signchart.com/");
options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

// قم بتحميل ملف HTML
Document pdfDocument = new Document(stream, options);
```

## الخطوة 3: حفظ ملف PDF الناتج
وأخيرا، سوف نقوم بحفظ ملف PDF الناتج. استخدم الكود التالي:

```csharp
// احفظ ملف PDF الناتج
pdfDocument.Save(dataDir + "ProvideCredentialsDuringHTMLToPDF_out.pdf");
```

 يحفظ الكود أعلاه ملف PDF الناتج باسم الملف`"ProvideCredentialsDuringHTMLToPDF_out.pdf"`.

### مثال على التعليمات البرمجية المصدر لتوفير بيانات الاعتماد أثناء HTML إلى PDF باستخدام Aspose.PDF لـ .NET

```csharp
try
{
	
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// قم بإنشاء طلب لعنوان URL.
	WebRequest request = WebRequest.Create("http:// My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
	// إذا طلب الخادم ذلك، قم بتعيين بيانات الاعتماد.
	request.Credentials = CredentialCache.DefaultCredentials;
	// احصل على الرد.
	HttpWebResponse response = (HttpWebResponse)request.GetResponse();

	// احصل على الدفق الذي يحتوي على المحتوى الذي تم إرجاعه بواسطة الخادم.
	Stream dataStream = response.GetResponseStream();
	// افتح الدفق باستخدام StreamReader لسهولة الوصول إليه.
	StreamReader reader = new StreamReader(dataStream);
	// اقرأ المحتوى.
	string responseFromServer = reader.ReadToEnd();
	reader.Close();
	dataStream.Close();
	response.Close();

	MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));

	HtmlLoadOptions options = new HtmlLoadOptions("http:// My.signchart.com/");
	options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

	// تحميل ملف HTML
	Document pdfDocument = new Document(stream, options);
	// حفظ الملف الناتج
	pdfDocument.Save("ProvideCredentialsDuringHTMLToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## خاتمة
في هذا البرنامج التعليمي، قمنا بتغطية العملية خطوة بخطوة لتحويل ملف HTML إلى PDF مع توفير بيانات الاعتماد عند الوصول إلى عنوان URL آمن باستخدام Aspose.PDF لـ .NET. باتباع الإرشادات الموضحة أعلاه، ستتمكن من تحويل محتوى HTML إلى PDF بنجاح مع توفير بيانات الاعتماد الصحيحة.

### الأسئلة الشائعة

#### س: ما هو Aspose.PDF لـ .NET؟

ج: Aspose.PDF for .NET هي مكتبة قوية تمكن المطورين من العمل مع مستندات PDF في تطبيقات C#. وهو يقدم مجموعة واسعة من الوظائف، بما في ذلك تحويل HTML إلى PDF.

#### س: كيف يمكنني جلب محتوى HTML آمن من عنوان URL؟

 ج: لجلب محتوى HTML آمن من عنوان URL، يمكنك استخدام`WebRequest` فئة في C#. تأكد من تعيين بيانات الاعتماد المناسبة باستخدام`Credentials` ملكية.

#### س: ما هي المتطلبات الأساسية لهذا البرنامج التعليمي؟

ج: قبل متابعة البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:

- المعرفة الأساسية بلغة البرمجة C#.
- مكتبة Aspose.PDF لـ .NET مثبتة على نظامك.
- بيئة تطوير مثل Visual Studio.

#### س: كيف يتعامل Aspose.PDF for .NET مع الموارد الخارجية أثناء تحويل HTML إلى PDF؟

 ج: يوفر Aspose.PDF لـ .NET`HtmlLoadOptions`فئة للتعامل مع الموارد الخارجية أثناء تحويل HTML إلى PDF. يمكنك تعيين بيانات اعتماد المورد الخارجي باستخدام`ExternalResourcesCredentials` ملكية.

#### س: هل يمكنني تخصيص اسم الملف لملف PDF الناتج؟

 ج: نعم، يمكنك تخصيص اسم الملف لملف PDF الناتج عن طريق تعديل الكود الذي يحفظ مستند PDF. ما عليك سوى تغيير اسم الملف المطلوب في ملف`pdfDocument.Save()` طريقة.