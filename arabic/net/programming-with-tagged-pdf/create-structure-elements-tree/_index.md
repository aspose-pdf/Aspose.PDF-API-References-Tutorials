---
title: إنشاء شجرة عناصر الهيكل
linktitle: إنشاء شجرة عناصر الهيكل
second_title: Aspose.PDF لمرجع .NET API
description: قم بإنشاء هيكل لعناصر الشجرة باستخدام Aspose.PDF لـ .NET. دليل خطوة بخطوة لإنشاء مستند PDF منظم.
type: docs
weight: 70
url: /ar/net/programming-with-tagged-pdf/create-structure-elements-tree/
---
في هذا الدليل المفصل خطوة بخطوة ، سنشرح الكود المصدري في C # لإنشاء هيكل لعناصر الشجرة باستخدام Aspose.PDF for .NET. سنوضح لك كيفية إنشاء مستند PDF بعناصر منظمة وكيفية تنظيمها بشكل هرمي. يؤدي استخدام مكتبة Aspose.PDF إلى تبسيط معالجة عناصر PDF بشكل كبير ويوفر وظائف متقدمة للعمل مع المستندات المنظمة.

## الخطوة الأولى: تهيئة البيئة
قبل أن تبدأ ، تأكد من إعداد بيئة التطوير الخاصة بك باستخدام Aspose.PDF for .NET. تأكد أيضًا من تعيين المسار إلى دليل المستندات في ملف`dataDir` عامل.

## الخطوة 2: إنشاء مستند PDF
 للبدء ، سننشئ مستند PDF جديدًا باستخدام ملف`Document` فئة مقدمة من Aspose.PDF. هذا هو رمز هذه الخطوة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بإنشاء مستند PDF
Document document = new Document();
```

## الخطوة 3: الحصول على المحتوى للعمل مع TaggedPdf
 تسمح مكتبة Aspose.PDF بالعمل مع مستندات PDF المهيكلة باستخدام مفهوم PDF ذي العلامات. لهذا ، نحتاج إلى الحصول على مرجع لعنصر المحتوى الموسوم باستخدام المستند`TaggedContent` ملكية. هذا هو رمز هذه الخطوة:

```csharp
// احصل على محتوى للعمل مع TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;
```

## الخطوة 4: حدد عنوان المستند ولغته
 قبل أن نبدأ في إنشاء بنية العناصر ، نحتاج إلى تحديد عنوان المستند ولغته. يمكن القيام بذلك باستخدام ملف`SetTitle` و`SetLanguage` طرق`taggedContent` هدف. هذا هو رمز هذه الخطوة:

```csharp
// حدد عنوان المستند ولغته
taggedContent.SetTitle("Structured PDF Document");
taggedContent.SetLanguage("fr-FR");
```

## الخطوة 5: تكوين عناصر البنية المنطقية
الآن بعد أن أعددنا وثيقتنا وقمنا بتعيين العنوان واللغة ، يمكننا البدء في إنشاء عناصر بنية منطقية. سيتم تنظيم هذه العناصر بشكل هرمي لتشكيل شجرة الهيكل. هذا هو رمز هذه الخطوة:

```csharp
// الحصول على عنصر بنية الجذر (مستند)
StructureElement rootElement = taggedContent.RootElement;

// قم بإنشاء الهيكل المنطقي
SectElement sect1 = taggedContent.CreateSectElement();
rootElement.AppendChild(sect1);

SectElement sect2 = taggedContent.CreateSectElement();
rootElement.AppendChild(sect2);

DivElement div11 = taggedContent.CreateDivElement();
sect1.AppendChild(div11);

DivElement div12 = taggedContent.CreateDivElement();
sect1.AppendChild(div12);

ArtElement art21 = taggedContent.CreateArtElement();
sect2.AppendChild(art21);

ArtElement art22

  = taggedContent.CreateArtElement();
sect2.AppendChild(art22);

DivElement div211 = taggedContent.CreateDivElement();
art21.AppendChild(div211);

DivElement div212 = taggedContent.CreateDivElement();
art21.AppendChild(div212);

DivElement div221 = taggedContent.CreateDivElement();
art22.AppendChild(div221);

DivElement div222 = taggedContent.CreateDivElement();
art22.AppendChild(div222);

SectElement sect3 = taggedContent.CreateSectElement();
rootElement.AppendChild(sect3);

DivElement div31 = taggedContent.CreateDivElement();
sect3.AppendChild(div31);
```

## الخطوة 6: حفظ مستند PDF الذي تم وضع علامة عليه
 بمجرد إنشاء بنية العنصر ، يمكننا حفظ مستند PDF. استخدم ال`Save` طريقة`document` لتحديد مسار واسم ملف PDF المراد حفظه. هذا هو رمز هذه الخطوة:

```csharp
// احفظ مستند PDF بعلامات
document.Save(dataDir + "StructureElementsTree.pdf");
```

### نموذج التعليمات البرمجية المصدر لـ Create Structure Elements Tree باستخدام Aspose.PDF for .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// إنشاء مستند PDF
Document document = new Document();
// الحصول على محتوى للعمل مع TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;
// تعيين العنوان واللغة للوثيقة
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
// الحصول على عنصر بنية الجذر (مستند)
StructureElement rootElement = taggedContent.RootElement;
// إنشاء بنية منطقية
SectElement sect1 = taggedContent.CreateSectElement();
rootElement.AppendChild(sect1);
SectElement sect2 = taggedContent.CreateSectElement();
rootElement.AppendChild(sect2);
DivElement div11 = taggedContent.CreateDivElement();
sect1.AppendChild(div11);
DivElement div12 = taggedContent.CreateDivElement();
sect1.AppendChild(div12);
ArtElement art21 = taggedContent.CreateArtElement();
sect2.AppendChild(art21);
ArtElement art22 = taggedContent.CreateArtElement();
sect2.AppendChild(art22);
DivElement div211 = taggedContent.CreateDivElement();
art21.AppendChild(div211);
DivElement div212 = taggedContent.CreateDivElement();
art21.AppendChild(div212);
DivElement div221 = taggedContent.CreateDivElement();
art22.AppendChild(div221);
DivElement div222 = taggedContent.CreateDivElement();
art22.AppendChild(div222);
SectElement sect3 = taggedContent.CreateSectElement();
rootElement.AppendChild(sect3);
DivElement div31 = taggedContent.CreateDivElement();
sect3.AppendChild(div31);
// حفظ وثيقة PDF الموسومة
document.Save(dataDir + "StructureElementsTree.pdf");

```

## خاتمة
لقد تعلمت كيفية إنشاء هيكل لعناصر الشجرة باستخدام Aspose.PDF لـ .NET. يوضح لك هذا الدليل الخطوات اللازمة لإعداد مستند PDF وإنشاء عناصر بنية منطقية وحفظ المستند النهائي. باستخدام Aspose.PDF ، يمكنك بسهولة معالجة عناصر PDF وإنشاء مستندات منظمة.
