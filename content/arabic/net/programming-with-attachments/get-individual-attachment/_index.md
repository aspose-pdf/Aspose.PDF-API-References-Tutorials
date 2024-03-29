---
title: احصل على مرفق فردي في ملف PDF
linktitle: احصل على مرفق فردي في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية الحصول على مرفق فردي في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 60
url: /ar/net/programming-with-attachments/get-individual-attachment/
---
في هذا البرنامج التعليمي، سنرشدك عبر التعليمات البرمجية المصدر لـ C# التالية خطوة بخطوة للحصول على مرفق فردي لملف PDF باستخدام Aspose.PDF لـ .NET.

تأكد من تثبيت مكتبة Aspose.PDF وإعداد بيئة التطوير الخاصة بك قبل البدء. لديك أيضًا معرفة أساسية ببرمجة C#.

### الخطوة 1: إعداد دليل المستندات

في الكود المصدري المقدم، تحتاج إلى تحديد الدليل الذي يوجد به ملف PDF الذي تريد الحصول على المرفق الفردي منه. قم بتغيير المتغير "dataDir" إلى الدليل المطلوب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### الخطوة 2: افتح مستند PDF الموجود

نفتح مستند PDF الموجود باستخدام المسار المحدد.

```csharp
Document pdfDocument = new Document(dataDir + "GetIndividualAttachment.pdf");
```

### الخطوة 3: الحصول على مرفق محدد

نقوم باسترجاع مرفق محدد من مجموعة مرفقات الوثيقة. في هذا المثال، نحصل على المرفق الأول باستخدام الفهرس 1.

```csharp
FileSpecification fileSpecification = pdfDocument.EmbeddedFiles[1];
```

### الخطوة 4: الحصول على خصائص الملف

نعرض خصائص المرفقات مثل الاسم والوصف ونوع MIME وتجزئة التحكم وتاريخ الإنشاء وتاريخ التعديل والحجم.

```csharp
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("MIME Type: {0}", fileSpecification.MIMEType);

// تحقق مما إذا كانت معلمات الكائن تحتوي على معلومات إضافية
if (fileSpecification.Params != null)
{
Console.WriteLine("Check Hash: {0}", fileSpecification.Params.CheckSum);
Console.WriteLine("Creation date: {0}", fileSpecification.Params.CreationDate);
Console.WriteLine("Modified date: {0}", fileSpecification.Params.ModDate);
Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}
```

### الخطوة 5: استرجاع المرفق وحفظه في الملف

نقوم باسترجاع محتوى المرفق وحفظه في ملف نصي. في هذا المثال، يتم حفظ الملف بالاسم "test_out.txt".

```csharp
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + "test_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();
```

### نموذج التعليمات البرمجية المصدر للحصول على مرفق فردي باستخدام Aspose.PDF لـ .NET 

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "GetIndividualAttachment.pdf");
// احصل على ملف مضمن معين
FileSpecification fileSpecification = pdfDocument.EmbeddedFiles[1];
// الحصول على خصائص الملف
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
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
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + "test_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();

```

## خاتمة

في هذا البرنامج التعليمي، شرحنا كيفية الحصول على مرفق فردي من ملف PDF باستخدام Aspose.PDF لـ .NET. يمكنك الآن استخدام هذه المعرفة لاستخراج المرفقات وحفظها من ملفات PDF الخاصة بك.

### الأسئلة الشائعة للحصول على مرفق فردي في ملف PDF

#### س: ما هو الغرض من الحصول على مرفق فردي من مستند PDF؟

ج: الحصول على مرفق فردي يسمح لك باستخراج وحفظ ملف مضمن محدد داخل ملف PDF، وهو ما يمكن أن يكون مفيدًا لمزيد من التحليل أو المعالجة.

#### س: كيف يمكنني الاستفادة من هذا البرنامج التعليمي في مهامي المتعلقة بملف PDF؟

ج: يوفر هذا البرنامج التعليمي إرشادات خطوة بخطوة وكود مصدر C# لاسترداد مرفق معين وحفظه من مستند PDF باستخدام Aspose.PDF لـ .NET.

#### س: ما هي خصائص المرفقات التي يمكنني الوصول إليها باستخدام هذا البرنامج التعليمي؟

ج: يمكنك الوصول إلى خصائص المرفق مثل الاسم والوصف ونوع MIME وتجزئة التحكم وتاريخ الإنشاء وتاريخ التعديل وحجم المرفق المحدد.

#### س: هل يمكنني تعديل الكود للحصول على مرفقات غير المرفق الأول؟

 ج: بالتأكيد، يمكنك ضبط الفهرس (على سبيل المثال،`pdfDocument.EmbeddedFiles[1]`) لاسترداد المرفقات بمؤشرات مختلفة داخل ملف PDF.

#### س: كيف يمكنني حفظ المرفق المسترد في ملف؟

ج: يوفر هذا البرنامج التعليمي رمزًا لاسترداد محتوى المرفق وحفظه في ملف نصي باسم محدد.

#### س: ما أهمية خاصية "التحقق من التجزئة" في المعلومات المرفقة؟

ج: تمثل خاصية "التحقق من التجزئة" قيمة تجزئة التحكم الخاصة بالمرفق، والتي يمكن استخدامها للتحقق من سلامة المرفق.

#### س: هل يمكنني توسيع هذه المعرفة لاستخراج المرفقات بمعايير محددة، مثل نوع الملف؟

ج: نعم، يمكنك تحسين التعليمات البرمجية لتصفية المرفقات بناءً على معايير محددة مثل نوع الملف أو خصائص أخرى.

#### س: كيف يعمل Aspose.PDF for .NET على تبسيط عملية استخراج المرفقات الفردية؟

ج: يوفر Aspose.PDF for .NET واجهة برمجة تطبيقات سهلة الاستخدام تسهل استخراج المرفقات ومعالجتها داخل مستندات PDF.

#### س: هل هذا البرنامج التعليمي مناسب لملفات PDF المحمية بكلمة مرور أيضًا؟

ج: نعم، يمكنك تكييف تقنيات مماثلة لاسترداد المرفقات الفردية من ملفات PDF المحمية بكلمة مرور باستخدام Aspose.PDF لـ .NET.
