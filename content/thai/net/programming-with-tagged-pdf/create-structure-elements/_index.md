---
title: สร้างองค์ประกอบโครงสร้าง
linktitle: สร้างองค์ประกอบโครงสร้าง
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีใช้ Aspose.PDF สำหรับ .NET เพื่อสร้างองค์ประกอบโครงสร้างในเอกสาร PDF ที่แท็ก
type: docs
weight: 60
url: /th/net/programming-with-tagged-pdf/create-structure-elements/
---
ซอร์สโค้ด C# ต่อไปนี้ใช้ Aspose.PDF สำหรับ .NET เพื่อสร้างองค์ประกอบโครงสร้าง ทำตามขั้นตอนด้านล่างเพื่อทำความเข้าใจวิธีการทำงานของโค้ด

## ขั้นตอนที่ 1: นำเข้าไลบรารีที่จำเป็น

```csharp
using Aspose.Pdf;
```

## ขั้นตอนที่ 2: กำหนดไดเร็กทอรีของเอกสารของคุณ

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

อย่าลืมระบุเส้นทางที่ถูกต้องไปยังไดเร็กทอรีเอกสารของคุณ

## ขั้นตอนที่ 3: สร้างเอกสาร PDF

```csharp
Document document = new Document();
```

เราสร้างวัตถุเอกสารใหม่ที่แสดงถึงเอกสาร PDF

## ขั้นตอนที่ 4: รับเนื้อหาเพื่อทำงานกับ TaggedPdf

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

เราดึงเนื้อหาที่แท็กของเอกสาร PDF สิ่งนี้จะทำให้เราสามารถจัดการองค์ประกอบโครงสร้างได้

## ขั้นตอนที่ 5: ตั้งชื่อเอกสารและภาษา

```csharp
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

เราตั้งชื่อและภาษาของเอกสาร PDF ที่แท็ก ซึ่งจะช่วยปรับปรุงการเข้าถึงเอกสาร

## ขั้นตอนที่ 6: สร้างองค์ประกอบการจัดกลุ่ม

```csharp
PartElement partElement = taggedContent.CreatePartElement();
ArtElement artElement = taggedContent.CreateArtElement();
SectElement sectElement = taggedContent.CreateSectElement();
DivElement divElement = taggedContent.CreateDivElement();
BlockQuoteElement blockQuoteElement = taggedContent.CreateBlockQuoteElement();
CaptionElement captionElement = taggedContent.CreateCaptionElement();
TOCElement tocElement = taggedContent.CreateTOCElement();
TOCIElement tociElement = taggedContent.CreateTOCIElement();
IndexElement indexElement = taggedContent.CreateIndexElement();
NonStructElement nonStructElement = taggedContent.CreateNonStructElement();
PrivateElement privateElement = taggedContent.CreatePrivateElement();
```

เราสร้างองค์ประกอบโครงสร้างที่แตกต่างกันสำหรับการจัดกลุ่มเนื้อหาในเอกสาร PDF

## ขั้นตอนที่ 7: สร้างองค์ประกอบโครงสร้างย่อหน้า

```csharp
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
```

เราสร้างองค์ประกอบโครงสร้างระดับบล็อกสำหรับย่อหน้าและส่วนหัว ตัวอย่างด้านบนแสดงการสร้างส่วนหัวระดับ 1

## ขั้นตอนที่ 8: สร้างองค์ประกอบโครงสร้างระดับอินไลน์

```csharp
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
```

เราสร้างองค์ประกอบโครงสร้างระดับอินไลน์สำหรับส่วนของข้อความที่ปรากฏภายในย่อหน้าหรือส่วนหัว

## ขั้นตอนที่ 9: สร้างองค์ประกอบโครงสร้างงานศิลปะ

```csharp
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
```

เราสร้างองค์ประกอบโครงสร้างสำหรับภาพประกอบและสูตรทางคณิตศาสตร์ที่มีอยู่ในเอกสาร

## ขั้นตอนที่ 10: บันทึกเอกสาร PDF ที่แท็ก

```csharp
document.Save(dataDir + "StructureElements.pdf");
```

เราบันทึกเอกสาร PDF ที่ติดแท็กด้วยองค์ประกอบโครงสร้างที่สร้างขึ้น

### ตัวอย่างซอร์สโค้ดสำหรับสร้างองค์ประกอบโครงสร้างโดยใช้ Aspose.PDF สำหรับ .NET 

```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// สร้างเอกสาร PDF
Document document = new Document();
// รับเนื้อหาสำหรับการทำงานกับ TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;
// ตั้งชื่อและภาษาสำหรับ Documnet
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
// สร้างองค์ประกอบการจัดกลุ่ม
PartElement partElement = taggedContent.CreatePartElement();
ArtElement artElement = taggedContent.CreateArtElement();
SectElement sectElement = taggedContent.CreateSectElement();
DivElement divElement = taggedContent.CreateDivElement();
BlockQuoteElement blockQuoteElement = taggedContent.CreateBlockQuoteElement();
CaptionElement captionElement = taggedContent.CreateCaptionElement();
TOCElement tocElement = taggedContent.CreateTOCElement();
TOCIElement tociElement = taggedContent.CreateTOCIElement();
IndexElement indexElement = taggedContent.CreateIndexElement();
NonStructElement nonStructElement = taggedContent.CreateNonStructElement();
PrivateElement privateElement = taggedContent.CreatePrivateElement();
// สร้างองค์ประกอบโครงสร้างระดับบล็อกข้อความ
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
// สร้างองค์ประกอบโครงสร้างระดับอินไลน์ข้อความ
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
// สร้างองค์ประกอบโครงสร้างภาพประกอบ
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
// วิธีการอยู่ระหว่างการพัฒนา
ListElement listElement = taggedContent.CreateListElement();
TableElement tableElement = taggedContent.CreateTableElement();
ReferenceElement referenceElement = taggedContent.CreateReferenceElement();
BibEntryElement bibEntryElement = taggedContent.CreateBibEntryElement();
CodeElement codeElement = taggedContent.CreateCodeElement();
LinkElement linkElement = taggedContent.CreateLinkElement();
AnnotElement annotElement = taggedContent.CreateAnnotElement();
RubyElement rubyElement = taggedContent.CreateRubyElement();
WarichuElement warichuElement = taggedContent.CreateWarichuElement();
FormElement formElement = taggedContent.CreateFormElement();
// บันทึกเอกสาร PDF ที่ติดแท็ก
document.Save(dataDir + "StructureElements.pdf");

