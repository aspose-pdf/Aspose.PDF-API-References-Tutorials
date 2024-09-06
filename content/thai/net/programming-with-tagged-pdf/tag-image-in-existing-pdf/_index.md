---
title: แท็กภาพใน PDF ที่มีอยู่
linktitle: แท็กภาพใน PDF ที่มีอยู่
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีการทำเครื่องหมายภาพใน PDF ที่มีอยู่ด้วย Aspose.PDF สำหรับ .NET คำแนะนำทีละขั้นตอนในการเพิ่มแท็กให้กับรูปภาพ
type: docs
weight: 210
url: /th/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
ในบทช่วยสอนโดยละเอียดนี้ เราจะแนะนำคุณทีละขั้นตอนเกี่ยวกับโค้ดต้นฉบับ C# ที่ให้มาเพื่อทำเครื่องหมายภาพใน PDF ที่มีอยู่โดยใช้ Aspose.PDF สำหรับ .NET ปฏิบัติตามคำแนะนำด้านล่างเพื่อทำความเข้าใจวิธีการเพิ่มแท็กให้กับภาพใน PDF

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม

ก่อนเริ่มต้น โปรดแน่ใจว่าคุณได้กำหนดค่าสภาพแวดล้อมการพัฒนาของคุณให้ใช้ Aspose.PDF สำหรับ .NET แล้ว ซึ่งรวมถึงการติดตั้งไลบรารี Aspose.PDF และกำหนดค่าโปรเจ็กต์ของคุณเพื่ออ้างอิงไลบรารีดังกล่าว

## ขั้นตอนที่ 2: เปิดเอกสาร PDF ที่มีอยู่

ในขั้นตอนนี้เราจะเปิดเอกสาร PDF ที่มีอยู่โดยใช้ Aspose.PDF

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// เส้นทางไฟล์อินพุตและเอาท์พุต
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// เปิดเอกสาร
Document document = new Document(inFile);
```

เราเปิดเอกสาร PDF ที่มีอยู่โดยใช้ Aspose.PDF

## ขั้นตอนที่ 3: รับเนื้อหาที่แท็กและองค์ประกอบโครงสร้างราก

ตอนนี้เราจะได้รับเนื้อหาที่แท็กของเอกสาร PDF และองค์ประกอบโครงสร้างรากที่สอดคล้องกัน

```csharp
// รับเนื้อหาที่แท็กและองค์ประกอบโครงสร้างราก
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

เราได้รับเนื้อหาที่แท็กของเอกสาร PDF และองค์ประกอบโครงสร้างรากที่สอดคล้องกัน

## ขั้นตอนที่ 4: ตั้งชื่อเรื่องให้กับเอกสาร PDF ที่ถูกแท็ก

ต่อไปเรามาตั้งชื่อให้กับเอกสาร PDF ที่ถูกแท็กกัน

```csharp
// กำหนดชื่อเรื่องสำหรับเอกสาร PDF ที่ถูกแท็ก
taggedContent.SetTitle("Document with images");
```

เราได้ตั้งชื่อเรื่องให้กับเอกสาร PDF ที่ถูกแท็กแล้ว

## ขั้นตอนที่ 5: กำหนดข้อความอื่นและกรอบขอบเขตให้กับรูปภาพ

ตอนนี้ สำหรับองค์ประกอบภาพแต่ละภาพ เราจะกำหนดข้อความ alt และกล่องขอบเขต

```csharp
foreach(FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
     // กำหนดข้อความทางเลือกให้กับรูปภาพ
     figureElement.AlternativeText = "Alternative text for image (technique 2)";
     // สร้างและกำหนดขอบเขตกล่อง (bbox)
     StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
     bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
     StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
     figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

เราได้กำหนดข้อความอื่นและกล่องขอบเขตให้กับองค์ประกอบรูปภาพแต่ละองค์ประกอบในเอกสาร PDF

## ขั้นตอนที่ 6: การย้ายองค์ประกอบ Span ไปยังย่อหน้า

ตอนนี้เรามาย้ายองค์ประกอบ Span ไปที่ย่อหน้ากัน

```csharp
// ย้ายองค์ประกอบ Span เข้าไปในย่อหน้า (ค้นหา Span และย่อหน้าที่ไม่ถูกต้องใน TD แรก)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// ย้ายองค์ประกอบช่วงในย่อหน้า
spanElement.ChangeParentElement(paragraph);
```

เราได้ย้ายองค์ประกอบ Span ไปยังย่อหน้าที่ระบุ

## ขั้นตอนที่ 7: บันทึกเอกสาร PDF ที่แก้ไขแล้ว

ตอนนี้เราได้ทำการเปลี่ยนแปลงที่จำเป็นแล้ว เราจะบันทึกเอกสาร PDF ที่แก้ไขแล้ว

```csharp
// บันทึกเอกสาร PDF
document. Save(outFile);
```

เราบันทึกเอกสาร PDF ที่แก้ไขแล้วในไดเร็กทอรีที่ระบุ

### ตัวอย่างโค้ดที่มาสำหรับแท็กรูปภาพใน PDF ที่มีอยู่โดยใช้ Aspose.PDF สำหรับ .NET 

```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// เปิดเอกสาร
Document document = new Document(inFile);

