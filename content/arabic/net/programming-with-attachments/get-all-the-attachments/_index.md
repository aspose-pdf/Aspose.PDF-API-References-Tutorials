---
title: احصل على جميع المرفقات في ملف PDF
linktitle: احصل على جميع المرفقات في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية الحصول على جميع المرفقات في ملف PDF باستخدام Aspose.PDF لـ .NET. دليل خطوة بخطوة لسهولة التعامل.
type: docs
weight: 40
url: /ar/net/programming-with-attachments/get-all-the-attachments/
---
في هذا البرنامج التعليمي، سنرشدك عبر التعليمات البرمجية المصدر لـ C# التالية خطوة بخطوة للحصول على جميع المرفقات في ملف PDF باستخدام Aspose.PDF لـ .NET.

تأكد من تثبيت مكتبة Aspose.PDF وإعداد بيئة التطوير الخاصة بك قبل البدء. لديك أيضًا معرفة أساسية ببرمجة C#.

### الخطوة 1: إعداد دليل المستندات

في الكود المصدري المقدم، تحتاج إلى تحديد الدليل الذي يوجد به ملف PDF الذي تريد الحصول على المرفقات منه. قم بتغيير المتغير "dataDir" إلى الدليل المطلوب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### الخطوة 2: افتح مستند PDF الموجود

نفتح مستند PDF الموجود باستخدام المسار المحدد.

```csharp
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
```

### الخطوة 3: الحصول على مجموعة المرفقات

نحصل على مجموعة المرفقات من الوثيقة.

```csharp
EmbeddedFileCollection embeddedFiles = pdfDocument.EmbeddedFiles;
```

### الخطوة الرابعة: استرجاع المرفقات

نتصفح المجموعة للحصول على جميع المرفقات وعرض معلوماتها. نقوم أيضًا بحفظ المرفقات في ملفات فردية.

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

// قم باسترجاع المرفق وحفظه في ملف
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
// احصل على مجموعة الملفات المضمنة
EmbeddedFileCollection embeddedFiles = pdfDocument.EmbeddedFiles;
// الحصول على عدد من الملفات المدمجة
Console.WriteLine("Total files : {0}", embeddedFiles.Count);
int count = 1;
// قم بالمراجعة عبر المجموعة للحصول على كافة المرفقات
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
	// احصل على المرفق واكتبه في ملف أو دفق
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

في هذا البرنامج التعليمي، شرحنا كيفية الحصول على كافة المرفقات من ملف PDF باستخدام Aspose.PDF لـ .NET. يمكنك الآن استخدام هذه المعرفة لاستخراج المرفقات من ملفات PDF الخاصة بك ومعالجتها.

## الأسئلة الشائعة للحصول على جميع المرفقات في ملف PDF

#### س: لماذا أحتاج إلى استرداد جميع المرفقات من مستند PDF؟

ج: يتيح لك استرداد المرفقات الوصول إلى الملفات الإضافية المضمنة في ملف PDF ومعالجتها، مما قد يكون مفيدًا للأرشفة أو المشاركة أو المعالجة الإضافية.

#### س: ما هي أنواع الملفات التي يمكن إرفاقها بمستند PDF؟

ج: يمكن أن تحتوي مستندات PDF على مجموعة واسعة من الملفات المرفقة، بما في ذلك الصور والمستندات وجداول البيانات والملفات الصوتية والمزيد.

#### س: كيف يساعدني هذا البرنامج التعليمي في استرداد المرفقات من ملف PDF باستخدام Aspose.PDF لـ .NET؟

ج: يوفر هذا البرنامج التعليمي إرشادات خطوة بخطوة وكود مصدر C# للوصول إلى جميع المرفقات واستردادها داخل مستند PDF.

#### س: هل يمكنني استرداد مرفقات معينة بدلاً من كافة المرفقات باستخدام هذا البرنامج التعليمي؟

ج: نعم، يمكنك تعديل الكود المقدم لاسترداد المرفقات بشكل انتقائي بناءً على متطلباتك.

#### س: ما هي المعلومات المتعلقة بكل مرفق التي يمكنني الحصول عليها باستخدام هذا البرنامج التعليمي؟

ج: يوضح هذا البرنامج التعليمي كيفية استرداد وعرض التفاصيل مثل اسم المرفق والوصف ونوع MIME وتاريخ الإنشاء وتاريخ التعديل والحجم.

#### س: كيف يتم حفظ المرفقات المستردة باستخدام هذا البرنامج التعليمي؟

ج: يرشدك البرنامج التعليمي خلال حفظ كل مرفق تم استرداده كملف منفصل في الدليل المحدد.

#### س: هل يمكنني استخدام هذه المعرفة لاستخراج المرفقات من ملفات PDF محمية بكلمة مرور؟

ج: نعم، يمكنك تطبيق مبادئ مماثلة لاسترداد المرفقات من ملفات PDF المحمية بكلمة مرور باستخدام Aspose.PDF لـ .NET.

#### س: كيف يسهل Aspose.PDF for .NET استرجاع المرفقات؟

ج: يوفر Aspose.PDF for .NET واجهة برمجة تطبيقات بديهية تسمح لك بالوصول إلى المرفقات في مستندات PDF ومعالجتها بسهولة.

#### س: هل هناك سيناريوهات محددة يوصى فيها باسترداد المرفقات؟

ج: يعد استرداد المرفقات مفيدًا عندما تحتاج إلى الوصول إلى الملفات المضمنة في ملف PDF، مثل استخراج الصور أو الملفات الصوتية أو المستندات الإضافية.