```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีใช้ Aspose.PDF สำหรับ .NET เพื่อสร้างองค์ประกอบโครงสร้างในเอกสาร PDF ที่แท็ก องค์ประกอบโครงสร้างช่วยปรับปรุงการเข้าถึงเอกสารและจัดระเบียบเนื้อหาอย่างมีความหมาย ตอนนี้คุณสามารถใช้ความรู้นี้เพื่อสร้างเอกสาร PDF ที่มีโครงสร้างและใช้งานง่าย

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของการสร้างองค์ประกอบโครงสร้างในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET คืออะไร

ตอบ: การสร้างองค์ประกอบโครงสร้างในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ช่วยเพิ่มความสามารถในการเข้าถึงและการจัดระเบียบเนื้อหาของเอกสาร องค์ประกอบโครงสร้างมีโครงสร้างแบบลำดับชั้นที่ปรับปรุงการนำทาง อรรถศาสตร์ และความเข้ากันได้กับเทคโนโลยีช่วยเหลือ

#### ถาม: รหัส C# ที่ให้มาสร้างองค์ประกอบโครงสร้างในเอกสาร PDF ได้อย่างไร

ตอบ: ตัวอย่างโค้ดสาธิตวิธีการสร้างองค์ประกอบโครงสร้างประเภทต่างๆ รวมถึงองค์ประกอบการจัดกลุ่ม (เช่น ส่วน ส่วน และ div) องค์ประกอบระดับบล็อก (เช่น ย่อหน้าและส่วนหัว) องค์ประกอบระดับอินไลน์ (ช่วง เครื่องหมายคำพูด หมายเหตุ ) และองค์ประกอบอาร์ตเวิร์ก (เช่น ตัวเลขและสูตร) องค์ประกอบโครงสร้างเหล่านี้ช่วยจัดระเบียบเนื้อหา

####  ถาม: เหตุใดการตั้งชื่อและภาษาของเอกสารจึงมีความสำคัญโดยใช้นามสกุลไฟล์`SetTitle` and `SetLanguage` methods?

 ตอบ: การตั้งชื่อเอกสารและภาษาโดยใช้`SetTitle` และ`SetLanguage`วิธีการปรับปรุงการเข้าถึงเอกสารและความหมาย ชื่อเรื่องให้คำอธิบายโดยย่อเกี่ยวกับวัตถุประสงค์ของเอกสาร ในขณะที่แอตทริบิวต์ภาษาช่วยปรับปรุงการแสดงผลและการเข้าถึงเฉพาะภาษา

####  ถาม: การจัดกลุ่มองค์ประกอบต่างๆ เช่น`PartElement` and `SectElement`, contribute to the structure of the PDF document?

ตอบ: การจัดกลุ่มองค์ประกอบจะสร้างโครงสร้างแบบลำดับชั้นภายในเอกสาร PDF ซึ่งช่วยให้คุณสามารถจัดระเบียบและจัดกลุ่มเนื้อหาที่เกี่ยวข้องได้อย่างมีเหตุผล สิ่งนี้ช่วยปรับปรุงการนำทางและให้โครงสร้างที่ชัดเจนสำหรับผู้ใช้

#### ถาม: องค์ประกอบโครงสร้างระดับบล็อกและระดับอินไลน์คืออะไร และแตกต่างกันอย่างไร

ตอบ: องค์ประกอบโครงสร้างระดับบล็อกแสดงถึงบล็อกเนื้อหาที่ใหญ่กว่า เช่น ย่อหน้าและส่วนหัว ในขณะที่องค์ประกอบระดับอินไลน์แสดงส่วนของข้อความภายในย่อหน้าหรือส่วนหัว เช่น ช่วง เครื่องหมายคำพูด และหมายเหตุ ช่วยกำหนดลำดับชั้นและความสัมพันธ์ของเนื้อหา

####  ถาม: องค์ประกอบโครงสร้างงานศิลปะเป็นอย่างไร`FigureElement` and `FormulaElement`, contribute to the document?

ตอบ: องค์ประกอบโครงสร้างอาร์ตเวิร์คช่วยให้คุณสามารถเพิ่มภาพประกอบ ตัวเลข และสูตรทางคณิตศาสตร์ลงในเอกสารได้ พวกเขามีวิธีการที่มีโครงสร้างในการรวมเนื้อหาภาพและคณิตศาสตร์

#### ถาม: ฉันสามารถใช้เทคนิคที่คล้ายกันเพื่อสร้างองค์ประกอบโครงสร้างประเภทอื่นๆ เช่น รายการ ตาราง หรือคำอธิบายประกอบได้หรือไม่

ตอบ: ได้ คุณสามารถใช้เทคนิคที่คล้ายกันเพื่อสร้างองค์ประกอบโครงสร้างประเภทอื่นๆ เช่น รายการ ตาราง คำอธิบายประกอบ การอ้างอิง และอื่นๆ Aspose.PDF มีวิธีการสร้างองค์ประกอบโครงสร้างที่หลากหลาย

####  ถาม: บันทึกเอกสาร PDF ที่แท็กโดยใช้ไฟล์`Save` method ensure the preservation of structure elements?

 ตอบ:`Save` วิธีการบันทึกเอกสาร PDF พร้อมกับองค์ประกอบโครงสร้างที่สร้างขึ้น ทำให้มั่นใจได้ว่าโครงสร้างลำดับชั้นและความหมายของเอกสารจะถูกรักษาไว้สำหรับการเข้าถึงและการนำทาง

#### ถาม: องค์ประกอบโครงสร้างมีประโยชน์อะไรบ้างในเอกสาร PDF ในแง่ของการเข้าถึงและความเข้ากันได้กับเทคโนโลยีช่วยเหลือ

ตอบ: องค์ประกอบโครงสร้างช่วยเพิ่มความสามารถในการเข้าถึงโดยจัดเตรียมโครงสร้างและอรรถศาสตร์ที่มีความหมายให้กับเอกสาร ซึ่งช่วยให้เทคโนโลยีช่วยเหลือ เช่น โปรแกรมอ่านหน้าจอสามารถตีความและถ่ายทอดเนื้อหาของเอกสารแก่ผู้ใช้ที่มีความพิการได้อย่างมีประสิทธิภาพมากขึ้น

#### ถาม: ฉันจะปรับแต่งเพิ่มเติมและรวมองค์ประกอบโครงสร้างประเภทต่างๆ ในเอกสาร PDF ของฉันได้อย่างไร

ตอบ: คุณสามารถรวมและปรับแต่งองค์ประกอบโครงสร้างได้โดยใช้วิธีการสร้างที่เหมาะสมที่ Aspose.PDF มอบให้ ทดลองใช้องค์ประกอบและคุณสมบัติต่างๆ เพื่อสร้างเอกสาร PDF ที่มีโครงสร้างและจัดระเบียบอย่างดี