// รับเนื้อหาที่ถูกแท็กและองค์ประกอบโครงสร้างราก
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;

// ตั้งชื่อให้กับเอกสาร PDF ที่ถูกแท็ก
taggedContent.SetTitle("Document with images");
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
	// ตั้งค่าข้อความทางเลือกสำหรับรูปภาพ
	figureElement.AlternativeText = "Figure alternative text (technique 2)";
	// สร้างและตั้งค่าแอตทริบิวต์ BBox
	StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
	bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
	StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
	figureLayoutAttributes.SetAttribute(bboxAttribute);
}

// ย้ายองค์ประกอบช่วงไปยังย่อหน้า (ค้นหาช่วงและย่อหน้าที่ไม่ถูกต้องใน TD แรก)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// ย้ายองค์ประกอบช่วงไปยังย่อหน้า
spanElement.ChangeParentElement(paragraph);

// บันทึกเอกสาร
document.Save(outFile);

//ตรวจสอบการปฏิบัติตาม PDF/UA สำหรับเอกสารของเรา
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีการทำเครื่องหมายรูปภาพใน PDF ที่มีอยู่โดยใช้ Aspose.PDF สำหรับ .NET ตอนนี้คุณสามารถใช้ Aspose.PDF เพื่อเพิ่มแท็กและแก้ไขรูปภาพในเอกสาร PDF ของคุณได้แล้ว

### คำถามที่พบบ่อย

#### ถาม: วัตถุประสงค์หลักของบทช่วยสอนนี้ในการแท็กรูปภาพใน PDF ที่มีอยู่โดยใช้ Aspose.PDF สำหรับ .NET คืออะไร

A: เป้าหมายหลักของบทช่วยสอนนี้คือเพื่อแนะนำคุณตลอดกระบวนการทำเครื่องหมายภาพในเอกสาร PDF ที่มีอยู่โดยใช้ Aspose.PDF สำหรับ .NET บทช่วยสอนนี้ให้คำแนะนำทีละขั้นตอนและตัวอย่างโค้ดต้นฉบับ C# เพื่อช่วยให้คุณเข้าใจวิธีการกำหนดข้อความทางเลือกและกรอบล้อมรอบให้กับภาพ การย้ายองค์ประกอบภายในเอกสาร และเพิ่มแท็กให้กับภาพ

#### ถาม: ข้อกำหนดเบื้องต้นสำหรับการปฏิบัติตามบทช่วยสอนนี้เกี่ยวกับการแท็กรูปภาพใน PDF โดยใช้ Aspose.PDF สำหรับ .NET มีอะไรบ้าง

A: ก่อนเริ่มต้น ให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนาของคุณเพื่อใช้ Aspose.PDF สำหรับ .NET แล้ว ซึ่งเกี่ยวข้องกับการติดตั้งไลบรารี Aspose.PDF และกำหนดค่าโปรเจ็กต์ของคุณเพื่ออ้างอิงไลบรารีดังกล่าว

#### ถาม: ฉันจะเปิดเอกสาร PDF ที่มีอยู่และเข้าถึงเนื้อหาที่แท็กโดยใช้ Aspose.PDF สำหรับ .NET ได้อย่างไร

A: บทช่วยสอนนี้มีตัวอย่างโค้ดต้นฉบับ C# ที่สาธิตวิธีการเปิดเอกสาร PDF ที่มีอยู่โดยใช้ Aspose.PDF สำหรับ .NET และเข้าถึงเนื้อหาที่มีแท็กเพื่อการจัดการเพิ่มเติม

#### ถาม: จุดประสงค์ของการกำหนดข้อความทางเลือกและกรอบล้อมรอบให้กับรูปภาพในเอกสาร PDF คืออะไร

