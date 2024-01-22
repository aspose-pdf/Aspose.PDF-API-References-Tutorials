---
title: แท็กรูปภาพในรูปแบบ PDF ที่มีอยู่
linktitle: แท็กรูปภาพในรูปแบบ PDF ที่มีอยู่
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีมาร์กอัปรูปภาพใน PDF ที่มีอยู่ด้วย Aspose.PDF สำหรับ .NET คำแนะนำทีละขั้นตอนในการเพิ่มแท็กให้กับรูปภาพ
type: docs
weight: 210
url: /th/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
ในบทช่วยสอนโดยละเอียดนี้ เราจะแนะนำคุณเกี่ยวกับซอร์สโค้ด C# ที่ให้มาทีละขั้นตอนเพื่อมาร์กอัปรูปภาพใน PDF ที่มีอยู่โดยใช้ Aspose.PDF สำหรับ .NET ทำตามคำแนะนำด้านล่างเพื่อทำความเข้าใจวิธีเพิ่มแท็กให้กับรูปภาพในรูปแบบ PDF

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้กำหนดค่าสภาพแวดล้อมการพัฒนาของคุณเพื่อใช้ Aspose.PDF สำหรับ .NET ซึ่งรวมถึงการติดตั้งไลบรารี Aspose.PDF และการกำหนดค่าโปรเจ็กต์ของคุณเพื่ออ้างอิง

## ขั้นตอนที่ 2: เปิดเอกสาร PDF ที่มีอยู่

ในขั้นตอนนี้ เราจะเปิดเอกสาร PDF ที่มีอยู่โดยใช้ Aspose.PDF

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// เส้นทางไฟล์อินพุตและเอาต์พุต
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// เปิดเอกสาร
Document document = new Document(inFile);
```

เราเปิดเอกสาร PDF ที่มีอยู่โดยใช้ Aspose.PDF

## ขั้นตอนที่ 3: รับเนื้อหาที่แท็กและองค์ประกอบโครงสร้างรูท

ตอนนี้เราจะได้รับเนื้อหาที่แท็กของเอกสาร PDF และองค์ประกอบโครงสร้างรูทที่เกี่ยวข้อง

```csharp
// รับเนื้อหาที่แท็กและองค์ประกอบโครงสร้างรูท
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

เราได้รับเนื้อหาที่แท็กของเอกสาร PDF และองค์ประกอบโครงสร้างรูทที่เกี่ยวข้อง

## ขั้นตอนที่ 4: การตั้งชื่อสำหรับเอกสาร PDF ที่แท็ก

ตอนนี้เรามาตั้งชื่อสำหรับเอกสาร PDF ที่แท็กแล้ว

```csharp
// กำหนดชื่อเรื่องสำหรับเอกสาร PDF ที่แท็ก
taggedContent.SetTitle("Document with images");
```

เราได้ตั้งชื่อสำหรับเอกสาร PDF ที่แท็กแล้ว

## ขั้นตอนที่ 5: กำหนดข้อความแสดงแทนและกรอบขอบให้กับรูปภาพ

ตอนนี้ สำหรับแต่ละองค์ประกอบรูปภาพ เราจะกำหนดข้อความแสดงแทนและกรอบขอบ

```csharp
foreach(FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
     // กำหนดข้อความแสดงแทนให้กับรูปภาพ
     figureElement.AlternativeText = "Alternative text for image (technique 2)";
     // สร้างและกำหนดขอบเขตกล่อง (bbox)
     StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
     bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
     StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
     figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

เราได้กำหนดข้อความแสดงแทนและกรอบล้อมรอบให้กับแต่ละองค์ประกอบรูปภาพในเอกสาร PDF

## ขั้นตอนที่ 6: ย้ายองค์ประกอบ Span ลงในย่อหน้า

ตอนนี้เรามาย้ายองค์ประกอบ Span ไปไว้ในย่อหน้ากัน

```csharp
// ย้ายองค์ประกอบ Span ไปที่ย่อหน้า (ค้นหาช่วงและย่อหน้าที่ไม่ถูกต้องใน TD แรก)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// ย้ายองค์ประกอบ Span ในย่อหน้า
spanElement.ChangeParentElement(paragraph);
```

เราย้ายองค์ประกอบ Span ไปยังย่อหน้าที่ระบุ

## ขั้นตอนที่ 7: บันทึกเอกสาร PDF ที่แก้ไข

ตอนนี้เราได้ทำการเปลี่ยนแปลงที่จำเป็นแล้ว เราจะบันทึกเอกสาร PDF ที่แก้ไขแล้ว

```csharp
// บันทึกเอกสาร PDF
document. Save(outFile);
```

เราบันทึกเอกสาร PDF ที่แก้ไขแล้วในไดเร็กทอรีที่ระบุ

### ตัวอย่างซอร์สโค้ดสำหรับแท็กรูปภาพในรูปแบบ PDF ที่มีอยู่โดยใช้ Aspose.PDF สำหรับ .NET 

```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// เปิดเอกสาร
Document document = new Document(inFile);

