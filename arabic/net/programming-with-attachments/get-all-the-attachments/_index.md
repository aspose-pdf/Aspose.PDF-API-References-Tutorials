---
title: احصل على جميع المرفقات في ملف PDF
linktitle: احصل على جميع المرفقات في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية الحصول على جميع المرفقات في ملف PDF باستخدام Aspose.PDF for .NET. دليل خطوة بخطوة لسهولة التعامل.
type: docs
weight: 40
url: /ar/net/programming-with-attachments/get-all-the-attachments/
---
في هذا البرنامج التعليمي ، سنرشدك خلال التعليمات البرمجية المصدر C # التالية خطوة بخطوة للحصول على جميع المرفقات في ملف PDF باستخدام Aspose.PDF for .NET.

تأكد من تثبيت مكتبة Aspose.PDF وإعداد بيئة التطوير الخاصة بك قبل أن تبدأ. لديك أيضًا معرفة أساسية ببرمجة C #.

### الخطوة 1: إعداد دليل المستند

في كود المصدر المقدم ، تحتاج إلى تحديد الدليل الذي يوجد به ملف PDF والذي تريد الحصول على المرفقات منه. قم بتغيير متغير "dataDir" إلى الدليل المطلوب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### الخطوة 2: افتح مستند PDF الحالي

نفتح مستند PDF الحالي باستخدام المسار المحدد.

```csharp
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
```

### الخطوة الثالثة: الحصول على مجموعة المرفقات

نحصل على مجموعة المرفقات من الوثيقة.

```csharp
EmbeddedFileCollection embeddedFiles = pdfDocument.EmbeddedFiles;
```

### الخطوة 4: استرجاع المرفقات

نمر على المجموعة للحصول على جميع المرفقات وعرض المعلومات الخاصة بهم. نقوم أيضًا بحفظ المرفقات في ملفات فردية.

```csharp
int count = 1;
foreach(FileSpecification fileSpecification in embeddedFiles)
{
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("MIME Type: {0}", fileSpecification.MIMEType);

// تحقق مما إذا كانت معلمات الكائن تحتوي على معلومات إضافية
if (fileSpecification.Params != null)
{
Console.WriteLine("CheckSum: {0}", fileSpecification.Params.CheckSum);
Console.WriteLine("Creation date: {0}", fileSpecification.Params.CreationDate);
Console.WriteLine("Modified date: {0}", fileSpecification.Params.ModDate);
Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}

// استرجع المرفق وحفظه في ملف
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + count + "_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();

count += 1;
}
```


### نموذج التعليمات البرمجية المصدر للحصول على كافة المرفقات باستخدام Aspose.PDF لـ .NET 

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
// الحصول على مجموعة الملفات المضمنة
EmbeddedFileCollection embeddedFiles = pdfDocument.EmbeddedFiles;
// احصل على عدد الملفات المضمنة
Console.WriteLine("Total files : {0}", embeddedFiles.Count);
int count = 1;
// قم بإجراء حلقة عبر المجموعة للحصول على جميع المرفقات
foreach (FileSpecification fileSpecification in embeddedFiles)
{
	Console.WriteLine("Name: {0}", fileSpecification.Name);
	Console.WriteLine("Description: {0}",
	fileSpecification.Description);
	Console.WriteLine("Mime Type: {0}", fileSpecification.MIMEType);
	//تحقق مما إذا كان كائن المعلمة يحتوي على المعلمات
	if (fileSpecification.Params != null)
	{
		Console.WriteLine("CheckSum: {0}",
		fileSpecification.Params.CheckSum);
		Console.WriteLine("Creation Date: {0}",
		fileSpecification.Params.CreationDate);
		Console.WriteLine("Modification Date: {0}",
		fileSpecification.Params.ModDate);
		Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
	}
	// احصل على المرفق واكتب في ملف أو دفق
	byte[] fileContent = new byte[fileSpecification.Contents.Length];
	fileSpecification.Contents.Read(fileContent, 0,
	fileContent.Length);
	FileStream fileStream = new FileStream(dataDir + count + "_out" + ".txt",
	FileMode.Create);
	fileStream.Write(fileContent, 0, fileContent.Length);
	fileStream.Close();
	count+=1;
}

```

## خاتمة

في هذا البرنامج التعليمي ، أوضحنا كيفية الحصول على جميع المرفقات من ملف PDF باستخدام Aspose.PDF for .NET. يمكنك الآن استخدام هذه المعرفة لاستخراج ومعالجة المرفقات من ملفات PDF الخاصة بك.

## الأسئلة الشائعة للحصول على جميع المرفقات في ملف PDF

#### س: لماذا أحتاج إلى استرداد جميع المرفقات من مستند PDF؟

ج: يتيح لك استرداد المرفقات الوصول إلى الملفات الإضافية المضمنة في ملف PDF ومعالجتها ، والتي يمكن أن تكون مفيدة للأرشفة أو المشاركة أو المعالجة الإضافية.

#### س: ما أنواع الملفات التي يمكن إرفاقها بمستند PDF؟

ج: يمكن أن تحتوي مستندات PDF على مجموعة كبيرة من الملفات المرفقة ، بما في ذلك الصور والمستندات وجداول البيانات والملفات الصوتية والمزيد.

#### س: كيف يساعدني هذا البرنامج التعليمي في استرداد المرفقات من ملف PDF باستخدام Aspose.PDF for .NET؟

ج: يوفر هذا البرنامج التعليمي إرشادات خطوة بخطوة وكود مصدر C # للوصول إلى جميع المرفقات واستردادها في مستند PDF.

#### س: هل يمكنني استرداد مرفقات معينة بدلاً من جميع المرفقات باستخدام هذا البرنامج التعليمي؟

ج: نعم ، يمكنك تعديل الكود المقدم لاسترداد المرفقات بشكل انتقائي بناءً على متطلباتك.

#### س: ما هي المعلومات حول كل مرفق التي يمكنني الحصول عليها باستخدام هذا البرنامج التعليمي؟

ج: يوضح هذا البرنامج التعليمي كيفية استرداد التفاصيل وعرضها مثل اسم المرفق والوصف ونوع MIME وتاريخ الإنشاء وتاريخ التعديل والحجم.

#### س: كيف يتم حفظ المرفقات المسترجعة باستخدام هذا البرنامج التعليمي؟

ج: يرشدك البرنامج التعليمي خلال عملية حفظ كل مرفق مسترجع كملف منفصل في الدليل المحدد.

#### س: هل يمكنني استخدام هذه المعرفة لاستخراج المرفقات من ملفات PDF المحمية بكلمة مرور؟

ج: نعم ، يمكنك تطبيق مبادئ مماثلة لاسترداد المرفقات من ملفات PDF المحمية بكلمة مرور باستخدام Aspose.PDF for .NET.

#### س: كيف يسهل Aspose.PDF for .NET استرجاع المرفقات؟

ج: يوفر Aspose.PDF for .NET واجهة برمجة تطبيقات سهلة الاستخدام تسمح لك بالوصول إلى المرفقات ومعالجتها في مستندات PDF بسهولة.

#### س: هل هناك سيناريوهات محددة حيث يوصى باسترجاع المرفقات؟

ج: يعد استرداد المرفقات مفيدًا عندما تحتاج إلى الوصول إلى الملفات المضمنة في ملف PDF ، مثل استخراج الصور أو الملفات الصوتية أو المستندات الإضافية.