ก: การกำหนดข้อความทางเลือกและกรอบล้อมรอบรูปภาพจะช่วยเพิ่มการเข้าถึงได้ด้วยการใส่ข้อความบรรยายรูปภาพและกำหนดเค้าโครงและตำแหน่งภายในเอกสาร ข้อมูลนี้มีความสำคัญอย่างยิ่งสำหรับโปรแกรมอ่านหน้าจอและเทคโนโลยีช่วยเหลืออื่นๆ

#### ถาม: ฉันจะตั้งชื่อเรื่องให้กับเอกสาร PDF ที่ถูกแท็กโดยใช้ Aspose.PDF สำหรับ .NET ได้อย่างไร

A: บทช่วยสอนนี้ประกอบด้วยตัวอย่างโค้ดต้นฉบับ C# ที่แสดงวิธีตั้งชื่อเรื่องให้กับเอกสาร PDF ที่มีแท็กโดยใช้ Aspose.PDF สำหรับ .NET

#### ถาม: กระบวนการย้ายองค์ประกอบภายในเอกสาร PDF เกี่ยวข้องกับอะไรบ้าง

A: การย้ายองค์ประกอบภายในเอกสาร PDF เกี่ยวข้องกับการเปลี่ยนแปลงองค์ประกอบหลักขององค์ประกอบเฉพาะ ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีการย้ายองค์ประกอบ Span ไปยังองค์ประกอบ Paragraph ที่ระบุภายในตาราง

#### ถาม: ฉันจะบันทึกเอกสาร PDF ที่แก้ไขแล้วหลังจากเพิ่มแท็กและแก้ไขรูปภาพได้อย่างไร

 A: เมื่อคุณเพิ่มแท็ก กำหนดข้อความทางเลือก ตั้งค่ากรอบขอบเขต และแก้ไขเอกสาร PDF แล้ว คุณสามารถใช้ตัวอย่างโค้ดต้นฉบับ C# ที่ให้มาเพื่อบันทึกเอกสาร PDF ที่แก้ไขแล้วโดยใช้`Save()` วิธี.

#### ถาม: จุดประสงค์ของโค้ดตัวอย่างที่ให้ไว้ในบทช่วยสอนคืออะไร

A: โค้ดตัวอย่างนี้ใช้เป็นข้อมูลอ้างอิงในทางปฏิบัติสำหรับการแท็กและจัดการรูปภาพโดยใช้ Aspose.PDF สำหรับ .NET คุณสามารถใช้โค้ดนี้เป็นจุดเริ่มต้นและปรับเปลี่ยนให้เหมาะกับความต้องการเฉพาะของคุณได้

#### ถาม: ฉันสามารถนำเทคนิคเหล่านี้ไปใช้กับองค์ประกอบประเภทอื่นในเอกสาร PDF ไม่ใช่แค่รูปภาพเท่านั้นได้หรือไม่

A: ใช่ เทคนิคที่สาธิตในบทช่วยสอนนี้สามารถปรับให้ใช้กับองค์ประกอบต่างๆ ในเอกสาร PDF ได้ คุณสามารถใช้หลักการเดียวกันนี้ในการแท็กและจัดการองค์ประกอบอื่นๆ เช่น ข้อความ ตาราง และอื่นๆ

#### ถาม: ฉันจะตรวจสอบความสอดคล้องของ PDF/UA ของเอกสาร PDF ที่แก้ไขได้อย่างไร

 A: บทช่วยสอนนี้มีตัวอย่างโค้ดต้นฉบับ C# ที่แสดงวิธีการตรวจสอบความสอดคล้องของ PDF/UA ของเอกสาร PDF ที่แก้ไขโดยใช้`Validate()` วิธีการและการสร้างรายงาน XML

#### ถาม: Aspose.PDF สำหรับ .NET มีฟีเจอร์อื่นๆ อะไรอีกบ้างสำหรับการทำงานกับเอกสาร PDF

A: Aspose.PDF สำหรับ .NET นำเสนอฟีเจอร์มากมายสำหรับการทำงานกับเอกสาร PDF รวมถึงการจัดการข้อความ การแทรกภาพ การสร้างตาราง การจัดการฟิลด์ฟอร์ม ลายเซ็นดิจิทัล คำอธิบายประกอบ และอื่นๆ อีกมากมาย โปรดดูเอกสารและทรัพยากรอย่างเป็นทางการเพื่อศึกษาเพิ่มเติม