// รับเนื้อหาที่แท็กและองค์ประกอบโครงสร้างรูท
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;

// ตั้งชื่อสำหรับเอกสาร PDF ที่ติดแท็ก
taggedContent.SetTitle("Document with images");
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
	// ตั้งค่าข้อความแสดงแทนสำหรับรูปภาพ
	figureElement.AlternativeText = "Figure alternative text (technique 2)";
	// สร้างและตั้งค่าแอตทริบิวต์ BBox
	StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
	bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
	StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
	figureLayoutAttributes.SetAttribute(bboxAttribute);
}

// ย้ายองค์ประกอบ Span ลงในย่อหน้า (ค้นหาช่วงและย่อหน้าที่ไม่ถูกต้องใน TD แรก)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// ย้ายองค์ประกอบ Span ลงในย่อหน้า
spanElement.ChangeParentElement(paragraph);

// บันทึกเอกสาร
document.Save(outFile);

//ตรวจสอบการปฏิบัติตามข้อกำหนด PDF/UA สำหรับเอกสารออก
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีมาร์กอัปรูปภาพใน PDF ที่มีอยู่โดยใช้ Aspose.PDF สำหรับ .NET ตอนนี้คุณสามารถใช้ Aspose.PDF เพื่อเพิ่มแท็กและแก้ไขรูปภาพในเอกสาร PDF ของคุณได้

### คำถามที่พบบ่อย

#### ถาม: วัตถุประสงค์หลักของบทช่วยสอนนี้เกี่ยวกับการแท็กรูปภาพใน PDF ที่มีอยู่โดยใช้ Aspose.PDF สำหรับ .NET คืออะไร

ตอบ: เป้าหมายหลักของบทช่วยสอนนี้คือการแนะนำคุณตลอดกระบวนการมาร์กอัปรูปภาพภายในเอกสาร PDF ที่มีอยู่โดยใช้ Aspose.PDF สำหรับ .NET บทช่วยสอนให้คำแนะนำทีละขั้นตอนและตัวอย่างซอร์สโค้ด C# เพื่อช่วยให้คุณเข้าใจวิธีกำหนดข้อความแสดงแทนและกรอบขอบให้กับรูปภาพ ย้ายองค์ประกอบภายในเอกสาร และเพิ่มแท็กให้กับรูปภาพ

#### ถาม: ข้อกำหนดเบื้องต้นสำหรับการติดตามบทช่วยสอนนี้เกี่ยวกับการแท็กรูปภาพใน PDF โดยใช้ Aspose.PDF สำหรับ .NET คืออะไร

ตอบ: ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนาของคุณเพื่อใช้ Aspose.PDF สำหรับ .NET สิ่งนี้เกี่ยวข้องกับการติดตั้งไลบรารี Aspose.PDF และการกำหนดค่าโปรเจ็กต์ของคุณเพื่ออ้างอิง

#### ถาม: ฉันจะเปิดเอกสาร PDF ที่มีอยู่และเข้าถึงเนื้อหาที่แท็กโดยใช้ Aspose.PDF สำหรับ .NET ได้อย่างไร

ตอบ: บทช่วยสอนนี้มีตัวอย่างซอร์สโค้ด C# ที่สาธิตวิธีเปิดเอกสาร PDF ที่มีอยู่โดยใช้ Aspose.PDF สำหรับ .NET และเข้าถึงเนื้อหาที่แท็กเพื่อการจัดการเพิ่มเติม

#### ถาม: จุดประสงค์ของการกำหนดข้อความแสดงแทนและกรอบขอบให้กับรูปภาพในเอกสาร PDF คืออะไร

