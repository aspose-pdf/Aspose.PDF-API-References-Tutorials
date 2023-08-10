---
title: صفحة الويب إلى PDF
linktitle: صفحة الويب إلى PDF
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لتحويل صفحة الويب إلى PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 320
url: /ar/net/document-conversion/web-page-to-pdf/
---
في هذا البرنامج التعليمي ، سنوجهك خطوة بخطوة حول كيفية تحويل صفحة ويب إلى PDF باستخدام Aspose.PDF لمكتبة .NET. سنشرح كود المصدر C # المقدم ونوضح لك كيفية تنفيذه في مشاريعك الخاصة. بنهاية هذا البرنامج التعليمي ، ستتمكن من تحويل صفحات الويب إلى مستندات PDF دون عناء.

## مقدمة
يعد تحويل صفحات الويب إلى تنسيق PDF مطلبًا شائعًا في العديد من التطبيقات. بتحويل محتوى الويب إلى PDF ، يمكنك بسهولة الحفاظ على تخطيط وتنسيق وصور صفحة الويب الأصلية. Aspose.PDF for .NET مكتبة قوية تسمح لك بإجراء هذا التحويل بكفاءة ودقة.

## متطلبات
قبل أن نبدأ ، تأكد من توفر المتطلبات الأساسية التالية:
- تم تثبيت Visual Studio على جهازك
- Aspose.PDF for .NET library (يمكنك تنزيله من موقع Aspose الرسمي)
- المعرفة الأساسية ببرمجة C #


## الخطوة 1: تحديد دليل المستندات
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
 يستبدل`"YOUR DOCUMENT DIRECTORY"` بالمسار الذي تريد حفظ ملف PDF الذي تم إنشاؤه فيه.

## الخطوة 2: إنشاء طلب ويب
```csharp
WebRequest request = WebRequest.Create("https://en.wikipedia.org/wiki/Main_Page ") ؛
request.Credentials = CredentialCache.DefaultCredentials;
```
قم بإنشاء كائن طلب ويب وحدد عنوان URL لصفحة الويب التي تريد تحويلها. يمكنك استبدال عنوان URL بأي صفحة ويب مطلوبة.

## الخطوة 3: احصل على استجابة الويب
```csharp
HttpWebResponse response = (HttpWebResponse)request.GetResponse();
```
أرسل طلب الويب واسترجع الاستجابة من الخادم.

## الخطوة الرابعة: قراءة محتوى الويب
```csharp
Stream dataStream = response. GetResponseStream();
StreamReader reader = new StreamReader(dataStream);
string responseFromServer = reader.ReadToEnd();
reader. Close();
dataStream.Close();
response. Close();
```
 اقرأ محتوى صفحة الويب باستخدام ملف`StreamReader` وتخزينه في ملف`responseFromServer` عامل.

## الخطوة 5: تحويل HTML إلى PDF
```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));
HtmlLoadOptions options = new HtmlLoadOptions("https://en.wikipedia.org/wiki/ ") ؛
Document pdfDocument = new Document(stream, options);
options.PageInfo.IsLandscape = true;
pdfDocument.Save(dataDir + "WebPageToPDF_out.pdf");
```
 إنشاء`MemoryStream` كائن لتحميل محتوى صفحة الويب. ثم قم بإنشاء مثيل لـ`HtmlLoadOptions` وتمرير عنوان URL الأساسي لصفحة الويب. بعد ذلك ، قم بإنشاء ملف`Document` باستخدام الدفق المحمل وخيارات تحميل HTML. تعيين`IsLandscape` الملكية ل`true` إذا كنت تريد أن يكون ملف PDF في اتجاه أفقي. أخيرًا ، احفظ مستند PDF في الدليل المحدد

.

## الخطوة 6: التعامل مع الاستثناءات
```csharp
catch (Exception ex)
{
Console.WriteLine(ex.Message);
}
```
اكتشف أي استثناءات قد تحدث أثناء عملية التحويل واعرض رسالة الخطأ.

### مثال على الكود المصدري لصفحة الويب إلى PDF باستخدام Aspose.PDF لـ .NET

```csharp
try
{
	
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// قم بإنشاء طلب لعنوان URL.
	WebRequest request = WebRequest.Create("https:// En.wikipedia.org/wiki/Main_Page ") ؛
	// إذا طلب الخادم ذلك ، فقم بتعيين بيانات الاعتماد.
	request.Credentials = CredentialCache.DefaultCredentials;
	// المهلة بالمللي ثانية قبل انتهاء مهلة الطلب
	// تاريخ الطلب = 100 ؛

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
	HtmlLoadOptions options = new HtmlLoadOptions("https:// En.wikipedia.org/wiki/ ") ؛


	// قم بتحميل ملف HTML
	Document pdfDocument = new Document(stream, options);

	options.PageInfo.IsLandscape = true;

	// احفظ الإخراج بتنسيق PDF
	pdfDocument.Save(dataDir + "WebPageToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية تحويل صفحة ويب إلى PDF باستخدام Aspose.PDF لمكتبة .NET. لقد راجعنا الدليل التفصيلي خطوة بخطوة لشرح كود مصدر C # المقدم. باتباع هذه التعليمات ، يمكنك بسهولة دمج صفحة الويب مع وظيفة تحويل PDF في تطبيقات .NET الخاصة بك.

### التعليمات

#### س: ما هو Aspose.PDF لـ .NET؟

ج: Aspose.PDF for .NET مكتبة قوية تسمح للمطورين بالعمل مع مستندات PDF في تطبيقات C #. يوفر وظائف مختلفة ، بما في ذلك تحويل صفحات الويب إلى PDF.

#### س: لماذا أرغب في تحويل صفحة ويب إلى PDF؟

ج: يعد تحويل صفحات الويب إلى PDF مفيدًا في الحفاظ على تخطيط وتنسيق وصور محتوى الويب الأصلي. يسمح لك بإنشاء لقطة لصفحة الويب لعرضها في وضع عدم الاتصال أو مشاركتها مع الآخرين.

#### س: ما هي المتطلبات الأساسية لهذا البرنامج التعليمي؟

ج: لمتابعة هذا البرنامج التعليمي ، تحتاج إلى تثبيت Visual Studio على جهازك ، ومكتبة Aspose.PDF for .NET ، وفهم أساسي لبرمجة C #.

#### س: هل يمكنني تحويل أي صفحة ويب إلى PDF؟

ج: نعم ، يمكنك تحويل أي صفحة ويب إلى PDF عن طريق توفير عنوان URL لصفحة الويب في الكود. سيقوم Aspose.PDF for .NET باسترداد محتوى الويب وتحويله إلى تنسيق PDF.

#### س: كيف يمكنني تخصيص إخراج PDF ، مثل اتجاه الصفحة؟

 ج: يمكنك تخصيص إخراج PDF باستخدام خيارات مثل`IsLandscape` لتعيين اتجاه الصفحة. في الكود المقدم ،`options.PageInfo.IsLandscape = true` يستخدم لإنشاء ملف PDF في اتجاه أفقي.