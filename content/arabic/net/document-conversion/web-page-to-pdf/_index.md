---
title: صفحة ويب إلى PDF
linktitle: صفحة ويب إلى PDF
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لتحويل صفحة الويب إلى PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 320
url: /ar/net/document-conversion/web-page-to-pdf/
---
في هذا البرنامج التعليمي، سنرشدك خطوة بخطوة حول كيفية تحويل صفحة ويب إلى PDF باستخدام مكتبة Aspose.PDF for .NET. سنشرح لك كود مصدر C# المقدم ونوضح لك كيفية تنفيذه في مشاريعك الخاصة. بحلول نهاية هذا البرنامج التعليمي، ستكون قادرًا على تحويل صفحات الويب إلى مستندات PDF دون عناء.

## مقدمة
يعد تحويل صفحات الويب إلى تنسيق PDF متطلبًا شائعًا في العديد من التطبيقات. من خلال تحويل محتوى الويب إلى PDF، يمكنك بسهولة الحفاظ على تخطيط صفحة الويب الأصلية وتنسيقها وصورها. Aspose.PDF for .NET هي مكتبة قوية تسمح لك بإجراء هذا التحويل بكفاءة ودقة.

## متطلبات
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
- تم تثبيت Visual Studio على جهازك
- Aspose.PDF لمكتبة .NET (يمكنك تنزيله من موقع Aspose الرسمي)
- المعرفة الأساسية ببرمجة C#


## الخطوة 1: تحديد دليل المستندات
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
 يستبدل`"YOUR DOCUMENT DIRECTORY"` بالمسار الذي تريد حفظ ملف PDF الذي تم إنشاؤه فيه.

## الخطوة 2: إنشاء طلب ويب
```csharp
WebRequest request = WebRequest.Create("https://en.wikipedia.org/wiki/Main_Page");
request.Credentials = CredentialCache.DefaultCredentials;
```
قم بإنشاء كائن طلب ويب وحدد عنوان URL لصفحة الويب التي تريد تحويلها. يمكنك استبدال عنوان URL بأي صفحة ويب مطلوبة.

## الخطوة 3: احصل على استجابة الويب
```csharp
HttpWebResponse response = (HttpWebResponse)request.GetResponse();
```
أرسل طلب الويب واحصل على الرد من الخادم.

## الخطوة 4: اقرأ محتوى الويب
```csharp
Stream dataStream = response. GetResponseStream();
StreamReader reader = new StreamReader(dataStream);
string responseFromServer = reader.ReadToEnd();
reader. Close();
dataStream.Close();
response. Close();
```
 اقرأ محتوى صفحة الويب باستخدام ملف`StreamReader`وتخزينها في`responseFromServer` عامل.

## الخطوة 5: تحويل HTML إلى PDF
```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));
HtmlLoadOptions options = new HtmlLoadOptions("https://en.wikipedia.org/wiki/");
Document pdfDocument = new Document(stream, options);
options.PageInfo.IsLandscape = true;
pdfDocument.Save(dataDir + "WebPageToPDF_out.pdf");
```
 إنشاء`MemoryStream` كائن لتحميل محتوى صفحة الويب. ثم قم بإنشاء مثيل لـ`HtmlLoadOptions` وقم بتمرير عنوان URL الأساسي لصفحة الويب. بعد ذلك، قم بإنشاء`Document` كائن باستخدام الدفق المحمل وخيارات تحميل HTML. تعيين`IsLandscape` الملكية ل`true` إذا كنت تريد أن يكون ملف PDF في الاتجاه الأفقي. وأخيرًا، احفظ مستند PDF في الدليل المحدد

.

## الخطوة 6: التعامل مع الاستثناءات
```csharp
catch (Exception ex)
{
Console.WriteLine(ex.Message);
}
```
اكتشف أي استثناءات قد تحدث أثناء عملية التحويل واعرض رسالة الخطأ.

### مثال على التعليمات البرمجية المصدر لصفحة ويب إلى PDF باستخدام Aspose.PDF لـ .NET

```csharp
try
{
	
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// قم بإنشاء طلب لعنوان URL.
	WebRequest request = WebRequest.Create("https:// En.wikipedia.org/wiki/Main_Page");
	// إذا طلب الخادم ذلك، قم بتعيين بيانات الاعتماد.
	request.Credentials = CredentialCache.DefaultCredentials;
	// تنتهي المهلة بالميلي ثانية قبل انتهاء مهلة الطلب
	// مهلة الطلب = 100؛

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
	HtmlLoadOptions options = new HtmlLoadOptions("https:// En.wikipedia.org/wiki/");


	// تحميل ملف HTML
	Document pdfDocument = new Document(stream, options);

	options.PageInfo.IsLandscape = true;

	// حفظ الإخراج بتنسيق PDF
	pdfDocument.Save(dataDir + "WebPageToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية تحويل صفحة ويب إلى PDF باستخدام مكتبة Aspose.PDF for .NET. لقد مررنا بالدليل خطوة بخطوة لشرح كود مصدر C# المقدم. باتباع هذه الإرشادات، يمكنك بسهولة دمج وظيفة تحويل صفحة الويب إلى PDF في تطبيقات .NET الخاصة بك.

### الأسئلة الشائعة

#### س: ما هو Aspose.PDF لـ .NET؟

ج: Aspose.PDF for .NET هي مكتبة قوية تتيح للمطورين العمل مع مستندات PDF في تطبيقات C#. ويوفر وظائف مختلفة، بما في ذلك تحويل صفحات الويب إلى PDF.

#### س: لماذا أرغب في تحويل صفحة ويب إلى PDF؟

ج: يعد تحويل صفحات الويب إلى PDF مفيدًا للحفاظ على تخطيط محتوى الويب الأصلي وتنسيقه وصوره. يسمح لك بإنشاء لقطة من صفحة الويب لمشاهدتها أو مشاركتها مع الآخرين في وضع عدم الاتصال.

#### س: ما هي المتطلبات الأساسية لهذا البرنامج التعليمي؟

ج: لمتابعة هذا البرنامج التعليمي، تحتاج إلى تثبيت Visual Studio على جهازك، وAspose.PDF لمكتبة .NET، وفهم أساسي لبرمجة C#.

#### س: هل يمكنني تحويل أي صفحة ويب إلى PDF؟

ج: نعم، يمكنك تحويل أي صفحة ويب إلى PDF عن طريق توفير عنوان URL لصفحة الويب في الكود. سيقوم Aspose.PDF for .NET باسترداد محتوى الويب وتحويله إلى تنسيق PDF.

#### س: كيف يمكنني تخصيص مخرجات PDF، مثل اتجاه الصفحة؟

 ج: يمكنك تخصيص إخراج PDF باستخدام خيارات مثل`IsLandscape` لتعيين اتجاه الصفحة. في الكود المقدم،`options.PageInfo.IsLandscape = true` يستخدم لإنشاء ملف PDF في الاتجاه الأفقي.