ตอบ: การกำหนดข้อความแสดงแทนและกรอบขอบให้กับรูปภาพจะช่วยเพิ่มความสามารถในการเข้าถึงโดยการให้ข้อความอธิบายสำหรับรูปภาพ และกำหนดเค้าโครงและตำแหน่งภายในเอกสาร ข้อมูลนี้มีความสำคัญสำหรับโปรแกรมอ่านหน้าจอและเทคโนโลยีช่วยเหลืออื่นๆ

#### ถาม: ฉันจะตั้งชื่อเอกสาร PDF ที่แท็กโดยใช้ Aspose.PDF สำหรับ .NET ได้อย่างไร

ตอบ: บทช่วยสอนประกอบด้วยตัวอย่างซอร์สโค้ด C# ที่แสดงวิธีตั้งชื่อสำหรับเอกสาร PDF ที่แท็กโดยใช้ Aspose.PDF สำหรับ .NET

#### ถาม: กระบวนการย้ายองค์ประกอบภายในเอกสาร PDF เกี่ยวข้องกับอะไรบ้าง

ตอบ: การย้ายองค์ประกอบภายในเอกสาร PDF เกี่ยวข้องกับการเปลี่ยนองค์ประกอบหลักขององค์ประกอบเฉพาะ ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีย้ายองค์ประกอบ Span ไปยังองค์ประกอบย่อหน้าที่ระบุภายในตาราง

#### ถาม: ฉันจะบันทึกเอกสาร PDF ที่แก้ไขแล้วได้อย่างไรหลังจากเพิ่มแท็กและแก้ไขรูปภาพแล้ว

 ตอบ: เมื่อคุณเพิ่มแท็ก กำหนดข้อความแสดงแทน ตั้งกรอบขอบเขต และแก้ไขเอกสาร PDF แล้ว คุณสามารถใช้ตัวอย่างซอร์สโค้ด C# ที่ให้มาเพื่อบันทึกเอกสาร PDF ที่แก้ไขแล้วโดยใช้`Save()` วิธี.

#### ถาม: จุดประสงค์ของซอร์สโค้ดตัวอย่างที่ให้ไว้ในบทช่วยสอนคืออะไร

ตอบ: ซอร์สโค้ดตัวอย่างทำหน้าที่เป็นข้อมูลอ้างอิงในทางปฏิบัติสำหรับการนำการแท็กและการจัดการรูปภาพไปใช้โดยใช้ Aspose.PDF สำหรับ .NET คุณสามารถใช้โค้ดนี้เป็นจุดเริ่มต้นและแก้ไขให้เหมาะกับความต้องการเฉพาะของคุณได้

#### ถาม: ฉันสามารถใช้เทคนิคเหล่านี้กับองค์ประกอบประเภทอื่นๆ ในเอกสาร PDF ไม่ใช่แค่รูปภาพได้หรือไม่

ตอบ: ได้ เทคนิคที่สาธิตในบทช่วยสอนนี้สามารถปรับให้ทำงานกับองค์ประกอบประเภทต่างๆ ภายในเอกสาร PDF ได้ คุณสามารถใช้หลักการที่คล้ายกันในการแท็กและจัดการองค์ประกอบอื่นๆ เช่น ข้อความ ตาราง และอื่นๆ

#### ถาม: ฉันจะตรวจสอบการปฏิบัติตามข้อกำหนด PDF/UA ของเอกสาร PDF ที่แก้ไขได้อย่างไร

 ตอบ: บทช่วยสอนนี้ให้ตัวอย่างซอร์สโค้ด C# ที่แสดงวิธีการตรวจสอบการปฏิบัติตามข้อกำหนด PDF/UA ของเอกสาร PDF ที่แก้ไขแล้วโดยใช้`Validate()` วิธีการและสร้างรายงาน XML

#### ถาม: Aspose.PDF สำหรับ .NET มีคุณสมบัติอื่นใดอีกบ้างสำหรับการทำงานกับเอกสาร PDF

ตอบ: Aspose.PDF สำหรับ .NET นำเสนอคุณสมบัติที่หลากหลายสำหรับการทำงานกับเอกสาร PDF รวมถึงการจัดการข้อความ การแทรกรูปภาพ การสร้างตาราง การจัดการฟิลด์แบบฟอร์ม ลายเซ็นดิจิทัล คำอธิบายประกอบ และอื่นๆ อีกมากมาย ศึกษาเอกสารและแหล่งข้อมูลอย่างเป็นทางการเพื่อการสำรวจเพิ่มเติม