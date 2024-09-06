---
title: สร้างองค์ประกอบโครงสร้าง
linktitle: สร้างองค์ประกอบโครงสร้าง
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีใช้ Aspose.PDF สำหรับ .NET เพื่อสร้างองค์ประกอบโครงสร้างในเอกสาร PDF ที่มีแท็ก
type: docs
weight: 60
url: /th/net/programming-with-tagged-pdf/create-structure-elements/
---
โค้ดต้นฉบับ C# ต่อไปนี้ใช้ Aspose.PDF สำหรับ .NET เพื่อสร้างองค์ประกอบโครงสร้าง ทำตามขั้นตอนด้านล่างเพื่อทำความเข้าใจวิธีการทำงานของโค้ด

## ขั้นตอนที่ 1: นำเข้าไลบรารีที่จำเป็น

```csharp
using Aspose.Pdf;
```

## ขั้นตอนที่ 2: กำหนดไดเรกทอรีของเอกสารของคุณ

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

อย่าลืมระบุเส้นทางที่ถูกต้องไปยังไดเร็กทอรีเอกสารของคุณ

## ขั้นตอนที่ 3: สร้างเอกสาร PDF

```csharp
Document document = new Document();
```

เราสร้างวัตถุเอกสารใหม่ที่แสดงเอกสาร PDF

## ขั้นตอนที่ 4: รับเนื้อหาให้ทำงานกับ TaggedPdf

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

เราเรียกค้นเนื้อหาที่ถูกแท็กของเอกสาร PDF ซึ่งจะทำให้เราสามารถจัดการองค์ประกอบโครงสร้างได้

## ขั้นตอนที่ 5: ตั้งชื่อเอกสารและภาษา

```csharp
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

เรากำหนดชื่อและภาษาของเอกสาร PDF ที่ถูกแท็ก ซึ่งช่วยให้เข้าถึงเอกสารได้ง่ายขึ้น

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

เราสร้างองค์ประกอบโครงสร้างที่แตกต่างกันเพื่อการจัดกลุ่มเนื้อหาในเอกสาร PDF

## ขั้นตอนที่ 7: สร้างองค์ประกอบโครงสร้างย่อหน้า

```csharp
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
```

เราสร้างองค์ประกอบโครงสร้างระดับบล็อกสำหรับย่อหน้าและหัวเรื่อง ตัวอย่างด้านบนแสดงการสร้างส่วนหัวระดับ 1

## ขั้นตอนที่ 8: สร้างองค์ประกอบโครงสร้างระดับอินไลน์

```csharp
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
```

เราสร้างองค์ประกอบโครงสร้างระดับอินไลน์สำหรับส่วนข้อความที่ปรากฏภายในย่อหน้าหรือหัวเรื่อง

## ขั้นตอนที่ 9: สร้างองค์ประกอบโครงสร้างงานศิลปะ

```csharp
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
```

เราสร้างองค์ประกอบโครงสร้างสำหรับภาพประกอบและสูตรทางคณิตศาสตร์ที่มีอยู่ในเอกสาร

## ขั้นตอนที่ 10: บันทึกเอกสาร PDF ที่ถูกแท็ก

```csharp
document.Save(dataDir + "StructureElements.pdf");
```

เราบันทึกเอกสาร PDF ที่ถูกแท็กด้วยองค์ประกอบโครงสร้างที่สร้างขึ้น

### ตัวอย่างโค้ดต้นฉบับสำหรับสร้างองค์ประกอบโครงสร้างโดยใช้ Aspose.PDF สำหรับ .NET 

```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// สร้างเอกสาร PDF
Document document = new Document();
// รับเนื้อหาสำหรับงานด้วย TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;
// ตั้งชื่อเรื่องและภาษาสำหรับ Documnet
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
// สร้างองค์ประกอบโครงสร้างข้อความแบบอินไลน์
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
// บันทึกเอกสาร PDF ที่ถูกแท็ก
document.Save(dataDir + "StructureElements.pdf");

