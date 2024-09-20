---
title: แท็กภาพใน PDF ที่มีอยู่
linktitle: แท็กภาพใน PDF ที่มีอยู่
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีแท็กภาพใน PDF ที่มีอยู่โดยใช้ Aspose.PDF สำหรับ .NET คำแนะนำทีละขั้นตอนเพื่อปรับปรุงการเข้าถึงโดยปฏิบัติตาม PDF/UA
type: docs
weight: 210
url: /th/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
## การแนะนำ

ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับวิธีการแท็กภาพใน PDF ที่มีอยู่โดยใช้ Aspose.PDF สำหรับ .NET เมื่ออ่านคู่มือนี้จบ คุณจะสามารถตั้งค่าข้อความทางเลือกสำหรับภาพ ปรับคุณลักษณะเค้าโครง และตรวจสอบให้แน่ใจว่า PDF ของคุณเป็นไปตามมาตรฐานการเข้าถึง

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มต้น มาดูสิ่งที่คุณต้องมีกันก่อน:

-  Aspose.PDF สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ดาวน์โหลดและติดตั้ง Aspose.PDF สำหรับ .NET เวอร์ชันล่าสุดแล้ว[ดาวน์โหลดที่นี่](https://releases.aspose.com/pdf/net/).
- .NET Framework: ตรวจสอบให้แน่ใจว่าคุณมีการตั้งค่าสภาพแวดล้อมการพัฒนา .NET เช่น Visual Studio
- ความเข้าใจพื้นฐานเกี่ยวกับโครงสร้าง PDF: ความคุ้นเคยกับองค์ประกอบโครงสร้าง PDF เช่น ย่อหน้า ช่วง ตาราง และรูปภาพ
-  ใบอนุญาตที่ถูกต้อง: คุณสามารถซื้อใบอนุญาตได้[ที่นี่](https://purchase.aspose.com/buy) หรือใช้แบบชั่วคราว[ที่นี่](https://purchase.aspose.com/temporary-license/).

## แพ็คเกจนำเข้า

ในการเริ่มต้นเขียนโค้ด คุณต้องนำเข้าเนมสเปซที่จำเป็นจาก Aspose.PDF สำหรับ .NET ซึ่งจะทำให้คุณเข้าถึงคลาสและวิธีการที่จำเป็นในการจัดการเอกสาร PDF ได้

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

ตอนนี้เราได้เตรียมฉากเรียบร้อยแล้ว มาแบ่งขั้นตอนการแท็กภาพออกเป็นหลายขั้นตอนกัน

## ขั้นตอนที่ 1: โหลดเอกสาร PDF ที่มีอยู่

ขั้นตอนแรกคือโหลดไฟล์ PDF ที่คุณต้องการใช้งาน ซึ่งอาจเป็นไฟล์ PDF ใดก็ได้ที่มีรูปภาพที่คุณต้องการแท็ก

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// เปิดเอกสาร
Document document = new Document(inFile);
```

-  แทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไฟล์ของคุณ
-  การ`Document` คลาสนี้ช่วยให้คุณโหลดไฟล์ PDF ที่มีอยู่ได้ คุณจะแก้ไขไฟล์ PDF นี้เพื่อแท็กรูปภาพ

## ขั้นตอนที่ 2: เข้าถึงเนื้อหาที่แท็กและองค์ประกอบโครงสร้างราก

เมื่อคุณเปิดไฟล์ PDF แล้ว ขั้นตอนต่อไปคือการเข้าถึงเนื้อหาที่แท็กไว้และระบุองค์ประกอบโครงสร้างหลัก ซึ่งเป็นสิ่งสำคัญมาก เนื่องจากช่วยให้คุณสามารถนำทางผ่านองค์ประกอบต่างๆ ใน PDF และปรับเปลี่ยนได้

```csharp
// รับเนื้อหาที่แท็กและองค์ประกอบโครงสร้างราก
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

- `TaggedContent` ให้การเข้าถึงองค์ประกอบที่มีโครงสร้างใน PDF
-  การ`RootElement` เป็นองค์ประกอบโครงสร้างบนสุด ซึ่งคุณสามารถเลื่อนลงไปยังองค์ประกอบอื่นๆ เช่น ย่อหน้า ตาราง และรูปภาพได้

## ขั้นตอนที่ 3: ตั้งชื่อให้กับเอกสาร PDF ที่ถูกแท็ก

การเพิ่มชื่อเรื่องให้กับเอกสาร PDF ที่ถูกแท็กจะช่วยให้แน่ใจว่าเอกสารของคุณมีป้ายกำกับอย่างถูกต้อง ซึ่งมีประโยชน์ต่อการเข้าถึงและการปฏิบัติตามมาตรฐาน PDF/UA

```csharp
// ตั้งชื่อเรื่องให้กับเอกสาร PDF ที่ถูกแท็ก
taggedContent.SetTitle("Document with images");
```

- การตั้งชื่อให้กับ PDF ที่คุณแท็กจะช่วยเพิ่มการเข้าถึงและปรับปรุงความชัดเจนของเอกสารสำหรับโปรแกรมอ่านหน้าจอและเทคโนโลยีช่วยเหลือ

## ขั้นตอนที่ 4: ค้นหาและแท็กภาพ

 ตอนนี้เรามาดูองค์ประกอบของภาพ (เรียกอีกอย่างว่า`FigureElement` ใน Aspose.PDF) ให้ตั้งค่าข้อความทางเลือกและกำหนดค่าแอตทริบิวต์เค้าโครงของมัน

```csharp
// วนซ้ำผ่านองค์ประกอบรูปภาพทั้งหมดและตั้งค่าข้อความทางเลือกและคุณลักษณะเค้าโครง
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
    // ตั้งค่าข้อความทางเลือกสำหรับรูปภาพ
    figureElement.AlternativeText = "Figure alternative text (technique 2)";
    
    // สร้างและตั้งค่าแอตทริบิวต์ BBox (กล่องขอบเขต)
    StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
    bboxAttribute.SetRectangleValue(new Aspose.Pdf.Rectangle(0.0, 0.0, 100.0, 100.0));
    
    // ตั้งค่าคุณลักษณะเค้าโครงของรูป
    StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
    figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

-  รหัสนี้จะวนซ้ำผ่านทั้งหมด`FigureElement` วัตถุในโครงสร้างรากซึ่งแสดงถึงรูปภาพ
- กำหนดข้อความทางเลือกเพื่อการเข้าถึงได้ (โปรแกรมอ่านหน้าจอจะใช้ข้อความนี้เพื่ออธิบายรูปภาพ)
- กล่องขอบเขต (`BBox`ระบุพิกัดสำหรับเค้าโครงของรูปภาพเพื่อให้แน่ใจว่าจะแสดงในเอกสารอย่างถูกต้อง

## ขั้นตอนที่ 5: แก้ไของค์ประกอบช่วงภายในตาราง

 ในบางกรณี คุณอาจต้องปรับเปลี่ยนองค์ประกอบ span ภายในตาราง ที่นี่ เราจะสาธิตวิธีค้นหา`SpanElement` และย้ายมันเข้าไปในย่อหน้า

```csharp
// ค้นหาองค์ประกอบของตาราง ช่วง และย่อหน้า
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// ย้ายองค์ประกอบช่วงเข้าไปในย่อหน้า
spanElement.ChangeParentElement(paragraph);
```

-  ที่นี่เราจะค้นหา`TableElement`, `SpanElement` , และ`ParagraphElement` ภายในไฟล์ PDF
-  การใช้`ChangeParentElement` วิธีการนี้ เราจะย้ายช่วงไปยังย่อหน้าเพื่อให้แน่ใจว่ามีการแท็กและโครงสร้างที่เหมาะสม

## ขั้นตอนที่ 6: บันทึกเอกสารและตรวจสอบการปฏิบัติตาม PDF/UA

เมื่อทำการเปลี่ยนแปลงทั้งหมดแล้ว ขั้นตอนสุดท้ายคือการบันทึก PDF ที่อัปเดตและตรวจสอบว่าเป็นไปตามมาตรฐาน PDF/UA หรือไม่

```csharp
// บันทึกเอกสาร PDF ที่ได้รับการอัพเดต
document.Save(outFile);

// ตรวจสอบการปฏิบัติตาม PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));
```

-  การ`Validate` วิธีการตรวจสอบเอกสาร PDF ตามมาตรฐาน PDF/UA และบันทึกผลลัพธ์
- การรับรองการปฏิบัติตามจะช่วยปรับปรุงการเข้าถึงและตอบสนองข้อกำหนดด้านกฎระเบียบสำหรับการเผยแพร่เอกสาร

## บทสรุป

ในบทช่วยสอนนี้ เราได้แสดงให้คุณเห็นถึงวิธีการแท็กรูปภาพใน PDF ที่มีอยู่โดยใช้ Aspose.PDF สำหรับ .NET คุณสามารถมั่นใจได้ว่า PDF ของคุณสามารถเข้าถึงได้และเป็นไปตามมาตรฐานสมัยใหม่ โดยการตั้งค่าข้อความทางเลือก การปรับแอตทริบิวต์เค้าโครง และการตรวจสอบเอกสารให้สอดคล้องกับ PDF/UA Aspose.PDF ช่วยให้คุณทำงานกับองค์ประกอบที่มีโครงสร้างได้ง่าย ช่วยให้คุณควบคุมเค้าโครงและการเข้าถึงเอกสารของคุณได้

## คำถามที่พบบ่อย

### Aspose.PDF สำหรับ .NET ใช้ทำอะไร?
Aspose.PDF สำหรับ .NET เป็นไลบรารีอันทรงพลังที่ใช้ในการสร้าง แก้ไข และจัดการเอกสาร PDF ด้วยโปรแกรมในสภาพแวดล้อม .NET

### ฉันจะมั่นใจได้อย่างไรว่าเป็นไปตามมาตรฐาน PDF/UA
 คุณสามารถใช้ Aspose.PDF ได้`Validate` วิธีการตรวจสอบความสอดคล้องกับ PDF/UA หลังจากทำการแก้ไขเอกสาร

### ข้อความทางเลือกใน PDF คืออะไร
ข้อความทางเลือกคือคำอธิบายที่เพิ่มลงในรูปภาพใน PDF เพื่อปรับปรุงการเข้าถึง โดยเฉพาะสำหรับผู้ใช้ที่ต้องใช้โปรแกรมอ่านหน้าจอ

### ฉันสามารถจัดการตารางและช่วงใน PDF ด้วย Aspose.PDF ได้หรือไม่
ใช่ Aspose.PDF ช่วยให้คุณสามารถจัดการตาราง ช่วง และองค์ประกอบที่มีโครงสร้างอื่น ๆ ภายในเอกสาร PDF ได้

### ฉันสามารถดาวน์โหลด Aspose.PDF สำหรับ .NET ได้ที่ไหน
 คุณสามารถดาวน์โหลด Aspose.PDF เวอร์ชันล่าสุดสำหรับ .NET ได้[ที่นี่](https://releases.aspose.com/pdf/net/).