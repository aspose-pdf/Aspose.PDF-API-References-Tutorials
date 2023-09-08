---
title: استخراج النص باستخدام جهاز النص
linktitle: استخراج النص باستخدام جهاز النص
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استخراج النص من مستند PDF باستخدام جهاز النص في Aspose.PDF لـ .NET.
type: docs
weight: 210
url: /ar/net/programming-with-text/extract-text-using-text-device/
---
سيرشدك هذا البرنامج التعليمي خلال عملية استخراج النص من مستند PDF باستخدام جهاز النص في Aspose.PDF لـ .NET. يوضح كود مصدر C# المقدم الخطوات اللازمة.

## متطلبات
قبل أن تبدأ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي مترجم C# آخر مثبت على جهازك.
- Aspose.PDF لمكتبة .NET. يمكنك تنزيله من موقع Aspose الرسمي أو استخدام مدير الحزم مثل NuGet لتثبيته.

## الخطوة 1: إعداد المشروع
1. قم بإنشاء مشروع C# جديد في بيئة التطوير المفضلة لديك.
2. قم بإضافة مرجع إلى Aspose.PDF لمكتبة .NET.

## الخطوة 2: استيراد مساحات الأسماء المطلوبة
في ملف التعليمات البرمجية الذي تريد استخراج النص منه، أضف ما يلي باستخدام التوجيهات الموجودة في الجزء العلوي من الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

## الخطوة 3: قم بتعيين دليل المستند
 في الكود، حدد السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدال`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل حيث يتم تخزين المستندات الخاصة بك.

## الخطوة 4: افتح مستند PDF
 افتح مستند PDF موجود باستخدام الملف`Document`منشئ وتمرير المسار إلى ملف PDF الإدخال.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## الخطوة 5: استخراج النص باستخدام جهاز النص
 إنشاء`StringBuilder` كائن للاحتفاظ بالنص المستخرج. قم بالتكرار خلال كل صفحة من المستند واستخدم أ`TextDevice` لاستخراج النص من كل صفحة.

```csharp
StringBuilder builder = new StringBuilder();
string extractedText = "";
foreach(Page pdfPage in pdfDocument.Pages)
{
using (MemoryStream textStream = new MemoryStream())
{
TextDevice textDevice = new TextDevice();
TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
textDevice.ExtractionOptions = textExtOptions;
textDevice.Process(pdfPage, textStream);
textStream. Close();
extractedText = Encoding.Unicode.GetString(textStream.ToArray());
}
builder. Append(extractedText);
}
```

## الخطوة 6: احفظ النص المستخرج
 حدد مسار ملف الإخراج واحفظ النص المستخرج في ملف نصي باستخدام الملف`File.WriteAllText` طريقة.

```csharp
dataDir = dataDir + "input_Text_Extracted_out.txt";
File.WriteAllText(dataDir, builder.ToString());
```

### نموذج التعليمات البرمجية المصدر لاستخراج النص باستخدام جهاز النص باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document( dataDir + "input.pdf");
System.Text.StringBuilder builder = new System.Text.StringBuilder();
//سلسلة للاحتفاظ بالنص المستخرج
string extractedText = "";
foreach (Page pdfPage in pdfDocument.Pages)
{
	using (MemoryStream textStream = new MemoryStream())
	{
		// إنشاء جهاز النص
		TextDevice textDevice = new TextDevice();
		// ضبط خيارات استخراج النص - ضبط وضع استخراج النص (خام أو نقي)
		TextExtractionOptions textExtOptions = new
		TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
		textDevice.ExtractionOptions = textExtOptions;
		// تحويل صفحة معينة وحفظ النص في الدفق
		textDevice.Process(pdfPage, textStream);
		// تحويل صفحة معينة وحفظ النص في الدفق
		textDevice.Process(pdfDocument.Pages[1], textStream);
		// إغلاق دفق الذاكرة
		textStream.Close();
		// الحصول على النص من دفق الذاكرة
		extractedText = Encoding.Unicode.GetString(textStream.ToArray());
	}
	builder.Append(extractedText);
}
dataDir = dataDir + "input_Text_Extracted_out.txt";
// احفظ النص المستخرج في ملف نصي
File.WriteAllText(dataDir, builder.ToString());
Console.WriteLine("\nText extracted successfully using text device from page of PDF Document.\nFile saved at " + dataDir);
```

## خاتمة
لقد نجحت في استخراج النص من مستند PDF باستخدام Text Device في Aspose.PDF لـ .NET. تم حفظ النص المستخرج في ملف الإخراج المحدد.

### الأسئلة الشائعة

#### س: ما هو الغرض من هذا البرنامج التعليمي؟

ج: يوفر هذا البرنامج التعليمي إرشادات حول استخراج النص من مستند PDF باستخدام ميزة Text Device في Aspose.PDF لـ .NET. يوضح كود مصدر C# المصاحب الخطوات اللازمة لتحقيق هذه المهمة.

#### س: ما هي مساحات الأسماء التي يجب علي استيرادها؟

ج: في ملف التعليمات البرمجية الذي تخطط لاستخراج النص منه، قم بتضمين ما يلي باستخدام التوجيهات في بداية الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

#### س: كيف أحدد دليل المستندات؟

 ج: في الكود، ابحث عن السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدال`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

#### س: كيف يمكنني فتح مستند PDF موجود؟

 ج: في الخطوة 4، ستفتح مستند PDF موجودًا باستخدام الملف`Document` منشئ وتوفير المسار إلى ملف PDF الإدخال.

#### س: كيف يمكنني استخراج النص باستخدام جهاز النص؟

 ج: تتضمن الخطوة 5 إنشاء ملف`StringBuilder` كائن للاحتفاظ بالنص المستخرج. ستقوم بعد ذلك بالتكرار خلال كل صفحة من المستند واستخدام`TextDevice` جنبا إلى جنب مع`TextExtractionOptions` لاستخراج النص من كل صفحة.

#### س: كيف يمكنني حفظ النص المستخرج في ملف؟

 ج: في الخطوة 6، ستحدد مسار ملف الإخراج وتستخدم ملف`File.WriteAllText`طريقة حفظ النص المستخرج في ملف نصي.

#### س: ما هي الوجبات الرئيسية من هذا البرنامج التعليمي؟

ج: باتباع هذا البرنامج التعليمي، تعلمت كيفية الاستفادة من ميزة Text Device في Aspose.PDF لـ .NET لاستخراج النص من مستند PDF. تم حفظ النص المستخرج في ملف إخراج محدد، مما يتيح لك التعامل مع المحتوى المستخرج واستخدامه حسب الحاجة.