```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีใช้ Aspose.PDF สำหรับ .NET เพื่อสร้างองค์ประกอบโครงสร้างในเอกสาร PDF ที่มีแท็ก องค์ประกอบโครงสร้างช่วยปรับปรุงการเข้าถึงเอกสารและจัดระเบียบเนื้อหาในลักษณะที่มีความหมาย ตอนนี้คุณสามารถใช้ความรู้เหล่านี้เพื่อสร้างเอกสาร PDF ที่มีโครงสร้างและนำทางได้ง่าย

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ในการสร้างองค์ประกอบโครงสร้างในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET คืออะไร

A: การสร้างองค์ประกอบโครงสร้างในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ช่วยเพิ่มการเข้าถึงและการจัดระเบียบเนื้อหาของเอกสาร องค์ประกอบโครงสร้างมอบโครงสร้างแบบลำดับชั้นที่ช่วยปรับปรุงการนำทาง ความหมาย และความเข้ากันได้กับเทคโนโลยีช่วยเหลือ

#### ถาม: โค้ด C# ที่ให้มาสร้างองค์ประกอบโครงสร้างในเอกสาร PDF ได้อย่างไร

A: ตัวอย่างโค้ดสาธิตวิธีการสร้างองค์ประกอบโครงสร้างประเภทต่างๆ รวมถึงองค์ประกอบการจัดกลุ่ม (เช่น ส่วนต่างๆ และ div) องค์ประกอบระดับบล็อก (เช่น ย่อหน้าและหัวเรื่อง) องค์ประกอบระดับอินไลน์ (สแปน คำพูด หมายเหตุ) และองค์ประกอบงานศิลป์ (เช่น รูปภาพและสูตร) องค์ประกอบโครงสร้างเหล่านี้ช่วยจัดระเบียบเนื้อหา

####  ถาม: เหตุใดจึงสำคัญที่ต้องตั้งชื่อเอกสารและภาษาโดยใช้`SetTitle` and `SetLanguage` methods?

 ก. ตั้งค่าชื่อเอกสารและภาษาโดยใช้`SetTitle` และ`SetLanguage`วิธีการดังกล่าวช่วยปรับปรุงการเข้าถึงและความหมายของเอกสาร หัวเรื่องจะอธิบายวัตถุประสงค์ของเอกสารโดยย่อ ในขณะที่แอตทริบิวต์ภาษาช่วยปรับปรุงการแสดงผลและการเข้าถึงเฉพาะภาษา

####  ถาม: การจัดกลุ่มองค์ประกอบต่างๆ เช่น`PartElement` and `SectElement`, contribute to the structure of the PDF document?

A: การจัดกลุ่มองค์ประกอบจะสร้างโครงสร้างแบบลำดับชั้นภายในเอกสาร PDF ช่วยให้คุณจัดระเบียบและจัดกลุ่มเนื้อหาที่เกี่ยวข้องได้อย่างมีตรรกะ ซึ่งจะช่วยเพิ่มประสิทธิภาพในการนำทางและให้โครงสร้างที่ชัดเจนแก่ผู้ใช้

#### ถาม: องค์ประกอบโครงสร้างระดับบล็อกและระดับอินไลน์คืออะไร และแตกต่างกันอย่างไร

A: องค์ประกอบโครงสร้างระดับบล็อกแสดงถึงเนื้อหาเป็นกลุ่มขนาดใหญ่ เช่น ย่อหน้าและหัวเรื่อง ในขณะที่องค์ประกอบระดับอินไลน์แสดงถึงส่วนของข้อความภายในย่อหน้าหรือหัวเรื่อง เช่น ช่วง คำพูด และหมายเหตุ องค์ประกอบเหล่านี้ช่วยกำหนดลำดับชั้นและความสัมพันธ์ของเนื้อหา

####  ถาม: งานศิลปะมีโครงสร้างองค์ประกอบต่างๆ อย่างไร เช่น`FigureElement` and `FormulaElement`, contribute to the document?

A: องค์ประกอบโครงสร้างงานศิลปะช่วยให้คุณสามารถเพิ่มภาพประกอบ รูปภาพ และสูตรคณิตศาสตร์ลงในเอกสารได้ โดยองค์ประกอบเหล่านี้ช่วยให้สามารถรวมเนื้อหาทางภาพและคณิตศาสตร์ได้อย่างมีโครงสร้าง

#### ถาม: ฉันสามารถใช้เทคนิคที่คล้ายคลึงกันเพื่อสร้างองค์ประกอบโครงสร้างประเภทอื่น เช่น รายการ ตาราง หรือคำอธิบายประกอบ ได้หรือไม่

A: ใช่ คุณสามารถใช้เทคนิคที่คล้ายกันเพื่อสร้างองค์ประกอบโครงสร้างประเภทอื่นๆ เช่น รายการ ตาราง คำอธิบายประกอบ การอ้างอิง และอื่นๆ อีกมากมาย Aspose.PDF มีวิธีการสร้างองค์ประกอบโครงสร้างให้เลือกใช้มากมาย

####  ถาม: การบันทึกเอกสาร PDF ที่ถูกแท็กโดยใช้`Save` method ensure the preservation of structure elements?

 ก. การ`Save` วิธีการนี้จะบันทึกเอกสาร PDF พร้อมกับองค์ประกอบโครงสร้างที่สร้างขึ้น โดยให้แน่ใจว่าโครงสร้างลำดับชั้นและความหมายของเอกสารได้รับการรักษาไว้สำหรับการเข้าถึงและการนำทาง

#### ถาม: องค์ประกอบโครงสร้างทำให้เอกสาร PDF มีประโยชน์อะไรบ้างในแง่ของการเข้าถึงและความเข้ากันได้กับเทคโนโลยีช่วยเหลือ

A: องค์ประกอบโครงสร้างช่วยเพิ่มการเข้าถึงโดยให้โครงสร้างและความหมายที่มีความหมายแก่เอกสาร ซึ่งช่วยให้เทคโนโลยีช่วยเหลือ เช่น โปรแกรมอ่านหน้าจอ สามารถตีความและถ่ายทอดเนื้อหาของเอกสารให้กับผู้ใช้ที่มีความทุพพลภาพได้อย่างมีประสิทธิภาพมากขึ้น

#### ถาม: ฉันจะปรับแต่งและรวมองค์ประกอบโครงสร้างประเภทต่างๆ เพิ่มเติมในเอกสาร PDF ได้อย่างไร

A: คุณสามารถรวมและปรับแต่งองค์ประกอบโครงสร้างโดยใช้เมธอดการสร้างที่เหมาะสมที่ Aspose.PDF จัดเตรียมไว้ให้ ทดลองใช้องค์ประกอบต่างๆ และคุณสมบัติขององค์ประกอบเหล่านั้นเพื่อสร้างเอกสาร PDF ที่มีโครงสร้างและจัดระเบียบที่ดี