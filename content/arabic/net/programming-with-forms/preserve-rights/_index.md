---
title: حفظ الحقوق
linktitle: حفظ الحقوق
second_title: Aspose.PDF لمرجع .NET API
description: حافظ على حقوق النموذج في مستندات PDF الخاصة بك باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 210
url: /ar/net/programming-with-forms/preserve-rights/
---
سنوضح لك في هذا البرنامج التعليمي كيفية الحفاظ على حقوق النموذج في مستند PDF باستخدام Aspose.PDF لـ .NET. سنشرح لك كود مصدر C# خطوة بخطوة لإرشادك خلال هذه العملية.

## الخطوة 1: التحضير

تأكد من استيراد المكتبات الضرورية وتعيين المسار إلى دليل المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: افتح المستند

 افتح مستند PDF المصدر باستخدام ملف`FileStream` مع إذن القراءة والكتابة:

```csharp
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
```

## الخطوة 3: تحرير حقول النموذج

قم بمراجعة جميع حقول النموذج في المستند وقم بإجراء التغييرات اللازمة. في هذا المثال، نقوم بتغيير قيمة حقل النموذج الذي يحتوي على "A1" في اسمه:

```csharp
foreach(Field formField in pdfDocument.Form)
{
if (formField.FullName.Contains("A1"))
{
TextBoxField textBoxField = formField as TextBoxField;
textBoxField.Value = "Testing";
}
}
```

## الخطوة 4: احفظ المستند المحدث

احفظ مستند PDF المعدل:

```csharp
pdfDocument.Save();
```

##  الخطوة 5: أغلق`FileStream`

 لا تنسى إغلاق`FileStream` الكائن عند الانتهاء:

```csharp
fs. Close();
```

### نموذج التعليمات البرمجية المصدر للحفاظ على الحقوق باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// اقرأ نموذج PDF المصدر باستخدام FileAccess للقراءة والكتابة.
// نحن بحاجة إلى إذن القراءة والكتابة لأنه بعد التعديل،
// نحتاج إلى حفظ المحتويات المحدثة في نفس المستند/الملف.
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
// إنشاء مثيل للمستند
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
// الحصول على القيم من كافة الحقول
foreach (Field formField in pdfDocument.Form)
{
	// إذا كان الاسم الكامل للحقل يحتوي على A1، فقم بإجراء العملية
	if (formField.FullName.Contains("A1"))
	{
		// تحويل حقل النموذج إلى TextBox
		TextBoxField textBoxField = formField as TextBoxField;
		// تعديل قيمة الحقل
		textBoxField.Value = "Testing";
	}
}
// احفظ المستند المحدث في حفظ FileStream
pdfDocument.Save();
// قم بإغلاق كائن تدفق الملفات
fs.Close();
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية الحفاظ على حقوق النموذج في مستند PDF باستخدام Aspose.PDF لـ .NET. باتباع هذه الخطوات، يمكنك بسهولة الوصول إلى حقول النموذج وإجراء تغييرات محددة مع الحفاظ على أذونات الوصول والكتابة.


### الأسئلة الشائعة

#### س: هل يمكنني الحفاظ على حقوق حقول نموذج معينة دون التأثير على الحقول الأخرى في مستند PDF؟

 ج: نعم، وذلك باستخدام`FullName` خاصية حقول النموذج، يمكنك استهداف حقول نموذج معينة للحفظ مع ترك الحقول الأخرى دون أن تتأثر.

#### س: هل يمكنني الحفاظ على حقوق النموذج في مستند PDF محمي بكلمة مرور؟

ج: نعم، يسمح لك Aspose.PDF for .NET بالحفاظ على حقوق النموذج حتى في مستندات PDF المحمية بكلمة مرور، طالما قمت بتوفير كلمة المرور الصحيحة للوصول إلى الملف وتعديله.

#### س: ماذا يحدث إذا حاولت تعديل حقول النموذج دون حقوق الوصول المناسبة؟

ج: إذا حاولت تعديل حقول النموذج دون حقوق الوصول المناسبة، فلن يتم حفظ التغييرات في مستند PDF، وقد تتلقى استثناءً أو رسالة خطأ.

#### س: هل يتوافق Aspose.PDF for .NET مع كافة إصدارات .NET Framework؟

ج: نعم، Aspose.PDF for .NET متوافق مع كافة إصدارات .NET Framework، بما في ذلك .NET Core و.NET Standard.

#### س: هل يمكنني الحفاظ على حقوق النموذج في مستند PDF برمجياً بلغات برمجة أخرى إلى جانب C#؟

ج: نعم، يدعم Aspose.PDF for .NET لغات البرمجة المختلفة، مثل VB.NET وASP.NET، بالإضافة إلى C#.